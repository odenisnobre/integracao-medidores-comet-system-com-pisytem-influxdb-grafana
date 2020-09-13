
<h1 align="center">
<br>
Integração Medidores Comet System com PI System, Influxdb e Grafana
</h1>

Integração medidores da [Comet System](https://www.cometsystem.com/) com historiador da OSISoft - PI System - e visualizar os mesmos através do Grafana. Expandindo também as funcionalidades mostrando també como enviar os mesmos dados para Influxdb para serem historizados também.

<p align="center">
  <a href="https://www.apache.org/licenses/LICENSE-2.0">
    <img src="https://img.shields.io/badge/apache-2.0-blue" alt="License Apache">
  </a>
</p>


<div align="center">
  <img src="https://github.com/dedynobre/integracao-medidores-comet-system-com-pisytem-influxdb-grafana/blob/master/imagem1.png" alt="comet-system" height="250" width="700">
</div>

<hr /> 

## Desenvolvimento

Que a conectividade está vindo para facilitar a visualização e disponibilização dos dados isto já é realidade em vários segmentos como um todos.
Cada dia mais instrumentos e medidores estão sendo equipados com interfaces web de programação e visualização de dados com isso sendo conectados diretamente a redes corporativas ou redes do tipo DMZ de modo que estes valores seja disponibilizados para outros sistemas e/ou ferramentas.
Um exemplo disso é o sensor modelo [T3510](https://www.cometsystem.com/products/web-sensor-remote-thermometer-hygrometer-with-ethernet-interface/reg-t3510#manuals) da Comet Sytem:

<div>
  <img src="https://github.com/dedynobre/integracao-medidores-comet-system-com-pisytem-influxdb-grafana/blob/master/imagem2.png" alt="comet-system" height="250" width="500">
</div>


O T3510 além de possuir uma interface web para parametrização e visualização:
<div>
  <img src="https://github.com/dedynobre/integracao-medidores-comet-system-com-pisytem-influxdb-grafana/blob/master/imagem5.png" alt="comet-system" height="250" width="500">
</div>

Possui também dois protocolos principais para consultas e integração disponíveis:

1) **SOAP**: que se encontra desabilitado para este caso em específico
	<div>
		<img src="https://github.com/dedynobre/integracao-medidores-comet-system-com-pisytem-influxdb-grafana/blob/master/imagem4.png" alt="comet-system" height="250" width="400">
	</div>
2) **Modbus TCP**: que será nosso caso de estudo
	<div>
		<img src="https://github.com/dedynobre/integracao-medidores-comet-system-com-pisytem-influxdb-grafana/blob/master/imagem3.png" alt="comet-system" height="250" width="400">
	</div>
	
Com todas essas informações já podemos partir para as configurações.
Com as ferramentas definidas, temos a seguinte situação configurada e rodando em um mesmo servidor Windows Server 2016:
+ Historiadores:
	+ PI System - OSISoft
	+ Influxdb
+ Visualização de dados:
	+ Grafana
+ Gateway de conexão/integração:
	+ Node-red
	
O Node-red será nosso orquestrador de dados, ou seja, ele que irá fazer as consultas e envio de informações.
Para envio dos dados para o PI System iremos utilizar o PI Web API. Aqui no meu github tem vários diretórios mostrando o uso do PI Web API.
Vamos focar mais no envido dados para o Influxdb.

A configuração de integração via Modbus fica conforme imagem abaixo:
<div>
  <img src="https://github.com/dedynobre/integracao-medidores-comet-system-com-pisytem-influxdb-grafana/blob/master/imagem6.png" alt="comet-system" height="250" width="1000">
</div>

A configuração Modbus fica da seguinte forma:

<div>
  <img src="https://github.com/dedynobre/integracao-medidores-comet-system-com-pisytem-influxdb-grafana/blob/master/imagem7.png" alt="comet-system" height=500" width="300">
</div>


O bloco marcado acima é a extração dos dados de temperatura e umidade e envio para PI Web API.

Os blocos a parte são o envio dos dados para o Influxdb.


