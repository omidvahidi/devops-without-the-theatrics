# Branching examples (minimal)

These patterns are intentionally simple. They are designed for clarity, reviewability, and low blast radius.

## Pattern A: Short-lived feature branches
Use for routine changes that should be reviewed before merging.

```bash
git checkout main
git pull --ff-only

git checkout -b feature/restrict-egress
# edit files
git add .
git commit -m "Restrict outbound traffic to approved ranges"
git push -u origin feature/restrict-egress
