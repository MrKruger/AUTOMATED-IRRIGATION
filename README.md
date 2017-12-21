# Irrigation

Este programa é um projeto de automação de irrigação para jardins e hortas residenciais. Seu funcionamento é simples e consiste basicamente de um sensor de umidade do solo que realiza a leitura de umidade correspondente e se o solo estiver seco, o sistema de irrigação é acionado automaticamente, permanecendo ligado até que o sensor de umidade do solo detecte que o solo está em um nível de umidade aceitável. Além disso, o software conta ainda com mais outros periféricos que complementam o sistema como um todo sendo eles, um sensor de umidade e temperatura do ar (DHT22), um sensor de chuva, um sensor de vazão, um RTC (Real Time Clock), um display TFT, uma placa de reles e uma válvula solenóide (127v). Os pinos do Arduino podem ser setados da forma que o usuário preferir, porém nesse projeto eles foram adotados da seguinte forma.:

PINOS               | DESCRIÇÃO     
------------------- | -------------------
A0 - A4             | Display TFT                        
A8                  | Sensor Umi. Do Solo    
A9                  | Sensor de Chuva               
39,41,43            | LEDs                      
42,44,46,48         | Reles                         
25                  | Sensor Umi. Do Solo           
35                  | Sensor Umi. e Temp.                      
18                  | Sensor de Vazão
                                                      

## Instalação do Hardware

* **ARDUINO**: Qualquer Arduino que tenha portas suficientes para todos os pinos usados no projeto pode ser utilizado. Normalmente todo Arduino vem com um cabo usb para transferência do código fonte e com uma fonte própria. Para a alimentação do Arduino pode-se utilizar a própria fonte. 

* **ATUADORES**: Os atuadores ou acionadores do projeto são os LEDs, os Reles, o Display TFT e a Válvula Solenóide. Entre eles o único dispositivo eletrônico que não é alimentado com a fonte do Arduino é a válvula solenóde que é alimentada com 127v e pode ser conectada em qualquer tomada existente em uma residência.

* **SENSORES**: Todos os sensores utilizados no projeto são alimentados diretamente pelo próprio Arduino.

* **CONEXÕES**: Todas as conexãos foram feitas através de jumpers e consistem basicamente em conectar os Sensores e Atuadores nas portas do Arduino indicadas, com exceção da Válvula. 

* **AQUISIÇÃO**: Os dispositivos utilizados podem ser adquiridos nos seguintes links.: 

  O Arduino utilizado está disponível em: https://www.filipeflop.com/categoria/arduino/placas-arduino

  O Sensor de Umidade e Temperatura do ar está disponível em: https://www.filipeflop.com/produto/sensor-de-umidade-e-temperatura-am2302-dht22/

  O Sensor de Umidade do Solo está disponível em: https://www.filipeflop.com/produto/sensor-de-umidade-do-solo-higrometro/
  
  O Sensor de Chuva está disponível em: https://www.filipeflop.com/produto/sensor-de-chuva/
  
  O RTC está disponível em: https://www.filipeflop.com/produto/real-time-clock-rtc-ds3231/
  
  O Display TFT está disponível em: https://www.filipeflop.com/produto/display-lcd-tft-2-4-touchscreen-shield-para-arduino/
  
  O Sensor de Fluxo de Água (Vazão) está disponível em: https://www.filipeflop.com/produto/sensor-de-fluxo-de-agua-12-yf-s201/
  
  O Módulo de Reles está disponível em: https://www.filipeflop.com/produto/modulo-rele-5v-4-canais/
  
  A Válvula Solenóide está disponível em: https://www.robocore.net/loja/produtos/valvula-solenoide.html?gclid=CjwKCAiA1O3RBRBHEiwAq5fD_Ji8pe4oEz5zEdmFKV6J3wZkX4DNm15WJ1-pdGp8pCQ0pkSMBAAFyhoCKsQQAvD_BwE
  

## Instalação do Software

* **BAIXAR O PROGRAMA**: Para baixar o código, aperte o botão de download ou clone via terminal ou cmd.:

   ```git
   git clone https://github.com/MrKruger/IRIS-VIRTUAL-HOME-ASSISTANT.git
   ```

* **BAIXAR O PYTHON**: Baixe e instale a última versão da linguagem python pelo site oficial. Não se esqueça de deixar a opção "Add Python 3.6 to PATH" marcada.: https://www.python.org/downloads/.


   OBS: Iris tem uma função para enviar emails com o módulo SMTP cujo qual funcionou apenas nas versões do Python 2.7 e 3.5 (de acordo com testes realizados por mim), dessa forma, se a opção de enviar emails for desejada, é indicado que o usuário impreterívelmente baixe a versão do Python 3.5.

* **BAIXAR OS MÓDULOS NECESSÁRIOS**: Para que Iris funcione corretamente é necessário instalar os móduclos adicionais que estão no arquivo Requirements.txt. Para fazer isso você precisa abrir o terminal ou cmd na pasta aonde se encontra o arquivo e digitar o seguinte comando.:

   ```py
   pip install -r Requirements.txt
   ```

* **CONFIGURAR O MICROFONE**: Iris precisa de um microfone para poder ouvir e entender os comandos de voz. Como existem várias entradas e saídas de áudio no computador, é necessário que o usuário selecione qual microfone (entrada de áudio) gostaria de usar. Assim, se torna necessário executar um programa para listar as entradas e saídas de áudio disponíveis no computador aonde Iris está sendo executada. Após a executação do código, será mostrado a lista de microfones disponíveis no computador, juntamente com as saídas de áudio, então o usuário precisa copiar qual microfone deseja utilizar e colar na linha de código do programa principal "Mic_Name = "NOME QUE APARECEU NA EXECUÇÃO DO ARQUIVO IrisMicList.py". É obrigatório copiar e colar o nome exatamente igual conforme apareceu no programa e entre aspas duplas. Para rodar o código, basta executar o seguinte comando.: 

   ```py
   python IrisMicList.py
   ```

* **EXECUTAR O CÓDIGO PRINCIPAL**: Após baixar e instalar o python juntamente com os módulos necessários, abra o terminal ou o cmd e vá até a pasta aonde se encontra o código fonte já descompactado e digite.:

   ```py 
   python Iris_VHA.py
   ```

O código será executado.

É isso, boa diversão!    
