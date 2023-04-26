[Stric](https://github.com/bunsvr) is a minimalist, blazing-fast framework for building APIs and web applications.

```typescript#index.ts
import { App } from "@stricjs/core";

export default new App()
    .use(() => new Response("Hi!"));
```

Stric supports [ArrowJS](https://arrow-js.com), a fast library to build user interface using **native** JavaScript.

```typescript#src/App.ts
import { html } from "@stricjs/arrow/utils";

export function render() {
    html`<p>Hi!</p>`;
};
```

For more info, see the Stric's [documentation](https://stricjs.gitbook.io/docs).
