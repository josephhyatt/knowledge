# ERB: Embedded Ruby

> **ERB** stands for **E**mbedded **R**u**B**y. This just means that Rails processes some special tags in those files and produces HTML output to send back to the user. There are **two ERB tags** that you need to remember: `<%= ruby_code %>` and `<% ruby_code %>`.

## Run & Show Ruby Code

> **&lt;%= %&gt;** Runs the Ruby code and inserts the result to the HTML at that position. You can put any kind of Ruby code between `<%=` and `%>`, for instance, `<%= 9 * 3 %>` will translate to **27** in the page that the user is viewing. However, typically this tag is used to display some data from a model, such as the price of a product, as shown in the example here.

```ruby
<%= @product.price %> 
```

## Run but Don't Show Ruby Code

> **&lt;% %&gt;**  The Ruby code between the delimiters `<%` and `%>` is run but the result will **not** be inserted at this point in the HTML. Therefore these tags are most commonly used for control flow structures such as an if statement in the example, or loops.

```ruby
# a conditional statement
<% if user.admin? %>
  <p>Hello Admin!</p>
<% end %>
```

