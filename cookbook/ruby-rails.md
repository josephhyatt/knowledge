# Ruby/Rails

## Search Array

### [Array\#bsearch](http://www.ruby-doc.org/core-2.1.5/Array.html#method-i-bsearch) 

can find a match with only O\(log n\) complexity.

```ruby
require 'benchmark'

data = (0..50_000_000)

Benchmark.bm do |x|
  # :find is slower
  x.report(:find) { data.find {|number| number > 40_000_000 } }
  # :besearch is faster
  x.report(:bsearch) { data.bsearch {|number| number > 40_000_000 } }
end
```

