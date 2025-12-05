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

