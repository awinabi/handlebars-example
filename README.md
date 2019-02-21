## Handlebars Example
Handlebars is an HTML templating engine. Give it data as JSON, and it will render the variables in the template to generate HTML.

### Setup

- **Add templates in js/templates folder**

  For example, check the `js/templates/books.handlebars` template file

- **Pre-compile handlebar templates**

  Use the following command, to precompile all templates into a single js file.
  This requires the `handlerbars` npm package.

  ```
  npm install -g handlebars
  handlebars -m js/templates/ -f js/templates/templates.js
  ```

- **Use templates in your html**


  ```

  <div class="container">
    <div id='app'>
    </div>
  </div>

  <!-- include the handlebars runtime js -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.11/handlebars.runtime.min.js"></script>

  <!-- include the compiled templates -->
  <script src="js/templates/templates.js"></script>

  <script type='text/javascript'>

    var template = Handlebars.templates['books'];

    //****
    //* Supply the data to the template as json
    //****
    $('#app').html(template({
      books: [{
        title: 'Python Crash Course',
        description: 'this is a basic handlebar2'
      },
      {
        title: 'Benitto Morses',
        description: 'this is a basic handlebar template'
      }]}));

  </script>
