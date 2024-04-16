
# django-admin-reorder
Easy way to order and rename models in the django admin page.


## Origin

When searching alternatives to [django-modeladmin-reorder](https://github.com/mishbahr/django-modeladmin-reorder), i found [this thread](https://forum.djangoproject.com/t/reordering-list-of-models-in-django-admin/5300) that gave me the idea of changing model names and order just by adding the data to the modeladmin. 
## Features

- Ordering Models inside Categories (ex: model ```truck``` before model ```car```)
- Ordering Categories (ex: app ```vehicules``` before app ```orders```)
- Changing the Model Label (ex: renaming the ```CarPartType``` model to ```Types of Car parts``` )



## Supported Versions

Works on Django:
- 5.0
- 4.2 

These are the only versions i tested, might work on more.
## Installation
(not published yet)

Install with pip

```bash
  pip install django-admin-reorder
```

Then in settings.py


```python
INSTALLED_APPS = (
    ...
    'admin-reorder',
    ...
)
```
## Documentation

Renaming a model :

```python
@admin.register(MyExampleModel)
class MyExampleModelAdmin(admin.ModelAdmin):
    reorder_label = "Changed the model name"

    list_display = ('one', 'two')


```

Ordering a model in a category :

```python
@admin.register(MyExampleModel)
class MyExampleModelAdmin(admin.ModelAdmin):
    reorder_label = "Changed the model name"
    reorder_priority = 10

    list_display = ('one', 'two')


```
## Roadmap

- Support listing a model more than once


## FAQ

#### How does it work

The [admin.AdminSite.get_app_list](https://github.com/django/django/blob/47c608202a58c8120d049c98d5d27c4609551d33/django/contrib/admin/sites.py#L29) method is replaced for custom behaviour.



