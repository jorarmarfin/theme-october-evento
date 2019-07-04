# Theme para eventos para OCTOBER

## Dependencias Plugins
* Pages

## Corrigiendo plugin de menu de page
```
{% for item in items if not item.viewBag.isHidden %}
    <li role="presentation" class="{{ item.isActive ? 'active' : '' }} {{ item.isChildActive ? 'child-active' : '' }} {{ item.viewBag.cssClass }}">
        {% if item.url %}
            <a href="{{ item.url }}" {{ item.viewBag.isExternal ? 'target="_blank"' }}>
                {{ item.title }}
                {% if item.items %}
                    <span class="caret"></span>
                {% endif %}
            </a>
        {% else %}
            <span>{{ item.title }}</span>
        {% endif %}

        {% if item.items %}
            <ul class="dropdown-menu">{% partial __SELF__ ~ "::items" items=item.items %}</ul>
        {% endif %}
    </li>
{% endfor %}
```