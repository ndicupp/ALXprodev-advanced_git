git checkout develop
git pull origin develop

git flow feature start implement-login

This automatically creates:
feature/implement-login

If doing it manually:
git checkout -b feature/implement-login

mkdir login-page
echo "Login Feature Coming soon" > login-page/README.md

New-Item -ItemType Directory login-page
Set-Content login-page/README.md "Login Feature Coming soon"

git add .
git commit -m "feat: scaffolding login page"

git push -u origin feature/implement-login


git checkout develop
git pull
git merge feature/implement-login


If there are conflicts:

Open the conflicting files

Fix conflicts manually

Save

Then run: 
git add .
git commit


git merge feature/implement-signup

If conflicts appear, resolve them the same way:
git add .
git commit

git push origin develop


Using GitFlow:
git flow release start 1.0.0

Manual:
git checkout -b release/1.0.0 develop



data requirements: email, firstName, lastName, profilePic

echo "data requirements: email, firstName, lastName, profilePic" >> signup-page/README.md

git add signup-page/README.md
git commit -m "chore: add data requirements to signup"
git push -u origin release/1.0.0


git checkout main
git pull origin main
git merge release/1.0.0
git push origin main

git checkout develop
git pull origin develop
git merge release/1.0.0
git push origin develop


git tag -a v1.0.0 -m "Release version 1.0.0"

git push origin --tags


