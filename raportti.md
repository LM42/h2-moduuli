#Puppetin ja gitin asentaminen

Tein tämän tehtävän Xubuntu 16.04 amd64 livetikulla.Ensimmäisenä koneen avauduttua kirjauduin githubiin ja loin repositoryn. Repositoryn luomisen jälkeen 
 avasin terminaalin asensin gitin  komennolla sudo apt-get install git. Kloonasin repon komennolla git clone https://github.com/LM42/h2-moduuli.git. 
Asensin puppetin komennolla sudo apt-get install puppet. 


#Moduulin teko
Puppetin  asennuksen jälkeen menin modules kansioon komennolla cd /etc/puppet/modules. Loin apaconf kansion komennolla
sudo mkdir apaconf. Jonka jälkeen tein Manifests kansion komennolla sudo mkdir manifests. Manifests kansioon loin init.pp. Käytin hyödyksi Joona Leppälahden koodipohjaa 
https://joonaleppalahti.wordpress.com/2016/10/24/palvelinten-hallinta-harjoitus-1/.
       
