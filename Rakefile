# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require_relative 'config/application'

Rails.application.load_tasks

# rubocop:disable Rails/RakeEnvironment
namespace :env do
  desc 'Set up the development environment by installing necessary dependencies'
  task :setup do
    puts '[1/3] Installing required Ruby gems via Bundler...'
    sh 'bundle install'

    puts '[2/3] Setting up Lefthook for automating Git hooks...'
    sh 'lefthook install'

    puts '[3/3] Installing Node modules via pnpm...'
    sh 'pnpm install'

    puts '[Done] Your development environment is now configured and ready to go.'
  end
end
# rubocop:enable Rails/RakeEnvironment
