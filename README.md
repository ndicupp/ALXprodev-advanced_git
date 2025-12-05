# ALXprodev-advanced_git
## git clone https://github.com/ndicupp/ALXprodev-advanced_git.git
Create the develop branch
git checkout -b develop

Push the develop branch to the remote
git push -u origin develop

nitialize Git Flow with default settings

This sets up branch prefixes and default main/develop branches.
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

Add and commit the README
git add README.md
git commit -m "Add empty README.md"

Push the changes
git push origin develop

What you should have at the end

A repo called ALXprodev-advanced_git

Two branches:
✔ main (empty)
✔ develop (with README.md)

Git Flow initialized with default settings

README committed and pushed
