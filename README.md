# 📡 Comunicação Serial com RP2040 - BitDogLab

## 📝 Descrição
Este projeto explora as interfaces de comunicação serial no **RP2040** utilizando a placa **BitDogLab**. O objetivo é integrar **UART e I2C** para manipular diferentes periféricos, incluindo **Matriz de LEDs WS2812, LED RGB, Botões e Display SSD1306**. A interação ocorre através do **Serial Monitor do VS Code**.

## 🎥 Demonstração
📌 **Vídeo demonstrativo** disponível em: [YouTube](https://youtu.be/keBC6GZiUd4)

## 🎯 Objetivos
✅ Compreender e aplicar a comunicação **UART** e **I2C** no RP2040.  
✅ Manipular **LEDs WS2812** e **LED RGB** com eficiência.  
✅ Implementar **interrupções (IRQ)** e **Debounce** para interação via botões.  
✅ Exibir caracteres no **display SSD1306** e números na **Matriz WS2812**.  
✅ Desenvolver um código **modular, organizado e comentado**.  

## 🛠 Componentes Utilizados
- 📟 **Display SSD1306** (I2C - GPIOs 14 e 15)
- 🔲 **Matriz 5x5 de LEDs WS2812** (GPIO 7)
- 🔴🟢🔵 **LED RGB** (GPIOs 11, 12 e 13)
- ⏹ **Botão A** (GPIO 5)
- ⏹ **Botão B** (GPIO 6)

## 🔧 Funcionalidades Implementadas

### 1️⃣ Modificação da Biblioteca `font.h`
- **Adição de caracteres minúsculos** para exibição no **display SSD1306**.

### 2️⃣ Entrada de Caracteres via PC (Serial Monitor)
- Digitar caracteres no **Serial Monitor** exibe-os no **display SSD1306**.
- **Números de 0 a 9** acionam a **Matriz WS2812** para exibição de símbolos correspondentes.

### 3️⃣ Interação com o Botão A
- **Alterna o LED Verde (GPIO 11)** entre ligado/desligado.
- Exibe no **Serial Monitor** e **Display SSD1306** o estado atualizado.
- Implementado via **Interrupção (IRQ) e Debounce**.

### 4️⃣ Interação com o Botão B
- **Alterna o LED Azul (GPIO 12)** entre ligado/desligado.
- Exibe no **Serial Monitor** e **Display SSD1306** o estado atualizado.
- Implementado via **Interrupção (IRQ) e Debounce**.

## 📂 Estrutura do Projeto
```
comunicacao-serial-com-rp2040/
├── build/                      # Diretório de compilação
├── includes/                   # Cabeçalhos das bibliotecas
│   ├── animacoes.h
│   ├── botao.h
│   ├── font.h
│   ├── led-rgb.h
│   ├── matriz-led.h
│   ├── ssd1306.h
├── src/                        # Implementação das funções
│   ├── animacoes.c
│   ├── botao.c
│   ├── led-rgb.c
│   ├── matriz-led.c
│   ├── ssd1306.c
├── comunicacao-serial-com-rp2040.c    # Código principal
├── comunicacao_serial_com_rp2040.pio  # Código PIO para manipular matriz de LEDs
├── CMakeLists.txt               # Configuração do CMake
├── pico_sdk_import.cmake        # Importação do SDK do Raspberry Pi Pico
├── wokwi.toml                   # Configuração para simulação no Wokwi
└── README.md                    # Documentação do projeto
```

## 🚀 Como Executar
### 🔹 **Pré-requisitos**
- Placa **BitDogLab** com RP2040
- **SDK do Pico** instalado
- **CMake e Ninja** configurados

### 🔹 **Passos**
```sh
# Clone o repositório
$ git clone https://github.com/brenotainandev/comunicacao-serial-com-rp2040.git
$ cd comunicacao-serial-com-rp2040

# Compile o projeto
$ mkdir build && cd build
$ cmake ..
$ ninja

# Flash na placa BitDogLab
$ picotool load -x comunicacao-serial-com-rp2040.uf2
```

## 📚 Referências
- **Pico SDK:** [https://github.com/raspberrypi/pico-sdk](https://github.com/raspberrypi/pico-sdk)
- **BitDogLab Docs:** [https://bitdoglab.com](https://bitdoglab.com)

## 📜 Licença

Este projeto é de **uso educacional** e segue a licença MIT. Sinta-se à vontade para modificá-lo e contribuir!