---
name: submit-github
description: Commits all current changes and pushes to the GitHub remote (git@github.com:Jellyperro/frh.git). Use when the user asks to 提交到 GitHub, push to GitHub, or publish to the frh repository. Do not use for Gitee submissions — use submit-project instead.
---

# 提交到 GitHub (Submit to GitHub)

Commit the current project and push it to the GitHub repository
`https://github.com/Jellyperro/frh`. SSH 公钥已配置，使用 SSH 地址推送。

## Remote

Use a dedicated remote named `github` so the existing Gitee `origin` stays intact:

```powershell
git remote -v
git remote add github git@github.com:Jellyperro/frh.git
```

If `github` already exists but points elsewhere, fix it:

```powershell
git remote set-url github git@github.com:Jellyperro/frh.git
```

## Workflow

1. Inspect the working tree so the commit only contains intended files:

   ```powershell
   git status
   git diff --stat
   ```

2. Stage the project changes:

   ```powershell
   git add -A
   ```

3. Create the commit. Write a concise Chinese message that matches the repo
   style (e.g. `提交项目：更新网页练习`). If there are no staged changes,
   there is nothing to commit — skip to step 4.

   ```powershell
   git commit -m "<message>"
   ```

4. Push to the GitHub remote. On the first push, set upstream:

   ```powershell
   git push -u github master
   ```

   Subsequent pushes:

   ```powershell
   git push github HEAD
   ```

## Notes

- This is a Windows PowerShell 5 environment — chain commands with `;`, never `&&`.
- Only commit and push when the user explicitly asks to submit to GitHub.
- Never commit secrets or credentials. Do not force-push.
- If the push is rejected, pull/rebase from `github` first and resolve conflicts; do not force-push to fix it.
- Verify success with `git log --oneline -1` and the push output.
