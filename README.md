# progressbar

> deno progress bars for the terminal

![demo gif](./demo.gif)

## Usage

```typescript
import ProgressBar from "./progressbar.ts";
import { percentageWidget, amountWidget } from "./widgets.ts";

const sleep = (ms: number) => new Promise((resolve) => setTimeout(resolve, ms));

const pb = new ProgressBar(30, 60, percentageWidget, amountWidget);

for (let i = 0; i < 30; i++) {
  await pb.update(i);
  await sleep(100);
}
await pb.finish();
```

You can also create widgets yourself, they are just a function which, given the total and current value, returns a string.
```typescript
const percentWidget = (i, total) => `${(i / total)  `;
```


## License

MIT © [Jakob Hellermann](mailto:jakob.hellermann@protonmail.com)
