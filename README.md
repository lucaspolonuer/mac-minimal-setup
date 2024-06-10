# Minimalistic dev setup for a new Mac

This guide is based on my personal experience. No BS, let's go.

## Index
- [Keyboard and Trackpad Setup](#keyboard-and-trackpad-setup)
- [Security](#security)
- [Terminal](#terminal)
- [Homebrew](#homebrew)
- [Visual Studio Code](#visual-studio-code)
- [Docker Desktop](#docker-desktop)
- [JavaScript Development](#javascript-development)
- [Extras](#extras)
- [My Workflow](#my-workflow)
- [Additional Recommendations](#additional-recommendations)
  - [Alfred](#alfred)
  - [Spectacle](#spectacle)
  - [Backup Solution](#backup-solution)
  - [Git Configuration](#git-configuration)
 
## Keyboard and Trackpad Setup
1. **Trackpad Settings**:
    - **More gestures**:
        - **Swipe between pages**: Scroll left or right with two fingers (useful for navigating back/forward in web browsing).
        - **Swipe between full-screen applications**: Swipe left or right with three fingers.
        - **Mission control**: Swipe up with three fingers.
2. **Dock**:
    - Automatically hide and show the Dock.
3. **Keyboard**:
    - **Key repeat**: Fast.
    - **Delay until repeat**: Short.

## Security
1. **System Preferences > Security & Privacy**:
    - **General**: Require password immediately after sleep or screen saver begins. (You can keep a grace period of a couple of minutes if you prefer, but I like to know that my computer locks as soon as I close it.)
    - **FileVault**: Ensure FileVault disk encryption is enabled.
    - **Firewall**: Click "Turn On Firewall" to enable it.
2. **iCloud**:
    - Enable Find My Mac.
3. **Finder**:
    - **Preferences > Advanced**: Check the box for "Show all filename extensions."
4. **Terminal App Secure Keyboard Entry** (same for iTerm):
    - **Terminal > Preferences > Profiles > Keyboard**: Check the box for "Secure Keyboard Entry."
5. **macOS Automatic Updates**:
    - **System Preferences > Software Update > Advanced**: Ensure all checkboxes are checked for automatic updates.

## Terminal
1. **Download and install iTerm2**.
2. **Install oh-my-zsh**:
    ```sh
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
    - If you encounter a recurring error after installing oh-my-zsh, set the locale in the terminal:
    ```sh
    echo 'export LANG=en_US.UTF-8' >> ~/.zshrc
    ```

## Homebrew
1. **Install Homebrew as a package manager**:
    ```sh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
    - Add Homebrew to your PATH:
    ```sh
    export PATH="/opt/homebrew/bin:$PATH" >> ~/.zshrc
    ```

## Visual Studio Code
1. **Download and install VSCode**.
2. **Configuration**:
    - Open settings.json by pressing `cmd⌘ + ,` and clicking on the document with an arrow icon at the top right corner. Add the following configuration:
    ```json
    {
      "editor.tabSize": 2,
      "editor.rulers": [80],
      "files.insertFinalNewline": true,
      "files.trimTrailingWhitespace": true,
      "workbench.editor.enablePreview": true
    }
    ```

## Docker Desktop
- The desktop app for Docker is pretty useful and has improved a lot since its release. You can install it [here](https://www.docker.com/products/docker-desktop).

## JavaScript Development
1. **Install `vscode-prettier-eslint` extension**:
    - Ensure you have the proper dev dependencies for ESLint and Prettier in your project (they are listed on the plugin instructions page).
2. **Modify settings.json in VSCode**:
    ```json
    {
      "editor.defaultFormatter": "rvest.vs-code-prettier-eslint",
      "editor.formatOnType": false,
      "editor.formatOnPaste": false,
      "editor.formatOnSave": true,
      "editor.formatOnSaveMode": "file",
      "vs-code-prettier-eslint.prettierLast": false
    }
    ```
3. **Install nvm for managing node versions**:
    - In your project folder, run:
    ```sh
    nvm install
    ```
    - Note: You may be asked to install XCode Command Line Tools at some point during these installs. Just run the wizard normally.

## Extras
**BetterTouchTool**:
- This app is very useful for mapping quick shortcuts that combine your keyboard and external mouse. For example:
    - **Ctrl + scroll wheel**: Displays Mission Control.
    - **Ctrl + left side button 1 of the mouse**: Switches workspaces to the left.
    - **Ctrl + left side button 2 of the mouse**: Switches workspaces to the right.
- Download BetterTouchTool [here](https://folivora.ai/).

## My Workflow
![image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*DVCxNoIlgpifE9iarutqcg.png)
- My Mac workflow for development consists of using workspaces dedicated to specific tasks and quickly switching contexts between them.
    - **Workspace Layout**:
        - All code-related workspaces are to the left.
        - All browser/client workspaces are to the right.
        - The Terminal workspace is in the middle.
    - **Quick Access Tools**:
        - Messaging apps, Postman, and SQL clients are on the main desktop for quick access from any workspace via Mission Control.
    - **Tip**:
        - Go to System Preferences > Mission Control, then un-check "Automatically rearrange Spaces based on most recent use" to keep workspaces in the place you left them.

## Additional Recommendations

1. **Alfred**:
    - A powerful productivity application that replaces Spotlight. It allows for quick searches, app launching, and custom workflows.
    - Download [here](https://www.alfredapp.com/).

2. **Spectacle**:
    - A simple and free app for window management.
    - Download [here](https://www.spectacleapp.com/).

3. **Backup Solution**:
    - Use Time Machine or another backup solution to ensure your data is regularly backed up.

4. **Git Configuration**:
    - **Set Up Your Global Git Configuration**:
        ```sh
        git config --global user.name "Your Name"
        git config --global user.email "your.email@example.com"
        ```
    - **Set Up SSH for Git**:
        - Using SSH keys is a secure way to authenticate with Git repositories. Follow the steps outlined in the [GitHub documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).

This setup should help streamline your Mac development environment, enhancing both security and productivity. If you have any other tools or configurations that you find indispensable, feel free to add them.
