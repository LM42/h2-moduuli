# Puppetin ja gitin asentaminen

Tein tämän tehtävän Xubuntu 16.04 amd64 livetikulla.Ensimmäisenä koneen avauduttua kirjauduin githubiin ja loin repositoryn. Repositoryn luomisen jälkeen 
 avasin terminaalin asensin gitin  komennolla sudo apt-get install git. Kloonasin repon komennolla git clone https://github.com/LM42/h2-moduuli.git. 
Asensin puppetin komennolla sudo apt-get install puppet. 


# Apache moduulin teko
Puppetin  asennuksen jälkeen menin modules kansioon komennolla cd /etc/puppet/modules. Loin apaconf kansion komennolla
sudo mkdir apaconf. Jonka jälkeen tein Manifests kansion komennolla sudo mkdir manifests. Manifests kansioon loin init.pp. Käytin hyödyksi Joona Leppälahden koodipohjaa 
https://joonaleppalahti.wordpress.com/2016/10/24/palvelinten-hallinta-harjoitus-1/. Ensin kokeilin package osiota. Ajoin moduulin komennolla sudo puppet apply -e  'class{apaconf}'
Apache asentui koneelle. 

Apachen asentumisen jälkeen tein file osion, joka muuttaa apache oletussivun. Koodin muutoksen jälkeen ajoin moduulin komennolla vielä kerran sudo puppet apply -e 'class{apaconf}'.

## Koodi
``` ruby
class apaconf {
 package { apache2:
 ensure => "installed",
 allowcdrom => 'true',

 }

file { "/var/www/html/index.html":
 content => "Hei Maailma\n",
 }
 

 service { "apache2":
 ensure => "running",
 enable => "true",
 }
}
```
# Lähteet
        
http://terokarvinen.com/2016/publish-your-project-with-github
http://terokarvinen.com/2017/aikataulu-%E2%80%93-palvelinten-hallinta-ict4tn022-2-%E2%80%93-5-op-uusi-ops-loppukevat-2017-p2
