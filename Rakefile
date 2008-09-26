# -*- ruby -*-

require 'rubygems'
require 'hoe'
require './lib/taza'
require 'spec/rake/spectask'

Hoe.new('taza', Taza::VERSION) do |p|
  p.rubyforge_name = 'taza' # if different than lowercase project name
  p.developer('Charley Baker', 'charley.baker@gmail.com')
end

Spec::Rake::SpecTask.new do |t|
  t.spec_files = FileList['spec/**/*_spec.rb']
end 

desc "Run all examples with RCov"
Spec::Rake::SpecTask.new('rcov') do |t|
  t.spec_files = FileList['spec/**/*_spec.rb']
  #puts t.methods
  t.rcov = true
  t.rcov_dir = 'artifacts'
  t.rcov_opts = ['--exclude', 'spec']
 
end

desc "Run all examples with Flog"
Spec::Rake::SpecTask.new('flog') do |t|
  t.spec_files = FileList['spec/**/*_spec.rb']
  t.name = "flog"
end

namespace :gem do
  desc "install a gem into vendor/gems"
  task :install do
    if ENV["name"].nil?
      STDERR.puts "Usage: rake gem:install name=the_gem_name"; exit 1
    end
  system "gem.bat install #{ENV['name']} --install-dir=vendor/gems  --no-rdoc --no-ri -p ""http://10.8.77.100:8080"""
  end
end


#define a task which uses flog
# vim: syntax=Ruby
