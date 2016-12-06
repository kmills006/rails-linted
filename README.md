[![Build Status](https://travis-ci.org/kmills006/rails-linted.svg?branch=master)](https://travis-ci.org/kmills006/rails-linted)

# Rails Linted
This is an example Rails project set up with [RuboCop](https://github.com/bbatsov/rubocop), [rspec-rails](http://rspec.info/) and [Travis CI](https://travis-ci.org/).

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

4. Add rspec to Gemfile development and test group
  ```
  # rspec testing framework
  gem 'rspec-rails', '~> 3.5'
  ```

5. Initialize the spec/ directory
  ```
  rails generate rspec:install
  ```

6. Create `.travis.yml`
  ```
  rvm:
    - 2.3.0
  install:
    - bundle install --retry=3
  script:
    - bundle exec rspec spec/
    - rubocop
  ```

7. Enable your repo in Travis CI settings (Note if adding to a private repo, use [https://travis-ci.com/](https://travis-ci.com/))

## Commands

* RuboCop: `rubocop`
* Test Suite: `bundle exec rspec spec/`
