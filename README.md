# My IO page with GitHub and Jekyll

Never hurts to start with docs.

## Initial Setup

- [Following the links from this page](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)

  - [Installing Jekyll](https://jekyllrb.com/docs/installation/other-linux/)

```bash
sudo pacman -S ruby base-devel

# commit echoes to dotfiles (done)
echo '# Install Ruby Gems to ~/gems' >> ~/.zshrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.zshrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.zshrc

s # my alias for source ~/.zshrc, defined in ~/.zsh_aliases

gem install jekyll bundler # This takes forever...
```

- I ended up needing to replace the last two lines with this for Arch, [based on this](https://wiki.archlinux.org/title/Ruby#RubyGems) and [this](https://www.reddit.com/r/archlinux/comments/ainrya/arch_jekyll_installation_problems/)

```bash
export GEM_HOME="$(ruby -e 'puts Gem.user_dir')"
export PATH="$PATH:$GEM_HOME/bin"
```

- 28 gems installed!

- I could create the site in a separate folder, or on a special branch, but it is the essence of this repo so I'll do it right here

  - Hmm, it doesn't seem to like the presence of this README, guess I'll stick it in `/docs`

## Goals

- I'd like to be able to post my thoughts about various resources and concepts

  - Some initial candidates I'd like to write about:

    - <https://www.kevinslin.com/notes/3dd58f62-fee5-4f93-b9f1-b0f0f59a9b64.html>

    - <https://fortelabs.co/blog/para/>

    - <https://martinfowler.com/articles/on-pair-programming.html>

- I'd like to improve the web experience of reading my documentation for other projects

  - this seems to be possible by setting up Jekyll in a `/docs` folder in a project

```bash
mkdir docs
cd docs
jekyll new .
```
