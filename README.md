# Python_Error.zip
Collection of Python errors and solutions

---------------------------------------------------

Win10 / Python3.6
cmd : pip list

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
