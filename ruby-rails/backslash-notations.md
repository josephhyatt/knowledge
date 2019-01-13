# Backslash Notations

> ```ruby
> \n                  # Newline (0x0a)
> \r                  # Carriage return (0x0d)
> \f                  # Formfeed (0x0c)
> \b                  # Backspace (0x08)
> \a                  # Bell (0x07)
> \e                  # Escape (0x1b)
> \s                  # Space (0x20)
> \x                  # Character x``
> \nnn                # Octal (n = 0-7)
> \xnn                # Hesadecimal (n = 0-9, a-f, A-F)
> \cx, \C-x           # Control-x
> \M-x                # Meta x; usually used for keyboard/terminal control
> \M-\C-x             # Meta-Control-x; usually used for keyboard/terminal control
> \unnnn              # Unicode code point U+nnnn (Ruby 1.9+)
> puts "ln1\nln2"     # Newline (0x0a); prints two lines
> puts "n123\rab"     # Carriage return (0x0d); prints one line, "ab23"
> puts "f12\f345"     # Formfeed (0x0c); prints two lines, offset
> puts "abc\bx"       # Backspace (0x08); prints 'abx'
> puts "bell\a\a\a"   # Bell (0x07); prints 'bell' and rings bell three times
> puts "ab\ecd"       # Escape (0x1b); prints 'abd'
> puts "ab\scd"       # Space (0x20); prints 'ab cd'
> puts "ab\xcd"       # Character x; prints 'abxcd'
> puts "ab\015x"      # Octal (n = 0-7); prints 'xb', same as \r
> puts "ab\xdx"       # Hesadecimal (n = 0-9, a-f, A-F); prints 'xb', same as \r
> puts "abc\C-Hxyz"   # Control-x; prints 'abxyz', same as \b; \C-@ == \x00, \C-A == \x01, ...  
> puts "\u2713"       # Unicode code point U+nnnn (Ruby 1.9+); prints "✓"
> ```

