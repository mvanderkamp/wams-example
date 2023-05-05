# wams-example
A quick demo of how WAMS would be used if we made it a library instead of a framework.

# To run
```javascript
node index.js
```

# About
This uses the `easier-integration` branch of the WAMS repo, which includes changes to support this.

This demonstrates how, with a few changes, we could support integrating WAMS into other applications, by featuring a web page that has the WAMS canvas as just another element in the page, in an application that has defined its own HTML and CSS files.
- The server and the static files are provided by this application instead of WAMS.
- The canvas does not take up the whole page, but rather just whatever space this application wants it to take up.
    - This would need more work to make sure that coordinates are appropriately transformed in all cases into canvas-relative coordinates before being sent to the server.

With a bit more work, we can also make the client side more flexible. We could allow users to import the WAMS client code into their client scripts, decide for themselves when to instantiate WAMS, when to connect/disconnect, etc, and perhaps even manually send model change requests to the server.

## Demo app details
- Static files are defined under `dist/`.
- The WAMS client script is served directly from the package in `node_modules`.

## How the demo was created
```bash
mkdir demo && cd demo
npm init
npm install mvanderkamp/wams#easier-integration
```
Then I ported over the polygons example and the static files.
