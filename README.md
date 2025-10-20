# Fastify Snippets for VS Code

[![Version](https://img.shields.io/visual-studio-marketplace/v/yourpublisherid.fastify-snippets?style=flat-square)](https://marketplace.visualstudio.com/items?itemName=yourpublisherid.fastify-snippets)
[![Installs](https://img.shields.io/visual-studio-marketplace/i/yourpublisherid.fastify-snippets?style=flat-square)](https://marketplace.visualstudio.com/items?itemName=yourpublisherid.fastify-snippets)
[![Rating](https://img.shields.io/visual-studio-marketplace/r/yourpublisherid.fastify-snippets?style=flat-square)](https://marketplace.visualstudio.com/items?itemName=yourpublisherid.fastify-snippets)

A collection of essential code snippets to supercharge your Fastify development in Visual Studio Code. Write less, code more!

---

## ✨ Features

This extension provides a comprehensive set of snippets for common Fastify patterns, allowing you to quickly scaffold:

*   **Fastify Server Instances:** Get a basic server up and running instantly.
*   **HTTP Routes:** Easily create `GET`, `POST`, `PUT`, `DELETE` routes and more.
*   **Plugins:** Boilerplate for creating and registering Fastify plugins.
*   **Hooks:** Quickly add `onRequest`, `preHandler`, `onSend` and other lifecycle hooks.
*   **Decorators:** Speed up the addition of custom properties/methods to `FastifyInstance`, `FastifyRequest`, or `FastifyReply`.
*   **Error Handling:** Common patterns for custom error handlers.
*   **Reply Utilities:** Snippets for common `reply` methods like `send`, `status`, `redirect`.
*   **JSON Schemas:** Basic structures for defining validation schemas.

---

## 🚀 Installation

1.  Open Visual Studio Code.
2.  Go to Extensions (Ctrl+Shift+X or Cmd+Shift+X).
3.  Search for "Fastify Snippets".
4.  Click "Install".

Alternatively, install directly from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=yourpublisherid.fastify-snippets).

---

## 💡 Usage

Start typing any of the prefixes below in a JavaScript file (`.js`) or a JavaScript-enabled region (e.g., inside `<script>` tags in an HTML file). VS Code's IntelliSense will suggest the snippet. Press `Tab` to expand it.

Many snippets include **tab stops** (`$1`, `$2`, etc.) and **placeholder values** to guide you. Press `Tab` repeatedly to jump between these points and fill in your custom details. Some even offer **choices** (e.g., `get|post|put`) that you can select from.

### Snippet Examples

| Prefix          | Description                                                    | Example Output                                                                                             |
| :-------------- | :------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `fserver`       | Basic Fastify server instance with a root route and logger.    | ```js\nconst fastify = require('fastify')({ logger: true })\n\nfastify.get('/', async (request, reply) => {\n  return { hello: 'world' }\n})\n\n// ... server start logic\n``` |
| `froute`        | Generic Fastify route handler (choose method).                 | ```js\nfastify.get('/path', async (request, reply) => {\n  // Your route logic here\n  return { status: 'success' }\n})\n``` |
| `fpost`         | Fastify POST route handler with request body.                  | ```js\nfastify.post('/path', async (request, reply) => {\n  const body = request.body\n  // Handle POST request with body\n  return { message: 'Data created', data: body }\n})\n``` |
| `fplugin`       | Boilerplate for a Fastify plugin using `fastify-plugin`.       | ```js\nconst fp = require('fastify-plugin')\n\nmodule.exports = fp(async function (fastify, opts) {\n  // Your plugin logic here\n}, { name: 'my-fastify-plugin' })\n``` |
| `fhookonrequest`| Add an `onRequest` hook.                                       | ```js\nfastify.addHook('onRequest', async (request, reply) => {\n  fastify.log.info(`Incoming request for ${request.method} ${request.url}`)\n})\n``` |
| `fdecorate`     | Decorate the Fastify instance with a new property or method.   | ```js\nfastify.decorate('myUtility', function () {\n  return 'Decorated value'\n})\n``` |
| `ferrorhandler` | Custom Fastify error handler (with validation example).        | ```js\nfastify.setErrorHandler(async (error, request, reply) => {\n  if (error.validation) { /* ... */ } else { /* ... */ }\n})\n``` |
| `fjsonschemaobject` | Basic JSON Schema object structure.                          | ```json\n{\n  type: 'object',\n  properties: { propertyName: { type: 'string' } },\n  required: ['propertyName']\n}\n``` |

*(Note: The examples above are simplified for readability. Full snippet output includes proper indentation and all defined tab stops.)*

---

## 🛠 Contribution

Found a bug or have a suggestion for a new snippet? We welcome contributions!

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'feat: Add new snippet for X'`).
5.  Push to the branch (`git push origin feature/your-feature`).
6.  Open a Pull Request.

---

## 📄 License

This extension is licensed under the [MIT License](LICENSE).

---

## ❤️ Support

If you find this extension helpful, please consider leaving a rating and review in the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=yourpublisherid.fastify-snippets)!

---