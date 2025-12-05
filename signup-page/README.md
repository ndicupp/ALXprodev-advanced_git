git checkout develop
git pull origin develop

Using GitFlow:
git flow feature start implement-signup

Manual alternative:
git checkout -b feature/implement-signup

mkdir signup-page
echo "feature coming soon" > signup-page/README.md

git add .
git commit -m "feat: scaffolding signup page"

git push -u origin feature/implement-signup


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


cd .git/hooks
touch pre-commit

#!/bin/bash

# Pre-commit hook: ensure every directory contains a README.md

missing_readmes=0

for dir in $(find . -type d | grep -v ".git"); do
    if [ ! -f "$dir/README.md" ]; then
        echo "❌ Missing README.md in directory: $dir"
        missing_readmes=1
    fi
done

if [ $missing_readmes -eq 1 ]; then
    echo "Commit aborted. Please add README.md files."
    exit 1
fi

exit 0

chmod +x pre-commit


cd .git/hooks
touch post-merge

#!/bin/bash

# Post-merge hook: log merges into main branch

branch=$(git rev-parse --abbrev-ref HEAD)

if [ "$branch" = "main" ]; then
    echo "$(date): Merge completed into main branch" >> merge-log.txt
fi

exit 0

chmod +x post-merge





