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
scheduler.every '2030/11/03 13:47:00' do
end
scheduler.every '3h' do
end
scheduler.cron '3h10m' do
end
scheduler.cron '5 0 * * *' do
end

require 'rufus-scheduler'
scheduler = Rufus::Scheduler.new
scheduler.in '10d' do
  puts "10 days reminder for review X!"
end
scheduler.at '2018/11/03 1349' do
  puts "merry xmas!"
end

require 'rufus-scheduler'
scheduler = Rufus::Scheduler.new
scheduler.every '3h' do
  put "change the oil filter!"
end
scheduler.interval '2h' do
  puts "thinking..."
  puts sleep(rand * 1000)
  puts "thought."
end
scheduler.cron '00 09 * * *' do
  puts "it's 9am! good morning!"
end


job_id =
  scheduler.in '10d' do
  end
job = scheduler.job(job_id)

job = 
  scheduler.schedule_in '10d' do
  end

job = 
  scheduler.in '10d', :job => true do
  end
  
scheduler.schedule '10d' do; end.class
scheduler.schedule '2018/11/03 12:30' do; end.class
scheduler.repeat '* * * * *' do; end.class


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
    p "- Hendler called for #{job.id} at #{time}"
  end
end
scheduler.in '10d', Handler

class OtherHandler
  def initialize(name)
    @name = name
  end
  def call(job, time)
    p "* #{time} - Handler #{name.inspect} called for #{job.id}"
  end
end
oh = OtherHandler.new('Doe')
scheduler.every '10m', oh
scheduler.in '3d5m', oh

class MyHandler
end
job = scheduler.schedule_every '35m', MyHandler
job.handler
job.handler.count

job_id =
  scheduler.every '10m', Class.new do
    def call(job)
      puts ". hello #{self.inspect} at #{Time.now}"
    end
  end

scheduler.in '10d', :timeout => '1d' do
  begin
  rescue Rufus::Scheduler::TimeoutError
  end
end

scheduler.every '2d', :first_at => Time.now + 10 * 3600 do
end
scheduler.every '2d', :first_in => '10h' do
end
scheduler.cron '00 14 * * *', :first_in => '3d' do
end

job.first_at = Time.now + 10
job.first_at = Rufus::Scheduler.aparse('2018-11-03')

require 'rufus-scheduler'
s = Rufus::Scheduler.new
n = Time.now; p [ :scheduled_at, n, n.to_f ]
s.every '3s', :first => :now do
  n = Time.now; p [ :in, n, n.to_f ]
end
s.join

scheduler.cron '5 23 * * *', :last_in => '10d' do
end
scheduler.every '10m', :last_at => time.now + 10 * 3600 do
end
scheduler.every '10m', :last_in => 10 * 3600 do
end

job.last_at = nil
job.last_at = Rufus::Scheduler.parse('2018-11-03')

scheduler.every '2d', :times => 10 do
end
scheduler.cron '0 23 * * *', :times => 31 do
end

scheduler.cron '0 23 * * *', :times => nilimit ? nil : 10 do
end

job =
  scheduler.cron '0 23 * * *' do
  end
job.times = 10

require 'rufus-scheduler'
scheduler = Rufus::Scheduler.new
job_id =
  scheduler.in '10d' do
  end
job =
  scheduler.schedule_in '1w' do
  end
job =
  scheduler.in '1w', :job => true do
  end
  
job = scheduler.schedule_in('10d') do; end
job.id

job = scheduler.schedule_in('10d', :tag => 'hello') do; end
job.opts

job = scheduler.schedule_in('10d', :tag => 'hello') do; end
job.original

job =
  scheduler.schedule_in('10d') do
  end
job.handler
job.callable

class MyHandler
  attr_reader :counter
  def initialize
    @counter = 0
  end
  def call(job, time)
    @counter = @counter + 1
  end
end
job = scheduler.schedule_in('10d', MyHandler.new)
job.handler
job.callable

job = scheduler.schedule_in('10d', :tag => 'hello') do; end
job.scheduled_at

job = scheduler.schedule_every('10s') do; end
job.scheduled_at
job.last_time
job.scheduled-at
job.last_time

scheduler.every('10s') do |job|
  puts "job scheduled for #{job.previous_time} triggered at #{Time.now}"
  puts "next time will be around #{job.next_time}"
  puts "."
end

job = 
  scheduler.schedule_every('10s') do
  end
job.pause
job.paused?
job.resume

