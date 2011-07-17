require 'rake'
require 'rubygems'
require 'bundler'

begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "acts_as_follower"
  gem.homepage = "https://github.com/sid137/acts_as_follower"
  gem.license = "MIT"
  gem.summary = %Q{one-line summary of your gem}
  gem.description = %Q{longer description of your gem}
  gem.email = "email@address.com"
  gem.authors = ["uthor Name"]
  # Include your dependencies below. Runtime dependencies are required when using your gem,
  # and development dependencies are only needed for development (ie running rake tasks, tests, etc)
  #  gem.add_runtime_dependency 'jabber4r', '> 0.1'
  #  gem.add_development_dependency 'rspec', '> 1.2.3'
end
Jeweler::RubygemsDotOrgTasks.new



require 'rcov/rcovtask'
namespace :rcov do
  desc "Generate a coverage report in coverage/"
  task :gen do
    sh "rcov --output coverage test/*_test.rb --exclude 'gems/*'"
  end

  desc "Remove generated coverage files."
  task :clobber do
    sh "rm -rdf coverage"
  end
end


desc 'Default: run unit tests.'
task :default => :test

require 'rake/testtask'
desc 'Test the acts_as_taggable_on_steroids plugin.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end

require 'rake/rdoctask'
desc 'Generate documentation for the acts_as_taggable_on_steroids plugin.'
Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'Acts As Follower'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

