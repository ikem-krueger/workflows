sudo apt-get install git-lfs
git lfs install
git lfs track "*.zip"
git add .gitattributes *.zip
git commit -m "Tracking files with LFS"
git push
