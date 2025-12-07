# CDXWriter
 This is a FIRSTDRAFT Starter Pack, which allows you to create your first drafts for technical documentation. Chat with the agents and create your custom content, locally. 
## What you can do
Create first drafts using source documents such as PRD, SFS, or notes that you have for a product feature, or review content and update agent review recommendations.  This is an authoring workspace that contains guidelines such a Cisco CTWG, Magnetic guidelines and any guidelines that you can add. This workspace contains a Writer and Reviewer agent. You can use Writer and Reviewer agents to create first drafts from uploaded Source materials, apply Templates and Guidelines, and produce reports and insights.
You can also use the agent reviewer to review any draft content against a set of available guidelines. The agent suggests recommendations for you to fix with the help of the agent, and also provides an insights and report.

## What's Inside
- `Source/` — PRDs, discussions, conversations (DOCX). You can include your own content.
- `Templates/` — First Draft template and Agent MD template.  You can also include your templates.
- `Guidelines/` — CTWG guidelines and Magnetic content guidelines. You can add additional guidelines.
- `Reference/` — Sample user guide for tone/structure. You can include your own content for the context.
- `Output/` — Generated drafts, reports, and insights.
- `system_prompt.txt` — Agent behavior contract.
- `run_instructions.md` — How to run agents and expected outputs.
- `AGENTS.md` — Roles and workflows for Writer/Reviewer agents.
- 'Readme.md' - Contains instruction details for you to use, locally.

## Workflows
- **Write**: Use Writer agent → read user-provided Source files → apply First Draft template → follow Guidelines and Reference → save to `Output/FirstDraftContent.xml` and `.docx`.
- **Review**: Use Reviewer agent → audit user-provided content against Guidelines → suggest fixes → save updated doc + `Output/Report.docx` and `Output/Insights.docx`. For offline review, use `Output/Report.csv` or `Report.xlsx`, mark Fix = Yes/No, save, then prompt the agent to apply the selected fixes.

## Get Started - Prerequisites
1. Download the FIRSTDRAFT.zip folder and unzip it.  Your workspace is ready and set up.
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
