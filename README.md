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


**2. Configuração da zona DNS "exemplo.com.br":**

`# cd /etc/bind`

`# nano named.conf.local`

<a href="https://github.com/ollinmagno/adm-web-docker/named.conf.local">named.conf.local</a>

`# nano db.exemplo.com.br`

<a href="https://github.com/ollinmagno/adm-web-docker/db.exemplo.com.br">db.exemplo.com.br</a>


**3. Verificar se existe algum erro na configuração e na zona DNS criada:**

`# named-checkconf`

`# named-checkzone  exemplo.com.br  db.exemplo.com.br`

*Iniciar o serviço BIND9*

`cd  /etc/init.d`

`./bind9  start`

**4. Verificar, através do utilitário nslookup se a zona DNS criada está funcionando:**

`nslookup  www.exemplo.com.br  127.0.0.1`

**5. Para deixar configurado o servidor de consulta DNS padrão, incluir no arquivo /etc/resolv.conf:**

`nameserver 127.0.0.1`
