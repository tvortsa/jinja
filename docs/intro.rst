Введение
============

Это документация по Jinja2 языка шаблонов общего назначения.
Jinja2 это библиотека для Python гибкая, быстрая и секюрная.

Если у вас есть доступ к другим языкам шаблонов на основе текста, таким как Smarty 
или Django, вы должны почуствовать себя как дома в Jinja2. Она разработана быть дружелюбной как для программистов так и для дизайнеров придерживаясь принципов Python и добавляя функциональности шаблон-среде.

Предпосылки
-------------

Jinja2 работает с Python 2.6.x, 2.7.x и >= 3.3.  Если вы используете Python
3.2 вы можете использовать старые релизы Jinja2 (2.6) поскольку поддержка Python 3.2
была остановлена в Jinja2 версии 2.7.

Если вы хотите использовать класс :class:`~jinja2.PackageLoader` вам также нужно
`setuptools`_ или `distribute`_ installed at runtime.

Установка
------------

You have multiple ways to install Jinja2.  If you are unsure what to do, go
with the Python egg or tarball.

As a Python egg (via `easy_install`)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can install the most recent Jinja2 version using `easy_install`_ or `pip`_::

    easy_install Jinja2
    pip install Jinja2

This will install a Jinja2 egg in your Python installation's site-packages
directory.

From the tarball release
~~~~~~~~~~~~~~~~~~~~~~~~~

1.  Download the most recent tarball from the `download page`_
2.  Unpack the tarball
3.  ``python setup.py install``

Note that you either have to have `setuptools` or `distribute` installed;
the latter is preferred.

This will install Jinja2 into your Python installation's site-packages directory.

Installing the development version
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.  Install `git`_
2.  ``git clone git://github.com/pallets/jinja.git``
3.  ``cd jinja2``
4.  ``ln -s jinja2 /usr/lib/python2.X/site-packages``

As an alternative to steps 4 you can also do ``python setup.py develop``
which will install the package via `distribute` in development mode.  This also
has the advantage that the C extensions are compiled.

.. _download page: https://pypi.python.org/pypi/Jinja2
.. _distribute: https://pypi.python.org/pypi/distribute 
.. _setuptools: http://peak.telecommunity.com/DevCenter/setuptools
.. _easy_install: http://peak.telecommunity.com/DevCenter/EasyInstall
.. _pip: https://pypi.python.org/pypi/pip
.. _git: https://git-scm.org/


MarkupSafe Dependency
~~~~~~~~~~~~~~~~~~~~~

As of version 2.7 Jinja2 depends on the `MarkupSafe`_ module.  If you
install Jinja2 via `pip` or `easy_install` it will be installed
automatically for you.

.. _MarkupSafe: https://pypi.python.org/pypi/MarkupSafe

Использование базового API
---------------------------

В этом разделе вы найдете краткое введение в Python API для шаблонов Jinja2.

Самый простой способ создать шаблон и сделать его это через
:class:`~jinja2.Template`.  Тем не менее этот способ не рекомендуется
если ваши шаблоны загружаются не через strings а через файловую систему или
другой источник данных:

>>> from jinja2 import Template
>>> template = Template('Hello {{ name }}!')
>>> template.render(name='John Doe')
u'Hello John Doe!'

Создавая экземпляр класса :class:`~jinja2.Template` вы получаете новый template
объект который предоставляет метод :meth:`~jinja2.Template.render` который при вызове
со словарем или keyword arguments расширяют темплате.  The dict
or keywords arguments переданные в шаблонe также называют "context"
шаблона.

What you can see here is that Jinja2 is using unicode internally and the
return value is an unicode string.  So make sure that your application is
indeed using unicode internally.


Experimental Python 3 Support
-----------------------------

Jinja 2.7 brings experimental support for Python >=3.3.  It means that all
unittests pass on the new version, but there might still be small bugs in
there and behavior might be inconsistent.  If you notice any bugs, please
provide feedback in the `Jinja bug tracker`_.

Also please keep in mind that the documentation is written with Python 2
in mind, so you will have to adapt the shown code examples to Python 3 syntax
for yourself.


.. _Jinja bug tracker: https://github.com/pallets/jinja/issues
