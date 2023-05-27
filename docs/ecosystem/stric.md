[Stric](https://github.com/bunsvr) is a minimalist, fast web framework for Bun.

{% codetabs %}

```ts#app.ts
import { App } from "@stricjs/core";

// Export the fetch handler and serve with Bun
export default new App()
  // Return "Hi!" on every request
  .use(() => new Response("Hi!"));
```

```ts#router.ts
import { Router } from "@stricjs/router";

// Create a router and serve using Bun
export default new Router()
  // Handle GET request to `/`
  .get("/", () => new Response("Hi"))
  // Handle POST request to `/json`
  .post("/json", async req => Response.json(await req.json()))
  // Return 90 for requests to `/id/90` for instance
  .get("/id/:id", req => new Response(req.params.id))
  // Use the default 404 handler
  .use(404);
```

{% /codetabs %}

[Stric](https://github.com/bunsvr) is one of the fastest Bun web frameworks. See the benchmark [here](https://github.com/bunsvr/benchmark/blob/main/results/index.md).
Stric also provides support for [ArrowJS](https://www.arrow-js.com), a library for building reactive interfaces in **native** JavaScript. 

{% codetabs %}

```ts#src/App.ts
import { html } from "@stricjs/arrow/utils";

// Code inside this function can use web APIs
export function render() {
  // Render a <p> element with text 'Hi'
  html`<p>Hi</p>`;
};

// Set the path to handle
export const path = "/";
```
```ts#index.ts
import { PageRouter } from "@stricjs/arrow";

// Create a page router, build and serve directly
new PageRouter().serve();
```

{% /codetabs %}

For more info, see Stric's [documentation](https://stricjs.gitbook.io/docs).
