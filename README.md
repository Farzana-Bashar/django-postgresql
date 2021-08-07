   $   pipenv install django

    $   pipenv shell 

    $   django-admin startproject myproject

    $   cd myproject

    $   python manage.py migrate  //for db

    $   python manage.py runserver  //for run server

    $   django-admin startapp demoproject  // to start app
don't forget tow add the 'app'(demoproject) in settings.py - INSTALLED_APPS

Write the model in models.py file then migrate:

    $ python manage.py makemigrations
It will create a model file in migrations folder

    $ python manage.py migrate  
It will migrate the table to the db

### ADD Data in DB
    $  python manage.py shell  
One interactive shell appears

    $ from demoproject.models import Company
    $ facebook = Company(name= 'Facebook', sub_name= 'facebook.com')
    $ facebook.save()


>>> from demoproject.models import Programmer, Company
>>> google= Company.objects.get(pk=1)
>>> facebook= Company.objects.get(name='Facebook')
>>> shajal = Programmer(name='shajal', company=google)
>>> zerin = Programmer(name='zerin', company=facebook)
>>> shajal.save()
>>> zerin.save()
>>> google.programmer_set.all()
<QuerySet [<Programmer: shajal>]>
