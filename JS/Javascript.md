#### Remove accents from string

```JavaScript
const str = "éèàêëËÊ"
    .normalize("NFD")
    .replace(/\p{Diacritic}/gu, "");

console.log(str);
// Output: eeaeeEE
```

#### Manual script injection

```JavaScript
const scriptDomId = "unique-script-id";
let elem = document.getElementById(scriptDomId);
if (!elem) {
    const scriptDom = document.createElement("script");
    scriptDom.setAttribute('id', scriptDomId);
    scriptDom.setAttribute('type', 'text/javascript');
    scriptDom.setAttribute('src', 'https://script-url.com/script.js');
    document.head.appendChild(scriptDom);
}
```

#### Capitalize

```JavaScript
const capitalize = (str) => {
  if (!str) {
    return str;
  }
  return str.charAt(0).toUpperCase() + str.toLowerCase().slice(1);
};
```

#### Utils

- [sha256](./Utils/sha256.md)
- [md5](./Utils/md5.md)
