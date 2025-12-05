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
Two branches:
✔ main (empty)
✔ develop (with README.md)

Git Flow initialized with default settings

README committed and pushed


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

