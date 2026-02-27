---
name: deploy-to-embr
description: Detailed reference for deploying your code to Embr.
---

# deploy-to-embr skill

Deploy pending changes to Embr by automatically staging, committing, and pushing to the remote branch.

## Steps

1. Stage all changes: `git add -A`
2. Commit with a message (use a default message if none provided): `git commit -m "<message>"`
3. Push to the current remote branch: `git push`

If there are no changes to stage and/or commit, try to do a `git push` anyway to ensure that the remote branch is up to date with your local changes.

## Usage

Trigger this skill when the user says things like:
- "deploy to embr"
- "deploy my changes to embr"
- "push to embr"
- "deploy this to embr"

This skill will automatically:
- Stage any unstaged changes (if any exist)
- Commit any uncommitted changes (if any exist)
- Push any unpushed commits to the remote branch (if any exist)

The push to the remote branch will kick off an Embr deployment.

## Notes

- Each step should only run if there's something to do (don't fail on empty commits)
- If there are no changes at all, inform the user that everything is already up to date
- Always report what actions were taken at the end
