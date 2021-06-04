# Използване на КЕП под Linux

Инструкциите са за устройство _Circle CIR115_ и _Ubuntu 18 (64 бита)_.
Всички необходими файлове са в директорията ```resources```, а последната ми версия може да бъде свалено то [Stampit.org](https://stampit.org/bg/page/795). 

## Инсталиране

#### 1. Драйвери
Първо инсталирайте **PC/SC Lite resource manager**.
```
sudo apt install pcscd
sudo apt install pcsc-tools
```
_***pcsc-tools** е, ако желаете да използвате командата ```pcsc_scan```, за да видите дали устройството се разпознава._

Инсталирайте драйверите от файла ```libabcccid_2.0.2-1_amd64.deb``` в архива ```Circle_Linux_Installer_v2.0.2.zip```.
```
sudo dpkg -i libabcccid_2.0.2-1_amd64.deb
```
Най-новият драейвер може да се вземе и от [официалния сайт](https://abcircle.com/en/product/2/CIR115B/sim-sized-contact-smart-card-reader/).

#### 2. Софтуер за управление 
Инсталирайте ```AWP_5.3.3_SR1_Admin_bionic_amd64.deb``` от архива ```Linux_AWP.zip```.
```
sudo dpkg -i AWP_5.3.3_SR1_Admin_bionic_amd64.deb
```
Програмата се старитра от ```/usr/local/AWP/IdentityManager```.

За по-лесно стартиране можете да създадете файл ```AWP.desktop``` в ```/usr/share/applications```.
```
[Desktop Entry]
Version=1.0
Name=AWP (Identity Manager)
Comment=AWP (Identity Manager)
Exec="/usr/local/AWP/IdentityManager"
Icon=/usr/local/AWP/awp.png
Terminal=false
Type=Application
Categories=Utility;
```

В ```AWP_5.2_FAQ.pdf``` могат да бъдат открити инструкии за работа със софтуера и как да си смените PIN кода.

#### 3. Добавяне към Firefox
В ```StampIT_usermanual_Windows_Firefox_bg_v4.0.0.pdf``` е описано подробно как става, но при мен беше достатъчно само добавянето на ```libcmP11.so``` файла от архива ```CSSI_Client_5.0_Linux.zip```.

Вместо това може и директно да се добави security device за Firefox и Chrome чрез следната команда:
```
sudo apt install opensc
```
