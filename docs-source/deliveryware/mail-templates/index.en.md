# E-Mail Templates

So that the appropriate configuration of the order is also displayed in the e-mails,
a manual adjustment is necessary.

### Just copy this excerpt into your email template

```html
{% if nestedItem.payload.dewa is defined and nestedItem.payload.dewa|length %}
    {% for item in nestedItem.payload.dewa %}
        <br/>
        {% if item.value is iterable %}
            {{ item.name }}: {{ item.value | join(', ') }}
        {% else %}
            {{ item.name }}: {{ item.value }}
        {% endif %}
    {% endfor %}
{% endif %}
```