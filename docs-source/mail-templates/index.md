# E-Mail Templates anpassen

Damit auch die passende Konfiguration der Bestellung in den E-Mails dargestellt wird,
ist eine manuelle Anpassung notwendig.

### Kopiere einfach diesen Auszug in Dein E-Mail Template

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