# vim-studio-code
Vim configuration to make Vim look/feel like Visual Studio Code

*Work in Progress*

The following is a guide in setting up your vim configuration to have it look and feel like you’re working from Visual Studio Code (see GIF below). Of course there are some differences but the hope of this demo is at the very least to show the power that Vim holds. It can be more than just a text editor with the right plugins.  My Vim configuration was originally a copy and paste from [this blog post.](https://dev.to/allanmacgregor/vim-is-the-perfect-ide-e80) What I have here is almost the same, with a few modifications. 

One modification is the additions of the web-devicons plugin, which provides the nice icons for the file explorer plugin, NERDTree. These icons rely on a special a special font-set called [Nerd Fonts,](https://github.com/ryanoasis/nerd-fonts) 

In this README, I also hope to provide a reasonable guide for getting these to work properly for WSL. These instructions may also be helpful if you are connecting to your Linux machine through a terminal emulator such MobaXterm or PuTTY. The key is to set the font in the terminal emulator and not on the Linux machine, though you should do this as well if you ever plan to connect directly to the box, and still want the icons to work.

# Quickstart
Clone this repository then run the setup script

```bash
git clone https://github.com/ludah65/vim-studio-code.git
cd vim-studio-code
./setup
```

Now open Vim and run <code>:PlugInstall</code>. Close Vim and re-open it! And voila:


Icons showing up as question marks? See WSL Setup section below.

## Summary of Important Keybindings
The keybindings for Vim are configured in the .vimrc under the Keybinding section. You can change this to your liking if your are familiar with Vim keybindings. If not, they are fairly easy to look up on google. I’ve tried to set up the key bindings such that they are somewhat intuitive.

**Note**:  a split in Vim might be what you think of as a window in VS Code. 

| Binding | Description |
| ------- | ----------- |
| CTRL + T | Opens a terminal window below all splits. None of the other keybindings work when you are working in the terminal. To move out of the terminal to another split, use CTRL + W + W. To close the terminal window, you can type exit on the command line while working in the terminal split in Vim.|
|CTRL + W + W | Move between splits sequentially in clockwise manner. Also use this to move off terminal split |
| CTRL + N | Toggle NERDTree (the file tree) on and off. | 
| CTRL + W | Activate window context: after hitting CTRL + W you can use the arrow keys to move between splits. |
| CTRL + (arrow key)| Resize current split in direction specified by arrow key. |
| i | When using the NERDTree file tree you can open files into a new horizontal split using ‘i’ |
| s | When using the NERDTree file tree you can open files into a new vertical split using ‘s’ |

**Note**: Mouse clicking is also enabled to allow you to switch between splits, as well as open files and directories in NERDTree. This can potentially cause issues with copying text out of Vim. If you’d like to disable this features
you can do so by removing the following line from the .vimrc

<code>set mouse=a</code>

**Note**: NERDTree is turned on by default when opening vim. This can be changed by removing or commenting (“) out the following line:

```vimscript
“start NERDTree automatically”
autocmd VimEnter * NERDTree
```

Then you can toggle it on and off using CTRL + N

# WSL Setup Enable web-devicons Plugin

If you do not perform this step and are connecting through a terminal emulator, the icons will probably show up as question marks. This is because the devicons plugin was meant to work with a Nerd Font.

The following assumes you are using WSL2 with Ubuntu 20.04 LTS as your distro. The first step is to install [windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701#activetab=pivot:overviewtab)

Once this is installed you may want to make Ubuntu your default upon opening Terminal:

Next you should run the ps1 script included in this repository and taken from [here](https://github.com/ryanoasis/nerd-fonts/issues/223#issuecomment-563141110)

This will install some Nerd Fonts and make them available. If you do not want to have to run this script every time you restart your computer, you should follow the steps in “Setting a Windows Profile for Nerd Fonts” in the following section. 

...

# Setting a Windows Profile for Nerd Fonts 
Here we will set the profile for All users. This requires that you be able to open PowerShell IDE as an administrator. 

...

# Adding Powerline to Shell
You may have noticed that my terminal has a fancy powerline. I am currently using this [powerline Go-lang app](https://github.com/justjanne/powerline-go)

An alternative is to use [this Python based option](https://medium.com/earlybyte/powerline-for-bash-6d3dd004f6fc)

<code>pip3 install powerline-gitstatus</code>

You will need to follow the instructions in either to set up a powerline for your shell.

# Some Other Cool Vim Plugins you Might Want to Add
* [Vimpyter](https://github.com/szymonmaszke/vimpyter)
* [vim-dadbod](https://github.com/tpope/vim-dadbod)
