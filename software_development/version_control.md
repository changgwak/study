
[[git]]  
[upload folders on remote](https://cocococo.tistory.com/entry/Git-Git%EC%97%90-%ED%8F%B4%EB%8D%94-%EC%97%85%EB%A1%9C%EB%93%9C-%EB%B0%A9%EB%B2%95)

[clone all branches](https://velog.io/@dataliteracy/%EB%AA%A8%EB%93%A0-git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%ED%81%B4%EB%A1%A0%ED%95%B4%EC%98%A4%EA%B8%B0feat.-git-alias)

[branch generate and checkout](https://mylko72.gitbooks.io/git/content/branch/checkout.html)

[push new branch on remote](https://magoker.tistory.com/220)

[git large file storage](https://git-lfs.com/)

[There isn't anything to compare. Nothing to compare, branches are entirely different commit histories](https://stackoverflow.com/questions/23344320/there-isnt-anything-to-compare-nothing-to-compare-branches-are-entirely-diffe)

<br>

git push <원격 저장소 명> <branch 이름>  
git push origin master  

<br>

git pull <원격 저장소 명> <branch 명>  
git pull origin master  


<br>

git init  
git checkout -b master  
git remote add origin <git remote repo>  
git pull origin master  
git checkout -b feature/display  

<br>  

git add .  
git commit -m "Edit display order"  
git push -u origin feature/display  // git push origin master

<br>

[.How to Clone All Remote Branches from a Git Repository]([How to Clone All Remote Branches from a Git Repository](https://www.youtube.com/watch?v=qUtb8-CvEoo)  
[.repository를 clone할 때 모든 branch를 local에 받기](https://github.com/jobhope/TechnicalNote/blob/master/github/CloneRepository.md)  

git clone --branch <브랜치이름> --single-branch <저장소URL>  
git clone [url]  
git branch --all  
git checkout [each branch]  

<br>  
<br>

[[git bundle]]  
git init .  
git add .
git commit -m "Initial commit"  

git bundle create file.bundle master

git clone -b master ./temp/file.bundle R2


<br>
<br>
<br>
<br>

## how to uplaod on remote at first time.  
generate git repo on git  
modity default branch to master from main  
git init .  
git pull [address]  
git add .  
git commit -m ""  
git remote add origin [address]  
git remote -v  
git push origin master  


<br>
<br>
<br>
<br>

### 🔗 **Git에서 Remote 연결 및 확인 방법**
Git에서 원격(remote) 저장소를 연결하고, 현재 어떤 remote 주소가 설정되어 있는지 확인하는 방법.

---

## **1️⃣ 원격(remote) 저장소 연결하는 방법**
Git에서 원격 저장소를 추가하려면 `git remote add` 명령어를 사용합니다.

### ✅ **Git 원격 저장소 연결**
```bash
git remote add origin <원격 저장소 URL>
```
예를 들어, GitHub의 원격 저장소를 연결하려면 다음과 같이 입력합니다:
```bash
git remote add origin https://github.com/username/repository.git
```
- `origin` : 원격 저장소의 이름 (보통 기본값으로 `origin`을 사용함)
- `<원격 저장소 URL>` : GitHub, GitLab, Bitbucket 등의 원격 저장소 주소

---

## **2️⃣ 연결된 Remote 저장소 확인하기**
### ✅ **설정된 remote 목록 확인**
```bash
git remote -v
```
출력 예시:
```
origin  https://github.com/username/repository.git (fetch)
origin  https://github.com/username/repository.git (push)
```
- `(fetch)`: 데이터를 가져올 때(fetch) 사용되는 URL
- `(push)`: 변경 사항을 push할 때 사용되는 URL

---

## **3️⃣ 원격 저장소 변경하기**
### ✅ **기존 remote URL 변경**
만약 기존에 설정된 원격 저장소 URL을 변경하고 싶다면:
```bash
git remote set-url origin <새로운 원격 저장소 URL>
```
예시:
```bash
git remote set-url origin https://github.com/new-user/new-repository.git
```

---

## **4️⃣ 원격 저장소 삭제하기**
만약 기존 원격 저장소를 삭제하려면:
```bash
git remote remove origin
```
또는:
```bash
git remote rm origin
```

---

## **5️⃣ 원격 저장소 이름 변경**
예를 들어 `origin`을 `upstream`으로 바꾸고 싶다면:
```bash
git remote rename origin upstream
```
변경 후 다시 확인:
```bash
git remote -v
```

---

### 🎯 **정리**
| 명령어 | 설명 |
|--------|------|
| `git remote add origin <URL>` | 원격 저장소 추가 |
| `git remote -v` | 설정된 원격 저장소 확인 |
| `git remote set-url origin <새 URL>` | 원격 저장소 주소 변경 |
| `git remote remove origin` | 원격 저장소 삭제 |
| `git remote rename origin upstream` | 원격 저장소 이름 변경 |




<br>
<br>

[[PYPI]]
## How to update PYPI (for only project manager)

### Revision codes
1. Update on Github after modifying codes.

### Update version

1. Update `__version__` in `__init__.py` file in package
2. Update `version` in `setup.py` file (Same setting as first step)
3. Update after addtion, if `install_requires` is added in `setup.py`

### Install pip
```bash
pip install wheel twine
```

### Generate whl file
```bash
python setup.py sdist bdist_wheel
python setup.py bdist_wheel
```

> Upload whl file
```bash
python -m twine upload dist/*
twine upload dist/pyautomation-X.X.X-py3-none-any.whl
