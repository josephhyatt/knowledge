# Selenium Cheat Sheet

## Getting Started

### Webpage:

```ruby
<html>
<head>
    <title>Testing with Ruby and Selenium WebDriver</title>
</head>
 
<body bgcolor="antiquewhite">
 
<img src="images/freebsd_daemon.jpg">
<h2>
 
 
Version 1.0</h2><h1>
 
 
Test Automation Training</h1><h3>
 
 
Testing Web Applications with Ruby and Selenium WebDriver</h3></body>
</html>
```

### Ruby Code:

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page1"
 
# Timeout = 15 sec
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
# Find text on the page by regexp
puts "Test Passed: Page 1 Validated" if wait.until {
    /Testing Web Applications with Ruby and Selenium WebDriver/.match(browser.page_source)
}
 
browser.quit
```

## Locators

### Web Page

```ruby
<html>
<head>
    <title>Testing with Ruby and Selenium WebDriver</title>
</head>
 
<body bgcolor="antiquewhite">
 
<img src="images/freebsd_daemon.jpg">
<h2>
 
 
Version 1.0</h2><h1>
 
 
Test Automation Training</h1><h3>
 
 
Testing Web Applications with Ruby and Selenium WebDriver</h3></body>
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page1"
 
# Timeout = 15 sec
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
# Find text on the page by regexp
puts "Test Passed: Page 1 Validated" if wait.until {
    /Testing Web Applications with Ruby and Selenium WebDriver/.match(browser.page_source)
}
 
browser.quit
```

## Forms

### Web Page

```ruby

<html>
<head>
    <title>Testing with Ruby and Selenium WebDriver</title>
</head>
 
<body bgcolor="antiquewhite">
 
<img src="images/freebsd_daemon.jpg">
<h2>
Version 1.0</h2>
<h1>
Test Automation Training</h1><h3>
Testing Web Applications with Ruby and Selenium WebDriver</h3><p>
Enter something interesting in the text box and click a button!</p><form name="input" action="page1.html" method="post">
 
    <p>
<input type="text" name="searchbox"></p><p>
<input type="submit" name="submit" value="submit"></p></form></body>
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page3"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
# Add text to a text box
input = wait.until {
    element = browser.find_element(:name, "searchbox")
    element if element.displayed?
}
input.send_keys("Information")
 
# Check that the form exists
form = wait.until {
    element = browser.find_element(:name, "input")
    element if element.displayed?
}
puts "Test Passed: Form input found" if form.displayed?
 
# Click the button based the form it is in (you can also call 'submit' method)
form.find_element(:name, "submit").click
 
browser.quit
```

## Images

### Web Page

```ruby
<html>
<head>
    <title>Images</title>
</head>
 
<body bgcolor="lightsteelblue">
 
<img src="images/freebsd_daemon.jpg">
<h2>Version 1.0</h2>
 
<h1>We are testing images...</h1><h3>Testing Web Applications with Ruby and Selenium WebDriver</h3>
<img name="watergraphic" src="images/WaterFaucet.jpg" alt="Image of water faucet"/>
<a href="page1.html"><img alt="Image Button" src="images/totoro.gif"/></a>
 
</body>
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page4"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
# Check that the image exists using different attributes and xpath
 
puts "Test Passed: Found a graphic with the path 'images/WaterFaucet.jpg' in the source filename" if wait.until {
    browser.find_element(:xpath => "//img[@src='images/WaterFaucet.jpg']").displayed?
}
 
puts "Test Passed: Found a graphic with the name watergraphic" if wait.until {
    browser.find_element(:name, "watergraphic").displayed?
}
 
puts "Test Passed: Found a graphic with 'Image of water faucet' as alt text" if wait.until {
    browser.find_element(:xpath => "//img[@alt='Image of water faucet']").displayed?
}
 
# Click the image button
image = wait.until {
    element = browser.find_element(:xpath => "//img[@src='images/totoro.gif']")
    element if element.displayed?
}
image.click
 
# Check the text on the new page
puts "Test Passed: Page 1 Validated" if wait.until {
    /Test Automation Training/.match(browser.page_source)
}
 
browser.quit
```

## Checkboxes

### Web Page

```ruby
<html>
<head>
    <title>Testing with Ruby and Selenium WebDriver</title>
</head>
 
<body bgcolor="cadetblue">
 
<img src="images/freebsd_daemon.jpg">
<h2>Version 1.0</h2>
 
