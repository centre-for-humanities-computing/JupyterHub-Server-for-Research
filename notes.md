# Installation of JupyterHub with dynamic user creation and isolated namespaces

## NodeJS

_enabiling node source_  
```
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
```

_installing node_  
```
sudo apt install nodejs
```

## Making Python3 default

_suggest using Python3 for python commands (and pip3 for pip)_  
```
update-alternatives --install /usr/bin/python python /usr/bin/python3 12
```

## JupyterHub

_use pip to install jupyterhub_  
```
python3 -m pip install jupyterhub
```

_install http server_
```
npm install -g configurable-http-proxy
```

_install local notebook server_
```
python3 -m pip install notebook
```

_create jupyterhub config file at ~/jupyterhub_config.py_
```
jupyterhub --generate-config
```

_configure jupyterHub_
```
nano jupyterhub_config.py
```

_config settings_
```python
c.JupyterHub.active_server_limit = 32           # limit concurrent users
c.JupyterHub.bind_url = 'http://128.0.0.1:80'   # expose service to load balancer on port 80

```
