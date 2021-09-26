###### [back](https://github.com/semleon333/GreyHack_Rus/blob/main/README.md)
# Documentation

---
## [Main.lib](https://github.com/semleon333/GreyHack_Rus/blob/main/Main/!Lib/Main.lib.src)

* **переменная** - комментарий

---
* **LibX** - MetaxploitLib
* **LibC** - cryptoLib
* **flag_dbg** - флаг обозначающий что включён дебаг мод, т.е. вывод доп информации через dbg()

2 сомнительных сокращения которые я стараюсь больше не использовать: 
* **shell=get_shell**
* **host=get_shell.host_computer**
 
---
* **функция**
     - комментарий
---
* **ERR_PRINT=function(str,fg)**
     - print("<color=#F22><b> ERROR: </b></color>"+str) >> if __fg__ then __return str__ else __return 0__
* **ERR_FATAL=function(str)**
     - exit("<color=#F22><b> ERROR_FATAL: </b></color>"+str)
* **ERR_STRING=function(str)**
     - return("<color=#F22><b> ERROR: </b></color>"+str)

---
* **cs=function(string)**
     - очищает экран >> выводит сообщение при его наличии
* **col=function(color,s)**
     - делает префикс к строке s тегом <color=#> Ex: col("fff","string")
* **mark=function(color,s)**
     - делает префикс к строке s тегом <color=#> Ex: mark("fff","string")
* **dbg=function(str)**
     - делает префикс к строке s "Debug: " >> принтит при флаге "flag_dbg"

---
* **list_s2int=function(list,strong=0)**
     - list of string >> list of number
* **includeLib=function()**
     - создаёт LibX и LibC переменные-библиотеки, если библиотеки нет, то в переменной null, и выводится ошибка на экран

---
* **prmExist= function(s)**
     - проверка существования параметра "s" в "globals.params" (возвращает true/false)
* **prmTake = function(s)**
     - проверка существования и __удаление__ параметра "s" в "globals.params" (возвращает true/false)

---
* **connF = function(shell, ip, pass, port = 22, username = "root", type = "ssh")**
     - надстройка над "connect_service" с обработкой исключения и бОльшим удобством
* **connChain = function(shellList, oldShell)**
     - подключение по цепочке используя "connF" (смысла мало, от админа не помогает(работает только без поднятия терминала в конце))

---
* **fill = function(s, ln, side="s+", filler=" ")**
     - добавления строки filler к строке s со строны side(+s или s+, заполнение со стороны плюса),
          до итоговой длинны ln(без отсечения изначально большого s, но с отсечением если filler больше одного символа)
* **form = function(list)**
     - принимает лист из строки и подмассивов, подмассивы являются аргументами для fill; Ex:(st - string) form([[st,4],st2,[st3,6,"+s","|"],"ololo"+"lolo"])

---
* **choose = function(choices, default = -1)**
     - принимает лист "choises", выводит его, возвращает ответ. default - ответ, который будет выбран, если user не выбрал ничего
* **chooseYesNo = function(default, prompt = "")**
     - принимает на вход "default" (true/false) и условие для осуществления выбора(prompt). Если выбор не сделан: возвращает default

---
* **updateСheckF = function()**
     - обращается на сервер, сверяет "PROGRAM.VERSION_S", с файлом на сервере. Если на сервере версия новее, то скачивает новую версию программы, запускает и удаляет старую.

---
### Old

* padSpaces
     - добавления символа "p" к строке "s" до длинны "l"
     * **padSpaces.Left = function(s, l, p=" ")**
     * **padSpaces.Right = function(s, l, p=" ")**
* **choice.list123 = function(choices, default = -1)**
     - принимает лист "choises", выводит его, возвращает ответ. default - ответ, который будет выбран, если user не выбрал ничего
* **choice.yesno = function(default, prompt = "")**
     - принимает на вход "default" (true/false) и условие для осуществления выбора(prompt). Если выбор не сделан: возвращает default


---
## [math.lib](https://github.com/semleon333/GreyHack_Rus/blob/main/Main/!Lib/math.lib.src)
одумайся!

* **dec2hex=function(dec,l=8)**
     - number decimal >> return string heximal длинной l
* **dec2bin=function(dec,l=8)**
     - number decimal >> return string binary длинной l
