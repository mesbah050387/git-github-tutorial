# FIRST GIT + GITHUB AUTHENTICATION (SSH)

git --version

git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"

# If you already have an SSH key, skip ssh-keygen
ssh-keygen -t ed25519 -C "your-email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Copy SSH key and add it to GitHub:
cat ~/.ssh/id_ed25519.pub
# GitHub → Settings → SSH and GPG keys → New SSH key

# Test authentication
ssh -T git@github.com

# Connect project to GitHub
git init
git remote add origin git@github.com:USERNAME/REPOSITORY.git
git branch -M main

# First push
git add .
git commit -m "Initial commit"
git push -u origin main

# Future updates
git add .
git commit -m "Describe your changes"
git push