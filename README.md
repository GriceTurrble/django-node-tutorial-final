# Django Node Tutorial - final version

Final version of a tutorial project demonstrating a basic Django site that integrates a Node/NPM toolchain and TailwindCSS within Django templates.

~~The full tutorial can be found [here](https://galenrice.com/2022/01/20/node-dev-for-the-django-dev.html).~~

## ⚠️ Archived

The project is archived and will no longer be maintained.

## Installation

### Python dependencies

This project uses [Poetry] for dependency management. If you don't have Poetry installed, follow the installation instructions in their GitHub repo for your platform first.

With Poetry installed, simply run:

```shell
poetry install
```

### Node dependencies

Use [NPM] to install Node packages as defined in the `js_toolchain` directory:

```shell
cd js_toolchain
npm install
```

### Django database setup

From the `django_node_example` directory (containing `manage.py` module), run the following to initialize the development database:

```shell
poetry run python manage.py migrate
```

To access the Admin site (http://localhost:8000/admin once the site is running), you must also create a superuser account by running `createsuperuser` command _after_ migrating the database:

```shell
poetry run python manage.py createsuperuser
```

## Starting development server

Use two terminal windows to start the development servers for Django and Tailwind respectively:

- For Django, navigate to the `django_node_example` directory that contains `manage.py` module, then run:

  ```shell
  poetry run python manage.py runserver 8000
  ```

- For Tailwind, navigate to the `js_toolchain` directory and run:

  ```shell
  npm run start
  ```

Open your browser and visit http://localhost:8000, and you should see the contents of [index.html] displayed as a static page.

[index.html]: django_node_example/templates/index.html
[npm]: https://www.npmjs.com/
[poetry]: https://github.com/python-poetry/poetry
