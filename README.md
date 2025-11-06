# Site build instructions

1. Install prerequisites:
  * Install ruby:
```bash
brew install ruby
```
  * Update ruby paths
```bash
echo 'export PATH="/usr/local/lib/ruby/gems/3.0.0/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```
  Check version for computer with `gem env`.
  - Then install jekyll
```bash
gem install bundler jekyll
```

1. Clone repository
2. Install dependencies:
```bash
cd  andrewbrettin.github.io
bundle install
```
1. Local build
```
bundle exec jekyll serve
```
Open browser at [http://localhost:4000](http://localhost:4000) or whatevver the given server address is.