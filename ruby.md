# Ruby

## OptionParser

Ruby standard library to help creating command line apps with arguments parsing

```ruby
require 'optparse'

options = {}
OptionParser.new do |opts|
  opts.banner = "Usage: example.rb [options]"

  opts.on("-v", "--[no-]verbose", "Run verbosely") do |v|
    options[:verbose] = v
  end
end.parse!

p options
p ARGV
```

[Read more](https://ruby-doc.org/stdlib/libdoc/optparse/rdoc/OptionParser.html)

## String\#unpack & Array\#pack

Useful for reading & parsing binary or hexadecimal data.

### String\#unpack

Decodes string and returns array, according to template string given.

```ruby
"ABC".unpack("H*") # Hex
=> ["414243"]
"ABC".unpack("H2")
=> ["41"]
"ABC".unpack("H2H2H2")
=> ["41", "42", "43"]
"ABC".unpack("U*") # Unicode
=> [65, 66, 67]
```

### Array\#pack

Packs the contents of arr into a binary sequence, can reverse the unpack method.

```ruby
["a", "b", "c"].pack("A")
=> "a"
["a", "b", "c"].pack("A3")
=> "a  "
["a", "b", "c"].pack("A3A4A5")
=> "a  b   c    "
[65, 66, 67].pack("U*")
=> "ABC"
["414243"].pack("H*")
=> "ABC"
["41", "42", "43"].pack("H2" * 3)
=> "ABC"
["ABCDE"].pack("m") # Base64 encode
=> "QUJDREU=\n"
```

There are many directives to use building template strings. See Ruby docs for detail.

### References

* [http://ruby-doc.org/core-2.6.3/String.html\#method-i-unpack](http://ruby-doc.org/core-2.6.3/String.html#method-i-unpack)
* [http://ruby-doc.org/core-2.6.3/Array.html\#method-i-pack](http://ruby-doc.org/core-2.6.3/Array.html#method-i-pack)
* [https://www.rubyguides.com/2017/01/read-binary-data/](https://www.rubyguides.com/2017/01/read-binary-data/)

