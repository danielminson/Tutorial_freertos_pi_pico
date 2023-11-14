# Coloque aqui o nome do tutorial de vocês

- **Alunes:** Daniel Minson Pucciariello
- **Curso:** Engenharia da Computação
- **Semestre:** 10
- **Contato:** danielp6@al.insper.edu.br
- **Ano:** 2023

## Começando

Para seguir esse tutorial é necessário:

- **Hardware:** Raspberry Pi PICO
- **Softwares:** FreeRTOS
- **Documentos:** [DE10-Standard_User_manual.pdf](https://github.com/Insper/DE10-Standard-v.1.3.0-SystemCD/tree/master/Manual)

## Motivação
Como engenheiro recém-formado, compartilho um tutorial prático sobre programar a Raspberry Pi Pico com FreeRTOS. Este recurso abrangente explora desde a configuração inicial até a implementação de tarefas concorrentes, capacitando os desenvolvedores a criar projetos eficientes e inovadores. 

Descubra as vastas possibilidades da programação embarcada com FreeRTOS na Raspberry Pi Pico!

## Baixar arquivo de setup
1. wget https://raw.githubusercontent.com/raspberrypi/pico-setup/master/pico_setup.sh
2. chmod +x pico_setup.sh
3. ./pico_setup.sh


!!! note 
    Tenha certeza que o seu cmake é pelo menos 3.12 usando `cmake --version`

    Caso contrario, é necessario desinstalar e instalar um novo
    

## Como instalar um novo cmake?
1. `sudo apt remove cmake`
2. baixe em https://cmake.org/download/ a versao mais nova do cmake estável
3. copie para a pasta /opt/
4. rode:`sudo bash /opt/cmake-3.*your_version*.sh`
5. crie um link simbolico (fazendo as devidas substituições ) `sudo ln -s /opt/cmake-3.*your_version*/bin/* /usr/local/bin`
6. teste com: `cmake --version`


**referência:** [Askubuntu](https://askubuntu.com/questions/829310/how-to-upgrade-cmake-in-ubuntu)


!!! note 
    É necessário ter um módulo que chama raspi-config, que pode ser que não esteja instalado. 

    rode “sudo raspi-config” para ver se está instalado, caso nao esteja, rode o seguinte script para instalacao (presente nesse [github](https://github.com/EmilGus/install_raspi-config))

## Como instalar um raspi-config?¶

1. wget https://github.com/EmilGus/install_raspi-config/blob/master/install.sh
2. chmod +x install.sh
3. ./install.sh 

**referência**: [Rootsaid](https://rootsaid.com/raspi-config-install-setup-in-any-raspberry-pi-linux-os/)

## Libusb
- muito provavelmente você vai ter que instalar essa biblioteca:

`sudo apt-get install libusb-1.0-0-dev`

!!! warning
    obs: se aparecer um erro, vc precisa apagar a pasta onde vc estava rodando o setup antes de rodar pico_setup.sh novamente

## instalar toolchain:

sudo apt update
sudo apt install cmake gcc-arm-none-eabi libnewlib-arm-none-eabi build-essential

## instalar sdk e exemplos:

1. git clone https://github.com/raspberrypi/pico-sdk.git --branch master

2. cd pico-sdk

3. git submodule update --init

4. cd ..

5. git clone https://github.com/raspberrypi/pico-examples.git --branch master

# **Compilação**
Para realizar a compilaçao, o sdk precisa estar com o export path configurado.

Isso pode ser feito configurando uma variavel no bash_rc ou de forma manual todas as vezes que você abrir o terminal.


`export PICO_SDK_PATH=/media/soc/rtos_pico_infra/pico-sdk`

ou 

`gedit .bashrc e ai definir PICO_SDK_PATH=/media/soc/rtos_pico_infra/pico-sdk`

1. crie uma pasta “build” dentro da pasta “pico_examples” 

----------------------------------------------

!!! info 
    Essas duas partes são obrigatórias no tutorial:
    
    - Nome de vocês
    - Começando
    - Motivação

## Recursos Markdown

Vocês podem usar tudo que já sabem de markdown mais alguns recursos:

!!! note 
    Bloco de destaque de texto, pode ser:
    
    - note, example, warning, info, tip, danger
    
    
??? info 
    Também da para esconder o texto, usar para coisas
    muito grandes, ou exemplos de códigos.
    
    ```txt
    ...
    
    
    
    
    
    
    
    
    
    
    
    oi!
    ```
    
- **Esse é um texto em destaque**
- ==Pode fazer isso também==

Usar emojis da lista:

:two_hearts: - https://github.com/caiyongji/emoji-list


```c
// da para colocar códigos
 void main (void) {}
```

É legal usar abas para coisas desse tipo:
    
=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

Inserir vídeo:

-  Abra o youtube :arrow_right: clique com botão direito no vídeo :arrow_right: copia código de incorporação:

<iframe width="630" height="450" src="https://www.youtube.com/embed/UIGsSLCoIhM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

!!! tip
    Eu ajusto o tamanho do vídeo `width`/`height` para não ficar gigante na página
    
Imagens você insere como em plain markdown, mas tem a vantagem de poder mudar as dimensões com o marcador `{width=...}`
    
![](icon-elementos.png)

![](icon-elementos.png){width=200}
