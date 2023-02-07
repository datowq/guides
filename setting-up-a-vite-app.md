###### UBUNTU 22.04.1 LTS (WSL2)
# SETTING UP A VITE APP
**Vite** (as of 2023) is an extremely fast and lightweight build tool that makes dev-ing much easier with out-of-the-box features like hot module replacement and rollup for production.

Here's how to set it up:


**Vite requires a Node.js version 14.18+, 16+**

For help setting up Node.js and npm with nvm, here's a quick guide:

https://github.com/datowq/guides/blob/main/node-npm-nvm.md


**After obtaining the correct Node.js version, run:**

`npm create vite@latest`.

Enter `y` to any package installation requests.

Now, Vite will ask for a project name, framework, and JS variant.

Follow the prompts, and run

`cd vite-project`

`npm i`

when the additional prompt appears.


Now, the **Vite** app should be all setup!

Host the web app locally with `npm run dev` and enjoy!
