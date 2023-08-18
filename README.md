# Build-a-Dapp

This repository contains the instructions and dependencies you need to start building a decentralized application (Dapp) on Thirdweb.

## 📋 Requirements

- A computer with an active internet connection.
- A code editor like [Visual Studio Code](https://code.visualstudio.com/download).
- Node Version Manager (NVM) and Node Package Manager (NPM) setup.

## 🚀 Getting Started

You can enter these code snippets in your terminal.

### For macOS:

1. **Install Homebrew**:

   Before we can install NVM and NPM, you need to have Homebrew installed:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Create NVM Working Directory**:

   ```bash
   mkdir ~/.nvm
   ```

3. **Configure NVM**:

   Add the necessary configurations to your `~/.zshrc` file:

   ```bash
   echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
   echo '[ -s "/usr/local/opt/nvm/nvm.sh" ] && \. "/usr/local/opt/nvm/nvm.sh" # This loads nvm' >> ~/.zshrc
   echo '[ -s "/usr/local/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/usr/local/opt/nvm/etc/bash_completion.d/nvm" # This loads nvm bash_completion' >> ~/.zshrc
   source ~/.zshrc
   ```

4. **Install Node using NVM**:

   ```bash
   nvm install node
   ```

5. **Resolve Potential Errors**:

   If you encounter a `http-stream` and/or `polyfill` error, resolve it by:

   ```bash
   npm install stream-http https-browserify browserify-zlib url
   ```

6. **Webpack Configuration**:

   Create a new file in your project folder named `webpack.config.js` and paste the following code:

   ```javascript
   module.exports = function override(config, env) {
       config.resolve = config.resolve || {};
       config.resolve.fallback = config.resolve.fallback || {};
       config.resolve.fallback["http"] = false;
       config.resolve.fallback["https"] = false;
       config.resolve.fallback["zlib"] = false;
       config.resolve.fallback["url"] = false;
       return config;
   }
   ```

### For Windows:

1. **Check if Node.js is Installed**:

   If not, download and install it from [Node.js official site](https://nodejs.org/en/download).

2. **Set the $PATH**:

   Ensure that the computer recognizes the Node.js command by setting the $PATH.

## 🛠 Thirdweb Setup

1. **Install Necessary Packages**:

   ```bash
   npm i @thirdweb-dev/react @thirdweb-dev/sdk ethers@^5
   ```

2. **Create Your App with Thirdweb**:

   ```bash
   npx thirdweb create app
   ```

3. **Start Your Dapp**:

   ```bash
   npm start
   ```
