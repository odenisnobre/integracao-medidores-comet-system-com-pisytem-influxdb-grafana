
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
Algumas definições nós já temos:
1) Historiadores:
	1.1) PI System OSISoft
	1.2) Influxdb
2) Visualização de dados:
	2.1) Grafana
3) Gateway de conexão/integração:
	3.1) Node-red