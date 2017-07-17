Jinja2
~~~~~~

Jinja2 движок шаблонов (шаблонизатор) написанный на чистом Python.  It provides a
`Django`_ вдохновлен не-XML синтаксисом но поддерживает инлайн-выражения и 
an optional `sandboxed`_ environment.

Nutshell
--------

Вот небольшой пример шаблона Jinja:

.. code-block:: jinja

    {% extends 'base.html' %}
    {% block title %}Memberlist{% endblock %}
    {% block content %}
      <ul>
      {% for user in users %}
        <li><a href="{{ user.url }}">{{ user.username }}</a></li>
      {% endfor %}
      </ul>
    {% endblock %}

Философия
----------

Логика приложения для контроллера, но не осложняйте жизнь дизайнеру шаблона
 слишком ограничивая функциональность.

Больше информации в `Jinja2 webpage`_ и `documentation`_.

 `Jinja2 tip`_ устанавливаем через ``pip`` с ``pip install
https://github.com/pallets/jinja/zipball/master``.

.. _sandboxed: https://en.wikipedia.org/wiki/Sandbox_(computer_security)
.. _Django: https://www.djangoproject.com/
.. _Jinja2 webpage: http://jinja.pocoo.org/
.. _documentation: http://jinja.pocoo.org/docs/
.. _Jinja2 tip: http://jinja.pocoo.org/docs/intro/#as-a-python-egg-via-easy-install

Сборки
------

+---------------------+------------------------------------------------------------------------------+
| ``master``          | .. image:: https://travis-ci.org/pallets/jinja.svg?branch=master             |
|                     |     :target: https://travis-ci.org/pallets/jinja                             |
+---------------------+------------------------------------------------------------------------------+
| ``2.9-maintenance`` | .. image:: https://travis-ci.org/pallets/jinja.svg?branch=2.9-maintenance    |
|                     |     :target: https://travis-ci.org/pallets/jinja                             |
+---------------------+------------------------------------------------------------------------------+