<h1>Test Automation Training</h1><h3>Testing Web Applications with Ruby and Selenium WebDriver</h3>
<form action="page1" method="post">
    <p><Input type="checkbox" name="checkthebox"></p>    <p><Input type="submit" value="submit"></p></form>
</body>
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page5"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
cb = browser.find_element(:name, "checkthebox")
 
# Check that the checkbox exists
cb = wait.until {
    element = browser.find_element(:name, "checkthebox")
    element if element.displayed?
}
puts "Test Passed: The check box exists" if cb
 
# Check the checkbox
cb.click
 
# Verify the state of checkbox
puts "Test Passed: The check box is selected now" if cb.selected? == true
 
sleep 2
 
# Un-Check the checkbox
cb.click
 
# Verify the state of checkbox again
puts "Test Passed: The check box is unselected now" if cb.selected? == false
 
browser.quit
```

## Radio Buttons

### Web Page

```ruby
<html>
<head>
    <title>Testing with Ruby and Selenium WebDriver</title>
</head>
 
<body bgcolor="antiquewhite"">
 
<img src="images/freebsd_daemon.jpg">
<h2>Version 1.0</h2>
 
<h1>Test Automation Training</h1><h3>Testing Web Applications with Ruby and Selenium WebDriver</h3>
<form action="page1" method="post">
    <p>Option 1<Input type="radio" name="radiobutton1"></p>    <p>Option 2<Input type="radio" name="radiobutton2"></p>    <p>Option 3<Input type="radio" name="radiobutton3"></p>    <p><input type="submit" value="submit"></p></form>
</body>
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page6"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
#### Check that the radio button exists
puts "Test Passed: Radio button found" if wait.until {
    browser.find_element(:name, "radiobutton1").displayed?
}
 
#### Change the state of the Radio Buttons
cb1 = wait.until {
    element = browser.find_element(:name, "radiobutton1")
    element if element.displayed?
}
cb1.click if cb1.selected? == false
 
cb3 = wait.until {
    element = browser.find_element(:name, "radiobutton3")
    element if element.displayed?
}
cb3.click if cb3.selected? == false
 
browser.quit
```

## Select Boxes

### Web Page

```ruby
<html>
<head>
    <title>Testing with Ruby and Selenium WebDriver</title>
</head>
 
<img src="images/freebsd_daemon.jpg">
<h2>Version 1.0</h2><h1>Test Automation Training</h1><h3>Testing select boxes</h3>
<form action="page1" method="post">
<select name="dropdown" multiple="multiple" size="2">
  <option value="1">Volvo</option>
  <option value="2">Saab</option>
  <option value="3">Mercedes</option>
  <option value="4">Audi</option>
</select>
    <p><Input type="submit" value="submit"></p></form>
</body>
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page7"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
#### Interact with the drop down box
select_list = wait.until {
    element = browser.find_element(:name, "dropdown")
    element if element.displayed?
}
select_list.clear
 
#### Extract all options from the select box
options=select_list.find_elements(:tag_name => "option")
 
#### Select the option "Volvo"
options.each do |g|
  if g.text == "Volvo"
  g.click
  break
  end
end
 
#### Select another option "Audi"
options.each do |g|
  if g.text == "Audi"
  g.click
  break
  end
end
 
#### Print currently selected options
options.each do |g|
  if g.selected?
  puts g.text 
  end
end
 
browser.quit
```

## Tables

### Web Page

```text
<html>
<head>
    <title>Testing with Ruby and Selenium WebDriver</title>
</head>
 
<img src="images/freebsd_daemon.jpg">
<h2>Version 1.0</h2><h1>Test Automation Training</h1><h3>Testing tables</h3>
<table id="booktable" border="1">
<tr>
<td>fraise</td>
<td>orange</td>
</tr>
<tr>
<td>vin</td>
<td>eau</td>
</tr>
</table>
</body>
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page8"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
#### Check that the table with the given id is displayed
table = wait.until {
    element = browser.find_element(:id, "booktable")
    element if element.displayed?
}
puts "Test Passed: Book Table found" if table
 
#### Print full table contents
puts "Table with id=booktable:\n" + table.text
 
#### Iterate through all cells of the table
browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr/td").each do |r|
    puts "Cell Value: " + r.text
end
 
#### Print the value from the 1'st column of the 2'nd row of the table
puts "Value from the 1'st column of the 2'nd row of the table: " + browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr")[1].text.split(' ')[0]
 
#### Print the value from the 2'nd column of the 1'st row of the table
puts "Value from the 2'nd column of the 1'st row of the table: " + browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr")[0].text.split(' ')[1]
 
