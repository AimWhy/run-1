# Slashd Run

**Slashd Run** is a tiny library to run untrusted code into a Web Worker. 
Its main purpose is to allow data transformation through snippet of code, therefore some global capabilities are disabled.

A Web Worker cannot access the DOM therefore it cannot manipulate the webpage that use it.

Ideally, the host can execute some code, providing some data and get back the result.

There are some helper libraries included to help formatting and transformation, such as:
- dayjs
- lodash
- numbro

In future version this specific capability will be configurable.





### Develop locally:

Start the watcher

```shell
npm start 
```



### Installation

With your favorite package manager:

```shell
npm install @slashd/run
```

Then, use it in the browser:

```html
<script src="node_modules/dist/slashd-run.min.js"></script>
```

or with ES6 in a module or within a bundler:

```js
import SlashdRun from '@slashd/run'
```





### How to use

**Slashd Run** return a promise, so you can use it with `await`:

```js
const myCode = `return Math.random() * param`

const res = await SlashdRun(myCode, {param:20})

// i.e. 12.345657676
```

