`views.py` fitxategian sartu eta horrelako bista sinple bat sortu
```
from django.shortcuts import render  
  
  
# Create your views here.  
def post_list(request):  
    return render(request, 'blog/post_list.html', {})
```

templateak sortzeko bi modu daude
### Pycharm erabiltzen ari bazara
kasu honetan `blog/post_list.html` deitzen den templatea existitzen ez dela esaten badizu, eman `Alt+Enter` kurtsorea horren gainean duzula, eta templates direktorioa eta estruktura berak sortuko dizkizu.
![[5-1.jpg]]
Templates root **ez bada automatikoki betetzen**, sortu `templates` direktorioa proiektuaren erroan
![[5-2.jpg]]

### Modu manuala
Sortu `templates` deitzen den direktorio bat prokektuaren erroan, eta hor barruan sortu hurrengo estruktura hau
![[5-3.jpg]]


### [[6- URLak|Hurrengo pausua ->]]
