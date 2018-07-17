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
>![](https://github.com/fogdingding/Travis_CI-hello/blob/master/img/%E5%AE%98%E6%96%B9%E7%B6%B2%E7%AB%99-%E6%89%93%E9%96%8B%E8%87%AA%E5%8B%95%E5%8C%96%E6%8C%89%E9%88%95.JPG)

5. 以及建立一個測試的py檔案，如下
```py
print ("hello，Travis-CI")
```

6. 然後就可以請Travis-CI先行跑一下，如下圖
###### 網站大概是 https://travis-ci.org/"github_user_name"/"github_project_name"/jobs/"random_ID"
>![](https://github.com/fogdingding/Travis_CI-hello/blob/master/img/%E5%AE%98%E6%96%B9%E7%B6%B2%E7%AB%99-%E8%87%AA%E5%8B%95%E5%8C%96%E6%B8%AC%E8%A9%A6%E7%B5%90%E6%9E%9C.JPG)

7. 如果沒什麼事情的話就會出現
>![](https://github.com/fogdingding/Travis_CI-hello/blob/master/img/%E5%AE%98%E6%96%B9%E7%B6%B2%E7%AB%99-%E8%87%AA%E5%8B%95%E5%8C%96%E6%B8%AC%E8%A9%A6%E7%B5%90%E6%9E%9C-2.JPG)