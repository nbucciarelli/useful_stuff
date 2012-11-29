# DOM Monster
Analyzes DOM and points out issues
http://mir.aculo.us/dom-monster/

# Hey Offline
Notifies users when they go offline
http://oskarkrawczyk.github.com/heyoffline.js/

# Rails Quiet Assets
Tells asset pipeline to shut the eff up

    gem 'quiet_assets', group: :development

# Rack Mini Profiler
Keeps track of your SQL queries' time spent, n+1 queries, etc

    gem 'rack-mini-profiler', group: :development

# Keep Dyno Alive (rake task)
Run on 1 Heroku dyno and keep it spooled up for your Rails app.
This version is for SSL:

    namespace :app do
      task :call_page => :environment do
        require 'net/http'
        url = URI.parse(URI.encode("#{YOUR_APP_URI}"))
        response = Net::HTTP.start(url.host, use_ssl: true, verify_mode: OpenSSL::SSL::VERIFY_NONE) do |http|
           http.get url.request_uri
        end
      end
    end

Have this task run every 10 minutes or so with Heroku Scheduler:

    $ rake app:call_page

# Rails 4 Upgrade
Helps you with deprecations and dependencies in preparation of Rails 4
https://github.com/alindeman/rails4_upgrade

    gem 'rails4_upgrade', github: 'alindeman/rails4_upgrade'