# install different nodejs version

Here's how you can do it:

1. **Install Node.js**: You can download and install Node.js from the official website or use a version manager like NVM (Node Version Manager) to easily switch between different Node.js versions.

   - To install Node.js using NVM (recommended for managing multiple Node.js versions):
     - If you don't have NVM installed, follow the instructions here: [NVM Installation](https://github.com/nvm-sh/nvm#installation)
     - Once NVM is installed, you can install Node.js 16.18.0 by running:
       ```
       nvm install 16.18.0
       ```
     - Set the newly installed Node.js version as the default for your project:
       ```
       nvm use 16.18.0
       ```

2. **Update Yarn**: After updating Node.js, you might also want to update Yarn to ensure it works with the new Node.js version. You can do this with the following command:

   ```
   npm install -g yarn
   ```
