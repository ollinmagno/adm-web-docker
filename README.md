# Administração de serviços web com docker
![](https://github.com/ollinmagno/adm-web-docker/blob/master/Dockerlab.png)
<br>
Labs : Play with Docker
https://labs.play-with-docker.com

*image: wordpress, mysql:5.7*

**docker-labs**

`git clone https://github.com/ollinmagno/adm-web-docker.git`

`cd admweb/wordpress`

`docker-compose up -d`
_______________________________________________________

**Configuração servidor DNS 17/10/2019**
<ul>
  <li>Consulta recursiva</li>
  <li>Zonas DNS</li>
  <li>Instalação do servidor BIND em um container docker ubuntu</li>
  <li>configuração de uma zona DNS </li>
</ul> 


**1. Criação do container "bind9" a partir de uma imagem "ubuntu" e feita a instalação do servidor bind9 e os editores de texto VIM, NANO e o utilitario dnsutils:**

`$ docker run --name bind9 -it -d ubuntu`

`$ docker exec -it bind9 bash`

`# apt-get update`

`# apt-get install bind9 nano vim dnsutils`


**2. Configuração da zona DNS "coxinhasdadita.com.br":**

`# cd /etc/bind`
`# nano named.conf.local`
