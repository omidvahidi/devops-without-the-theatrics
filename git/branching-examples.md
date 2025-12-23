# Branching examples (minimal)

These patterns are intentionally simple. They are designed for clarity, reviewability, and low blast radius.  

## Pattern A: Short-lived feature branches
Use for routine changes that should be reviewed before merging.  

bash  
git checkout main  
git pull --ff-only  

git checkout -b feature/restrict-egress  
### edit files
git add .  
git commit -m "Restrict outbound traffic to approved ranges"  
git push -u origin feature/restrict-egress  

## Pattern B: Hotfix branches with traceability  
git checkout main  
git pull --ff-only  

git checkout -b hotfix/block-open-egress  
### edit files 
git add .  
git commit -m "Hotfix: block unrestricted outbound traffic"  
git push -u origin hotfix/block-open-egress  

Merge through PR if possible. If not, document the exception and follow up with normal review after the incident.  

## Pattern C: Release branches only when required
Use when change windows, certification, or external release processes force separation.  
git checkout -b release/2026-01  
git push -u origin release/2026-01  
Treat release branches as contracts. Limit scope. Avoid feature work on them.  
