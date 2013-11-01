PythonImproved
==============

A better `Python.tmLanguage` language definition for Sublime Text and TextMate. Inspired by:

- the original TextMate and Sublime Text 2 `.tmLanguage` definitions
- facelessuser's [Better Python](https://github.com/facelessuser/sublime-languages)
- Djaniero's [Django syntax](https://github.com/squ1b3r/Djaneiro)

as well as a number of my own changes to make things more consistent and understandable. For customized syntax highlighting taking advantage of all the new scopes, use PythonImproved with the [Neon Color Scheme](https://sublime.wbond.net/packages/Neon%20Color%20Scheme).

## Installation and Use

If you haven't already, [install Package Control](https://sublime.wbond.net/installation), then select **`Python Improved`** from the `Package Control: Install Package` option in the Command Palette. To use as your default Python syntax, open a `.py` file, then select `View -> Syntax -> Open all with current extension as... -> PythonImproved`.

## New/Changed Scopes

If you prefer to modify your own color scheme, here is a list of new/modified scopes, along with some examples. It's not perfectly complete, but it's a start.

- `support.ipython.in` and `support.ipython.out`: [IPython](http://ipython.org) `In [1]:`/`Out [1]:` fields &mdash; designed for use with [SublimeREPL](https://sublime.wbond.net/packages/SublimeREPL)
- [Django](http://www.djangoproject.com)-specific:
    - `support.type.django.model`: `(meta|models).` `DecimalField`, `EmailField`, `ForeignKey`, `ManyToManyField`, etc.
    - `support.other.django.module`: `django`, `django.contrib`, etc.
    - `variable.other.django.settings`: [`settings.py`](https://docs.djangoproject.com/en/1.6/ref/settings/) options like `ADMINS`, `DATABASES`, `INSTALLED_APPS`, `MIDDLEWARE_CLASSES`, etc. Should be complete as of Django 1.6.
    - `support.function.django.view`: view functions `get_list_or_404`, `get_object_or_404`, `load_and_render`, `loader`, `render_to_response`, `render`
    - `support.function.django.model`: model functions `get_object`, `get_list`, `get_count`, etc.
- `constant.numeric.integer.(long).binary.python`: binary literals `0b00101010`, `0b00101010L`
- `keyword.control.import.python` now contains `import`, `from`, _and_ `as`
- `keyword.other.python` now only contains `assert` &mdash; `as`, `del`, `exec`, and `print` have been relocated
- `support.type.exception.python` now matches any identifier that ends with `Exception` or `Error`, not just the built-in ones like `IndentationError` or `RuntimeException`, allowing for the highlighting of custom exceptions such as those included in third-party modules
- Miscellaneous changes to `support.function.builtin.python` and `support.type.python` &mdash; a lot of personal judgement went in to deciding which word went where (for example, `list` is a built-in function, but it's also a type, so I put it in `type`), so if you have a good reason for disagreeing please tell me.
- You can now have comments in multi-line function definitions:
```python
def myfunc(self,            # gotta have self
           param1="value",  # values are cool
           param2=True,     # or False, whatever
           **kwargs):       # you never know
```

## Issues

I'd love to be able to add support for Python 3's [function annotations](http://www.python.org/dev/peps/pep-3107/):

```python
def greet(name: str, age: int) -> str:
    print('Hello {0}, you are {1} years old'.format(name, age))
# instead of the standard
def greet(name, age):
    print(...)
```
This is a bit complex, and I've been having all sorts of trouble trying to match the various parts. If you'd like to help, let me know!

If you have questions, concerns, or suggested improvements, I'd love to hear from you! Feel free to [open an issue](https://github.com/MattDMo/PythonImproved/issues/new) or send a [pull request](https://github.com/MattDMo/PythonImproved/compare/) and I'll get back to you as soon as I can. You can also email me at <mattdmo@pigimal.com>.


## License

&copy; 2013 Matt Morrison <mattdmo@pigimal.com>.

This is free software. It is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>. Feel free to use this in your own work. However, if you modify and/or redistribute it, please attribute me in some way, and distribute your work under this or a similar license. A shout-out or a beer would be appreciated.

<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/"><img alt="Creative Commons License" style="border-width:0;align:center" src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a>

<!-- <a href="https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=R97MGGYES6GAJ&lc=US&item_name=Matthew%20D%2e%20Morrison&item_number=neon%2dsublime%2dtheme&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donate_SM%2egif%3aNonHosted"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif" border="0" name="Donate" alt="PayPal - The safer, easier way to pay online!"></a> -->
<p>
You can also [give on Gittip](https://www.gittip.com/on/github/MattDMo/).
