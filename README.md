# CDXWriter
1. Download the FIRSTDRAFT.zip folder and unzip it.
2. Include your files in the relevant folders - Source, Reference, Guidelines, Templates.  Retain existing files in Guidelines and Templates and add new files to them. Do not alter or delete any workspace system files (md, txt). 
3. Install VSCode and add extension Codex on your local machine by using prompts provided in the folder - readme.md  They are also listed here:
  Quick Install:
   - Windows (PowerShell): `Invoke-WebRequest -Uri "https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user" -OutFile "$env:TEMP\\VSCodeSetup.exe"; Start-Process -FilePath "$env:TEMP\\VSCodeSetup.exe" -ArgumentList "/VERYSILENT /SUPPRESSMSGBOXES /NORESTART" -Wait; "$env:LOCALAPPDATA\\Programs\\Microsoft VS Code\\bin\\code" --install-extension openai.chatgpt`
  - macOS (Homebrew): `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"; brew install --cask visual-studio-code; code --install-extension openai.chatgpt`
  - macOS (no Homebrew): `curl -L "https://update.code.visualstudio.com/latest/darwin-universal/stable" -o /tmp/vscode.zip && sudo unzip -q /tmp/vscode.zip -d /Applications && "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" --install-extension openai.chatgpt`
  - Linux (Debian/Ubuntu): `curl -L "https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64" -o /tmp/vscode.deb && sudo dpkg -i /tmp/vscode.deb; code --install-extension openai.chatgpt`

4. Install dependent python files (pandoc, textutil etc) as listed in the readme.md.  If you choose to not install it initially, the agent installs these for you during the chat and asks permissions to install these files. 
5. Open VS Code and open the FIRSTDRAFT workspace. You can view all the listed files in the workspace called FIRSTDRAFT.
6. Click the ChatGPT icon on the right side pane of VS Code. Converse with Codex (ChatGPT window in VS Code) and ask it to - 'Create first draft'   or 'Review the 'name of the doc' in Source folder'
7. View your created or updated docs in the Output folder.
