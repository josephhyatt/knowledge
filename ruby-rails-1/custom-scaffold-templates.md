# Custom Scaffold Templates

* Create a`templates` **folder** in the `lib` **directory**.
  * Create `erb` **folders** in `templates`**directory**.
    * Create a `scaffold` **folder** inside `erb`**directory**.
      * Create `index.html.erb` **file** in `scaffold`**directory**.

```text
lib/
-- templates
  -- erb
    -- scaffold
      --| _form.html.erb.tt
      --| edit.html.erb.tt
      --| index.html.erb.tt
      --| new.html.erb.tt
      --| show.html.erb.tt
```

* Inside `index.html.erb` file in scaffold **directory**.

```ruby
<!-- lib/templates/erb/scaffold/index.html.erb.tt -->

<div class="container mx-auto my-8 px-4">
  <div class="flex justify-between items-center mb-4">
    <h1 class="h2"><%= plural_table_name.titleize %></h1>

    <%% if @<%= plural_table_name %>.exists? %>
      <%%= link_to 'New <%= singular_table_name.titleize %>', new_<%= singular_route_name %>_path, class: "btn btn-default" %>
    <%% end %>
  </div>

  <%% if @<%= plural_table_name %>.exists? %>
    <div class="bg-white rounded shadow">
      <table class="w-full">
        <thead>
          <tr>
<% attributes.reject(&:password_digest?).each do |attribute| -%>
            <th class="p-3 uppercase text-left text-xs text-gray-700"><%= attribute.human_name %></th>
<% end %>
            <th class="p-3 uppercase text-left text-xs text-gray-700">Actions</th>
          </tr>
        </thead>

        <tbody>
        <%% @<%= plural_table_name %>.each do |<%= singular_table_name %>| %>
          <tr class="group border-t border-gray-400 hover:bg-gray-100">
            <% attributes.reject(&:password_digest?).each do |attribute| -%>
              <td class="p-3"><%%= <%= singular_table_name %>.<%= attribute.column_name %> %></td>
            <% end %>
            <td>
              <%%= link_to "View", <%= singular_table_name %>, class: "btn btn-default" %>
              <%%= link_to "Edit", edit_<%= singular_table_name %>_path(<%= singular_table_name %>), class: "btn btn-default" %>
            </td>
          </tr>
        <%% end %>
        </tbody>
      </table>
    </div>

  <%% else %>
    <div class="bg-white rounded shadow flex items-center justify-between p-8">
      <div class="flex-1 text-center">
        <p class="text-xl font-semibold mb-4">Create your first <%= singular_table_name.titleize %></p>
      <%%= link_to 'New <%= singular_table_name.titleize %>', new_<%= singular_route_name %>_path, class: "btn btn-default" %>
      </div>
    </div>
  <%% end %>
</div>
```



### A number of things to note:

* This assumes you created a new rails app using my [Kickoff Tailwind](https://github.com/justalever/kickoff_tailwind) template. The classes you see pertain to Tailwind CSS as well as some custom components that come by default when you create a new rails app using the template. I talk more about recent changes to the template [here](https://web-crunch.com/latest-news-rails-6-jumpstart-pro-kickoff-updates/).
* The `<%%` signs are new and essentially act as a templating preformatter when a scaffold gets run within the context of `erb` files.
* Inside these templates, we have access to local variables and methods like `singular_table_name` or `singular_route_name` of which are dynamic. These will get replaced with whatever resource you’re generating. In our case, it would be `post`.

