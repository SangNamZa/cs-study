# XSS (Cross Site Scripting)

게시판이나 웹 메일 등에 자바스크립트오 같은 스크립트 코드를 삽입해 개발자가 고려하지 않은 기능이 작동하게 하는 공격.

## Reflected XSS

<img width="729" alt="image" src="https://user-images.githubusercontent.com/38755868/206629498-8e8b086a-7b13-453b-8a4c-e3e03bc12111.png">
<img width="724" alt="image" src="https://user-images.githubusercontent.com/38755868/206629599-1c0fb0bc-a411-422f-bde3-62fb8cd86f0f.png">

## Stored XSS

웹 사이트의 게시판에 스트립트 삽입하는 공격 방식.

공격자가 게시판에 스크립트를 삽입한 후 공격 대상작 해당 게시글으 클릭하도로 유도.

<img width="488" alt="image" src="https://user-images.githubusercontent.com/38755868/206629969-9bdada15-d3da-45ff-966a-325a68f7ba9a.png">

## XSS 방지법

1. script 문자 필터링

```javascript
function XSSCheck(str, level) {
    if (level == undefined || level == 0) {
        str = str.replace(/\<|\>|\"|\'|\%|\;|\(|\)|\&|\+|\-/g,"");
    } else if (level != undefined && level == 1) {
        str = str.replace(/\</g, "&lt;");
        str = str.replace(/\>/g, "&gt;");
    }
    return str;
}
```
