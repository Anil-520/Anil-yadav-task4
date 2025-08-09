# 1. Initialize a new Git repository
git init

# 2. Add remote GitHub repository (replace with your repo link)
git remote add origin https://github.com/YourUsername/your-repo.git

# 3. Create main branch and push it
git checkout -b main
git add .
git commit -m "Initial commit"
git push -u origin main

# 4. Create dev branch from main
git checkout -b dev
git push -u origin dev

# 5. Create a feature branch from dev
git checkout -b feature
# (Make some changes here, e.g., create a file)
echo "# My DevOps Project" > README.md
git add README.md
git commit -m "Add README file"
git push -u origin feature

# 6. Merge feature into dev (locally)
git checkout dev
git merge feature
git push origin dev

# 7. Create a .gitignore file
echo "node_modules/" > .gitignore
git add .gitignore
git commit -m "Add .gitignore"
git push

# 8. Tag a version
git tag -a v1.0 -m "First release"
git push origin v1.0

# 9. Merge dev into main (final step before release)
git checkout main
git merge dev
git push origin main