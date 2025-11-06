# Site build instructions

1. Install prerequisites:
  * Install ruby:
```bash
brew install ruby
```
  * Update ruby paths
```bash
# echo 'export PATH="/usr/local/lib/ruby/gems/3.4.0/bin:$PATH"' >> ~/.zshrc
echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```
    - Check version for computer with `gem env`.
    - For Apple silicon, homebrew is in /opt/homebrew/. Do `echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc` instead.
  - Then install jekyll
```bash
gem install bundler jekyll
```
2. Clone repository
3. Install dependencies:
```bash
cd  andrewbrettin.github.io
bundle install
```
4. Local build
```
bundle exec jekyll serve
```
Open browser at [http://localhost:4000](http://localhost:4000) or whatevver the given server address is.