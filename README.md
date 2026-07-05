# Projeto-eletronica-USP-Arduino

## Projeto 2: Sensor de ré

Projeto da disciplina de Eletrônica para computação desenvolvida pelos alunos da USP São Carlos do curso de Ciências de Computação. O projeto tem como objetivo o desenvolvimento de um sistema embarcado de assistência à manobra (sensor de ré), integrando hardware e software para a detecção automatizada de obstáculos em tempo real. O sistema utiliza um sensor ultrassônico para a aquisição de dados de distância, processados por um microcontrolador que gerencia as interfaces de saída: um display OLED para exibição métrica, LEDs indicadores para alertas visuais progressivos e um sinalizador sonoro (buzzer) para advertências acústicas de proximidade.

## Componentes
| Componente                | Qtd           |       Valor       |
|---------------------------|:-------------:|:-----------------:|
|LED’s (verde e vermelho)   | 4             |R$ 0,50 x 4 = R$ 2,00|
|Resistores de 330 Ohms     | 4             |R$  0,07 x 4 = R$ 0,28|
|Buzzer                     | 1             |R$ 9,70            |
|Arduino UNO                | 1             |Emprestado         |
|Sensor Ultrassônico        | 1             |R$ 16,00           |
|Protoboard                 | 1             |R$ 23,80           |
|Display OLED 128x64        | 1             |R$ 34,00           |
|Total:                     | 13             |R$ 85,78          |

## Descrição dos Componentes:

### Sensor Ultrassônico

A função do sensor ultrassônico é a de medir a distância entre o sistema e o obstáculo presente no percurso. Ele realiza essa medição emitindo uma onda sonora de alta frequência (ultrassom) que viaja pelo ar, colide com o obstáculo e retorna ao sensor; o componente calcula o tempo de ida e volta desse eco para determinar, com precisão, a distância em centímetros.

### Display OLED 128x64

O display utilizado possui a função de Interface Homem-Máquina (IHM), atuando como o visor principal do sistema. Ele é responsável por exibir textualmente e em tempo real o valor exato da distância medida pelo sensor (ex: "Distância: 30 cm"), além de permitir a renderização de alertas visuais gráficos e mensagens de advertência para o usuário.

### LEDs (Verde e Vermelho)

Os LEDs de 5mm possuem a função de sinalização visual rápida e intuitiva baseada na proximidade do obstáculo. Eles são associados à lógica do código de forma que o LED verde permaneça aceso quando o objeto estiver a uma distância segura, enquanto o LED vermelho é acionado (ou pisca intermitentemente) quando o objeto entra na zona crítica de colisão.

### Resistor 330 Ohms

Estes componentes possuem a função de limitação de corrente elétrica (proteção) para os LEDs do circuito. Como as portas digitais do Arduino fornecem uma tensão de 5V — valor superior à tensão de operação suportada pelos LEDs —, os resistores de 330 Ohms são associados em série com cada LED para evitar a queima dos diodos e proteger as portas do microcontrolador.

### Sonalarme (Buzzer)

O sonalarme de 3V a 7V tem a função de emitir a sinalização sonora de emergência do sistema de ré. Ele atua de forma complementar aos LEDs, emitindo bipes intermitentes cuja frequência (velocidade do "bip") aumenta progressivamente à medida que a distância até o obstáculo diminui, tornando-se um som contínuo quando o veículo atinge o limite mínimo de segurança.

### Protoboard

A protoboard (matriz de contatos) possui a função de base de prototipagem rápida e interconexão elétrica dos componentes. Ela permite que o Arduino, o sensor, o display, os resistores, o buzzer e os LEDs sejam conectados entre si através de jumpers de forma segura e sem a necessidade de soldagem, facilitando testes, medições e modificações estruturais durante o desenvolvimento do projeto.

## Cálculos utilizados

### Cálculo de distância:

Para calcular a distância real até o obstáculo, o sistema utiliza a seguinte equação de movimento uniforme adaptada:

$$distancia = \frac{time \times 10^{-6} \times som}{2}$$

Onde:
* **time**: Tempo de ida e volta do pulso em microsegundos ($\mu s$).
* **0.000001 ($10^{-6}$)**: Fator de conversão de microsegundos para segundos.
* **som**: Velocidade do som no ar (ex: $343\text{ cm/s}$).
* **2**: Divisor necessário para desconsiderar o tempo de volta (eco) do som.

## Vídeo do projeto
https://youtu.be/9TrQdXB9II0

## Imagens do projeto
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/bf9b9667-a262-4ca6-96a2-e281a6aabab4" />
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/cdfcac68-10ee-4c91-81f3-eabd3165db98" />

## Alunos
- Adilson Armando Miguel NºUSP: 17379918
- Gabriel Galli Brandini NºUSP: 16985392
- Mateus Augusto Coutinho Rezende NºUSP: 15753450
- Pedro Iori Garcia NºUSP: 17839261

## Agradecimentos
O projeto foi bastante enriquecedor, pois consolidou o conteúdo aprendido na disciplina de eletrônica durante o semestre.
Agradecer ao professor Simões pelo auxilio no aprendizado e no precesso de elaboração do projeto em questão!
