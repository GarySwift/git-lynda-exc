__Create a new repository on the command line__

echo "# git-lynda-exc" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/GarySwift/git-lynda-exc.git
git push -u origin master