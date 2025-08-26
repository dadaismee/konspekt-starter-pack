---
title: "{{title}}"
authors: {{authors}}
citekey: {{citekey}}
url: {{url}}
date-added: {% if date %}{{date | format("YYYY-MM-DD")}}{% endif %}
annotations_count: {{annotations.length}}
---
# {{title}}
- Темы:
- [Зотеро]({{desktopURI}}) {%for attachment in attachments | filterby("path", "endswith", ".pdf") %} [pdf](<file://{{attachment.path}}> | replace(" ", "%20")}}) [url]({{url}}) {%endfor %}

## Резюме источника

→ *Параграф текста про источник для литобзора* ←

## Ключевые идеи автора

{% for annotation in annotations %}

{% if annotation.annotatedText %}

- [ ] *Суть идеи своими словами*
	{% if annotation.comment %}
- **{{annotation.comment}}**
	{% endif %}

> {{annotation.annotatedText}}

---

{% endif %}

{% endfor %}

## Мои идеи по тексту

## Связанные заметки