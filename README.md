django-site
===========
- Installs Django BASH completion
- Creates a user for the app
- Adds the user's group to the groups of www-data user
- Clones the project to a build dir and makes the app user the owner
- Installs an `.env` file
- Installs Python dependencies
- Runs migrations and `collectstatic`
- Copies the site to the deployment path
- Deletes the build dir


Role Variables
==============
| Variable | Description | Default value |
|----------|-------------|---------------|
|`site_app_user`| User running the app | `{{ site_repo_name }}` |
|`site_app_group`| Group of the user running the app | `{{ site_app_user }}` |
|`site_django_bash_completion_url`| URL of the bash completion file for Django | `https://raw.githubusercontent.com/django/django/master/extras/django_bash_completion` |
|`site_django_settings`| Django settings module | `{{ site_repo_name }}.settings` |
|`site_pip_requirements`| Path to the requirements file | `{{ site_build_path }}/requirements/{{ ENV }}.pip` |
|`site_prod_env`| Whether the current deployment is for production | `ENV != development`
|`site_deployment_path`| Path to where the site is deployed | `/var/www/{{ site_repo_name }}` |
|`site_build_path`| Intermediate path used to collect static files | `/tmp/{{ site_repo_name }}` |
|`site_virtualenv`| Path to virtual env used by the site | `{{ python_virtualenvs_dir }}/{{ site_repo_name }}` |


Dependencies
============
- [python](https://github.LucianU/ansible-python)

License
=======
BSD
