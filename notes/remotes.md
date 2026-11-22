# Remote repositories

- `git remote add origin <url>` links a local repo to GitHub.
- `git push -u origin main` pushes and sets upstream tracking.
- `git remote -v` lists fetch and push URLs.
- `git pull` fetches upstream changes and integrates them into your current branch:
  - `git pull --ff-only` updates only when Git can fast-forward, and stops otherwise.
  - `git pull --rebase` replays your local commits on top of the fetched branch.
- If `--ff-only` stops because the branches have diverged, run `git fetch`, then `git log --oneline --left-right 'HEAD...@{upstream}'` to see both sides. Use `git pull --rebase` if your local commits are unpublished, or merge the fetched branch with `git merge '@{upstream}'` to preserve shared history.
- Rebasing rewrites commit IDs. Avoid rebasing commits you have already shared.
- To choose a default for this repository, use `git config pull.ff only` for fast-forward-only or `git config pull.rebase true` for rebase. Choose one.
