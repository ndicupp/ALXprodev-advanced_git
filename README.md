# ALXprodev-advanced_git
## git clone https://github.com/ndicupp/ALXprodev-advanced_git.git
cd ALXprodev-advanced_git

git checkout -b develop

git push -u origin develop
git flow init -d

-d automatically accepts default configuration:

main → main (or master depending on your repo)

develop → develop

feature prefix → feature/

release prefix → release/

hotfix prefix → hotfix/

Create an empty README.md file
touch README.md

If on Windows (PowerShell):
New-Item README.md

git add README.md
git commit -m "Add empty README.md"

git push origin develop

What you should have at the end

A repo called ALXprodev-advanced_git

Two branches:
✔ main (empty)
✔ develop (with README.md)

Git Flow initialized with default settings

README committed and pushed
