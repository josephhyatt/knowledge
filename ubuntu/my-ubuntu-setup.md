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

