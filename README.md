# PythonError.zip
Collection of Python errors and solutions

## Index
[TypeError: expected str, bytes or os.PathLike object, not int](#ErrorNo.1)
[ImportError: The requests library is not installed from please install the requests package to use the requests transport.
](#ErrorNo.2)

---------------------------------------------------
#### ErrorNo.1

Env : Win10 / Python3.6<br>
cmd : pip list -> TypeError: expected str, bytes or os.PathLike object, not int

Traceback (most recent call last):
  File "C:\Program Files\Python36\lib\runpy.py", line 193, in _run_module_as_main
    "__main__", mod_spec)
  File "C:\Program Files\Python36\lib\runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "C:\Users\usrname\venv\tf1\Scripts\pip.exe\__main__.py", line 9, in <module>
  File "c:\users\usrname\venv\tf1\lib\site-packages\pip\__init__.py", line 233, in main
    return command.main(cmd_args)
  File "c:\users\usrname\venv\tf1\lib\site-packages\pip\basecommand.py", line 251, in main
    timeout=min(5, options.timeout)) as session:
  File "c:\users\usrname\venv\tf1\lib\site-packages\pip\basecommand.py", line 69, in _build_session
    if options.cache_dir else None
  File "C:\Program Files\Python36\lib\ntpath.py", line 75, in join
    path = os.fspath(path)
TypeError: expected str, bytes or os.PathLike object, not int

#### Solution : py -m pip install --upgrade pip --no-cache-dir

---------------------------------------------------
#### ErrorNo.2

Env : Win10 / Python3.7<br>
cmd : tensorboard --logdir=path (related to tensorflow) -> ImportError: The requests library is not installed from please install the requests package to use the requests transport.


Traceback (most recent call last):
  File "c:\probuf\lib\site-packages\google\auth\transport\requests.py", line 26, in <module>
    import requests
  File "c:\probuf\lib\site-packages\requests\__init__.py", line 43, in <module>
    import urllib3
  File "c:\probuf\lib\site-packages\urllib3\__init__.py", line 42, in <module>
    "urllib3 v2.0 only supports OpenSSL 1.1.1+, currently "
ImportError: urllib3 v2.0 only supports OpenSSL 1.1.1+, currently the 'ssl' module is compiled with 'OpenSSL 1.1.0h  27 Mar 2018'. See: https://github.com/urllib3/urllib3/issues/2168

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "C:\Program Files\Python37\Lib\runpy.py", line 193, in _run_module_as_main
    "__main__", mod_spec)
  File "C:\Program Files\Python37\Lib\runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "C:\probuf\Scripts\tensorboard.exe\__main__.py", line 4, in <module>
  File "c:\probuf\lib\site-packages\tensorboard\main.py", line 27, in <module>
    from tensorboard import default
  File "c:\probuf\lib\site-packages\tensorboard\default.py", line 33, in <module>
    from tensorboard.plugins.audio import audio_plugin
  File "c:\probuf\lib\site-packages\tensorboard\plugins\audio\audio_plugin.py", line 25, in <module>
    from tensorboard.data import provider
  File "c:\probuf\lib\site-packages\tensorboard\data\__init__.py", line 17, in <module>
    from tensorboard.data import experimental  # noqa: F401
  File "c:\probuf\lib\site-packages\tensorboard\data\experimental\__init__.py", line 17, in <module>
    from tensorboard.data.experimental.experiment_from_dev import (  # noqa: F401
  File "c:\probuf\lib\site-packages\tensorboard\data\experimental\experiment_from_dev.py", line 25, in <module>
    from tensorboard.uploader import auth
  File "c:\probuf\lib\site-packages\tensorboard\uploader\auth.py", line 25, in <module>
    import google_auth_oauthlib.flow
  File "c:\probuf\lib\site-packages\google_auth_oauthlib\__init__.py", line 21, in <module>
    from .interactive import get_user_credentials
  File "c:\probuf\lib\site-packages\google_auth_oauthlib\interactive.py", line 24, in <module>
    import google_auth_oauthlib.flow
  File "c:\probuf\lib\site-packages\google_auth_oauthlib\flow.py", line 68, in <module>
    import google.auth.transport.requests
  File "c:\probuf\lib\site-packages\google\auth\transport\requests.py", line 30, in <module>
    ) from caught_exc
ImportError: The requests library is not installed from please install the requests package to use the requests transport.

#### Solution : pip install urllib3==1.26.6 <br>
https://stackoverflow.com/questions/76187256/importerror-urllib3-v2-0-only-supports-openssl-1-1-1-currently-the-ssl-modu
