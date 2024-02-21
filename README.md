# Hello Electron

Project to learn electron basics.

## Notes

- The entry point of any Electron application is its main script. This script controls the main process, which runs in a full Node.js environment.
- In Electron, each window displays web contents that can be loaded from either a local HTML file or a remote URL.
- You can use the process global's `platform` attribute to run code specifically for certain operating systems.
- You can't just edit the DOM from the main process because it has no access to the renderer's document context. They're in entirely different processes! `preload` solves this.
  -  A preload script runs before the renderer process is loaded, and has access to both renderer globals (e.g. window and document) and a Node.js environment.
- For any interactions with your web contents, you want to add scripts to your renderer process.
- The fastest way to distribute your newly created app is using Electron Forge.
  - `sudo apt-get install rpm` for linux
  - ```bash
    npm install --save-dev @electron-forge/cli
    npx electron-forge import
    ```