browser.quit
```

## Executing JavaScript code on the page. Handling popup dialog's.

### Web Page

```ruby
<script type="text/javascript">
function enter_name()
{
var name=prompt("Please enter your name","Artem");
if (name!=null && name!="")
  {
  document.write("Hello " + name + "! How are you today?");
  window.stop();
  }
}
function enter_age()
{
var age=prompt("Please enter your age","27");
if (age!=null && age!="")
  {
  document.write("You are " + age + " years old.");
  window.stop();
  }
}
</script>
  <input type="button" onclick="enter_name()" value="Name">
<p><input type="button" onclick="enter_age()" value="Age"></p>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page9"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
# Execute 1st JavaScript function on the page and Cancel the prompt box
browser.execute_script("enter_name()")
a = browser.switch_to.alert
if a.text == 'Please enter your name'
  a.dismiss
else
  a.accept
end
 
# Execute 2nd JavaScript function on the page and Accept the prompt box
browser.execute_script("enter_age()")
a = browser.switch_to.alert
if a.text == 'Please enter your name'
  a.dismiss
else
  a.send_keys("99")
  a.accept
end
 
# Find the age on the page by regexp
puts "Test Passed: Page 9 Validated" if wait.until {
    /99/.match(browser.page_source)
}
 
browser.get "http://localhost/page9"
 
# Execute any custom JavaScript code
puts browser.execute_script("return window.location.pathname")
 
browser.quit
```

## Frames

### Web Page

```ruby
<html>
 
<frameset cols="25%,50%,25%">
 
  <frame id="frame1" src="http://www.debian.org" />
  <frame id="frame2" src="http://www.kernel.org" />
  <frame id="frame3" src="http://www.ubuntu.com" />
 
</frameset>
 
</html>
```

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
 
browser = Selenium::WebDriver.for :firefox
browser.get "http://localhost/page10"
 
wait = Selenium::WebDriver::Wait.new(:timeout => 15)
 
# Switch to the 1st frame
browser.switch_to.frame("frame1")
 
# Find text in the 1st frame by regexp
puts "Test Passed: Frame 1 Validated" if wait.until {
    /An operating system is the set of basic programs and utilities that make
your computer run/.match(browser.page_source)
}
 
# Switch to parent page
browser.switch_to.default_content
 
# Switch to the 2nd frame
browser.switch_to.frame("frame2")
 
# Find text in the 2nd frame by regexp
puts "Test Passed: Frame 2 Validated" if wait.until {
    /Welcome to the Linux Kernel Archives/.match(browser.page_source)
}
 
# Switch to parent page
browser.switch_to.default_content
 
# Switch to the 3rd frame
browser.switch_to.frame("frame3")
 
# Find text in the 3rd frame by regexp
puts "Test Passed: Frame 3 Validated" if wait.until {
    /Ubuntu is, and always will be, absolutely free/.match(browser.page_source)
}
 
browser.quit
```

## Test/Unit

### Ruby Code

```ruby
require 'rubygems'
require 'selenium-webdriver'
require 'test/unit'
 
class ExampleTestCase < Test::Unit::TestCase
 
#### Starting browser before each test
def setup
    @browser = Selenium::WebDriver.for :firefox
    @browser.get "http://localhost/page8"
    @wait = Selenium::WebDriver::Wait.new(:timeout => 15)
end
 
#### Closing browser after each test 
def teardown
    @browser.quit
end
 
#### Check that the table is there
def test_table_existence
    assert @wait.until {
        @browser.find_element(:id, "booktable").displayed?
    }
end
 
#### Checking values in the table cells
def test_table_values
    ##### Waiting for the values to appear
    assert @wait.until {
        @browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr")[0].text.split(' ')[0] == "fraise"
    }
    assert @wait.until {
        @browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr")[0].text.split(' ')[1] == "orange"
    }
    ##### Not waiting for the values to appear, assuming they are already visible
    assert_equal(@browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr")[1].text.split(' ')[0], "vin")
    assert_equal(@browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr")[1].text.split(' ')[1], "eau")
    assert_not_equal(@browser.find_elements(:xpath => "//table[@id='booktable']/tbody/tr")[1].text.split(' ')[0], "fake")
end
 
end
```

## Test Suite

### Ruby Code

```ruby
#### Test suite
require 'rubygems'
require 'test/unit'
 
#### Below you can include any number of files to your test suite
require 'example_testunit'
```

