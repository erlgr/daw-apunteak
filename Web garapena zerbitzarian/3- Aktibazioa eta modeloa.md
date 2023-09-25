### Aktibazioa
`settings.py` barruan sartuko gara eta pare bat gauza aldatuko ditugu. Hasteko, `INSTALLED_APPS` barruan gure aplikazioa gehituko dugu, horrelako zerbait geratuko da:
```
INSTALLED_APPS = [  
    'django.contrib.admin',  
    'django.contrib.auth',  
    'django.contrib.contenttypes',  
    'django.contrib.sessions',  
    'django.contrib.messages',  
    'django.contrib.staticfiles', 
    'blog', 
]
```

Eta `TIME_ZONE` aldagaian `'Europe/Madrid'` jarriko dugu.

### Modeloa
Modeloa sortzeko goazen `models.py` fitxategira, hau ia hutsik egongo da.
```
from django.db import models  
  
# Create your models here.  
class Post(models.Model):  
    title = models.CharField(max_length=200)  
    author = models.CharField(max_length=200)  
    body = models.TextField()  
    created_at = models.DateTimeField(auto_now_add=True)  
  
    def __unicode__(self):  
        return self.title
```

### Migrazioak
Eta modelo hau aplikatzeko, komando pare bat exekutatuko ditugu
```
python manage.py makemigrations
python manage.py migrate
```

Jada datu base bat bazeneukan, hau egin dezakezu horren ordez
```
python manage.py inspectdb
```

### [[4- Admin erabiltzailea eta panela|Hurrengo pausua ->]]
