# Odoo 11.0 Windows Installation
Install odoo-11.0 from source on Windows

### Prerequisite<br />
You must have 64 bit version of operating system.<br />
You must install 64 bit version of following softwares.<br />

Download and install [Git for Windows](https://git-scm.com/download/win).<br />
Download and install [Node.js LTS](https://nodejs.org/en/download/).<br />
<br />
Launch `Command Prompt` as Administrator.
 * Install `Less.js` by `> npm install -g less less-plugin-clean-css`

Download and install [PostgreSQL](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads).<br />
add PostgreSQL's `bin` directory (default: `C:\Program Files\PostgreSQL\x.x\bin`) to your `PATH`.<br />
<br />
create a `postgres` user with a password using the `PgAdmin` GUI:<br />
 * open `PgAdmin4`,
 * expand `server` node to create a connection,
 * expand `PostgreSQL` node,
 * select **Object-> Create -> Login/Group Role**,
    * enter the username in the `Role Name` field (e.g. odoo),
    * open the `Definition` tab and enter the password (e.g. odoo),
    * open the `Privileges` tab and give `login` and `create database` rights,
 * click `save`.

Download and install <a href="https://www.python.org/downloads/" target="_blank">Python3</a> `version 3.6.3` or newer version.<br />
 * goto `Python3` installation directory (default: `C:\Users\UserName\AppData\Local\Programs\Python\PythonXX`.<br />
 * rename `python.exe` to `python3.exe` and `pythonw.exe` to `pythonw3.exe`.<br />
 * add `Python3` installation directory (default: `C:\Users\UserName\AppData\Local\Programs\Python\PythonXX`) to your `PATH`.<br />

Some of `python` dependencies requires `C/C++` compilation during their installation process. you can install those dependencies using one of the following approaches.
 1. Download and install already compiled dependencies in `Wheel (.whl)` format for your system architecture.
 2. Download and install `C/C++` compiler than install those dependencies from `source`.

For installing dependencies from `Wheel (.whl)`, launch `Command Prompt` as Administrator.<br />
 * Install `pypiwin32` by `> python3 -m pip install pypiwin32`
 * Install [`Pillow`](https://github.com/kasim1011/odoo-11.0-windows-installation/blob/master/Pillow-3.4.2-cp36-cp36m-win_amd64.whl) by `> python3 -m pip install Pillow-3.4.2-cp36-cp36m-win_amd64.whl`
 * Install [`gevent`](https://github.com/kasim1011/odoo-11.0-windows-installation/blob/master/gevent-1.2.2-cp36-cp36m-win_amd64.whl) by `> python3 -m pip install gevent-1.2.2-cp36-cp36m-win_amd64.whl`
 * Install [`lxml`](https://github.com/kasim1011/odoo-11.0-windows-installation/blob/master/lxml-3.8.0-cp36-cp36m-win_amd64.whl) by `> python3 -m pip install lxml-3.8.0-cp36-cp36m-win_amd64.whl`
 * Install [`psutil`](https://github.com/kasim1011/odoo-11.0-windows-installation/blob/master/psutil-5.3.1-cp36-cp36m-win_amd64.whl) by `> python3 -m pip install psutil-5.3.1-cp36-cp36m-win_amd64.whl`
 * Install [`psycopg2`](https://github.com/kasim1011/odoo-11.0-windows-installation/blob/master/psycopg2-2.7.3-cp36-cp36m-win_amd64.whl) by `> python3 -m pip install psycopg2-2.7.3-cp36-cp36m-win_amd64.whl`
 * Install [`pyldap`](https://github.com/kasim1011/odoo-11.0-windows-installation/blob/master/pyldap-2.4.37-cp36-cp36m-win_amd64.whl) by `> python3 -m pip install pyldap-2.4.37-cp36-cp36m-win_amd64.whl`
 * Install [`reportlab`](https://github.com/kasim1011/odoo-11.0-windows-installation/blob/master/reportlab-3.4.0-cp36-cp36m-win_amd64.whl) by `> python3 -m pip install reportlab-3.4.0-cp36-cp36m-win_amd64.whl`

For installing dependencies from `source`, download [`Visual C++ 2015 Build Tools`](http://landinghub.visualstudio.com/visual-cpp-build-tools).<br />
 * run the installer,
 * select `custom` mode for installation,
 * uncheck all optional features (including `Windows 8.1 SDK`, `Windows 10 SDK`, `ATL/MFC SDK`, `.NET Framework SDK` and other)
 * click `Install`.<br />

After installation process completes, launch `Command Prompt` as Administrator
 * Install `pypiwin32` by `> python3 -m pip install pypiwin32`
 * Install `Pillow` by `> python3 -m pip install pillow`
 * Install `gevent` by `> python3 -m pip install gevent`
 * Install `lxml` by `> python3 -m pip install lxml`
 * Install `psutil` by `> python3 -m pip install psutil`
 * Install `psycopg2` by `> python3 -m pip install psycopg2`
 * Install `pyldap` by `> python3 -m pip install pyldap`
 * Install `reportlab` by `> python3 -m pip install reportlab`

Install remaining [`requirements`](https://github.com/kasim1011/odoo-11.0-windows-installation/raw/master/requirements.txt) using
 * `$ python3 -m  pip install -r requirements.txt`
 * `$ python3 -m pip install -U werkzeug`

Download and install [wkhtmltopdf](https://wkhtmltopdf.org/downloads.html).<br />
Add wkhtmltopdf's `bin` directory (default: `C:\Program Files\wkhtmltopdf\bin`) to your `PATH`.<br />
<br />
Launch `Command Prompt`.<br />
Switch to (`cd`) your desired `odoo` installation directory<br />
clone `odoo` repository by `git clone https://github.com/odoo/odoo.git -b 11.0`<br />

Switch to `odoo` installation directory and run `odoo` using<br />
`$ python3 odoo-bin -w odoo -r odoo --addons-path=addons --log-level=debug_rpc`<br />
