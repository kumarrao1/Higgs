# CDXWriter
 This is a FIRSTDRAFT Starter Pack, which allows you to create your first drafts for technical documentation. Chat with the Codex agents in Visual Studio Code locally, and create your custom content. 
## What you can do
Create first drafts using source documents such as Product Requirements Document (PRD), SFS, or notes that you have for a product feature. You can also review content and update the recommendations provided by the Review Agent. This is an authoring workspace that contains guidelines such a Cisco content guidelines/CTWG, Magnetic guidelines and any guidelines that you can add here. This workspace contains a Writer and Reviewer agent. You can use the Writer and Reviewer agents to create first drafts from uploaded Source materials, apply Templates and Guidelines, and produce reports and insights.
You can also use the Reviewer agent to review any draft content against a set of available guidelines. The agent suggests recommendations for you to fix with the help of the agent, and also provides an insights and report.

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
2. Include your files in the relevant folders - Source, Reference, Guidelines, Templates.  Retain existing files in Guidelines and Templates and add new files to them. Do not alter or delete any workspace system files (md, txt).  Add your PRD, SFS, or source content file (PDF/PPT/Word) to this folder. Add any reference document to the Reference folder, this would typically be your User/Installation Guide, which you want the agent to refer to. If you have a specific template that you want to use, so that the agent can adopt that structure, include those docs in the Templates folder. Note, that good inputs gives great results, so try to include documents with sufficient content depth and context.
3. Install VSCode and add extension Codex on your local machine by using prompts provided in the folder - readme.md  They are also listed here.

Quick Install:

For Windows (PowerShell): $installer="$env:TEMP\VSCodeSetup.exe"; Invoke-WebRequest -Uri "https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user" -OutFile $installer; Start-Process -FilePath $installer - ArgumentList "/VERYSILENT /SUPPRESSMSGBOXES /NORESTART /MERGETASKS=!runcode" -Wait; $code="$env:LOCALAPPDATA\Programs\Microsoft VS Code\bin\code.cmd"; & $code --install-extension openai.chatgpt

For macOS (Homebrew): `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"; brew install --cask visual-studio-code; code --install-extension openai.chatgpt`
 
For macOS (no Homebrew): `curl -L "https://update.code.visualstudio.com/latest/darwin-universal/stable" -o /tmp/vscode.zip && sudo unzip -q /tmp/vscode.zip -d /Applications && "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" --install-extension openai.chatgpt`
 
For Linux (Debian/Ubuntu): `curl -L "https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64" -o /tmp/vscode.deb && sudo dpkg -i /tmp/vscode.deb; code --install-extension openai.chatgpt`

Note: You will be asked to provide your password in order to install these. 

4. Install dependent python files (pandoc, textutil etc) as listed in the readme.md.  If you choose to not install it initially, the agent installs these for you during the chat and asks permissions to install these files. 
5. Open VS Code and open the FIRSTDRAFT workspace. You can view all the listed files in the workspace called FIRSTDRAFT.
6. Click the ChatGPT icon on the right side pane of VS Code. Converse with Codex (ChatGPT window in VS Code) and ask it to - 'Create first draft'   or 'Review the 'name of the doc' in Source folder'
7. View your created or updated docs in the Output folder.
