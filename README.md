<html>
<body>
<h1>
Ardupilot_Modded_Firmware
</h1>
<p>
Este guia contém o passo a passo para realizar a instalação e a     configuração de uma versão modificada do Firmware ArduCopter    para ser transferido à placa Pixhawk.
</p>
<p>
Assista o vídeo abaixo para mais informações: <br>
https://www.youtube.com/watch?v=PLGezPQYMrs
</p>
Instale GIT:
<p>

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install git
</p>

<h3>
Instale QGroundControl:
</h3>
<p>
https://docs.qgroundcontrol.com/master/en/getting_started/download_and_install.html
</p>
<h3>
Depois de instalado, para rodar QGroundControl via terminal:
</h3>
<p>

    ./QGroundControl.AppImage
</p>
<h3>
Rode o comando abaixo par instalar Python 3 e C++:
</h3>
<p>
    
    sudo apt-get install python3-pip build-essential
</p>
<h3>
Faça o clone do repositório da Ardupilot e atualize seus    módulos auxiliares:
</h3>
<p>

    git clone https://github.com/ArduPilot/ardupilot.git
    cd ardupilot
    git submodule update --init --recursive
</p>
<h3>
Rode as linhas abaixo para instalar arquivos importantes:
</h3>
<p>

    ./home/your/path/here/ardupilot/Tools/environment_install/ install-prereqs-ubuntu.sh -y
    . ~/.profile
    sudo apt-get install gcc-arm-none-eabi
    sudo apt-get update
    sudo apt-get upgrade
</p>
<h3>
Reinicie o computador. E, depois de ligado, vá na pasta ardupilot e com o programa WAF (https://github.com/ArduPilot/ardupilot/blob/master/BUILD.md) verifique qual placa será usada:
</h3>
<p>

    cd /home/your/path/here/ardupilot
    sudo su
    ./waf list_boards
</p>
<h3>
Selecione qual placa será usada e por último o tipo de Firmware:
</h3>
<p>

    ./waf configure --board Pixhawk1-1M
    ./waf copter
</p>
</body>
</html>
