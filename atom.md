# Atom editor

## 단축키

**설정 진입**  
`Cmd + ,` or `Ctrl + ,`

**단축키 설정**  
위의 **설정 진입** 이후  
`Settings` -> `KeyBinding`  
`your keymap file`링크 클릭

**폴더 트리구조 보이기/가리기 단축키**  
`cmd + \` or `Ctrl + \`

**동일텍스트 선택**  
`cmd + d` or `Ctrl + d`


## sass-autocompile 패키지 설치

먼저 `Node.js`를 설치 후, `Node.js`의 패키지 관리자인 `NPM`을 이용해 `node-sass`패키지를 설치


**Ubuntu**  
`sudo apt-get install -y nodejs`   
`sudo apt-get install -y npm`

**macOS**  
`brew install node`

---

**nodejs 및 npm설치 이후**  

터미널에서 `node -v` 입력

> 정상출력:  
> `v7.?.?` 또는 `v4.?.?`

에러가 난다면 `nodejs -v` 를 입력 해 보고, `node -v`로는 에러가 나지만 `nodejs -v`로는 버전이 정상적으로 출력되면 아래와 같이 입력

```
sudo ln -s /usr/bin/nodejs /usr/bin/node
```
 
---

**`node -v`가 정상적으로 작동하는걸 확인했다면**

`node-sass` npm패키지 설치  
`sudo npm install node-sass -g`