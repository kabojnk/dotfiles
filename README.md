# My Dot Files for OS X

![screenshot](https://cloud.githubusercontent.com/assets/296099/12076078/65927d6a-b150-11e5-95a2-1a7c69d31b62.png)

This is like heavily [and manually] forked from [Chris Hunt's dot files project](https://github.com/chrishunt/dot-files).  There are some slight changes in mine, and some things that I wante to note that weren't explicit in other instructions. I don't expect anyone to really use these, but I figured I'd flesh out a longer README to give some information to anyone diving into updating or redoing his/her dot files after a number of years years.

## Should you be using this?

Like I said, probably not. But if you're lazy, feel free to use it. If you're technical-minded, I'd suggest forking from [Chris Hunt's dot files project](https://github.com/chrishunt/dot-files) instead like I did.

## This is for a zsh shell

Likewise, it uses [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh/) for themes and all sorts of goodness. If you're familiar with bash, your commands will work just fine in zsh. Zsh is like bash on steroids.

## After cloning, but before installing/running, do the following:

### Pre-req software to install (step 1 of 2)

This depends on some software to really work well.

#### 1. homebrew

If you haven't already, you will need to [install homebrew](http://brew.sh/). Lets you install all sorts of nice *nixy stuff on OS X, including tmux.

#### 2. tmux and reattach-to-user-namespace

If you don't know/care what tmux is, feel free to skip this step. For more info on how to use tmux, [go here](http://code.tutsplus.com/tutorials/intro-to-tmux--net-33889).

`brew install tmux && brew install reattach-to-user-namespace`

Keep in mind that **if** you _do_ install `tmux`, **you also need to install `reattach-to-user-namespace` for `tmux` to work on OS X!**

**By the way, your `^b` prefix shortcut for tmux is now `^j`**

#### 3. tpm (tmux plugin manager)

Command to do this: `^j + I` (that is a capital I, not lowercase; also assumes you kept your prefix to `^j`).

This will download and install all of the `tpm` plugins that were listed to be autolaoded in `.tmux.cfg`. The installed plugins will go into `~/.tmux/plugins`. If you choose not to install the plugins, it will should not break anything. I only use it with the [maglev](https://github.com/caiogondim/maglev) tmux theme.

#### 4. Patched Fonts from Powerline (optional, but recommended)

This is if you want to use some of the fancy zsh themes (like [bullet-train](https://github.com/caiogondim/bullet-train-oh-my-zsh-theme) and tmux themes (like [maglev](https://github.com/caiogondim/maglev)) that have neato font thingies, like special icons.

Go ahead and clone this project temporarily and install with the following command.

`git clone https://github.com/powerline/fonts.git && cd fonts && ./install.sh`

Feel free to delete the cloned directory after you're done.

#### 5. iTerm (optional)

I like this better than Terminal.app, but it's not a deal-breaker.

### 6. Files to Edit (step 2 of 2)

Here are some files to edit before doing anything

#### 7. .gitignore

Everyone's home directory is different. My .gitignore is pretty useless on another machine.  I decided to alter it on my own (I technically started my own repo and added the dot files and submodules in after the fact, but I don't recommend that). It's easier just to do an `ls` of your `~` directory and paste in all of the stuff there, and then erase the files you _do_ want committed.

#### 8. .gitconfig

These should be changed. You'd want your own config options in here (like your git credentials, github username, etc).

#### 9. .zshrc

You will probably want to specify your own zsh theme, and if you're not a fan of `tmux` you can swap it out for `screen` here. If you're not using `boxen`, remove this line from the file, too, if you don't want a warning message to pop up every time you start a new session: `source /opt/boxen/env.sh`


## Now you can run your stuff

As this is forked from [Chris Hunt's dot files project](https://github.com/chrishunt/dot-files), I opted to also leave in his install/update scripts. They can be found in `scripts` and you can see his github project for more info. The basics are: `scripts/install.sh` to install and init all of the git submodules, and `scripts/update.sh` to update everything (which would theoretically be from this repo, and I don't really promise that I will be updating this religiously or at all, so be aware of that).

Provided that this is in your `~` directory somehow, the easiest way to go about this is either in Terminal.app or iTerm2, go to your preferences and find a field for `command` and type in `zsh`.

Bonus: If you have `tmux` installed, it will automatically re-attach to an existing session, or create a new session if an existing one isn't found.

## tmux special notes

I sort of mentioned above, but the usual `^b` binding for tmux is now `^j`, mainly because that's the way Chris has it in his stuff. I actually kind of like the new binding.
