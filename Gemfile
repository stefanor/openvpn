# encoding: UTF-8
# -*- mode: ruby -*-
# vi: set ft=ruby :

source 'https://rubygems.org'

chef_version = ENV.key?('CHEF_VERSION') ? ENV['CHEF_VERSION'] : nil

group :test do
  gem 'rake'
  gem 'rspec',      '~> 3.0'
  gem 'berkshelf',  '~> 3.2'
  gem 'codeclimate-test-reporter', group: :test, require: nil
end

group :style do
  gem 'foodcritic', '~> 4.0'
  gem 'rubocop',    '~> 0.30'
end

group :unit do
  gem 'chef', chef_version unless chef_version.nil? # Ruby 1.9.3 support
  gem 'chefspec',   '~> 4.2'
end

group :integration do
  gem 'vagrant-wrapper', '~> 2.0'
  gem 'test-kitchen',    '~> 1.4'
  gem 'kitchen-vagrant', '~> 0.17'
end

group :integration, :integration_cloud do
  gem 'kitchen-ec2',          '~> 0.8'
  gem 'kitchen-digitalocean', '~> 0.8'
  gem 'serverspec',           '~> 2.0'
end
