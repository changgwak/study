
[[git]]  
[upload folders on remote](https://cocococo.tistory.com/entry/Git-Git%EC%97%90-%ED%8F%B4%EB%8D%94-%EC%97%85%EB%A1%9C%EB%93%9C-%EB%B0%A9%EB%B2%95)

[clone all branches](https://velog.io/@dataliteracy/%EB%AA%A8%EB%93%A0-git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%ED%81%B4%EB%A1%A0%ED%95%B4%EC%98%A4%EA%B8%B0feat.-git-alias)

[branch generate and checkout](https://mylko72.gitbooks.io/git/content/branch/checkout.html)

[push new branch on remote](https://magoker.tistory.com/220)

[git large file storage](https://git-lfs.com/)

[There isn't anything to compare. Nothing to compare, branches are entirely different commit histories](https://stackoverflow.com/questions/23344320/there-isnt-anything-to-compare-nothing-to-compare-branches-are-entirely-diffe)

git push <원격 저장소 명> <branch 이름>
git push origin master

git pull <원격 저장소 명> <branch 명>
git pull origin master



git init  
git checkout -b master  
git remote add origin <git remote repo>  
git pull origin master  
git checkout -b feature/display  
git add .  
git commit -m "Edit display order"  
git push -u origin feature/display  // git push origin master


[How to Clone All Remote Branches from a Git Repository]([How to Clone All Remote Branches from a Git Repository](https://www.youtube.com/watch?v=qUtb8-CvEoo))
git clone [url]
git branch --all
git checkout [each branch]

[[PYPI]]
## How to update PYPI (for only project manager)

### Revision codes
1. Update on Github after modifying codes.

### Update version

1. Update `__version__` in `__init__.py` file in package
2. Update `version` in `setup.py` file (Same setting as first step)
3. Update after addtion, if `install_requires` is added in `setup.py`

### Generate whl file
```bash
python setup.py sdist bdist_wheel
python setup.py bdist_wheel
```

> Upload whl file
```bash
python -m twine upload dist/*
twine upload dist/pyautomation-X.X.X-py3-none-any.whl
