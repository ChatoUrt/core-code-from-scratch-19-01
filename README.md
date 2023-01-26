# core-code-from-scratch-19-01

## ---

---
## ---

---
## ---

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
