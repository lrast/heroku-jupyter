# heroku-jupyter

Use this application to deploy [Jupyter Notebook](https://jupyter.org/) to
heroku. If a postgres database is available,
[pgcontents](https://github.com/quantopian/pgcontents) is used as notebook
storage.
This is my stripped down version using basic environment specification.


## Start

Jupyter notebook will not start until the environment variable
`JUPYTER_NOTEBOOK_PASSWORD` is set. Use a good password:
```
$ heroku config:set JUPYTER_NOTEBOOK_PASSWORD=<your_passwd> -a <your_app>
```

If you are really sure, that you do not want a password protected notebook
server, you can set `JUPYTER_NOTEBOOK_PASSWORD_DISABLED` to `DangerZone!`.

## Environment variables

- `JUPYTER_NOTEBOOK_PASSWORD`: Set password for notebooks
- `JUPYTER_NOTEBOOK_PASSWORD_DISABLED`: Set to `DangerZone!` to disable password
  protection
- `JUPYTER_NOTEBOOK_ARGS`: Additional command line args passed to
  `jupyter notebook`; e.g. get a more verbose logging using `--debug`

## Python version

If you want to use a special python version, you should set it in runtime.txt
