# Installation

## Git

- ```sudo apt install git```
- ```curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg```
- ```echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null```
- ```sudo apt update```
- ```sudo apt install gh```
- ```sudo apt-get install -y git-flow```

## Node

- ```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash```
- ```nvm install --lts```
- ```nvm use --lts```
- ```corepack enable```
  
## Docker

- ```sudo apt-get update```
- ```sudo apt-get install \ ca-certificates \ curl \ gnupg \ lsb-release```
- ```sudo mkdir -p /etc/apt/keyrings```
- ```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg```
- ```echo \ "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null```
- ```sudo apt-get update```
- ```sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin```
- ```sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose```
- ```sudo chmod +x /usr/local/bin/docker-compose```
- ```docker-compose --version```

## Terminal

- ```sudo apt install zsh```
- ```zsh --version```
- ```chsh -s $(which zsh)```
- ```sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"```
- ```sudo apt-get install dconf-cli```s
- ```git clone https://github.com/dracula/gnome-terminal```
- ```cd gnome-terminal```
- ```./install.sh```
- go to https://github.com/tonsky/FiraCode/releases and download font
- ```mkdir ~/.fonts```
- copy and paste .ttf fonts to the new folder
- ```git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"```
- ```ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"```
- ```nano ~/.zshrc``` and put:
  <pre>ZSH_THEME="spaceship"</pre>
  <pre>
  SPACESHIP_PROMPT_ORDER=(
    user          # Username section
    dir           # Current directory section
    host          # Hostname section
    git           # Git section (git_branch + git_status)
    hg            # Mercurial section (hg_branch  + hg_status)
    exec_time     # Execution time
    line_sep      # Line break
    vi_mode       # Vi-mode indicator
    jobs          # Background jobs indicator
    exit_code     # Exit code section
    char          # Prompt character
  )
  SPACESHIP_USER_SHOW=always
  SPACESHIP_PROMPT_ADD_NEWLINE=false
  SPACESHIP_CHAR_SYMBOL="$"
  SPACESHIP_CHAR_SUFFIX=" "
  </pre>
- ```bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"```
- ```nano ~/.zshrc``` and put:
  <pre>
  zinit light zdharma/fast-syntax-highlighting
  zinit light zsh-users/zsh-autosuggestions
  zinit light zsh-users/zsh-completions
  </pre>

## Brave

- ```sudo apt install apt-transport-https curl```
- ```sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg```
- ```echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list```
- ```sudo apt update```
- ```sudo apt install brave-browser```

## Ubuntu software

- code
- telegram-desktop
- dbeaver-ce
- insomnia

## VS-Code extensions

- Omni Theme
- Material Icons
- C++
- Color Highlight
- Docker
- Doxygen Documentation Generator
- EditorConfig
- ESLint
- GitLens
- Markddown
- Prettier

## VS-Code config

<pre>
{
  "workbench.colorTheme": "Omni",
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,
  "editor.fontSize": 14,
  "explorer.compactFolders": false,
  "workbench.editor.labelFormat": "short",
  "explorer.confirmDragAndDrop": false,
  "explorer.confirmDelete": false,
  "editor.rulers": [80, 120],
  "editor.semanticHighlighting.enabled": false,
  "workbench.iconTheme": "material-icon-theme",
  "javascript.updateImportsOnFileMove.enabled": "always",
  "typescript.updateImportsOnFileMove.enabled": "always",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "editor.tabSize": 2,
  "editor.renderWhitespace": "all",
  "files.associations": {
    "*.rmd": "markdown"
  },
  "C_Cpp.updateChannel": "Insiders",
  "editor.formatOnSave": true,
  "[cpp]": {
    "editor.defaultFormatter": "ms-vscode.cpptools"
  },
  "[html]": {
    "editor.defaultFormatter": "vscode.html-language-features"
  },
  "[markdown]": {
    "editor.defaultFormatter": "yzhang.markdown-all-in-one"
  },
  "terminal.integrated.enableMultiLinePasteWarning": false,
  "remote.SSH.defaultExtensions": ["gitpod.gitpod-remote-ssh"],
  "remote.SSH.configFile": "/tmp/gitpod_ssh_config-7452-gfEdJk4xAPXF"
}
</pre>

## Dumping

- ```docker cp ./dumps/FILE.sql <CONTAINER_ID>:/```
- ```docker exec -it <CONTAINER_ID> sh```
- ```psql -U postgres -d dashboard -f FILE.sql```
