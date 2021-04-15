<html>
<body>
    Ardupilot_Modded_Firmware
    
    Este guia contém o passo a passo para realizar a instalação e a     configuração de uma versão modificada do Firmware ArduCopter    para ser transferido à placa Pixhawk.


    Assista o vídeo abaixo para mais informações: <br>
    https://www.youtube.com/watch?v=PLGezPQYMrs

    	Instale GIT:

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install git

    	Instale QGroundControl:<br>
    https://docs.qgroundcontrol.com/master/en/getting_started/  download_and_install.html

    	Depois de instalado, para rodar QGroundControl via terminal:

    ./QGroundControl.AppImage

    	Rode o comando abaixo par instalar Python 3 e C++:

    sudo apt-get install python3-pip build-essential

    	Faça o clone do repositório da Ardupilot e atualize seus    módulos auxiliares:

    git clone https://github.com/ArduPilot/ardupilot.git
    cd ardupilot
    git submodule update --init --recursive

    	Rode as linhas abaixo para instalar arquivos importantes:

    ./Desktop/Modded_Ardupilot/ardupilot/Tools/environment_install/ install-prereqs-ubuntu.sh -y
    . ~/.profile
    sudo apt-get install gcc-arm-none-eabi
    sudo apt-get update
    sudo apt-get upgrade

    	Reinicie o computador. E depois de ligado vá na pasta   ardupilot e com o programa WAF (https://github.com/ArduPilot/ ardupilot/blob/master/BUILD.md) verifique qual placa será usada:

    cd /home/lra/Desktop/Modded_Ardupilot/ardupilot
    sudo su
    ./waf list_boards

    Selecione qual placa será usada e por último o tipo de Firmware:

    ./waf configure --board Pixhawk1-1M
    ./waf copter
</body>
</html>