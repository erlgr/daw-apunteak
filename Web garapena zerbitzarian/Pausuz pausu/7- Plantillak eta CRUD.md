### CSS-a kargatzen
Html-a idatzi baino lehen, gogoratu ```{% load static %}``` idaztea.

### Datuak ikusten
Hasteko, idatzi `doc` html-ko plantilla bat sortzeko. orain, body-aren barruan egin edukiaren for bat
```
{% for post in posts %}

{% endfor %}
```

eta barruan sartu zure edukia. Adibidez:
```
{% for post in posts %}
	<h1>{{ post.title }}</h1>
	<p>{{ post.content }}</p>
{% endfor %}
```

