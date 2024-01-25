# my dotfiles, using gnome and dwm
## whats inside?
My wallpapers, scripts, css file for improved workspace indicator (gnome), "plymouth wait for animation" file (only copied to documents), grub config (only copied to documents), Nautilus Templates, zsh settings and starship config
## how to restore
<ul>
<li>
  add alias =====> dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" 
</li>
<li>
  echo ".dotfiles" >> .gitignore   
</li>
<li>
  git clone --recursive --bare https://github.com/glubbfreund/dotfiles $HOME/.dotfiles
</li>
<li>
  dotfiles config --local status.showUntrackedFiles no
</li>
<li>
  mkdir -p .dotfiles-backup && \
  dotfiles checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
  xargs -I{} mv {} .dotfiles-backup/{}
</li>
<li>
  dotfiles checkout
</li>
<li>
  load the submodules:
  git submodule init 
  git submodule update
</li>
</ul>
