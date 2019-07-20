# My Ubuntu Setup

## Applications/Software

* [Chrome](https://www.google.com/chrome/) - Perfered Web Browser.
* [Visual Studio Code](https://code.visualstudio.com/) - Favorite Text Editor.
* [Albert](https://albertlauncher.github.io/docs/installing/) - Albert is a desktop agnostic launcher.
* [OBS](https://obsproject.com/) - Video recording and live streaming software.
* [Station](https://getstation.com/) - A single place for all of your web applications.
* [Gnome Tweak Tool](https://linuxconfig.org/how-to-install-tweak-tool-on-ubuntu-18-04-bionic-beaver-linux) - An extension of the _GNOME_ shell that can be used to modify the _GNOME_ interface.
* [Flameshot](https://flameshot.js.org/#/) - Powerful yet simple to use screenshot software.
* [FileZilla](https://filezilla-project.org/) - Cross-platform FTP application.
* [HydraPaper](https://github.com/GabMus/HydraPaper) - A Gtk utility to set two different backgrounds for each monitor on GNOME.
* [Stacer](https://github.com/oguzhaninan/Stacer) - Linux System Optimizer and Monitoring.

## Terminal Setup

* [Terminal Settings Installer](https://noobs-term.com/#/?id=overview) - A easy way to setup a GREAT terminal
  * [zsh](https://ohmyz.sh/) - A popular shell with features like completion, path correction, spelling correction, and more.
  * [tmux](https://github.com/tmux/tmux) - Terminal multiplexer allows you to manage multiple terminal sessions from a single window.
  * [neovim](https://neovim.io/) - \(I uninstall neovime and use normal vim\) A project that seeks to aggressively refactor Vim.
  * [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) - A framework for managing your zsh configuration.
  * [vim-sensible](https://github.com/tpope/vim-sensible) - Vim settings everyone can agree on.
  * [tmux -sensible](https://github.com/tmux-plugins/tmux-sensible) - Tmux settings everyone can agree on.
  * [nord-tmux](https://github.com/arcticicestudio/nord-tmux) - An arctic, north-bluish clean and elegant tmux color theme.
  * [nord-vim](https://github.com/arcticicestudio/nord-vim) - An arctic, north-bluish clean and elegant Vim color theme.
  * [spaceship-prompt](https://github.com/denysdovhan/spaceship-prompt) - A zsh prompt for Astronauts.

### Terminal Plugins I Add

* [theFuck](https://github.com/nvbn/thefuck) - Magnificent app which corrects your previous console command .
* [cheat.sh ](https://github.com/chubin/cheat.sh)- The only cheat sheet you need.
* [lazygit](https://github.com/jesseduffield/lazygit) - Simple terminal UI for git commands.
* [fzf](https://github.com/junegunn/fzf) - A command-line fuzzy finder.
* [Ranger](https://www.digitalocean.com/community/tutorials/installing-and-using-ranger-a-terminal-file-manager-on-a-ubuntu-vps) - Ranger is a terminal file manager with vim-like keybindings that uses the ncurses library to provide a powerful interface for your filesystem.
* [exa](https://github.com/ogham/exa) - A modern replacement for `ls`.
* [Lazyme](https://github.com/pawurb/lazyme) - A simple gem to help you optimize your shell workflow.
* [the\_silver\_searcher](https://github.com/ggreer/the_silver_searcher) - A code-searching tool similar to ack, but faster.
* [zsh-history-substring-search](https://github.com/zsh-users/zsh-history-substring-search) - History search feature, where you can type in any part of any command from history and then press chosen keys, such as the UP and DOWN arrows, to cycle through matches.
* [peco](https://github.com/peco/peco) - Simplistic interactive filtering tool \(like grep\).
* [tig](https://github.com/jonas/tig) - Text-mode interface for git.
* [fac](https://github.com/mkchoi212/fac) - Easy-to-use CUI for fixing git conflicts.
* [httpie](https://github.com/jakubroztocil/httpie) - Modern command line HTTP client.
* [fd](https://github.com/sharkdp/fd/) - A simple, fast and user-friendly alternative to 'find'.
* [tldr](https://github.com/tldr-pages/tldr) - Simplified and community-driven man pages.
* [howdoi](https://github.com/gleitz/howdoi) - Instant coding answers via the command line.
* [ghq](https://github.com/motemen/ghq) - Remote repository management made easy.

## Dotfiles

### .bashrc

```bash
# ~/.bashrc: executed by bash(1) for non-login shells.
# see /usr/share/doc/bash/examples/startup-files (in the package bash-doc)
# for examples

# If not running interactively, don't do anything
case $- in
    *i*) ;;
      *) return;;
esac

# don't put duplicate lines or lines starting with space in the history.
# See bash(1) for more options
HISTCONTROL=ignoreboth

# append to the history file, don't overwrite it
shopt -s histappend

# for setting history length see HISTSIZE and HISTFILESIZE in bash(1)
HISTSIZE=1000
HISTFILESIZE=2000

# check the window size after each command and, if necessary,
# update the values of LINES and COLUMNS.
shopt -s checkwinsize

# If set, the pattern "**" used in a pathname expansion context will
# match all files and zero or more directories and subdirectories.
#shopt -s globstar

# make less more friendly for non-text input files, see lesspipe(1)
[ -x /usr/bin/lesspipe ] && eval "$(SHELL=/bin/sh lesspipe)"

# set variable identifying the chroot you work in (used in the prompt below)
if [ -z "${debian_chroot:-}" ] && [ -r /etc/debian_chroot ]; then
    debian_chroot=$(cat /etc/debian_chroot)
fi

# set a fancy prompt (non-color, unless we know we "want" color)
case "$TERM" in
    xterm-color|*-256color) color_prompt=yes;;
esac

# uncomment for a colored prompt, if the terminal has the capability; turned
# off by default to not distract the user: the focus in a terminal window
# should be on the output of commands, not on the prompt
#force_color_prompt=yes

if [ -n "$force_color_prompt" ]; then
    if [ -x /usr/bin/tput ] && tput setaf 1 >&/dev/null; then
	# We have color support; assume it's compliant with Ecma-48
	# (ISO/IEC-6429). (Lack of such support is extremely rare, and such
	# a case would tend to support setf rather than setaf.)
	color_prompt=yes
    else
	color_prompt=
    fi
fi

if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
unset color_prompt force_color_prompt

# If this is an xterm set the title to user@host:dir
case "$TERM" in
xterm*|rxvt*)
    PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"
    ;;
*)
    ;;
esac

# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

# colored GCC warnings and errors
#export GCC_COLORS='error=01;31:warning=01;35:note=01;36:caret=01;32:locus=01:quote=01'

# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'

# Add an "alert" alias for long running commands.  Use like so:
#   sleep 10; alert
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'

# Alias definitions.
# You may want to put all your additions into a separate file like
# ~/.bash_aliases, instead of adding them here directly.
# See /usr/share/doc/bash-doc/examples in the bash-doc package.

if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi

# enable programmable completion features (you don't need to enable
# this, if it's already enabled in /etc/bash.bashrc and /etc/profile
# sources /etc/bash.bashrc).
if ! shopt -oq posix; then
  if [ -f /usr/share/bash-completion/bash_completion ]; then
    . /usr/share/bash-completion/bash_completion
  elif [ -f /etc/bash_completion ]; then
    . /etc/bash_completion
  fi
fi

# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/jh/anaconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/jh/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/home/jh/anaconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/jh/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<

‘export PATH=”/home/jh/ .rbenv/bin:/home/linuxbrew/.linuxbrew/bin:/home/linuxbrew/.linuxbrew/sbin:/home/jh/.local/bin:/home/jh/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin”’
‘export PATH=”/home/jh/ .rbenv/bin:/home/linuxbrew/.linuxbrew/bin:/home/linuxbrew/.linuxbrew/sbin:/home/jh/.local/bin:/home/jh/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin”’
‘eval “”’
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

```

### .irbrc \(ruby\)

```bash
puts "Work your magic..."

# Make gems available
require 'rubygems'
require 'awesome_print'
require 'interactive_editor'

# include Date automatically as well as Time enhancements
require 'date'
require 'time'

# include my gem for doing Project Euler tasks and the like
# require 'boqwij'

AwesomePrint.irb!
# Create an alias for a quick exit
alias q exit

ANSI = {}
ANSI[:RESET]     = "\e[0m"
ANSI[:BOLD]      = "\e[1m"
ANSI[:UNDERLINE] = "\e[4m"
ANSI[:LGRAY]     = "\e[0;37m"
ANSI[:GRAY]      = "\e[0;90m"
ANSI[:RED]       = "\e[31m"
ANSI[:GREEN]     = "\e[32m"
ANSI[:YELLOW]    = "\e[33m"
ANSI[:BLUE]      = "\e[34m"
ANSI[:MAGENTA]   = "\e[35m"
ANSI[:CYAN]      = "\e[36m"
ANSI[:WHITE]     = "\e[37m"

# Build a simple colorful IRB prompt
IRB.conf[:PROMPT][:SIMPLE_COLOR] = {
  :PROMPT_I => "#{ANSI[:BLUE]}>>#{ANSI[:RESET]} ",
  :PROMPT_N => "#{ANSI[:BLUE]}>>#{ANSI[:RESET]} ",
  :PROMPT_C => "#{ANSI[:RED]}?>#{ANSI[:RESET]} ",
  :PROMPT_S => "#{ANSI[:YELLOW]}?>#{ANSI[:RESET]} ",
  :RETURN   => "#{ANSI[:GREEN]}=>#{ANSI[:RESET]} %s\n",
  :AUTO_INDENT => true }

# Load the readline module.
IRB.conf[:USE_READLINE] = true

# Replace the irb(main):001:0 with a simple >>
IRB.conf[:PROMPT_MODE]  = :SIMPLE_COLOR

# Tab completion
require 'irb/completion'

# Automatic indentation
IRB.conf[:AUTO_INDENT]=true

# Save History between irb sessions
require 'irb/ext/save-history'
IRB.conf[:SAVE_HISTORY] = 1000
IRB.conf[:HISTORY_FILE] = "#{ENV['HOME']}/.irb_history"

# Loading extensions of the console. This is wrapped
# because some might not be included in your Gemfile
# and errors will be raised.
def extend_console(name, care = true, required = true)
  if care
    require name if required
    yield if block_given?
    $console_extensions << "#{ANSI[:GREEN]}#{name}#{ANSI[:RESET]}"
  else
    $console_extensions << "#{ANSI[:GRAY]}#{name}#{ANSI[:RESET]}"
  end
rescue LoadError
  $console_extensions << "#{ANSI[:RED]}#{name}#{ANSI[:RESET]}"
end
$console_extensions = []



# Hirb is a mini view framework for console applications, designed
# to make formatting of ActiveRecord objects easier on the eyes
# http://tagaholic.me/2009/03/13/hirb-irb-on-the-good-stuff.html
extend_console 'hirb' do
  Hirb.enable
  extend Hirb::Console
end

# Fancy IRB is a gem that colorizes irb and adds other helpers
# See https://github.com/janlelis/fancy_irb
#extend_console 'fancy_irb' do
#  FancyIrb.start
#end


# # Trick I like from Thoughtbot's Dan Croak to show log info in console
# # http://robots.thoughtbot.com/post/159806033/irb-script-console-tips
# # Log to STDOUT if in Rails (useful for showing the SQL query run)
# if ENV.include?('RAILS_ENV') && !Object.const_defined?('RAILS_DEFAULT_LOGGER')
#  require 'logger'
#  RAILS_DEFAULT_LOGGER = Logger.new(STDOUT)
# end

# The above trick doesn't work in Rails 3, but this does...
# ActiveRecord::Base.logger = Logger.new(STDOUT) if defined? Rails::Console

# When you're using Rails 2 console, show queries in the console
extend_console 'rails2', (ENV.include?('RAILS_ENV') && !Object.const_defined?('RAILS_DEFAULT_LOGGER')), false do
  require 'logger'
  RAILS_DEFAULT_LOGGER = Logger.new(STDOUT)
end

# When you're using Rails 3 console, show queries in the console
extend_console 'rails3', defined?(ActiveSupport::Notifications), false do
  $odd_or_even_queries = false
  ActiveSupport::Notifications.subscribe('sql.active_record') do |*args|
    $odd_or_even_queries = !$odd_or_even_queries
    color = $odd_or_even_queries ? ANSI[:CYAN] : ANSI[:MAGENTA]
    event = ActiveSupport::Notifications::Event.new(*args)
    time  = "%.1fms" % event.duration
    name  = event.payload[:name]
    sql   = event.payload[:sql].gsub("\n", " ").squeeze(" ")
    puts "  #{ANSI[:UNDERLINE]}#{color}#{name} (#{time})#{ANSI[:RESET]}  #{sql}"
  end
end

# Simple methods in Rails console to get names of tables, columns(given a table), and models
def tables
  ActiveRecord::Base.connection.tables.sort!
end

def columns(table)
  ActiveRecord::Base.connection.columns(table).map(&:name).sort!
end

def models
  tables.select{|t| t != "schema_migrations"}.map{|t| t.underscore.singularize.camelize.to_sym}
end

# Automating the creating of contexts in rails console
def set_context
  require 'factory_bot_rails'
  require './test/contexts'
  include Contexts
  puts 'Contexts enabled'
  if Contexts.respond_to?(:create_all)
    create_all
    puts 'Contexts built'
  end
end
```

### .pryrc \(ruby\)

```bash
# === EDITOR ===
Pry.editor = 'code'
Pry.config.color = true
Pry.config.theme = "solarized"

# === PROMPT ===
Pry.prompt = [proc { |obj, nest_level, _| "#{RUBY_VERSION} (#{obj}):#{nest_level} > " }, proc { |obj, nest_level, _| "#{RUBY_VERSION} (#{obj}):#{nest_level} * " }]

# === COLORS ===
unless ENV['PRY_BW']
  Pry.color = true
  Pry.config.theme = "railscasts"
  Pry.config.prompt = PryRails::RAILS_PROMPT if defined?(PryRails::RAILS_PROMPT)
  Pry.config.prompt ||= Pry.prompt
end

# === HISTORY ===
Pry.config.history.should_save = true
Pry::Commands.command /^$/, "repeat last command" do
  _pry_.run_command Pry.history.to_a.last
end

# == Pry-Nav - Using pry as a debugger ==
Pry.commands.alias_command 'c', 'continue' rescue nil
Pry.commands.alias_command 's', 'step' rescue nil
Pry.commands.alias_command 'n', 'next' rescue nil
Pry.commands.alias_command 'f', 'finish' rescue nil
Pry.commands.alias_command 'l', 'whereami' rescue nil
Pry.commands.alias_command 'r!', 'reload!' rescue nil

# === Listing config ===
# Better colors - by default the headings for methods are too
# similar to method name colors leading to a "soup"
# These colors are optimized for use with Solarized scheme
# for your terminal
Pry.config.ls.separator = "\n" # new lines between methods
Pry.config.ls.heading_color = :magenta
Pry.config.ls.public_method_color = :green
Pry.config.ls.protected_method_color = :yellow
Pry.config.ls.private_method_color = :bright_black

# == PLUGINS ===
# awesome_print gem: great syntax colorized printing
# look at ~/.aprc for more settings for awesome_print
begin
  require 'awesome_print'
  # The following line enables awesome_print for all pry output,
  # and it also enables paging
  Pry.config.print = proc {|output, value| Pry::Helpers::BaseHelpers.stagger_output("=> #{value.ai}", output)}

  # If you want awesome_print without automatic pagination, use the line below
  module AwesomePrint
    Formatter.prepend(Module.new do
      def awesome_self(object, type)
        if type == :string && @options[:string_limit] && object.inspect.to_s.length > @options[:string_limit]
          colorize(object.inspect.to_s[0..@options[:string_limit]] + "...", type)
        else
          super(object, type)
        end
      end
    end)
  end

  AwesomePrint.defaults = {
    :string_limit => 80,
    :indent => 2,
    :multiline => true
  }
  AwesomePrint.pry!
rescue LoadError => err
  puts "gem install awesome_print  # <-- highly recommended"
end

# === CUSTOM COMMANDS ===
default_command_set = Pry::CommandSet.new do
  command "sql", "Send sql over AR." do |query|
    if ENV['RAILS_ENV'] || defined?(Rails)
      pp ActiveRecord::Base.connection.select_all(query)
    else
      pp "No rails env defined"
    end
  end
end

Pry.config.commands.import default_command_set

# === CONVENIENCE METHODS ===
class Array
  def self.sample(n=10, &block)
    block_given? ? Array.new(n,&block) : Array.new(n) {|i| i+1}
  end
end

class Hash
  def self.sample(n=10)
    (97...97+n).map(&:chr).map(&:to_sym).zip(0...n).to_h
  end
end

# === COLOR CUSTOMIZATION ===
# Everything below this line is for customizing colors, you have to use the ugly
# color codes, but such is life.
CodeRay.scan("example", :ruby).term # just to load necessary files
# Token colors pulled from: https://github.com/rubychan/coderay/blob/master/lib/coderay/encoders/terminal.rb

$LOAD_PATH << File.dirname(File.realpath(__FILE__))

# In CodeRay >= 1.1.0 token colors are defined as pre-escaped ANSI codes
if Gem::Version.new(CodeRay::VERSION) >= Gem::Version.new('1.1.0')
  require "escaped_colors"
else
  require "unescaped_colors"
end

module CodeRay
  module Encoders
    class Terminal < Encoder
      # override old colors
      TERM_TOKEN_COLORS.each_pair do |key, value|
        TOKEN_COLORS[key] = value
      end
    end
  end
end
```

### .tmux.conf

```bash
#
# Main Settings
# 

set-option -g prefix C-a # Set mode key to Control + a
bind-key C-a send-prefix
setw -g mouse on
set-option -sg escape-time 10 #

#
# Plugins
# 

# List of plugins
set -g @tpm_plugins 'tmux-plugins/tpm' # tmux package manager
set -g @tpm_plugins 'tmux-plugins/tmux-sensible' # sensible settings everyone can agree on (hopefully)
set -g @tpm_plugins 'tmux-plugins/tmux-resurrect' # persist tmux environment across system restarts
set -g @tpm_plugins 'tmux-plugins/tmux-continuum' # continuous saving of tmux environment
set -g @tpm_plugins 'tmux-plugins/tmux-yank' # for copying to system clipboard
set -g @tpm_plugins 'tmux-plugins/tmux-prefix-highlight' # highlights when you press tmux prefix key

#
# Theme
#

set -g @tpm_plugins 'arcticicestudio/nord-tmux' # an arctic, north-bluish theme

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'

```

### .vimrc

```bash
set nocompatible              " be iMproved, required
filetype off                  " required

set ignorecase
set smartcase
" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" let Vundle manage Vundle, required
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
Plugin 'VundleVim/Vundle.vim'

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" all plugins
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
Plugin 'Valloric/YouCompleteMe'
Plugin 'SirVer/ultisnips'
Plugin 'honza/vim-snippets'
Plugin 'vim-syntastic/syntastic'
Plugin 'haya14busa/incsearch.vim'
Plugin 'sheerun/vim-polyglot'

Plugin 'google/vim-maktaba'
Plugin 'google/vim-codefmt'
Plugin 'google/vim-glaive'

Plugin 'scrooloose/nerdtree'
Plugin 'vim-airline/vim-airline'
Plugin 'Raimondi/delimitMate'
Plugin 'morhetz/gruvbox'
Plugin 'ctrlpvim/ctrlp.vim'
Plugin 'majutsushi/tagbar'
Plugin 'Yggdroot/indentLine'

Plugin 'octol/vim-cpp-enhanced-highlight'
Plugin 'bfrg/vim-cpp-modern'
Plugin 'vim-ruby/vim-ruby'
Plugin 'tpope/vim-rails'
Plugin 'dbeniamine/cheat.sh-vim'

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Cheat.sh
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Vim command used to open new buffer
let g:CheatSheetReaderCmd='new"'

" Cheat sheet file type
let g:CheatSheetFt='markdown'

" Program used to retrieve cheat sheet with its arguments
let g:CheatSheetUrlGetter='curl --silent'

" Flag to add cookie file to the query
let g:CheatSheetUrlGetterIdFlag='-b'

" cheat sheet base url
let g:CheatSheetBaseUrl='https://cht.sh'

" cheat sheet settings do not include style settings neiter comments,
" see other options below
let g:CheatSheetUrlSettings='q'

" cheat sheet pager
let g:CheatPager='less -R'

" pygmentize theme used for pager output, see :CheatPager :styles-demo
let g:CheatSheetPagerStyle='rrt'

" Show comments in answers by default
" (setting this to 0 means giving ?Q to the server)
let g:CheatSheetShowCommentsByDefault=1

" cheat sheet buffer name
let g:CheatSheetBufferName="_cheat"

" Default selection in normal mode (line for whole line, word for word under cursor)
let g:CheatSheetDefaultSelection="line"

" Default query mode
" 0 => buffer
" 1 => replace (do not use or you might loose some lines of code)
" 2 => pager
" 3 => paste after query
" 4 => paste before query
let g:CheatSheetDefaultMode=0

" Path to cheat sheet cookie
let g:CheatSheetIdPath=expand('~/.cht.sh/id')

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" All of your Plugins must be added before the following line
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
call vundle#end()            " required
call glaive#Install()        " enable this line after the installation of glaive
filetype plugin indent on    " required

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" custom setting
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set mouse=a
set number
set encoding=utf-8
set backspace=indent,eol,start
set cursorline
set guioptions=
syntax on

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Set SPELLCHeCK YYAH
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set spell spelllang=en_ca

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" indent for global
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set expandtab
set shiftwidth=4
set softtabstop=4
set autoindent

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" indent for special file
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
autocmd FileType c,cpp setlocal expandtab shiftwidth=2 softtabstop=2 cindent
autocmd FileType python setlocal expandtab shiftwidth=4 softtabstop=4 autoindent
autocmd FileType ruby setlocal expandtab shiftwidth=2 tabstop=2
autocmd FileType eruby setlocal expandtab shiftwidth=2 tabstop=2

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Ultisnips
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
let g:UltiSnipsExpandTrigger="<tab>"
let g:UltiSnipsJumpForwardTrigger="<c-f>"
let g:UltiSnipsJumpBackwardTrigger="<c-z>"
let g:UltiSnipsEditSplit="vertical"

" If you have `brew install clang-format` (and why don't you?)
map <C-K> :pyf ~/bin/clang-format.py<cr>
imap <C-K> <c-o>:pyf ~/bin/clang-format.py<cr>

" And for incsearch.vim
map /  <Plug>(incsearch-forward)
map ?  <Plug>(incsearch-backward)
map g/ <Plug>(incsearch-stay)

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" setup for ycm
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
let g:ycm_global_ycm_extra_conf = '~/.vim/bundle/YouCompleteMe/third_party/ycmd/examples/.ycm_extra_conf.py'
let g:ycm_python_binary_path = 'python'
let g:ycm_complete_in_comments = 1
let g:ycm_autoclose_preview_window_after_completion = 1
let g:ycm_autoclose_preview_window_after_insertion = 1
let g:ycm_semantic_triggers =  {
  \ 'c' : ['re!\w{2}'],
  \ 'cpp' : ['re!\w{2}'],
  \ 'python' : ['re!\w{2}'],
  \ }

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" setup for syntastic
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set statusline+=%#warningmsg#
set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*
let g:syntastic_always_populate_loc_list = 0
let g:syntastic_auto_loc_list = 0
let g:syntastic_check_on_open = 0
let g:syntastic_check_on_wq = 0
let g:syntastic_python_checkers = ['flake8']

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" autoformat
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
augroup autoformat_settings
  autocmd FileType c,cpp,proto,javascript AutoFormatBuffer clang-format
  autocmd FileType python AutoFormatBuffer yapf
augroup END
" use google style for clang-format
Glaive codefmt clang_format_style='google'

" open NERDTree automatically when vim starts up on opening a directory
autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 1 && isdirectory(argv()[0]) && !exists("s:std_in") | exe 'NERDTree' argv()[0] | wincmd p | ene | endif

map <silent> <F5> : NERDTreeToggle<CR>

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" setup for gruvbox
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set t_Co=256
set background=dark
colorscheme gruvbox
" let g:gruvbox_contrast_dark = 'soft'

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" setup for ctrlp
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
let g:ctrlp_map = '<c-p>'
let g:ctrlp_cmd = 'CtrlP'
let g:ctrlp_working_path_mode = 'ra'
let g:ctrlp_custom_ignore = '\v[\/]\.(git|hg|svn)$'
let g:ctrlp_custom_ignore = {
  \ 'dir':  '\v[\/]\.(git|hg|svn)$',
  \ 'file': '\v\.(exe|so|dll)$',
  \ 'link': 'some_bad_symbolic_links',
  \ }
set wildignore+=*/tmp/*,*.so,*.swp,*.zip
let g:ctrlp_user_command = ['.git', 'cd %s && git ls-files -co --exclude-standard']

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" setup for tagbar
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
nmap <F8> :TagbarToggle<CR>

"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" setup for indent line
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
let g:indentLine_char = '│'
set tags=./tags,tags;$HOME
"source ~/cscope_maps.vim
```

### .zsh\_aliases

```bash
#################################################
###############  Files/Movement  ################
#################################################

# Quick clear of terminal
alias c='clear'

# Show hidden files
alias l.='ls -d .* --color=auto'

# Using colorls gem
alias ls='colorls -A'

# Quick Home Directory
alias home='cd ~'

# A quick way to get out of current directory
alias ..='cd ..'
alias ...='cd ../../../'
alias ....='cd ../../../../'
alias .....='cd ../../../../'
alias .4='cd ../../../../'
alias .5='cd ../../../../..'

# Make a folder and cd into it
mkcd() { mkdir -p $1; cd $1 }

# Changes directory and lists directories contents
function cdd() {
    cd $1
    ls
}

# Colorize the grep command output for ease of use (good for log files)
alias grep='grep --color=auto'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'

# Search Through Terminal History
alias hs='history | grep'

# Make mount command output pretty / readable
alias mount='mount |column -t'

# Create a new set of commands
alias path='echo -e ${PATH//:/\\n}'
alias now='date +"%T"'
alias nowtime=now
alias nowdate='date +"%d-%m-%Y"'


#################################################
################    Root User    ################
#################################################

## Tune sudo and su ##
alias root='sudo -i'
alias su='sudo -i'


#################################################
################   System Info   ################
#################################################

## pass options to free ##
alias meminfo='free -m -l -t'

## get top process eating memory
alias psmem='ps auxf | sort -nr -k 4'
alias psmem10='ps auxf | sort -nr -k 4 | head -10'

## get top process eating cpu ##
alias pscpu='ps auxf | sort -nr -k 3'
alias pscpu10='ps auxf | sort -nr -k 3 | head -10'

## Get server cpu info ##
alias cpuinfo='lscpu'

## get GPU ram on desktop / laptop##
alias gpumeminfo='grep -i --color memory /var/log/Xorg.0.log'


#################################################
################    Shortcuts    ################
#################################################

## Prints Shortcuts
function shortcuts() {
    cat ~/.custom_aliases # the file with your aliases
}

## Saves Shortcuts
function saveshortcuts() {
    source ~/.custom_aliases # the file with your aliases
}

## Edit Shortcuts
function editshortcuts() {
    code ~/.custom_aliases # the file with your aliases
}

# edit the selected ZSH config file
function editzsh {
    echo $1
    if [[ "$1" == "a" ]]; then
        code ~/.zsh_aliases
    elif [[ "$1" == "f" ]]; then
        code ~/.zsh_functions
    else
        code ~/.zshrc
    fi
    echo "done"
}


#################################################
################   Ruby/Rails   #################
#################################################

# ----------------------
# Rails Aliases
# ----------------------
alias rg='rails generate'
alias rc='rails console'
alias rs='rails server'
alias rgc='rails generate controller'
alias rgmd='rails generate model'
alias rgm='rails generate migration'
alias rgr='rails generate resource'
alias rgbt='rails g bootstrap:themed'
alias rdbm='rake db:migrate'
alias rdbm0='rake db:migrate VERSION=0'
alias rdbmu='rake db:migrate:up'
alias rdbmd='rake db:migrate:down'
alias rdbr='rake db:rollback'
alias rdbc='rake db:create'
alias rdbp='rake db:drop'
alias rdbs='rake db:seed'
alias rdbhr='pgr && rake db:drop db:create db:migrate db:schema:dump db:setup' # db hard reset
alias rr='rake routes'
alias rrg='rake routes | grep'
alias ber='bundle exec rspec'
alias bi='bundle install'
alias biwp='bundle install --without production'
alias bup='bundle update'
alias bui='bundle update && bundle install' # Bundle update and install, update doesn't touch Gemfile.lock

#-----------------------
# Rails Setup Helpers (make into generators?)
#-----------------------
# Devise Setup (Add a name for the user model at the end)
alias sud='rails generate devise:install && rails generate devise'

# Devise with Bootstrap Setup (Still need to add to application.css)
alias sudbs='rails generate bootstrap:install static && rails g devise:views:locale en && rails g devise:views:bootstrap_templates'

# ----------------------
# RBENV
# ----------------------
alias rbv='rbenv install' # Install a specific Ruby version
alias rbg='rbenv global' # Sets the global version of Ruby to be used in all shells
alias rbh='rbenv rehash' # Run this command after you install a new version of Ruby

# ----------------------
# RVM
# ----------------------
# This is often needed after switching ruby versions.
alias rvmlid='rvm use ruby --latest --install --default' # RVM latest stable ruby install as default
alias bs='gem install bundle && bundle install' # Bundle Setup, adds the bundle gem and updates
alias bsu='gem install bundle && bundle update && bundle install' # Bundle Setup, adds the bundle gem and updates

# ----------------------
# MySQL
# ----------------------
alias msr="sudo /etc/init.d/mysql stop && sudo /etc/init.d/mysql start" # Restart MySQL server

# ----------------------
# Google/StackOverflow Search
# ----------------------
function google() {
    open -na "Google Chrome" --args "https://www.google.com/search?q=$*"
}
function stackoverflow() {
    open -na "Google Chrome" --args "https://www.google.com/search?q=site:stackoverflow.com $*"
}


#################################################
################     Python     ################
#################################################

## Show Current Python Environment
function currentenv() {
    conda env list | grep \* | cut -d ' ' -f 1
}


#################################################
################       C++       ################
#################################################

## Compile C++ Program
function compilecpp() {
    g++ "$1".cpp -o "$1" &&
    ./$1
}


#################################################
################       Git       ################
#################################################
alias gic='git init && git add -A && git commit -m "Initial commit"' # Git initial commit
alias gaa='git add .'  # ... Exclude Deleted
alias gaad='git add -A && git diff --staged' # Stage All and check diffs
alias gan='git add -u' # ... Exclude New
alias gac='git add -A && git commit -m' # Add all and commit
alias gb='git branch'
alias gbd='git branch -d' # Safer Delete
alias gbda='git branch | grep -v "master\|staging\|develop" | xargs git branch -d' # Safer Delete
alias gbD='git branch -D' # Risky Delete
alias gbDa='git branch | grep -v "master\|staging\|develop" | xargs git branch -D' # Risky Delete
alias gbr='git branch -m' # Git Branch Rename
alias gcm='git commit -m'
alias gco='git checkout'
alias gcob='git checkout -b'
alias gcom='git checkout master'
alias gcos='git checkout staging'
alias gcod='git checkout develop' # Checkout development branch
alias gcodev='git checkout development' # Checkout development branch
alias gcl='git clone'
alias gd='git diff'
alias gda='git diff HEAD'
alias gds='git diff --staged'
alias gf='git fetch'
alias gi='git init'
alias gl="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
alias glg='git log --graph --oneline --decorate --all'
alias gld='git log --pretty=format:"%h %ad %s" --date=short --all'
alias gm='git merge --no-ff'
alias gmff='git merge'
alias gp='git pull'
alias gpm='git push' # Push to Github
alias gpom='git push -u origin master' # Push to Github (V2)
alias gphm='git push heroku master' # Push to Heroku
alias gphp='git push heroku-production master' # Push to Heroku (production)
alias gphs='git push heroku-staging staging:master' # Push to Heroku (staging)
alias grbc="git rebase --continue"
alias grbac="git add -A && git rebase --continue"
alias grbrc="git reset && git rebase --continue"
alias grHa="git add -A && git reset --hard HEAD" # Git Reset Hard All, Add all and reset hard to HEAD
alias grhH="git reset --hard HEAD" # Git Reset Hard All, Add all and reset hard to HEAD
alias grs="git reset HEAD" # Git Remove From Staging
alias grs="git reset HEAD" # Git Remove From Staging
alias guc='git reset HEAD^ && gss' # Git Undo Commit; unstage, undo commit, and show status
alias gss='git status -s'
alias gs='git status'
alias gst='git stash'
alias gstl='git stash list'
alias gstp='git stash pop'
alias gstd='git stash drop'
alias gtd='git update-index --assume-unchanged' # Git Track Disable; disable tracking of changes
alias gte='git update-index --no-assume-unchanged' # Git Track Enabled; enable tracking of changes

function gitpush() {
    B=$(git branch | sed -n -e 's/^\* \(.*\)/\1/p')
    git add -A .
    git commit -m $1
    git push -u origin $B
}

function gitrefresh() {
    B=$(git branch | sed -n -e 's/^\* \(.*\)/\1/p')
    git checkout master
    git pull origin master
    git checkout $B
}


#################################################
################     Heroku     #################
#################################################
alias hf="heroku update || heroku help" # Heroku Fix; Fixes most heroku issues
alias huf="wget -qO- https://cli-assets.heroku.com/install-ubuntu.sh | sh" # Heroku Update Force, updates forcefully
alias hai="heroku apps:info" # Get info on current Heroku App
alias hgra="heroku git:remote -a" # Heroku Add Git Remote, adds git remote for app
alias hrm='heroku run --remote heroku-production'
alias hrs='heroku run --remote heroku-staging'
alias hrdm="heroku run rake db:migrate"
alias hrdhr="heroku run 'rake db:drop db:create db:migrate db:schema:dump db:setup'"
alias hrdbm0='rake db:migrate VERSION=0'
alias hl="heroku logs" # Logs
alias hlg="heroku logs -n 10000 | grep" # Logs w/ grep
alias hlt="heroku logs -t"
alias hltg="heroku logs -t -n 10000 | grep" # Logs Tail w/ grep
alias hld="heroku logs -n 10000 > tmp/heroku-logs.log" # Heroku logs dump, dumps heroku logs to tmp file
alias rap="RAILS_ENV=production rake assets:precompile" # Rails assets precompile
alias hpa="rap && gac 'Precompile assets for Heroku' " # Heroku Precompile Assets and Commit


#################################################
################    Learn co    #################
#################################################
alias lrn="learn" # Checks Learn co if assignment is complete with no errors
alias lrns="learn submit" # Submits Learn co assignment

#################################################
################    Personal    #################
#################################################
# Shortcut to save dotfiles to github
# dotfiles add <file being added>
# dotfile commit -m "commit message"
# dotfile push
alias dotfiles="/usr/bin/git --git-dir=$HOME/dotfiles/ --work-tree=$HOME"
alias code="code ."
alias f='fzf'
alias lg='lazygit'  # A simple terminal UI for git commands
alias aliases='code ~/.zsh_aliases'  # opens .zsh_aliases in vscode
alias cheat='cht.sh $1'  # cheat sheet
alias exa='exa --long --header --git'  # a color version of ls -l
alias help='tldr'
alias h='function hdi(){ howdoi $* -c -n 5; }; hdi'

# shows file path
filepath() {
    for f in "$@"; do echo ${f}(:A); done
}

# make manpages look nicer
man () {
    LESS_TERMCAP_mb=$(tput setaf 4)\
    LESS_TERMCAP_md=$(tput setaf 4;tput bold) \
    LESS_TERMCAP_so=$(tput setaf 7;tput setab 4;tput bold) \
    LESS_TERMCAP_us=$(tput setaf 6) \
    LESS_TERMCAP_me=$(tput sgr0) \
    LESS_TERMCAP_se=$(tput sgr0) \
    LESS_TERMCAP_ue=$(tput sgr0) \
    command man "$@"
}
```

### .zshrc

```bash
#
# Tmux
#

if [ -z "$TMUX" ] # When zsh is started attach to current tmux session or create a new one
then
    tmux attach -t TMUX || tmux new -s TMUX
fi

#
# vim
#

export EDITOR="vim"
alias vim="vim"

#
# Oh-my-zsh
#

export ZSH="$HOME/.oh-my-zsh"

SPACESHIP_PROMPT_FIRST_PREFIX_SHOW=true # Show prefix before first line in prompt
ZSH_THEME="spaceship" # Set theme

plugins=(
  # git # https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git
  history-substring-search # ZSH port of Fish history search. Begin typing command, use up arrow to select previous use
  zsh-autosuggestions # Suggests commands based on your history
  zsh-completions # More completions
  zsh-syntax-highlighting # Fish shell like syntax highlighting for Zsh
  colored-man-pages # Self-explanatory
  sudo # adds sudo to front of text by double pressing Esc
  history-substring-search
  )
autoload -U compinit && compinit # reload completions for zsh-completions

source $ZSH/oh-my-zsh.sh # required

source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh # required
[[ -f ~/.bash_aliases ]] && . ~/.bash_aliases

# Colorize autosuggest
export ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=5'

#
# Spaceship-prompt
#

# Spaceship-prompt customization
SPACESHIP_PROMPT_ORDER=(
dir             # Current directory section
user            # Username section
host            # Hostname section
git             # Git section (git_branch + git_status)
time          # Time stampts section
# hg            # Mercurial section (hg_branch  + hg_status)
# package       # Package version
# node          # Node.js section
# ruby          # Ruby section
# elixir        # Elixir section
# xcode         # Xcode section
# swift         # Swift section
# golang        # Go section
# php           # PHP section
# rust          # Rust section
# haskell       # Haskell Stack section
# julia         # Julia section
# docker        # Docker section
# aws           # Amazon Web Services section
# venv          # virtualenv section
# conda         # conda virtualenv section
# pyenv         # Pyenv section
# dotnet        # .NET section
# ember         # Ember.js section
# kubecontext   # Kubectl context section
exec_time       # Execution time
line_sep        # Line break
battery         # Battery level and status
vi_mode         # Vi-mode indicator
jobs            # Background jobs indicator
# exit_code     # Exit code section
char            # Prompt character
)

SPACESHIP_DIR_PREFIX="%{$fg[blue]%}┌─[%b "
SPACESHIP_DIR_SUFFIX="%{$fg[blue]%} ] "
SPACESHIP_CHAR_SYMBOL="%{$fg[blue]%}└─▪%b "

#
# Other
#

# This speeds up pasting w/ autosuggest
# https://github.com/zsh-users/zsh-autosuggestions/issues/238
pasteinit() {
  OLD_SELF_INSERT=${${(s.:.)widgets[self-insert]}[2,3]}
  zle -N self-insert url-quote-magic # I wonder if you'd need `.url-quote-magic`?
}

pastefinish() {
  zle -N self-insert $OLD_SELF_INSERT
}
zstyle :bracketed-paste-magic paste-init pasteinit
zstyle :bracketed-paste-magic paste-finish pastefinish

export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"
export PATH="/Users/jh/.gem/ruby/2.5.0/bin:$PATH"

export PATH="$HOME/bin:$PATH"
## Load Aliases
[[ -f ~/.zsh_aliases ]] && . ~/.zsh_aliases

eval $(thefuck --alias)
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completionsource /usr/local/share/zsh-history-substring-search/zsh-history-substring-search.zsh

# zsh-history-substring-search
bindkey '^[[A' history-substring-search-up
bindkey '^[[B' history-substring-search-down
```

