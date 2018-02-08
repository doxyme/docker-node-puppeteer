# Node 8 + Puppeteer docker image

https://hub.docker.com/r/doxyme/node8-puppeteer/

Image has all packages required to run Google puppeteer. Contains:

* Node 8.9.4 (with Yarn preinstalled)
* Preinstalled [Codecept.js Puppeteer](https://codecept.io/puppeteer/) 1.1.0
* Preinstalled Gulp 3.9.1

## Usage

1. Pass `--no-sandbox, --disable-setuid-sandbox` args when launch browser:

```js
const puppeteer = require('puppeteer');

(async() => {
    const browser = await puppeteer.launch({
        args: [
            '--no-sandbox',
            '--disable-setuid-sandbox'
        ]
    });
    // ...
})();
```

2. It's recommended to increase shm-size:
```bash
docker run --shm-size 1G doxyme/node8-puppeteer:latest
```