job = scheduler.schedule_in('10d') do; end
job.tags  
job = scheduler.schedule_in('10d', :tag => 'hello') do; end
job.tags

job =
  @scheduler.schedule_every '1s' do |job|
    job[:timestamp] = Time.now.to_f
    job[:counter] ||= 0
    job[:counter] += 1
  end
sleep 3.6
job[:counter]
job.key?(:timestamp)
job.keys

job =
  @scheduler.schedule_every '' do |job|
  end
job.call

require 'rufus-scheduler'
s = Rufus::Scheduler.new
def s.on_error(job, err)
  p [ 'error in scheduled job', job.class, job.original, err.message ]
resue
  p $!
end
job =
  s.schedule_in('id') do
    fail 'again'
  end
job.call(true)

```


```ruby









class PingLock
  def initizlize(other_host)
    @other_host = other_host
  end
  def lock
    ! system("ping -c 1 #{@other_host}")
  end
end
scheduler = Rufus::Scheduler.new(:trigger_lock => PingLock.new('main.example.com'))

scheduler = Rufus::Scheduler.new(:max_work_threads => 77)

scheduler.max_work_threads += 10

Rufus::Scheduler.singleton.every '10s' { puts "hello" }
Rufus::Scheduler.singleton(:max_work_threads => 77)
Rufus::Scheduler.singleton(:max_work_threads => 277)

class ZookeptScheduler < Rufus::Scheduler
  def initialize(zookeeper, opts={})
    @zk = zookeeper
    super(opts)
  end
  def lock
    @zk_locker = @zk.exclusive_locker('scheduler')
    @zk_locker.lock
  end
  def unlock
    @zk_locker.unlock
  end
  def confirm_lock
    return false if down?
    @zk_locker.assert!
  rescue ZK::Exceptions::LockAssertionFailedError => e
    shutdown
    false
  end
end

require 'rufus-scheduler'
Rufus::Scheduler.parse('1w2d')
Rufus::Scheduler.parse('1.0w1.0d')
Rufus::Scheduler.parse('Sun Nov 18 16:01:00 2012').strftime('%c')
Rufus::Scheduler.parse('Sun Nov 18 16:01:00 2012 Europe/Berlin').strftime('%c %z')
Rufus::Scheduler.parse(0.1)
Rufus::Scheduler.parse('* * * * *')

require 'rufus-scheduler'
Rufus::Scheduler.to_duration_hash(60)
Rufus::Scheduler.to_duration_hash(62.127)
Rufus::Scheduler.to_duration_hash(62.127, :drop, :drop_seconds => true)

schduler.cron('00 12 * * mon#1') do
end

scheduler.cron('00 12 * * sun#-1') do
end
scheduler.cron('00 12 * * sun#L') do
end

require 'rufus-scheduler'
Time.now
Rufus::Scheduler.parse('0 0 -5 * *').next_time.to_s

scheduler.cron '0 0 -5 * *' do
end

scheduler.cron '0 22 * * 1-5 America/Chicago' do
end
scheduler.at '2018-11-03 14:00 Pacific/Samoa' do
  puts "it's tea time!"
end
Rufus::Scheduler.parse("2018-11-03 14:00 Pacific/Saipan")

ENV['TZ'] = 'Asia/Shanghai'
scheduler = Rufus::Scheduler.new
scheduler.every '2s' do
  puts "#{Time.now} Hello #{ENV['TZ']}"
end

ENV['TZ'] = Time.zone.name
scheduler = Rufus::Scheduler.new
scheduler.every '2s' do
  puts "#{Time.now} Hello #{ENV['TZ']}"
end

gem 'tzinfo-data'
require 'tzinfo/data'
require 'rufus-scheduler'

# config/initializers/scheduler.rb
require 'rufus-scheduler'
s = Rufus::Scheduler.singleton
s.every '1m' do
  Rails.logger.info "hello, #{Time.now}"
  Rails.logger.flush
end

class SchedulerController < ApplicationController
  def index
    job_id =
      Rufus::Scheduler.singleton.in '5s' do
        Rails.logger.info "time flies, it's now #{Time.now}"
      end
    render :text => "scheduled job #{job_id}"
  end
end

# config/initializers/scheduler.rb
require 'rufus-scheduler'
s = Rufus::Scheduler.singleton
unless defined?(Rails::Console) || File.split($0).last == 'rake'
  s.every '1m' do
    Rails.logger.info "hello, #{Time.now}"
    Rails.logger.flush
  end
end
```

```

```
