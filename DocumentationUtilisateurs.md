## Recettes et exemples ##

### Récupérer les informations d'une série ###
```
>>> import betapy
>>> beta = betapy.Beta()
>>> print beta.shows_display("dexter")
{'show': {u'status': u'Continuing', ...}
```

### Authentification du membre ###
```
>>> import betapy
>>> beta = betapy.Beta(login="dev001", password="developer")
>>> print beta.members_auth()
{u'member': {u'login': u'dev001', u'token': u'aee2fb8d0b9a'}, ...}
```

### Récupération de la liste des derniers sous-titres ###
```
>>> import betapy
>>> beta = betapy.Beta(format="xml")
>>> print beta.subtitles_last()
<?xml version="1.0" encoding="UTF-8"?>
<root>
 <subtitles>
  <subtitle>
   <title>Castle (2009)</title>
   <season>3</season>
   <episode>18</episode>
   ...

```