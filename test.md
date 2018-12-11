# Test from book

Template pages are extremely important for a theme because all of the page content is rendered inside the active template. There is only ever one active template on your website at any given time and this can be chosen by each physical page.

A template page can be thought of as the _master template_; all other theme layouts are rendered inside of it. Any elements that are repeated in a theme e.g. \( site navigations, header, footer, etc.\) should be placed inside a template page.

## Blocks  <a id="blocks"></a>

Blocks are a vital part of liquid themes. They allow content to be dynamically outputted to a template page from all other liquid templates.

1. Ensure the Physical Page is extending the Template Page: `{% extends 'MASTER' %}`
2. Add a corresponding block to both a "Template Page" and the "Physical Page" layouts

### Template Page \(MASTER\)  <a id="template-page-master"></a>

MASTER

```text
<html>    
<head>        
<title>Master Template Page</title>    
</head>    
<body>          
{% block page-content %}            
<!-- Content from a physical page will be injected here -->        
{% endblock %}       
</body>
</html>
Physical Page (HOME)
```

HOME

```text
<!-- Replace 'MASTER' with your template page's code -->{% extends 'MASTER' %}​{% block page-content %}    <h1>Hello, World!</h1>{% endblock %}
```

### Result  <a id="result"></a>

Output

```text
<html>    <head>        <title>Master Template Page</title>    </head>    <body>         <h1>Hello, World!</h1>     </body></html>
```

​

