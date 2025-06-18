# olist

Step 1: Generate an SSH Key
ssh-keygen -t ed25519 -C "your_email@example.com"  # Or `-t rsa -b 4096`

Step 2: Add the Key to SSH Agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

Step 3: Link the Key to Your Git Account
GitHub: Settings > SSH and GPG Keys > New SSH Key

GitLab: Preferences > SSH Keys

Paste the contents of ~/.ssh/id_ed25519.pub.

Step 4: Configure Git to Use SSH

git remote set-url origin git@github.com:username/repo.git  # Replace with your repo URL

(Verify with git remote -v.)