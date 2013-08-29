## New Relic Sidekiq Plugin

Monitors Sidekiq, a library for processing background jobs, reporting the following data for multiple specified instances:

  - Number of working workers
  - Pending jobs number
  - Total failed jobs number
  - Number of workers
  - Number of processed jobs
  - Queues and the enqueued count

### Requirements

In order to use this plugin, you must have an active New Relic account.

Plugin should work on any generic Unix environment with the following
software components installed:

  - Ruby (>= 1.8.7)
  - bundler for Ruby: https://github.com/carlhuda/bundler
  - Sidekiq


### Instructions for running the Sidekiq plugin agent

1. run `bundle install` to install required gems
2. Copy `config/newrelic_plugin.yml.example` to `config/newrelic_plugin.yml`
3. Edit `config/newrelic_plugin.yml` and replace "YOUR_LICENSE_KEY_HERE" with your New Relic license key
4. Edit the `config/newrelic_plugin.yml` file and add Redis connection string
5. Running the plugin

In order to check your configuration, you can launch the plugin
in foreground mode, with all output going to stdout:

  ./newrelic_sidekiq_agent

Carefully check plugin's output for any possible error messages.
In case of success, collected data should appear in the New Relic
user interface shortly after starting.

Plugin can also be started as a daemon using the following command:

  ./newrelic_sidekiq_agent.daemon start

In this case you can check its status by running

  ./newrelic_sidekiq_agent.daemon status

and stop it with

  ./newrelic_sidekiq_agent.daemon stop

