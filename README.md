# promise-map-template

```
var Promise = require("bluebird");

var t0;

function exitHandler() {
  const t1 = new Date();
  console.log("time", (t1 - t0) / 1000);

  // insert logic to handle at exit

  process.exit(0);
}

process.on("SIGINT", exitHandler);

(async function main() {
  try {
    const array = [];
    t0 = new Date();
    await Promise.map(
      array,
      (entry, index) => {
        // return promise here
      },
      { concurrency: 50 },
    );
  } catch (error) {
    console.log(error);
  } finally {
    exitHandler();
  }
})();
```
