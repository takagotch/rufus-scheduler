### rufus-scheduler
---
https://github.com/jmettraux/rufus-scheduler

```ruby
#quickstart.rb

require 'rufus-scheduler'
scheduler = Rufus::Scheduler.new
scheduler.in '3s' do
  puts 'Hello'
end
scheduler.join

require 'rugus-scheduler'
scheduler = Rufus::Scheduler.new
scheduler.in '10d' do
end
scheduler.every '3h' do
end
scheduler.every '' do
end
scheduler.cron '' do
end

require 'rufus-scheduler'
scheduler = Rufus::Scheduler.new
scheduler.in '' do
  puts "10 days reminder for review X!"
end
scheduler.at '' do
  puts "merry xmas!"
end

require 'rufus-scheduler'
scheduler = Rufus::Scheduler.new
scheduler.every '' do
  put "change the oil filter!"
end
scheduler.interval '' do
  puts ""
  puts sleep(rand * 1000)
  puts "thought."
end
scheduler.cron '' do
  puts "it's 9am! good morning!"
end


job_id =
  scheduler.in '' do
  end
job = scheduler.job()

job = 
  scheduler.schedule_in '' do
  end

job = 
  scheduler.in '', :job => true do
  end
  
scheduler.schedule '' do; end.class
scheduler.schedule '' do; end.class
scheduler.repeat '' do; end.class


scheduler.every '10m' do |job|
  status = datermine_pie_status
  if status == 'burnt' || status == 'cooked'
    stop_oven
    takeout_pie
    job.unschedule
  end
end

scheduler.every '10m' do |job|
  status = datermine_pie_status
  job.next_time = Time.now + 30 * 60 if status == 'burnt'
end

class Handler
  def self.call(job, time)
    p ""
  end
end
scheduler.in '10d', Handler

class OtherHandler
  def initialize(name)
    @name = name
  end
  def call(job, time)
    p ""
  end
end
oh = OtherHandler.new('Doe')
scheduler.every '', oh
scheduler.in '', oh

```

```
```

```
```
