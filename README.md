### Whenever
---
https://github.com/javan/whenever

```
gem install whenever
gem 'whenever', require: false
cd /apps/my-great-project
wheneverize .

cd /apps/my-great-project
whenever

whenever --update-contab

whenever --user app
whenever --load-file config/my_schedule.rb
whenever --crontab-command 'sudo crontab'
```

```ruby
every 3.hours do
  runner "MyModel.some_process"
  rake "my:rake:task"
  command "/usr/bin/my_great_command"
end
every 1.day, at: '4:30 am' do
  runner "MyModel.task_to_run_at_four_thirty_in_the_morning"
end
every 1.day, at: ['4:30 am', '6:00 pm'] do
  runner "Mymodel.task_to_run_in_two_times_every_day"
end
every :hour do
  runner "SomeModel.labeeda"
end
every :sunday, at: '12pm' do
  runner "Task.do_something_great"
end
every '0 0 27-31 * *' do
  command "echo 'you can use raw cron syntax too'"
end
every :day, at: '12:20am', roles: [:app] do
  rake "app_server:task"
end

job_type :awesome, '/usr/local/bin/awesome :task :fun_level'
every 2.hours do
  awesome "party", fun_level: "extreme"
end

job_type :command, ":task :output"
job_type :rake, "cd :path && :environment_variable=environment bundle exec rake :task --silent :output"
job_type :runner, "cd :path && bin/rails runner -e :environment ':task' :output"
job_type :script, "cd :path && :environment_variable=:environment bundle exec script/:task :output"

set :job_template, "bash -l -c ':job'"
set :job_template, nil

set :chronic_options, hour24: true
every 1.day, at: '3:00' do
  runner "MyModel.nightly_archive_job"
end

env 'MAIOTO', 'output_of_cron@example.com'
every 3.hours do
  command "/usr/bin/my_great_command"
end

every 3.hours, mailto: 'my_super_command@example.com' do
  command "/usr/bin/my_super_command"
end

every 3.hours do
  command "/usr/bin/my_super_command", mailto: 'my_super_command_output@example.com'
end

require "whenever/capistrano"

set :whenever_command, "bundle exec whenever"
require "whenever/capistrano"

set :whenever_environment, defer { stage }
require "whenever/capistrano"

set :whenever_environment, defer { stage }
set :whenever_identifier, defer { "#{applicaton_#{stage}}" }
require "whenever/capistrano"

set :whenever_load_file, defer { "#{release_path}/somewhere/else/schedule.rb" }
require "whenever/capistrano"

require "whenever/capistrano"
set :whenever_identifier, ->{ "#{fetch(:application)}_#{fetch(:stage)}" }

every :day, at: '12:20am' do
  rake 'foo:bar'
end

every :day, at: '1:37pm', roles: [:app] do
  rake 'app:task'
end
every :hour, roles: [:db] do
  rake 'db:task'
end
every :day, at: '12:02am' do
  command "run_this_everywhere"
end

```



```
```
