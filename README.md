- [Exemplo de utilização](https://codepen.io/nenitf/pen/gObPvON)

```js
/*
 * Link do arquivo:
 * https://github.com/nenitf/fakeapi/blob/master/neni.dev/links.json
 */
let ep = 'https://raw.githubusercontent.com/nenitf/fakeapi/master/neni.dev/links.json'
fetch(ep)
	.then(res => res.json())
  .then(function(data) {
		str = JSON.stringify(data);
		document.querySelector(".container").innerHTML = str
   })
```

---

- [Com gist](https://codepen.io/nenitf/pen/ExYJPMV)

```js
/*
 * API Github:
 * https://developer.github.com/v3/gists/#list-a-users-gists
 *
 * Link do gist:
 * https://gist.github.com/nenitf/d48ef344b22a15e6b3d6efa7390d4d23
 * ID do gist: d48ef344b22a15e6b3d6efa7390d4d23
 *
 * EndPoint para consumir o gist:
 * https://api.github.com/gists/d48ef344b22a15e6b3d6efa7390d4d23
 */
let ep = 'https://api.github.com/gists/d48ef344b22a15e6b3d6efa7390d4d23'
fetch(ep)
  .then(response => response.json())
  .then(function(json) {
		// Lê arquivo json
		// Possui quebra de linhas como "\n"
		let fileContent = json.files["neni.dev.json"].content;
	
		// Interpreta arquivo como obj
		let fileParsed = JSON.parse(fileContent)
		console.log(fileParsed)
	
		str = JSON.stringify(fileParsed);
		document.querySelector(".container").innerHTML = str
	})
```
