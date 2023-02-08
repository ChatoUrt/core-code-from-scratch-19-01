# core-code-from-scratch-19-01

## ---Counting duplicates---

* [Test](https://www.codewars.com/kata/54bf1c2cd5b56cc47f0007a1/train/javascript)

Solution / /

``` javascript 
function duplicateCount(text){
    if (text == '') return 0;
    text = text.toLowerCase().split('').sort().join('');
    let CurrAc = '';
    let count = 0;
    for (let i = 0; i < text.length - 1; i++) {
        if (text[i] == text[ i + 1 ]) {
            if (CurrAc == text[i]) {
                continue
            }
            count++
            CurrAc = text[i];
        }
    }
    return count;
}
```

---
## ---Encypt this---
* [Test](https://www.codewars.com/kata/5848565e273af816fb000449/train/javascript)

Solution / / 

``` javascript
var encryptThis = function (text) {
  text = text.split(' ')
  let fullCode = '';
  let nose = [];
  text.forEach((word) => {
    let code = word.substring(0, 1).charCodeAt();
    fullCode = code
    if(word.length !== 1) {
      fullCode = fullCode + word[word.length - 1];
      if(word.length !== 2){
        let str = word.substring(1);
        let first = str[0];
        let last = str[str.length - 1];
        let middle = str.substring(1, str.length - 1);
        fullCode = code + last + middle + first;
      }
    }
    nose.push(fullCode);    
  })
  nose = nose.join(' ').trim();
  return nose
}
```

---
## ---Valid Parenthesis---

* [Test](https://www.codewars.com/kata/52774a314c2333f0a7000688/train/javascript)

Solution / /

``` javascript 
function validParentheses(parens) { 
  let counter = 0;
  for (let i = 0; i < parens.length; i++) {
    if (parens[i] === ')') counter--;
    if (parens[i] === '(') counter++;
    if (counter < 0) return false;
    }
  return counter == 0;
}
```

---
## ---String to Camel Case---

* [Test](https://www.codewars.com/kata/517abf86da9663f1d2000003/train/javascript)

Solution / / 

``` javascript
function toCamelCase {
  if (str === '') return str;
  const noSpace = str.replace(/-/g, ' ').replace(/_/g, ' ');
  const mayus = noSpace.split(' ');
  for (let i = 1; i < mayus.length; i++) { 
    mayus[i] = mayus[i][0].toUpperCase() + mayus[i].substr(1);
  }
  let result = mayus.join(' ').replace(/[' ']/g, '');
  return result;
}
```

Other's solutions / /

-1

``` javascript
function toCamelCase(str){
  return str.split(/-|_/g).map((w, i) => (i > 0 ? w.charAt(0).toUpperCase() : w.charAt(0)) + w.slice(1)).join('');
}
```

-2
``` javascript
function toCamelCase(str){
  return str.replace(/[_-]\w/gi, ch => ch[1].toUpperCase());
}
```
