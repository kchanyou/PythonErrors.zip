# PythonError.zip
Collection of Python errors and solutions

## Index
- [TypeError: expected str, bytes or os.PathLike object, not int](#ErrorNo.1) <br>
- [ImportError: The requests library is not installed from please install the requests package to use the requests transport.
](#ErrorNo.2)
- [TypeError: Descriptors cannot be created directly.(PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python)
](#ErrorNo.2)

---------------------------------------------------
### ErrorNo.1 <a id="ErrorNo.1"></a> 
#### Env : Win10 / Python3.6<br>
cmd : pip list -> TypeError: expected str, bytes or os.PathLike object, not int

```
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
```

#### Solution : py -m pip install --upgrade pip --no-cache-dir

---------------------------------------------------
### ErrorNo.2  <a id="ErrorNo.2"></a>

#### Env : Win10 / Python3.7<br>
cmd : tensorboard --logdir=path (related to tensorflow) -> ImportError: The requests library is not installed from please install the requests package to use the requests transport.

```
Traceback (most recent call last):
  File "c:\users\usrname\venv\tf2\lib\site-packages\google\auth\transport\requests.py", line 26, in <module>
    import requests
  File "c:\users\usrname\venv\tf2\lib\site-packages\requests\__init__.py", line 43, in <module>
    import urllib3
  File "c:\users\usrname\venv\tf2\lib\site-packages\urllib3\__init__.py", line 42, in <module>
    "urllib3 v2.0 only supports OpenSSL 1.1.1+, currently "
ImportError: urllib3 v2.0 only supports OpenSSL 1.1.1+, currently the 'ssl' module is compiled with 'OpenSSL 1.1.0h  27 Mar 2018'. See: https://github.com/urllib3/urllib3/issues/2168

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "C:\Program Files\Python37\Lib\runpy.py", line 193, in _run_module_as_main
    "__main__", mod_spec)
  File "C:\Program Files\Python37\Lib\runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "c:\users\usrname\venv\tf2\Scripts\tensorboard.exe\__main__.py", line 4, in <module>
  File "c:\users\usrname\venv\tf2\lib\site-packages\tensorboard\main.py", line 27, in <module>
    from tensorboard import default
  File "c:\users\usrname\venv\tf2\lib\site-packages\tensorboard\default.py", line 33, in <module>
    from tensorboard.plugins.audio import audio_plugin
  File "c:\users\usrname\venv\tf2\lib\site-packages\tensorboard\plugins\audio\audio_plugin.py", line 25, in <module>
    from tensorboard.data import provider
  File "c:\users\usrname\venv\tf2\site-packages\tensorboard\data\__init__.py", line 17, in <module>
    from tensorboard.data import experimental  # noqa: F401
  File "c:\users\usrname\venv\tf2\site-packages\tensorboard\data\experimental\__init__.py", line 17, in <module>
    from tensorboard.data.experimental.experiment_from_dev import (  # noqa: F401
  File "c:\users\usrname\venv\tf2\lib\site-packages\tensorboard\data\experimental\experiment_from_dev.py", line 25, in <module>
    from tensorboard.uploader import auth
  File "c:\users\usrname\venv\tf2\lib\site-packages\tensorboard\uploader\auth.py", line 25, in <module>
    import google_auth_oauthlib.flow
  File "c:\users\usrname\venv\tf2\lib\site-packages\google_auth_oauthlib\__init__.py", line 21, in <module>
    from .interactive import get_user_credentials
  File "c:\users\usrname\venv\tf2\lib\site-packages\google_auth_oauthlib\interactive.py", line 24, in <module>
    import google_auth_oauthlib.flow
  File "c:\users\usrname\venv\tf2\lib\site-packages\google_auth_oauthlib\flow.py", line 68, in <module>
    import google.auth.transport.requests
  File "c:\users\usrname\venv\tf2\probuf\lib\site-packages\google\auth\transport\requests.py", line 30, in <module>
    ) from caught_exc
ImportError: The requests library is not installed from please install the requests package to use the requests transport.
```

#### Solution : pip install urllib3==1.26.6 <br>
https://stackoverflow.com/questions/76187256/importerror-urllib3-v2-0-only-supports-openssl-1-1-1-currently-the-ssl-modu

---------------------------------------------------
### ErrorNo.3 <a id="ErrorNo.3"></a> 
#### Env : Win10 / Python3.7<br>
cmd : TensorFlow execution code

```
TypeError: Descriptors cannot be created directly.
If this call came from a _pb2.py file, your generated code is out of date and must be regenerated with protoc >= 3.19.0.
If you cannot immediately regenerate your protos, some other possible workarounds are:
 1. Downgrade the protobuf package to 3.20.x or lower.
 2. Set PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python (but this will use pure-Python parsing and will be much slower)
```

#### Solution : The protobuf 3.16(and more version) package is missing 'builder.py', which is necessary for resolving errors that may occur during the installation and verification of the object detection API. To address this, install Protocol Buffer version 22.0 and then refer to the solution with the most votes at the link provided below.
#### https://stackoverflow.com/questions/71759248/importerror-cannot-import-name-builder-from-google-protobuf-internal<br>
And if you're looking for the location of builder.py, refer to the path below.
```
# Path of builder.py
venv(or conda)dir/Lib/site-packages/google/protobuf/internal
```

-----------------------------------------------------
### ErrorNo.4 <a id="ErrorNo.4"></a> 
#### Env : Win10 / Python3.7<br>
cmd : TensorFlow Object Detection API install code

  Downloading avro-python3-1.9.2.1.tar.gz (37 kB)
  Preparing metadata (setup.py) ... done
Discarding https://files.pythonhosted.org/packages/5a/80/acd1455bea0a9fcdc60a748a97dcbb3ff624726fb90987a0fc1c19e7a5a5/avro-python3-1.9.2.1.tar.gz (from https://pypi.org/simple/avro-python3/) (requires-python:>=3.5): Requested avro-python3 from https://files.pythonhosted.org/packages/5a/80/acd1455bea0a9fcdc60a748a97dcbb3ff624726fb90987a0fc1c19e7a5a5/avro-python3-1.9.2.1.tar.gz (from object-detection==0.1) has inconsistent version: expected '1.9.2.1', but metadata has 'file-.avro-VERSION.txt'
  Downloading avro-python3-1.9.2.tar.gz (37 kB)
  Preparing metadata (setup.py) ... error
  error: subprocess-exited-with-error

  × python setup.py egg_info did not run successfully.
  │ exit code: 1
  ╰─> [6 lines of output]
      Traceback (most recent call last):
        File "<string>", line 36, in <module>
        File "<pip-setuptools-caller>", line 34, in <module>
        File "C:\Users\usrname\AppData\Local\Temp\pip-install-3ods4_97\avro-python3_9fc70627553a4f0abf0833839d23fbe7\setup.py", line 41, in <module>
          import pycodestyle
      ModuleNotFoundError: No module named 'pycodestyle'
      [end of output]

  note: This error originates from a subprocess, and is likely not a problem with pip.
error: metadata-generation-failed

× Encountered error while generating package metadata.
╰─> See above for output.

note: This is an issue with the package mentioned above, not pip.
hint: See above for details.

#### Solution : pip install pycodestyle


-----------------------------------------------------
### ErrorNo.5 <a id="ErrorNo.5"></a> 
#### Env : Win10 / Python3.7<br>
cmd : TensorFlow Object Detection API install code

  Downloading seqeval-1.2.2.tar.gz (43 kB)
     ---------------------------------------- 43.6/43.6 kB ? eta 0:00:00
  Preparing metadata (setup.py) ... error
  error: subprocess-exited-with-error

  × python setup.py egg_info did not run successfully.
  │ exit code: 1
  ╰─> [30 lines of output]
      c:\users\usrname\venv\tf1\lib\site-packages\setuptools\pep425tags.py:89: RuntimeWarning: Config variable 'Py_DEBUG' is unset, Python ABI tag may be incorrect
        warn=(impl == 'cp')):
      c:\users\usrname\venv\tf1\lib\site-packages\setuptools\pep425tags.py:93: RuntimeWarning: Config variable 'WITH_PYMALLOC' is unset, Python ABI tag may be incorrect
        warn=(impl == 'cp')):
      C:\users\usrname\AppData\Local\Programs\Python\Python37\lib\distutils\dist.py:274: UserWarning: Unknown distribution option: 'long_description_content_type'
        warnings.warn(msg)
      Traceback (most recent call last):
        File "<string>", line 36, in <module>
        File "<pip-setuptools-caller>", line 34, in <module>
        File "C:\users\usrname\AppData\Local\Temp\pip-install-tqu3gn5q\seqeval_c998f837783c4ca289538d78bb370dd9\setup.py", line 56, in <module>
          'Programming Language :: Python :: Implementation :: PyPy'
        File "c:\users\usrname\venv\tf1\lib\site-packages\setuptools\__init__.py", line 129, in setup
          return distutils.core.setup(**attrs)
        File "C:\Users\usrname\AppData\Local\Programs\Python\Python37\lib\distutils\core.py", line 108, in setup
          _setup_distribution = dist = klass(attrs)
        File "c:\users\usrname\venv\tf1\lib\site-packages\setuptools\dist.py", line 372, in __init__
          _Distribution.__init__(self, attrs)
        File "C:\Users\usename\AppData\Local\Programs\Python\Python37\lib\distutils\dist.py", line 292, in __init__
          self.finalize_options()
        File "c:\users\usrname\venv\tf1\lib\site-packages\setuptools\dist.py", line 528, in finalize_options
          ep.load()(self, ep.name, value)
        File "c:\users\usrname\venv\tf1\lib\site-packages\pkg_resources\__init__.py", line 2324, in load
          return self.resolve()
        File "c:\users\usrname\venv\tf1\lib\site-packages\pkg_resources\__init__.py", line 2330, in resolve
          module = __import__(self.module_name, fromlist=['__name__'], level=0)
        File "c:\users\usrname\appdata\local\temp\pip-install-tqu3gn5q\seqeval_c998f837783c4ca289538d78bb370dd9\.eggs\setuptools_scm-8.1.0-py3.7.egg\setuptools_scm\__init__.py", line 8, in <module>
          from ._config import DEFAULT_LOCAL_SCHEME
        File "c:\users\usrname\appdata\local\temp\pip-install-tqu3gn5q\seqeval_c998f837783c4ca289538d78bb370dd9\.eggs\setuptools_scm-8.1.0-py3.7.egg\setuptools_scm\_config.py", line 13, in <module>
          from typing import Protocol
      ImportError: cannot import name 'Protocol' from 'typing' (C:\Users\usrname\AppData\Local\Programs\Python\Python37\lib\typing.py)
      [end of output]

  note: This error originates from a subprocess, and is likely not a problem with pip.
error: metadata-generation-failed

× Encountered error while generating package metadata.
╰─> See above for output.

note: This is an issue with the package mentioned above, not pip.
hint: See above for details.

#### Solution : pip install typing-extensions
