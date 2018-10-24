# RPiPWM_Board
## Описание
Проект платы расширения для одноплатного компьютера Raspberry Pi (версии B+, 2B, 3B, с 40 пинами).    
Включает в себя PCA9685 - I2C генератор ШИМ сигнала на 16 каналов, и АЦП.  
Предусмотрен преобразователь напряжения LM2596-5.0 для питания Raspberry Pi от аккумулятора, 
номинальное напряжение питания до 25 В, при превышении возможен выход из строя некоторых (или всех) компонентов.  
Предусмотрено место для EEPROM CAT24C32 с обвязкой - для использования технологии 
[Raspberry Pi HAT](https://www.raspberrypi.org/blog/introducing-raspberry-pi-hats/), 
однако данная технология пока не используется.

Необходимые нестандартные библиотеки - в папке libraries.  
Список изменений - в файле `Changes.md`.

## Функции

- Питание Raspberry Pi от аккумулятора (напряжение аккумулятора не должно превышать 25 В);
- Создание ШИМ сигнала на 16 каналах (0 - 15). Каналы 0 - 11 имеют возможность подключения внешнего источника питания
(предназначены для управления сервоприводами), каналы 12 - 15 предназначены для подключения драйверов, которые
 генерируют свое напряжение на данном разъеме;
- Определение напряжения питания (при подключении через клеммы), с помощью одноканального АЦП;
- Подключение I2C OLED дисплея SSD1306 размером 128x32 пикселя (может запаиваться на плату). Либо это посадочное место
может использоваться для подключения других I2C устройств при помощи разъема с шагом 2.54 мм;
- Кнопка и светодиод, подключенные к GPIO Raspberry Pi, функционал для которых может задаваться пользователем;

## Использование
Для данной платы написан [модуль](https://github.com/RTC-SCTB/RPiPWM) на языке Python 3,
реализующий весь перечисленный функционал.
