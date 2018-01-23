# Node 8 + Puppeteer docker image

Image has all packages required to run Google puppeteer. Contains:

* Node 8.9.4 (with Yarn preinstalled)
* Preinstalled [Google Puppeteer](https://github.com/GoogleChrome/puppeteer)

## Usage

1. Pass `--no-sandbox, --disable-setuid-sandbox` args when launch browser

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

2. In case of `BUS_ADRERR` crash ([issue](https://bugs.chromium.org/p/chromium/issues/detail?id=571394)), increase shm-size

```bash
docker run --shm-size 1G ...
```
