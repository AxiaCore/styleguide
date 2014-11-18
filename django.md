## Phylosophy

Things should be short and easy to understand.

### Which code should be within `utils.py`

We should have only code that is intended to be used in many places, that is, if a section of code is only
used in a view and nowhere else, it's better to keep it in that view and not in `utils.py`. However, when a section 
of code is used in several views, it qualifies for being under `utils.py`

### Generalities 
* Use single quotes `''` for strings.
* Use underscore in templates names.

### Table of contents

* [Urls](#URLS)


### URLS 

Use `/` slash at the end of the URL

> Incorrect example 

```python 
r'^(?P<slug>[-\w]+)/settings$'
```

> Correct example

```python 
r'^(?P<slug>[-\w]+)/settings/$'
```

### Templates naming

When naming your 

### Includes 

Use an include for every dependency, even if they're under the same package.

> Bad example
```python
from app.views import HomeView, NewsletterView, WidgetView
```

> Good example
```python 
from app.views import HomeView
from app.views import NewsletterView
from app.views import WidgetView
```


### Comments

Preferably, use docstrigns when describing classes and methods behaviour.

> Bad example

```python 
class UserForm(UpdateView):
    # For for updating user info.
  
  ...
```

> Good example

```python 
class UserForm(UpdateView):
    """ Form for updating user info.
    """
    
    ...
```



