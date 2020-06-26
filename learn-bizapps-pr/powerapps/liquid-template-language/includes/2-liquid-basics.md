Like any traditional programming language, Liquid has defined syntax, can use variables definitions, and includes constructs such as output and logic. Liquid constructs are easy to recognize by two sets of delimiters: the double curly brace delimiters `{{ }}`, which denote output from the objects and variables, and the curly brace percentage delimiters `{% %}`, which denote logic and control flow.

> [!TIP]
> Page content and content snippets make it easy to "practice" Liquid by entering the Liquid content using the Portal Studio source code editor. As you go along, try any of the sample Liquid fragments by copying and pasting the code directly into a page on your portal.

### Output

An output statement is a set of double curly braces containing an expression. When the output is rendered, it gets replaced with the value of that expression. The expression can include Liquid objects, their properties, and variables. Here is simple example of the output:

```twig
Hello {{ user.firstname }} from {{ 'Power Apps portals' }}
```

which produces (assuming that the user's first name is Doug)

> Hello Doug from Power Apps portals

### Filters

Output markup can take filters, which modify the result of the output statement. You can add filters by following the output expression with a pipe character (`|`), the name of the filter, and optional parameters after a colon (`:`).

```twig
Hello {{ user.firstname | upcase }} from {{ 'Power Apps portals' }}. The time is {{ 'now' | date: 'g' }}
```

which generates

> Hello DOUG from Power Apps portals. The time is 6/24/2020 11:33 AM

### Tags

Tags are used for the logic and control flow in your template. For example (and we added some HTML as well):

```twig
{% assign product = 'Power Apps portals' %}

{% if user %}
  Hello {{ user.firstname | upcase }} from <strong>{{ product }}</strong>
{% else %}
  Greetings <em>visitor</em> from <strong>{{ product }}</strong>
{% endif %}

The time is {{ 'now' | date: 'g' }}
```

In this fragment `assign` creates a new variable, and the `if... else` construct generates output depending on whether the user is defined (in other words, whether a portal user signed in). The output for an anonymous user is:

> Greetings *visitor* from **Power Apps portals**
>
> The time is 6/24/2020 11:33 AM

Let's take a quick look at the Liquid and some of its common concepts in this video introduction.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/]

Liquid includes a lot of built-in objects and tags that make it very versatile and flexible. Of course, the real benefits come from the Liquid extensions implemented by Power Apps portals.
