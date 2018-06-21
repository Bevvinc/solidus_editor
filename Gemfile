source "https://rubygems.org"

git_source(:github) do |repo_name|
  repo_name = "#{repo_name}/#{repo_name}" unless repo_name.include?('/')
  "https://github.com/#{repo_name}.git"
end

branch = ENV.fetch('SOLIDUS_BRANCH', 'master')
gem "solidus", github: "solidusio/solidus", branch: branch

if branch == 'master' || branch >= "v2.0"
  gem "rails-controller-testing", group: :test
else
  gem "rails_test_params_backport"
  gem "rails", "~> 4.2.7"
end

gem 'pg', '~> 0.21'
gem 'mysql2', '~> 0.4.10'
gem 'ckeditor', github: 'galetahub/ckeditor'

group :development, :test do
  gem "pry-rails"
end

gemspec
