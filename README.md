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

```

```
```

```
```
