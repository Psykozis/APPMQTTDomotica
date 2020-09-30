#CHAVES PARA CENTRAL DE DOMÓTICA UTILIZANDO MQTT

Na primeira tela há o título, uma solicitação de leitura do contrato, e se de acordo o usuário ao marcar a check box é direcionado para a segunda tela onde é feita a configuração do broker, como exemplo pode ser deixado com os valores default, onde o broker padrão é livre. Ao se clicar em conectar, somos direcionados à ultima página, nela a ‘mágica’ acontece, dividida em três regiões, na parte inferior o botão configurar nos direciona para a página anterior, para ajustes no broker, acima deste são mostradas as configurações após primeira conexão. Acima das configurações está o botão de conectar, quando ele está verde, significa que está conectado e o cliente está acessando ao broker, quando ele está cinza significa que a comunicação foi interrompida, propositalmente ou não, e que é necessário clicar nele novamente para estabelecer nova comunicação. Sempre que estiver conectado, os check boxes da parte superior quando acionados ou des-acionados, enviam valores para os respectivos tópicos (sw1 à sw8 dentro do caminho especificado) que serão acessados pela placa e acionados ou não. Abaixo destes existem sliders que mostram como a informação está no servidor, e como deveria estar na placa e em todos os clientes que estão inscritos neste tópico.

O arquivo para comunicação da NodeMCU deve ser modificado para o correto funcionamento

//----------------WiFi------------------------------------ 

const char* SSID =  "COLOQUE AQUI O NOME DA SUA REDE WI-FI"

const char* PASSWORD = "coloque aqui sua senha"

WiFiClient wifiClient; 

//----------------------Mqtt-------------------------------

const char* BROKER_MQTT = "COLOQUE AQUI A URL DO SEU BROKER (A QUE JÁ ESTÁ NO CÓDIGO FUNCIONA com o modo default do app)";  //broker MQTT URL

int BROKER_PORT = coloque aqui a porta (a que já está no código funciona com o modo default do app );                   // Broker MQTT port



//-------- defines -------------------------------------------

#define ID_MQTT  "COLOQUE AQUI O ID do CLIENTE (qualquer nome, mas necessariamente diferente dos demais conectados)"             //ID for this node

//substitua o seu caminho em  "topico/routeExample/";        (ESTE CAMINHO FUNCIONA COM O MODO DEFAULT DO APP)

//paste your route for the topic in "topico/routeExample/";

const char* substopic[] ={

"topico/routeExample/sw1",   //#0    (sw1~sw8 são os tópicos para o app, porém podem ser modificados para outras aplicações)

"topico/routeExample/sw2",   //#1

"topico/routeExample/sw3",   //#2

"topico/routeExample/sw4",   //#3

"topico/routeExample/sw5",   //#4

"topico/routeExample/sw6",   //#5

"topico/routeExample/sw7",   //#6

"topico/routeExample/sw8"    //#7

};


