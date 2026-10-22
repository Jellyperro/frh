---
name: "submit-project"
description: "Commits all current changes and pushes to Gitee remote (https://gitee.com/Jellyperro/Furuohan929.git). Invoke when user asks to submit, commit and push, or publish the project."
---

# 提交项目 (Submit Project)

Commit the current project and push it to the Gitee remote
`https://gitee.com/Jellyperro/Furuohan929.git`.

## Remote

The target repository is:

```
https://gitee.com/Jellyperro/Furuohan929.git
```

`origin` may already be configured. Ensure it points at the target before
pushing; if it is missing or wrong, set it:

```powershell
git remote get-url origin
git remote set-url origin https://gitee.com/Jellyperro/Furuohan929.git
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

3. Create the commit. Write a concise message that matches the repo style
   (Chinese is fine, e.g. `提交项目：更新网页练习`). If there are no staged
   changes, there is nothing to commit — skip to step 4.

   ```powershell
   git commit -m "<message>"
   ```

4. Push to the Gitee remote:

   ```powershell
   git push origin HEAD
   ```

## Notes

- Only commit and push when the user explicitly asks to submit the project.
- Never commit secrets or credentials. Do not force-push.
- If the push is rejected, pull/rebase first and resolve conflicts; do not
  force-push to fix it.
