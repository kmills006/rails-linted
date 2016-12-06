# Rails Linted
This is an example Rails project set up with [RuboCop](https://github.com/bbatsov/rubocop) and Travis CI

## Instructions

1. Create new rails project
  ```
  cd ~/code
  mkdir my-awesome-rails-project
  cd my-awesome-rails-project
  rails new .
  ```

2. Add Git remote and push initial commit
  ```
  git init
  git remote add origin [git remote url]
  git add .
  git commit -m "Initial Commit"
  git push origin master
  ```

3. Add RuboCop to Gemfile development group
  ```
    # Code analyzer to enforce community style guide
    gem 'rubocop', require: false
  ```

4. Create `.travis.yml`
  ```
  rvm:
    - 2.3.0
  install:
    - bundle install --retry=3
  script:
    - bundle exec rspec spec/
    - rubocop
  ```

## Commands

* RuboCop: `rubocop`
* Test Suite: `bundle exec rspec spec/`
