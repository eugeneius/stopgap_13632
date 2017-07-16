## Description
Ruby gem temporary stopgap workaround for MRI Ruby versions 2.2.7, 2.3.4, 2.4.1 for the bug https://bugs.ruby-lang.org/issues/13632 until proper fix gets backported.

## Installation:
```ruby
gem install stopgap_13632
require 'stopgap_13632'
```

## Usage
And when an "IOError: stream closed" happens in a thread, accessing a busy IO:
```
rescue IOError
  Thread.current.purge_interrupt_queue
end
```
It will unblock the thread and allow it to proceed.

## Contributing:
```bash
rake compile
rake test
```
