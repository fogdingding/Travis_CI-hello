# Travis_CI-hello
for Travis_CI simple teaching

### 這是一個簡易的教學，對於[Travis CI](https://travis-ci.org/)這個方便的工具。
>>在單元測試的部分，有一套工具可以自動化的執行自己寫的單元測試檔案。
>>在這套工具上，因為跟github有極高的相容性，所以選擇他。

---
##### 如果想要有一個能夠自動化進行單元測試的話，可以依照下列步驟
1. 首先申請一個[github帳號](https://github.com)。

2. 在申請一個[Travis CI-帳號](https://travis-ci.org/)
>>因有github帳號了，可以直接做登入。

3. 只需在上傳github的時候，多上傳一個檔案即可
###### [參考官方教學網站](https://docs.travis-ci.com/user/languages/python/)
###### 檔案內容如下，檔案名稱為 .travis.yml
```
language: python
# set language
notifications:
  email: false
# Cancel EMAIL notification
python:
  - "3.6"
# command to install dependencies
install:
  - pip3 install --user -r requirements.txt
# command to run tests
script:
  - python3 hello.py
# or py.test for Python versions 3.5 and below
before_install:
  - sudo apt-get update
# work around https://github.com/travis-ci/travis-ci/issues/8363
  - pyenv global system 3.6
  - which pip3
  - python --version
  - pip3 --version
```
####### PS.如果忘記如何使用git指令 可以參考[github教學網站](https://github.com/fogdingding/github)

4. 接下來要打開自動化按鈕，如下圖
![]()

5. 以及建立一個測試的py檔案，如下
```py
print ("hello，Travis-CI")
```

6. 然後就可以請Travis-CI先行跑一下，如下圖
###### 網站大概是 https://travis-ci.org/github_user_name/github_project_name/requests
![]()

7. 關於測試的檔案如何撰寫，就要....