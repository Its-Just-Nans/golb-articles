# NodeJS

## Simple HTTP server

Commande pour créer un serveur web rapidement

```sh
npm install -g http-server
# now use the installed command
http-server

# or
npx http-server
```

> Légende :
>
> - `-g` means `--global`
> - une option utile est `-p` pour choisir le port du serveur
> - exemple : `http-server -p 80` pour un serveur web
> - il y a également d'autres options (voir la documentation)

Reference : [http-server](https://www.npmjs.com/package/http-server)

## `npm` && `npx`

- `npm` means "Node Packet Manager" and [a lot of things](https://github.com/npm/npm-expansions)
- `npx` means "Node Package eXecute", it download and execute the package

Here is some great `npx` commands

```sh
npx npm-check-updates

npx unimported

npm outdated
```

```bash
npx -p lolcatjs -p cowsay -c 'echo hello | cowsay | lolcatjs'
```

## (stupid) tricks

```js
// create a default value by constructing a fake similar object
const result = (playlist.tracks || { data: [] }).data;

// normal destructuring
const myObj = { hello: "world" };
const { hello: myVariable } = myObj;
console.log(myVariable); // "world"

// destructing object with key name
const keyName = "hello";
const { [keyName]: myVariable2 } = myObj;
console.log(myVariable2); // "world"
```

## Discord Webhook Browser

```js
const url = "https://discord.com/api/webhooks/..."
const data = {
    content: "my content",
    username: "log",
    avatar_url: "",
    embeds: [] // for many small messages
}
fetch(url, {
    method : "POST"
    body: data
});
// with axios
// axios.post(url, data);
```

## Node.js must have

```js
process.on('uncaughtException', (err, origin) => {
    console.error('Uncaught Exception origin ->', origin);
    console.error('Uncaught Exception err ->', err);
});

process.on('unhandledRejection', (reason, promise) => {
    console.error('Unhandled rejection promise ->', promise);
    console.error('Unhandled rejection reason  ->', reason);
});
```

## NVM : node version manager

- [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)

```sh
# download and install
# do the post-install
nvm install node
nvm use node

# others commands
nvm list # list versions
nvm ls-remote
nvm install 'lts/NAME' # download the version
nvm alias default lts # take lts as default
```

## Speed up videos

```js
const max = 16; // https://stackoverflow.com/a/32320020
const accelerate = (e) => e.playbackRate = max;
const videoAccelerate = (d) => [...d.getElementsByTagName("video")].forEach(accelerate);
videoAccelerate(document);
[...document.getElementsByTagName("iframe")].forEach((iframe)=> videoAccelerate(iframe.contentWindow.document));
```

## numberSafeParse

```ts
function numberSafeParse(input: string): number | null {
    if (input.trim() === '') return null
    let parsed = Number(input)
    if (!Number.isFinite(parsed)) return null
    return parsed
}

// - Return `null` instead of `NaN` on failure (with matching type)
// - Doesn't parse things like "42foo" as `42` (vs using `Number.parseFloat()`)
// - Doesn't parse whitespace-only strings as `0` (vs using `Number()`)
// - Doesn't parse "NaN" into `NaN` or "Infinity" into `Infinity` (vs `Number()` or `Number.parseFloat()`)
// - In short, only parses token sequences that are *exactly* valid JS numbers


// from https://twitter.com/buildsghost/status/1766273406608294298
```
