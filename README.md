# Protótipo de Sensor para Estacionamento em Garagem

O projeto utiliza um sensor ultrassônico para detectar a proximidade de um objeto, como um carro, e aciona sinais visuais e sonoros para indicar a distância.

## Configuração

### Distância Mínima
A distância mínima para acionar o alerta está configurada em **10 centímetros**. Essa distância pode ser ajustada conforme necessário, modificando a constante `distancia_carro` no início do código.

```cpp
const int distancia_carro = 10;
```

### Configurações de Pinagem

As portas do Arduino estão configuradas da seguinte maneira:

- Sensor Ultrassônico:
  - **TRIG (Trigger):** Pino 3
  - **ECHO (Echo):** Pino 2

- LEDs:
  - **ledGreen:** Pino 7
  - **ledRed:** Pino 8

- Buzzer:
  - **buzzer:** Pino 9

## Funcionamento

O código no loop principal realiza as seguintes operações:

1. **Leitura da Distância:**
   - Utiliza a função `sensor_morcego` para obter a distância em centímetros entre o sensor ultrassônico e o objeto.

2. **Avaliação da Distância:**
   - Se a distância for menor ou igual à distância configurada (`distancia_carro`), indica um alerta de proximidade.
   - Caso contrário, indica que o espaço está livre.

3. **Sinalização Visual e Sonora:**
   - Aciona LEDs e um buzzer conforme a situação.

## Funções Adicionais

### Função `sensor_morcego`
```cpp
int sensor_morcego(int pinotrig, int pinoecho);
```

Esta função utiliza o sensor ultrassônico para medir a distância. Ela recebe os pinos `TRIG` e `ECHO` como parâmetros e retorna a distância em centímetros.

### Função `tocaBuzzer`
```cpp
void tocaBuzzer();
```

Esta função é responsável por gerar um som de alerta quando a distância mínima é detectada. Ela utiliza a função `tone` do Arduino para gerar um som modulado.

## Configuração da Comunicação Serial

O programa também fornece informações úteis por meio da comunicação serial, como a distância atual medida pelo sensor.

```cpp
Serial.begin(9600);
```

A comunicação serial está configurada para uma velocidade de 9600 bps. Isso pode ser ajustado conforme necessário.

## Galeria

### Circuito no Tinkercad
<img src="https://raw.githubusercontent.com/DSantosxTech/Arduino-sensor-estacionamento/main/github/Circuito.jpeg" alt="circuito">

### Fotos do Projeto

<img src="https://raw.githubusercontent.com/DSantosxTech/Arduino-sensor-estacionamento/main/github/Galeria%20(2).jpeg" alt="circuito2" width="200">

<img src="https://raw.githubusercontent.com/DSantosxTech/Arduino-sensor-estacionamento/main/github/Galeria%20(3).jpeg" alt="circuito3" width="200">

## •Tecnologias e Linguagens
<div style="display: inline_block">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/arduino/arduino-original-wordmark.svg" height="50" width="60"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/cplusplus/cplusplus-original.svg" height="50" width="60"/>
</div>

## • Referências e documentações
| **[C++](https://en.cppreference.com/w/)**

## Assista 👇

[<img alt="Youtube" src="https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white"/>](https://youtube.com/shorts/QcdDXgQLeNk?si=6_nTfxqE1FCtIVvS)
