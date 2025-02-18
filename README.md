# Projeto: Controle de LEDs e Display OLED com Joystick no RP2040

## Descrição Geral

Este projeto tem como objetivo controlar LEDs e um display **OLED SSD1306** utilizando um **joystick analógico** no microcontrolador **RP2040**, presente na placa **Raspberry Pi Pico**. O código foi desenvolvido utilizando **Pico SDK** no **VS Code**.

## Objetivos

- **Controlar a intensidade de LEDs via PWM** com base na posição do joystick.
- **Alternar o estado do LED verde e exibir um retângulo no display** ao pressionar o botão do joystick.
- **Ativar e desativar o controle dos LEDs via PWM** utilizando o Botão A.
- **Exibir um cursor móvel no display** representando a posição do joystick.

## Componentes Utilizados

- **Microcontrolador**: RP2040 (Raspberry Pi Pico)
- **Display OLED SSD1306**: Comunicação via I2C (GPIO 14 - SDA, GPIO 15 - SCL)
- **Joystick Analógico**: Leitura via ADC (GPIO 26 - Eixo X, GPIO 27 - Eixo Y)
- **LEDs**:
  - LED Azul (GPIO 13 - PWM)
  - LED Vermelho (GPIO 12 - PWM)
  - LED Verde (GPIO 11 - Alternado pelo botão do joystick)
- **Botões**:
  - Botão do Joystick (GPIO 22)
  - Botão A (GPIO 5)

## Funcionalidades Implementadas

### 1. Controle da Intensidade dos LEDs por Joystick
- **O eixo X do joystick ajusta o brilho do LED azul (GPIO 13).**
- **O eixo Y do joystick ajusta o brilho do LED vermelho (GPIO 12).**
- **Os LEDs ficam apagados quando o joystick está centralizado.**
- **O brilho aumenta conforme o joystick se move para os extremos.**

### 2. Controle do LED Verde e Retângulo no Display
- **Ao pressionar o botão do joystick (GPIO 22), o LED verde (GPIO 11) alterna entre ligado e desligado.**
- **O mesmo botão alterna a exibição de um retângulo adicional no display.**

### 3. Ativação e Desativação do PWM pelo Botão A
- **O Botão A (GPIO 5) ativa ou desativa o controle de brilho dos LEDs via PWM.**
- **Se desativado, os LEDs vermelho e azul permanecem apagados.**
- **Mensagens são exibidas no console para indicar o estado do PWM.**

### 4. Movimento do Cursor no Display
- **O cursor no display reflete a posição do joystick.**
- **Os limites do retângulo no display são respeitados.**
- **A letra 'X' foi substituída por um quadrado de 4x4 pixels na `font.h`.**

## Como Executar o Projeto

### 1. Configuração do Ambiente
- Instale o **VS Code** e configure o **Pico SDK**.
- Conecte a placa **Raspberry Pi Pico** ao computador via USB.

### 2. Compilação e Execução
- Compile o código e gere um arquivo `.uf2`.
- Transfira o arquivo para a placa **Raspberry Pi Pico**.
- Utilize o **Serial Monitor** do VS Code para monitorar o funcionamento.

### 3. Testes e Depuração
- Movimente o **joystick** para ajustar a intensidade dos **LEDs** e mover o cursor no **display**.
- Pressione **o botão do joystick** para alternar o LED verde e o retângulo no display.
- Pressione **o Botão A** para ativar ou desativar o controle de intensidade dos LEDs via PWM.

## Estrutura do Projeto

- `main.c`: Código principal do projeto.
- `ssd1306.h / ssd1306.c`: Biblioteca para controle do display OLED SSD1306.
- `font.h`: Arquivo da fonte do display, onde a letra 'X' foi substituída por um quadrado 4x4 pixels.
- `README.md`: Documentação do projeto.

## Espaço para Vídeo de Demonstração

(ESPAÇO PARA LINK)

👨‍💻 Autor
Kauan Teixeira da Hora