# thomshutt.github.io

## Running the site locally

This site is built with [Jekyll](https://jekyllrb.com/) and uses Bundler to manage Ruby gems.

### Prerequisites

- Homebrew
- [rbenv](https://github.com/rbenv/rbenv)
- Ruby 3.3.x (to match the GitHub Pages workflow)

### Recommended setup (rbenv)

Install `rbenv` and `ruby-build`:

```bash
brew update
brew install rbenv ruby-build
```

Initialize `rbenv` in `~/.zshrc`:

```bash
echo 'eval "$(rbenv init - zsh)"' >> ~/.zshrc
source ~/.zshrc
```

Install and select Ruby 3.3:

```bash
rbenv install 3.3.0
rbenv local 3.3.0
ruby -v
```

Install Bundler under the `rbenv` Ruby:

```bash
gem install bundler
rbenv rehash
bundle -v
```

### Install dependencies

From the project root:

```bash
bundle config set --local path 'vendor/bundle'
bundle install
```

### Serve the site locally

Run Jekyll via Bundler:

```bash
bundle exec jekyll serve
```

Then open:

```text
http://127.0.0.1:4000/
```

Jekyll watches for changes to posts, pages, styles, and talks files and reloads automatically.

### Troubleshooting

If you see:

```text
Gem::FilePermissionError: You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory
```

you are still on macOS system Ruby. Move to the `rbenv` setup above, then verify:

```bash
which ruby
ruby -v
which bundle
```

`which ruby` should point to your `~/.rbenv/shims/ruby`, not `/usr/bin/ruby`.

If you see:

```text
bundler requires Ruby version >= 3.2.0 ... current ruby version is 2.6.x
```

your shell is still using system Ruby. Run:

```bash
rbenv local 3.3.0
exec zsh
ruby -v
bundle -v
```

