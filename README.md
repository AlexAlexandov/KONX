# KONX
Показал пункт-занес характеристику роботу-лживые параметры
В электронном виде заполняется
Три документа :по итогу 1) данные 2) то что сами вводят 3)акт приемки
A1   ctrl + h
Sudo raspi-config
If config- ip шник менять
к компу
Sudo mcedit 
ssh pi@turtlebro20.local 
ifconfig
sudo nano /etc/hostname - изменить имя машины
/etc/hosts и /etc/hostname расположенные на роботе и переименовать turtlebro01->tutlebroNN.
A2 1. cat /etc/lsb-release
2. lsb_release -a
3. python --version
4. pip show rospy
5. vcgencmd measure_temp температуру процессора в градуса
6. rostopic /board_info mcu_id и версия прошивки
7.
8. cat /proc/cpuinfo - информация об аппаратной части
cat /proc/cpuinfo | grep Serial | cut -d ' ' -f 2 - серийный номер платы
9. cat /proc/meminfo - объём оперативной памяти   Free -k -оперативная память
10. timedatectl | grep "Time zone" - часовой пояс в нужном формате
11.cd - -
sudo nano - образ расбери
A3 iwconfig <имя сетевого адаптера>
ip a    это чтобы имя получить
iw/list ‘e ’ frequency             - iwlist ‘e ‘frequency
A4   ls
rostopic list
A4
Tutlebro инструкция там есть топики
Они есть и на роботе
Если нет топиков на роботе значит проблемы с платой
ros pack list
А5 Камера вкл выкл просто выделить
Video 0
1600-1200 разрешение
A6 rostopic pub -r 10 /cmd_vel geometry_msgs/Twist '{linear: {x: 0.1, y: 0.0, z: 0.0}, angular: {x: 0.0,y: 0.0,z: 0.0}}' 
- это чтобы заставить робота ехать вперёд линейно
A7  rostopic echo /battery_state -n 1
rostopic info /bat
rostopic echo bat -1
rosmsg info sensor_msg/BatteryState
rostopic echo imu -n 1
rostopic hz imu
Rviz
export ros master по имене иои айпишник
ifconfig- айпи адрес
export ROS_HOSTNAME айпишник
Если стрелка дергается вниз то в инструкции
Важно установить
Продемонстрировать что вращаются колеса
Сбросить параметры -reset
Лево полодительные, право отриц
По критериям одометрии- робот едет вперед координата х увеличивается, коорд х уменьш.
Робот едет назад
Поворот, можно на столе. Вращение на полигоне лучше
rosservice call reset
А9
Загружаем на гит хабе
Открываем ардуино де
Открыввюаем библиотеку
Выбираем плату Mega..
Нажимаем upload работает ок
Вкладка работа с ардуино-берем библиотеку ros lib
rostopic list
rostopic echo /arduino test..
+

rostopic echo /odom

rosrun map_server map_saver -f -/map

ros service  board_info_

cd /media/

Rviz
    lazerscan

rosservice call reset 
rqt

Arduino
Sudo  chmod 666 /dev/ttyUSB0

Roslaunch

Модуль B1,В2,В3 в четкой последовательности
cd_catkin_ws/srs/
Демонстрирует последовательность команд для выполнения
git pull HEAD обновление пакета



http://wiki.ros.org/sound_play?distro=noetic
http://wiki.ros.org/audio_common/Tutorials/Streaming%20audio

Либо команда  play
Или aplay
Если что-то не заработает возможно пакет воспроизведения нужно будет поставить через sudo apt-get install
хотел бы создать систему
сигнализации с поддержкой окна
Ubuntu (без графического интерфейса),
которое воспроизводит различные
звуковые дорожки объявлений и
сигналов тревоги (. mp3 или .wav)
через командную строку.
Например:
root> audioplay ./hello.wav
Звук должен поступать из
аудиоразъема ПК. Я мог бы также
обернуть это с другим слушателем
сокета. (например, Руби Синатра)
Есть идеи, как я могу это сделать?
linux ubuntu audio
- C2H2
источник
1 На всякий случай, если вы
ищете примеры файлов:
/usr/share/sounds это
хорошее место для их поиска.
