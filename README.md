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
2. Include your files in the relevant folders - Source, Reference, Guidelines, Templates.  Retain existing files in Guidelines and Templates and add new files to them. Do not alter or delete any workspace system files (md, txt).  Add your PRD, SFS, or source content file (PDF/PPT/Word) to the Source folder. Add any reference document to the Reference folder, this would typically be your User/Installation Guide, which you want the agent to refer to. If you have a specific template that you want to use, so that the agent can adopt that structure, include those docs in the Templates folder. Note, that good inputs gives great results, so try to include documents with sufficient content depth and context.
3. Install VSCode and add extension Codex on your local machine by using prompts provided in the folder - readme.md  They are also listed here.

This is a method, where you first install Visual Studio Code, and then install Codex.

Step 1: Install VS Code (platform-specific):
 - Windows (Powersheell)
 $installer="$env:TEMP\VSCodeSetup.exe"; Invoke-WebRequest -Uri "https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user" -OutFile $installer; Start-Process -FilePath $installer -ArgumentList "/VERYSILENT /SUPPRESSMSGBOXES /NORESTART /MERGETASKS=!runcode" -Wait

- macOS (Homebrew):
brew install --cask visual-studio-code

- macOS (no Homebrew): 
curl -L "https://update.code.visualstudio.com/latest/darwin-universal/stable" -o /tmp/vscode.zip && sudo ditto -xk /tmp/vscode.zip /Applications && xattr -dr com.apple.quarantine "/Applications/Visual Studio Code.app"

- Linux (Debian/Ubuntu):
curl -L "https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64" -o /tmp/vscode.deb && sudo apt-get update && sudo apt-get install -y /tmp/vscode.deb

Step 2: Install the Codex extension after VS Code is installed
1.Open VS Code
2.Go to Extensions (Ctrl/Cmd+Shift+X)
3.Search for the extension - Codex
4.Click Install
5.You will be prompted to login to ChatGPT using your enterprise ID.
6.Connect and use Codex on Visual Studio code.

When using Codex, you will be prompted to install the relevant Python files. Codex helps you with this.

Quick installs:
  - Windows (PowerShell): 
  $installer="$env:TEMP\VSCodeSetup.exe"; Invoke-WebRequest -Uri "https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user" -OutFile $installer; Start-Process -FilePath $installer -ArgumentList "/VERYSILENT /SUPPRESSMSGBOXES /NORESTART /MERGETASKS=!runcode" -Wait; $code="$env:LOCALAPPDATA\Programs\Microsoft VS Code\bin\code.cmd"; & $code --install-extension openai.chatgpt
  
  - macOS (Homebrew):
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" && brew install --cask visual-studio-code && "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" --install-extension openai.chatgpt

  - macOS (no Homebrew): 
  curl -L "https://update.code.visualstudio.com/latest/darwin-universal/stable" -o /tmp/vscode.zip && sudo ditto -xk /tmp/vscode.zip /Applications && xattr -dr com.apple.quarantine "/Applications/Visual Studio Code.app" && "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" --install-extension openai.chatgpt
  
  - Linux (Debian/Ubuntu): 
  curl -L "https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64" -o /tmp/vscode.deb && sudo apt-get update && sudo apt-get install -y /tmp/vscode.deb && code --install-extension openai.chatgpt

Note: You will be asked to provide your password in order to install both these applications. Use your enteprise ID to connect with Codex/ChatGPT and then you can see Codex active on VS Code.

To use Visual Studio and Codex:
1. Open Visual Studio Code.
2. Open the Codex extension. You will be asked to connect to ChatGPT using your Enterprise ID login.  If you are not able to, then check if you have the license to do so.
3. Inside Visual Studio Code, once you are connected to Codex, you will see the ChatGPT icon on the left-side on the navigation bar.
4. Select the ChatGPT icon to open up a chat window.  Now you can start conversing with Codex.
   Note: Your agent uses python and its related packages, and hence may prompt for installation of packages, which you can allow it to do so.

## Detailed Steps
To use CDX Writer to create First Drafts:
1. Open the FIRSTDRAFT workspace/folder. You can view all the listed files in the workspace called FIRSTDRAFT.
2. Add your files to the Source folder. These are the files that you will use as inputs for the agent to understand/review/create content. These are typically the PRD, SFS, SME notes, discussion transcripts etc.
3. Add your reference files to the Reference folder. These are typically the files you want the agent to use a reference for better context. Example, a user guide, installation/deployment guide etc.
4. Add a template to the Templates folder, if you have any specific template that you want the agent to use to construct the output.  Note that since this is a first draft, it may not use the exact document visual styles, but it will use the content structures to create your output.
5. In VS Code, click the ChatGPT icon on the left-side pane of VS Code. The ChatGPT conversation window opens up.
6. Converse with Codex (ChatGPT window in VS Code). Prompt the agents, For example, 'Create a first draft using the Writer agent'  or 'Review the 'name of the doc' in the Source folder' or 'Use the @writer.agent or @reviewer.agent to create a first draft for my content that is in the Source folder'.
Note, that you dont need to copy the system prompts and paste in the chat to use. This is inbuilt and automatically used by the agents.
7. Once completed, you can view the created First Draft document or the updated docs in the timestamped run folder under `Output/WriterRuns/` or `Output/ReviewerRuns/`. Open the docx format output in MS Word to see the output.  The xml output is provided just as a backup and may not open with the needed Cisco UTF and styles. This xml doc is provided to ideally be used if you plan to reuse (copy+paste) this content in other xml tools.

When you want to create a new First Draft for a different context, you can delete all the documents that you added to the related folders, and include the new ones in the relevant folders and converse with Codex. Each new run will create its own timestamped folder in `Output/WriterRuns/` or `Output/ReviewerRuns/`, preserving history.

