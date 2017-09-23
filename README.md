An Ansible role to configure PyPI mirror for pip and easy_install.

### Dependencies
None

### Tested Environment
* Ansible 2.3
* CentOS 7

### Installation

```
ansible-galaxy install rhops.pypi-mirror
```

### Role Variables
Default values could be  referenced from the [role's defaults directory](defaults/main.yml).

* Use PyPi mirror

```
pypi_index_url: https://pypi.python.org/simple
```

You are free to use any PyPi mirror—`https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple/` for example.

* PyPI search server

```
pypi_search_index: https://pypi.python.org/pypi
```

* Configure PyPI trusted host

```
pypi_trusted_host: ""
```

If https protocol is not supported in your mirror, you should configure this. For example

```
pypi_index_url: http://mirrors.aliyun.com/pypi/simple/
pypi_trusted_host: mirrors.aliyun.com
```

* easy_install users

```
pypi_users: 
  - "{{ ansible_ssh_user }}"
  - root
```

This is a list of easy_install users. Because easy_install uses `~/.pydistutils.cfg` to configure the PyPI server, you have to specify the list of users of easy_install explicitly.

### License
Apache 2.0

### Author Information

This role was created in 2017 by [Jeff Li](https://blog.jeffli.me)
