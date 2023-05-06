# Lab 4
* ## Install Django and Django REST framework
    ```sh
    (lab4) C:\codes\design 6\iot\lesson4>pip install django 
    (lab4) C:\codes\design 6\iot\lesson4>pip install djangorestframework
    (lab4) C:\codes\design 6\iot\lesson4>pip install django-filter
    (lab4) C:\codes\design 6\iot\lesson4>pip install markdown
    (lab4) C:\codes\design 6\iot\lesson4>pip install requests
    ```
* ## Start Django project "stevens," run server, and view app 
    * ### Start a Django project
        ```sh
        (lab4) C:\codes\design 6\iot\lesson4\stevens>django-admin startproject stevens
        ```
    * ### Start a Django app
        ```sh
        (lab4) C:\codes\design 6\iot\lesson4\stevens>python manage.py startapp myapp
        ```
    * ### Create MySQL database
        ```sh
        (lab4) C:\codes\design 6\iot\lesson4>mysqlsh -u root -p 
        MySQL  localhost:33060+ ssl  SQL > ALTER USER 'root'@'localhost' IDENTIFIED BY '*******'; 
        MySQL  localhost:33060+ ssl  SQL > show databases;
        +--------------------+
        | Database           |
        +--------------------+
        | information_schema |
        | mysql              |
        | performance_schema |
        | sakila             |
        | sys                |
        | world              |
        +--------------------+
        6 rows in set (0.0015 sec)
        MySQL  localhost:33060+ ssl  SQL > create database stevens;
        Query OK, 1 row affected (0.0048 sec)
        MySQL  localhost:33060+ ssl  SQL > grant all privileges on stevens.* to root@localhost;
        Query OK, 0 rows affected (0.0064 sec)
        MySQL  localhost:33060+ ssl  SQL > \quit
        Bye!
        ```
    * ### Edit settings.py in ~/stevens/stevens
        ```py
        """
        Django settings for stevens project.

        Generated by 'django-admin startproject' using Django 4.2.1.

        For more information on this file, see
        https://docs.djangoproject.com/en/4.2/topics/settings/

        For the full list of settings and their values, see
        https://docs.djangoproject.com/en/4.2/ref/settings/
        """

        from pathlib import Path

        # Build paths inside the project like this: BASE_DIR / 'subdir'.
        BASE_DIR = Path(__file__).resolve().parent.parent


        # Quick-start development settings - unsuitable for production
        # See https://docs.djangoproject.com/en/4.2/howto/deployment/checklist/

        # SECURITY WARNING: keep the secret key used in production secret!
        SECRET_KEY = 'django-insecure-_!h&!5-0mpikpfy4mn%qx@qpd6(lwk$gme0bfr_ukiw-7^_gm^'

        # SECURITY WARNING: don't run with debug turned on in production!
        DEBUG = True

        ALLOWED_HOSTS = ['*']


        # Application definition

        INSTALLED_APPS = [
            'django.contrib.admin',
            'django.contrib.auth',
            'django.contrib.contenttypes',
            'django.contrib.sessions',
            'django.contrib.messages',
            'django.contrib.staticfiles',
            'myapp',
        ]

        MIDDLEWARE = [
            'django.middleware.security.SecurityMiddleware',
            'django.contrib.sessions.middleware.SessionMiddleware',
            'django.middleware.common.CommonMiddleware',
            'django.middleware.csrf.CsrfViewMiddleware',
            'django.contrib.auth.middleware.AuthenticationMiddleware',
            'django.contrib.messages.middleware.MessageMiddleware',
            'django.middleware.clickjacking.XFrameOptionsMiddleware',
        ]

        ROOT_URLCONF = 'stevens.urls'

        TEMPLATES = [
            {
                'BACKEND': 'django.template.backends.django.DjangoTemplates',
                'DIRS': [],
                'APP_DIRS': True,
                'OPTIONS': {
                    'context_processors': [
                        'django.template.context_processors.debug',
                        'django.template.context_processors.request',
                        'django.contrib.auth.context_processors.auth',
                        'django.contrib.messages.context_processors.messages',
                    ],
                },
            },
        ]

        WSGI_APPLICATION = 'stevens.wsgi.application'


        # Database
        # https://docs.djangoproject.com/en/4.2/ref/settings/#databases

        DATABASES = {
            'default': {
        #        'ENGINE': 'django.db.backends.sqlite3',
        #        'NAME': BASE_DIR / 'db.sqlite3',    
                'ENGINE': 'django.db.backends.mysql',
                'NAME': 'stevens',
                'USER': 'root',
                'PASSWORD': '********',
                'HOST': '',
                'PORT': '',
                'OPTIONS': {
                    'init_command': "SET sql_mode='STRICT_TRANS_TABLES'",
                },
            }
        }


        # Password validation
        # https://docs.djangoproject.com/en/4.2/ref/settings/#auth-password-validators

        AUTH_PASSWORD_VALIDATORS = [
            {
                'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
            },
            {
                'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
            },
            {
                'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
            },
            {
                'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
            },
        ]


        # Internationalization
        # https://docs.djangoproject.com/en/4.2/topics/i18n/

        LANGUAGE_CODE = 'en-us'

        TIME_ZONE = 'America/New_York'

        USE_I18N = True

        USE_TZ = True


        # Static files (CSS, JavaScript, Images)
        # https://docs.djangoproject.com/en/4.2/howto/static-files/

        STATIC_URL = 'static/'

        # Default primary key field type
        # https://docs.djangoproject.com/en/4.2/ref/settings/#default-auto-field

        DEFAULT_AUTO_FIELD = 'django.db.models.BigAutoField'

        ```
    * ### Copy urls.py to ~/stevens/stevens
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/stevens$ cp /mnt/c/codes/design\ 6/iot/lesson4/stevens/urls.py .
        ```
    * ### Copy admin.py, models.py, and views.py to ~/stevens/myapp
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/stevens/admin.py .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/stevens/models.py .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/stevens/views.py .
        ```
    * ### Copy index.html
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp$ mkdir static templates
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp$ cd templates
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp/templates$ mkdir myapp
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp/templates$ cd myapp
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp/templates/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/stevens/index.html .
        ```
    * ### Edit index.html to add the Google Maps API key
        * Substitute YOUR_API_KEY in index.html with the [API key](https://developers.google.com/maps/documentation/javascript/get-api-key)
    * ### Copy static files
        ```sh
        cp /mnt/c/codes/design\ 6/iot/lesson4/static/favicon.ico .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp/static$ mkdir myapp
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp/static$ cd myapp/
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp/static/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/static/*css .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/stevens/stevens/myapp/static/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/static/*js .
        ```
    * ### createsuperuser
        ```sh
        (lab4) C:\codes\design 6\iot\lesson4\stevens\stevens>python manage.py makemigrations myapp
        Migrations for 'myapp':
            myapp\migrations\0001_initial.py
                - Create model TemperatureData
        (lab4) C:\codes\design 6\iot\lesson4\stevens\stevens>python manage.py migrate  
        Operations to perform:
        Apply all migrations: admin, auth, contenttypes, myapp, sessions
        Running migrations:
        Applying contenttypes.0001_initial... OK
        Applying auth.0001_initial... OK
        Applying admin.0001_initial... OK
        Applying admin.0002_logentry_remove_auto_add... OK
        Applying admin.0003_logentry_add_action_flag_choices... OK
        Applying contenttypes.0002_remove_content_type_name... OK
        Applying auth.0002_alter_permission_name_max_length... OK
        Applying auth.0003_alter_user_email_max_length... OK
        Applying auth.0004_alter_user_username_opts... OK
        Applying auth.0005_alter_user_last_login_null... OK
        Applying auth.0006_require_contenttypes_0002... OK
        Applying auth.0007_alter_validators_add_error_messages... OK
        Applying auth.0008_alter_user_username_max_length... OK
        Applying auth.0009_alter_user_last_name_max_length... OK
        Applying auth.0010_alter_group_name_max_length... OK
        Applying auth.0011_update_proxy_permissions... OK
        Applying auth.0012_alter_user_first_name_max_length... OK
        Applying myapp.0001_initial... OK
        Applying sessions.0001_initial... OK
        (lab4) C:\codes\design 6\iot\lesson4\stevens\stevens>python manage.py createsuperuser  
        Username (leave blank to use 'dorzh'): 
        Email address: ddenisov@stevens.edu
        Password: 
        Password (again):
        Superuser created successfully.
        ```
    * ### Run Django server
        ```sh
        (lab4) C:\codes\design 6\iot\lesson4\stevens\stevens>python manage.py runserver 
        Watching for file changes with StatReloader
        Performing system checks...

        System check identified no issues (0 silenced).
        May 06, 2023 - 03:56:36
        Django version 4.2.1, using settings 'stevens.settings'
        Starting development server at http://127.0.0.1:8000/
        ```
    * ### Go to http://127.0.0.1:8000/admin
        ![](/lab_04/Django%20administration.PNG)
    * ### Click temperature data to add
        ![](/lab_04//Add%20temperature%20data.PNG)
    * ### run Django server at 0.0.0.0:8000
        ```sh
        PS C:\codes\design 6\iot\lesson4\stevens\stevens> python manage.py runserver 0.0.0.0:8000
        Watching for file changes with StatReloader
        Performing system checks...

        System check identified no issues (0 silenced).
        May 06, 2023 - 04:03:31
        Django version 4.2.1, using settings 'stevens.settings'
        Starting development server at http://0.0.0.0:8000/
        Quit the server with CTRL-BREAK.

        ```
    * ### Result
        ![](/lab_04/2023-05-06.png)
* ## Start Django REST project "mycpu," run server, and view app
    * ### Start a Django project
        ```sh
        (lab4) PS C:\codes\design 6\iot\lesson4\mycpu> django-admin startproject mycpu
        (lab4) PS C:\codes\design 6\iot\lesson4\mycpu> cd .\mycpu\
        ```
    * ### Start a Django app
        ```sh
        (lab4) PS C:\codes\design 6\iot\lesson4\mycpu\mycpu> python manage.py startapp myapp
        ```
    * ### Edit settings.py in ~/mycpu/mycpu
        ```sh
        """
        Django settings for mycpu project.

        Generated by 'django-admin startproject' using Django 4.2.1.

        For more information on this file, see
        https://docs.djangoproject.com/en/4.2/topics/settings/

        For the full list of settings and their values, see
        https://docs.djangoproject.com/en/4.2/ref/settings/
        """

        from pathlib import Path

        # Build paths inside the project like this: BASE_DIR / 'subdir'.
        BASE_DIR = Path(__file__).resolve().parent.parent


        # Quick-start development settings - unsuitable for production
        # See https://docs.djangoproject.com/en/4.2/howto/deployment/checklist/

        # SECURITY WARNING: keep the secret key used in production secret!
        SECRET_KEY = 'django-insecure-7m+z1+nennaw0-h9_$_8%kv*d11&8_0ni8#2f=hb#b6pb1#g(o'

        # SECURITY WARNING: don't run with debug turned on in production!
        DEBUG = True

        ALLOWED_HOSTS = ['*']


        # Application definition

        INSTALLED_APPS = [
            'django.contrib.admin',
            'django.contrib.auth',
            'django.contrib.contenttypes',
            'django.contrib.sessions',
            'django.contrib.messages',
            'django.contrib.staticfiles',
            'myapp',
            'rest_framework',
        ]

        MIDDLEWARE = [
            'django.middleware.security.SecurityMiddleware',
            'django.contrib.sessions.middleware.SessionMiddleware',
            'django.middleware.common.CommonMiddleware',
            'django.middleware.csrf.CsrfViewMiddleware',
            'django.contrib.auth.middleware.AuthenticationMiddleware',
            'django.contrib.messages.middleware.MessageMiddleware',
            'django.middleware.clickjacking.XFrameOptionsMiddleware',
        ]

        ROOT_URLCONF = 'mycpu.urls'

        TEMPLATES = [
            {
                'BACKEND': 'django.template.backends.django.DjangoTemplates',
                'DIRS': [],
                'APP_DIRS': True,
                'OPTIONS': {
                    'context_processors': [
                        'django.template.context_processors.debug',
                        'django.template.context_processors.request',
                        'django.contrib.auth.context_processors.auth',
                        'django.contrib.messages.context_processors.messages',
                    ],
                },
            },
        ]

        WSGI_APPLICATION = 'mycpu.wsgi.application'


        # Database
        # https://docs.djangoproject.com/en/4.2/ref/settings/#databases

        DATABASES = {
            'default': {
                'ENGINE': 'django.db.backends.sqlite3',
                'NAME': BASE_DIR / 'db.sqlite3',
            }
        }


        # Password validation
        # https://docs.djangoproject.com/en/4.2/ref/settings/#auth-password-validators

        AUTH_PASSWORD_VALIDATORS = [
            {
                'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
            },
            {
                'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
            },
            {
                'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
            },
            {
                'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
            },
        ]


        # Internationalization
        # https://docs.djangoproject.com/en/4.2/topics/i18n/

        LANGUAGE_CODE = 'en-us'

        TIME_ZONE = 'America/New_York'

        USE_I18N = True

        USE_TZ = True


        # Static files (CSS, JavaScript, Images)
        # https://docs.djangoproject.com/en/4.2/howto/static-files/

        STATIC_URL = 'static/'

        # Default primary key field type
        # https://docs.djangoproject.com/en/4.2/ref/settings/#default-auto-field

        DEFAULT_AUTO_FIELD = 'django.db.models.BigAutoField'

        ```
    * ### Copy urls.py to ~/mycpu/mycpu
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/mycpu$ cp /mnt/c/codes/design\ 6/iot/lesson4/mycpu/urls.py .
        ```
    * ### Copy admin.py, models.py, views.py, and serializers.py to ~/mycpu/myapp
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/mycpu/admin.py .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/mycpu/models.py .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/mycpu/views.py .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/mycpu/serializers.py .
        ```
    * ### Change the default password 'admin' in views.py
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp$ nano views.py
        ```
    * ### Copy index.html
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp$ mkdir static templates
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp$ cd templates
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/templates$ mkdir myapp
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/templates$ cd myapp
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/templates/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/mycpu/index.html .
        ```
    * ### Edit index.html to add the Google Maps API key
        * Substitute YOUR_API_KEY in index.html with the [API key](https://developers.google.com/maps/documentation/javascript/get-api-key)
    * ### Copy static files
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/static$ cp /mnt/c/codes/design\ 6/iot/lesson4/static/favicon.ico .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/static$ mkdir myapp
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/static$ cd myapp
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/static/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/static/*css .
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu/myapp/static/myapp$ cp /mnt/c/codes/design\ 6/iot/lesson4/static/*js .
        ```
    * ### Copy controller.py to ~/mycpu
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu$ cp /mnt/c/codes/design\ 6/iot/lesson4/mycpu/controller.py .
        ```
    * ### Change the default password 'admin' in controller.py
        ```sh
        senku@Senku:/mnt/c/codes/design 6/iot/lesson4/mycpu/mycpu$ nano controller.py
        ```
    * ### createsuperuser
        ```sh
        (lab4) PS C:\codes\design 6\iot\lesson4\mycpu\mycpu> python manage.py makemigrations myapp
        Migrations for 'myapp':
        myapp\migrations\0001_initial.py
            - Create model Cpu
            - Create model Dt
            - Create model LocationData
            - Create model Mem
        (lab4) PS C:\codes\design 6\iot\lesson4\mycpu\mycpu> python manage.py migrate
        Operations to perform:
        Apply all migrations: admin, auth, contenttypes, myapp, sessions
        Running migrations:
        Applying contenttypes.0001_initial... OK
        Applying auth.0001_initial... OK
        Applying admin.0001_initial... OK
        Applying admin.0002_logentry_remove_auto_add... OK
        Applying admin.0003_logentry_add_action_flag_choices... OK
        Applying contenttypes.0002_remove_content_type_name... OK
        Applying auth.0002_alter_permission_name_max_length... OK
        Applying auth.0003_alter_user_email_max_length... OK
        Applying auth.0004_alter_user_username_opts... OK
        Applying auth.0005_alter_user_last_login_null... OK
        Applying auth.0006_require_contenttypes_0002... OK
        Applying auth.0007_alter_validators_add_error_messages... OK
        Applying auth.0008_alter_user_username_max_length... OK
        Applying auth.0009_alter_user_last_name_max_length... OK
        Applying auth.0010_alter_group_name_max_length... OK
        Applying auth.0011_update_proxy_permissions... OK
        Applying auth.0012_alter_user_first_name_max_length... OK
        Applying myapp.0001_initial... OK
        Applying sessions.0001_initial... OK
        (lab4) PS C:\codes\design 6\iot\lesson4\mycpu\mycpu> python manage.py createsuperuser
        Username (leave blank to use 'dorzh'): 
        Email address: ddenisov@stevens.edu
        Password: 
        Password (again):
        Superuser created successfully.
        ```
    * ### Run Django server
        ```sh
        (lab4) PS C:\codes\design 6\iot\lesson4\mycpu\mycpu> python manage.py runserver
        Watching for file changes with StatReloader
        Performing system checks...

        System check identified no issues (0 silenced).
        May 06, 2023 - 05:22:03
        Django version 4.2.1, using settings 'mycpu.settings'
        Starting development server at http://127.0.0.1:8000/
        Quit the server with CTRL-BREAK.
        ```
    * ### Add location data - Stevens
        ![](/lab_04/Add%20location%20data%20stevens.PNG)
    * ### Add location data - Xidian
        ![](/lab_04/Add%20location%20data%20Xidian.PNG)
    * ### Post Dt list
        ![](/lab_04/dt%20list.PNG)
    * ### Post cpu list 
        ![](/lab_04/cpu%20list.PNG)
    * ### Post mem list
        ![](/lab_04/mem%20list.PNG)
    * ### Run native controller service on a separate terminal window
        ```sh
        (lab4) C:\codes\design 6\iot\lesson4\mycpu\mycpu>python controller.py
        2023-05-06 05:30:09
        CPU Usage:        12.5%
        Memory Available: 8.2 GB
        ```

    * ### Result 
        ![](/lab_04/2023-05-06-cpu.png)
* # Run Flask server via hello_world.py and view app
    * ## Run Flask server
    ```
    (lab4) PS C:\codes\design 6\iot\lesson4> python hello_world.py
    * Serving Flask app 'hello_world'
    * Debug mode: off
    WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
    * Running on http://127.0.0.1:5000
    ```
    * ## Result
    ![](/lab_04/Flask.PNG)