`admin.py` fitxategian horrelako zerbait idatzi behar da zure modeloaren arabera
```
from django.contrib import admin  
from blog.models import Post  
  
  
# Register your models here.  
class PostAdmin(admin.ModelAdmin):  
    list_display = ('title', 'author', 'created_at')  
    search_fields = ('title', 'author')  
    ordering = ('-created_at',)  
  
  
admin.site.register(Post, PostAdmin)
```

Eta horren ondoren admin erabiltzailea sortuko dugu terminaletik
```
python manage.py createsuperuser
```

Egiaztatzeko, sartu [localhost:8000/admin](localhost:8000/admin)-era, eta egin logina hor.

### [[5- Bistak sortzen|Hurrengo pausua ->]]
