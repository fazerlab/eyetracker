# Eyetracker
 Rastreamento movimento Olhos, Iris e Cabeça em video em tempo real
 
 # O que é
 O Eyetracker é um aplicativo para a plataforma Windows 10 ou superior que utiliza o video da webcam padrão de um computador PC para detectar em tempo real a localização e posicionamento de olhos, iris e cabeça.
 
 # Objetivo
 Disponibilizar uma aplicação capaz de detectar de forma consistente as coordenadas que indicam a posição da iris e enviar via Websocket essas coordenadas para que aplicações relacionadas a rastreamento de iris e olhos possam ser desenvolvidas.
 
 # Como utilizar
 1. Faça o [download do aplicativo](https://drive.google.com/file/d/18jWRX2f206NDKEwFeZ6oelABps7FRlF4/view?usp=sharing) e descompacte em uma pasta de sua escolha. Execute o arquivos **iris_03.exe**. 
 2. Baixar a pasta cliente dessse repositório e abrir no navegador web o arquivo **cliente_05.html** . O mapa de calor será alterado de acordo com o posicionamento dos olhos.

# Funcionamento e Comunicação
O aplicativo Eyetracker disponibiliza as coordenadas da iris x e y via websocket. O cliente recebe essas mensagens e trata de acordo com o proposito da análise. Abaixo destaque do código do cliente que faz a recepção das mensagens Websocket

```javascript
socket.addEventListener('message', function (event) { 
    //console.log(event.data);  
	const coord = JSON.parse(event.data);
    document.getElementById("coordx").innerHTML =  coord.x;
	document.getElementById("coordy").innerHTML =  coord.y;
```
Aplicações cliente provavelmente necessitarão de procedimentos para calibração de acordo com a distancia do usuário da tela, tamanho da tela , entre outros parâmetros.



  
 
 
 
 
 
