Problem: ImportError from Django application when I tried to Dockerize it
```
ImportError: Couldn't import Django. Are you sure it's installed and available on your PYTHONPATH environment variable? Did you forget to activate a virtual environment?
```

Workaround:
Turns out that instead of initializing a virtualenv, I could just put the dependencies into `usr/local` inside Docker container for the application to recognize the installed dependencies. 

Solution:
```
RUN pip install --prefix="/install" -r requirements.txt
COPY /install /usr/local
```
