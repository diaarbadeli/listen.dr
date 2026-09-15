# Git Access for Agents (this repo)

How an agent (or contributor) with a GitHub fine-grained PAT pushes to this repo.

## The pattern

```bash
git clone https://<github-username>:<token>@github.com/diaarbadeli/listen.dr.git
```

The token is passed as the HTTP basic-auth "password." No SSH key, no `gh auth login`
needed. This works for `clone`, `push`, and `pull` — just build the remote URL with
the token embedded.

If you already have a local clone with a plain `https://github.com/...` remote,
you can inject the token for one operation instead of rewriting the remote:

```bash
git -c http.extraheader="Authorization: basic $(printf 'x-access-token:<token>' | base64)" push origin main
```

## Token scope expectations

Tokens used for this repo should be **fine-grained** and scoped to:

- Repository access: this repo only (not "all repositories")
- Permissions: Contents: Read and write — nothing broader (no Actions, no admin, no other repos)
- A short expiration (days, not months)

If a token in hand has broader scope than that, say so before using it, but proceed
if the user confirms.

## Handling the token safely during a session

- Never echo the raw token in a shell command's visible output, a file, or a commit.
- Pipe any command output that might contain it through a redaction step, e.g.:
  `sed 's/github_pat_[A-Za-z0-9_]*/[REDACTED]/g'`
- Don't write the token into any file that gets committed (obviously), and don't
  write it into scratch files either — keep it in the command invocation only.
- Delete local clones that used the embedded-token remote when the task is done,
  since the remote URL itself contains the token in plaintext (`.git/config`).
- A token pasted into a chat conversation is already exposed in that conversation's
  history. That doesn't change how it should be used in-session, but it means the
  token should be treated as short-lived: use it for the task at hand, and it's the
  repo owner's call whether to revoke and rotate it afterward.

## Verifying access before doing real work

`git clone` succeeding is sufficient proof of read access. For write access, the
first real push will confirm it — no need for a separate "test" commit.
