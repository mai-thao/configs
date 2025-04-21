source $HOMEBREW_PREFIX/share/zsh-autocomplete/zsh-autocomplete.plugin.zsh

# For Autocomplete configuration notes, see: https://github.com/marlonrichert/zsh-autocomplete?tab=readme-ov-file#configuration
zstyle ':autocomplete:*' min-input 3
zstyle ':autocomplete:*' delay 0.1  # seconds (float)
zstyle -e ':autocomplete:*:*' list-lines 'reply=( 10 )'

# ------------------ 
# Get Git current branch
function git_branch() {
	git branch --show-current 2> /dev/null | sed -e 's/.*/[&]/'
}

COLOR_DEF=$'%f'			    # White
COLOR_USR=$'%F{010}'		# Green
COLOR_DIR=$'%F{011}'		# Yellow
COLOR_GIT=$'%F{009}'		# Red
COLOR_DOLLA_SIGN=$'%F{014}'	# Blue

setopt PROMPT_SUBST

# Update and customize prompt to refresh git branch
precmd() {
PROMPT="${COLOR_USR}%n ${COLOR_DIR}%~ ${COLOR_GIT}$(git_branch)
${COLOR_DOLLA_SIGN}$ ${COLOR_DEF}"
}

# ------------------ 
# Aliases
### Git
alias gs='git status'
alias gb='git branch'
alias gp='git pull'

### Docker
alias dsa='docker ps -a'
alias dcu='docker-compose up'
alias dcud='docker-compose up -d'
alias dcd='docker-compose down'

### Gradle and Gradle Wrapper
alias gbr='./gradlew bootRun'
alias gb='./gradlew build'
alias gcb='./gradlew clean build'
alias gcbr='./gradlew clean bootRun'
alias gt='./gradlew test'
alias gct='./gradlew clean test'
alias gstatus='gradle --status'
alias gstop='gradle --stop'

### Make ls fancy:
alias ls='ls -GF'
# -G enables colorized output
# -F add type symbols to filenames
