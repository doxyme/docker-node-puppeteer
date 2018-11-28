# Node 10 + Puppeteer docker image

https://hub.docker.com/r/doxyme/node-puppeteer/

Image has all linux packages required to run Google puppeteer. Includes Node 10 with Yarn preinstalled.

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
docker run --shm-size 1G doxyme/node-puppeteer:latest
```
