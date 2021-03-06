# BIOS

## Голосарий

**BIOS** (Basic Input-Output System). Ранее эта аббревиатура переводилась дословно как Базовая Система Ввода-Вывода (БСВВ), однако теперь приобрела нарицательное значение и подразумевает под собой любой код или часть кода, выполняемого платформой для начальной инициализации устройств, настройки и другой подготовительной работы.  

**Стартовая процедура BIOS** (Основная цель стартового блока BIOS – это инициализация необходимых регистров чип сета, определение типа и размера памяти, поиск и инициализация видео подсистемы, последовательных и параллельных портов ввода-вывода, накопителей на гибких и жестких магнитных дисках, поиск дополнительного оборудования, установленного на системную плату. Этот процесс состоит из приблизительно ста промежуточных этапов.) выполняется центральным процессором после подачи питающих напряжений. Она расположена в той части BIOS, которая назывется Boot Block.  

**Flash ROM** - особый вид энергонезависимой памяти с возможностью многократной записи.  
Flash ROM Характеризуется:  
* определенным размером (1Mbit, 2Mbit, 3Mbit, 4Mbit, 8Mbit, 16Mbit)  
* интерфейсом (протоколом) работы (LPC, FWH, PP, SPI)  
* кодами производителя (VendorID) и модели (DeviceID)  

**LPC** (Low Pin Count interface) - интерфейс, предназначенный для подключения таких устройств, как Super I/O Chip и Flash ROM (https://www.intel.com/content/www/us/en/design/technologies-and-topics/low-pin-count-interface-specification.html).  

**FWH** (Firmware Hub) - Специальный тип флешек, а заодно и интерфейс доступа к ним, применяемый на Интеловских платформах.  

**PP** (Parallel Programming) - Режим параллельного программирования. Этот термин применяется по отношению к FlashROM-памяти и означает, что сигналы данных и адреса разделены.  

**SIP** (Serial Initialization Packet) - протокол инициализации процессора в AMD K7-системах. Северный мост посылает серию таких "пакетов" процессору сразу же после старта системы. Посредством этого протокола задаются характеристики шины EV6.  

**I2C** - Интерфейс I2C разработан компанией Philips. На персональных платформах используется его подмножество SM-Bus для считывания данных SPD, а также для доступа к генератору тактовых частот. В редких случаях SM-Bus используется для подключения некоторых дополнительных устройств: POST-индикатор от Abit, микросхемы-экспандеры GPIO (встречаются у ABIT и MSI), доступ к чипам мониторинга и CoreCell, к серверным корзинам, бек-плейнам и пр.). На некоторых платформах SM-Bus выведен на разъем для подключения специализированных контроллеров системного мониторинга. Определение PnP-мониторов тоже идёт по ЛОКАЛЬНОЙ I2C шине видеоадаптера (их там может быть больше одной), к которой подключены чипы VIVO (Video In / Video Out), ВЧ-блок по типу All-in-Wonder.  

**SPI** (Serial Peripheral Interface) - Последовательный 4-х проводный интерфейс для подключения периферийных устройств к процессору. В последнее время используется для записи/чтения содержимого BIOS, хранящегося в SPI Flash ROM (см., например, Winbond W25P80).  

**Boot block** - часть BIOS, исполняющаяся сразу после включения питания компьютера. Выполняет предварительную программную настройку/проверку "железа" и распаковку остального кода ("главных частей") BIOS в оперативную память.  

**CMOS** – энергозависимая память с крайне малым потреблением энергии. Применительно к PC – небольшая по объему (128-256 байт) память на материнской плате, которая хранит текущие дату и время, а также настройки BIOS: состояние набортных устройств, тайминги памяти, напряжение процессора, пароль BIOS и др. Питается от батарейки, поэтому сохраняет информацию и при полном отключении питания компьютера.  

**ESCD** (Extended System Configuration Data) — специальная таблица, хранящаяся в CMOS-памяти, предназначенная для распределения аппаратных ресурсов компьютера. Эта таблица заполняется в момент первого включения компьютера после изменения его конфигурации. Она значительно упрощает процесс распределения ресурсов при включении или перезагрузке. На некоторых материнских платах имеется функция защиты от перезаписи Flash-памяти, которая препятствует изменению ESCD при установке нового оборудованиях, однако эта функция легко отключается при помощи специальных перемычек на материнской плате либо в настройках BIOS.  

**SIO, MIO** (Super I/O, Multi I/O) -  контроллер ввода/вывода. Контроллер I/O объединяет интерфейсы различных низкочастотных устройств.  
Как правило, включает в себя следующие функции:  
* контроллер дисковода флоппи (FDD)
* параллельный порт (LPT) (обычно используется для принтеров)
* один или более последовательных (COM) портов
* контроллер клавиатуры и мыши (PS/2)
* интерфейс MIDI
* джойстик
* и другие интерфейсы
* встроенный Hardware Monitoring
* контроллер управления скоростью вентиляторов
* интерфейс для подключения CompactFlash-карт
* watchdog
Изначально контроллеры I/O связывались с процессором (CPU) через ISA шину. Современные контроллеры I/O используют шину LPC (Low Pin Count) вместо шины ISA для связи с CPU. Интерфейс шины LPC предоставляет южный мост материнской платы. Самые современные SIO-контроллеры обеспечивают через SPI интерфейс доступ к системному BIOS.  

**CPU** (Central Processor Unit) - Процессор.  

**MSR** (Model-Specific Registers) – модельно-специфические регистры. Эти регистры предоставляют средства программной связи с микроархитектурой процессора, все важнейшие настройки которые можно менять программно находятся именно там.  
Существует два уровня архитектуры процессора:  
* модельно-независимый - все то, что обеспечивает совместимость процессоров от поколения к поколению: регистры общего назначения, система команд и т.д.  
* модельно-зависимый уровень составляют средства, которые могут поддерживаться в одном процессоре, и не поддерживаться в последующих. Эти средства нужны, например, для программного взаимодействия с какими-либо функциями процессора, которые присутствуют только в данном процессоре, эти функции поддерживаются с помощью особых 64-разрядных регистров MSR.  
Например, управление параметрами кэша, множителем частоты и т.д. всегда осуществляется через MSR, поскольку все эти вещи существенно меняются от процессора к процессору:  
* Команда RDMSR (ReaD from Model Specific Register) выполняет чтение из MSR-регистра. Действие команды заключается в проверке двух условий: во-первых, проверяется наличие нулевого уровня привилегированности кода, во-вторых, проверяется наличие в регистре ЕСХ значения, адресующего один из MSR-регистров. Если хотя бы одно из этих условий не выполняется, то выполнение команды RDMSR заканчивается. Если выполняются оба условия, то значение MSR-регистра, адресуемого содержимым регистра ЕСХ, помещается в пару 32-битных регистров EDX:EAX.  
* Команда WRMSR (WRite to Model Specific Register) производит запись значения в один из 64-разрядных MSR-регистров. Действие команды заключается в проверке тех же двух условий: во-первых, проверяется наличие нулевого уровня привилегированности кода, во-вторых, проверяется наличие в регистре ЕСХ значения, адресующего один из MSR-регистров. Если хотя бы одно из этих условий не выполняется, то работа команды WRMSR заканчивается. Если выполняются оба условия, то значение пары 32-битных регистров EDX:ЕАХ пересылается в 64-битный MSR-регистр, номер которого задан в регистре ЕСХ.  

**CPUID** (CPU Identification) — ассемблерная инструкция процессоров x86, используемая для получения информации о процессоре. Используя её, программа может определить тип ЦП и его особенности.  

**clock generator** (clock synthesizer, clocker, интезатор частот, тактовый генератор, клокер) - Генератор тактовых частот - устройство, формирующее основные тактовые частоты, используемые на материнской плате и в процессоре. Источником опорной частоты для него служит, как правило, кварцевый резонатор ("кварц"). Частота на процессор подается через умножитель.  
Именно на этом факте и основывается разгон с помощью перепайки кварца. Поскольку все частоты зависят от кварца, то, заменив его, можно поменять все частоты одновременно. При изменении частоты кварца пропорционально вырастет частота, подаваемая на процессор и шину PCI (что есть хорошо, этого и добиваемся) и прочие частоты, например сигнал таймера, контроллера клавиатуры, шину USB м пр. (что есть плохо, но вполне исправимо).  
На современных платформах многие модели клокеров являются программно-доступным ресурсом, запись в который выполняет чипсет по шине I2C. С недавних пор такого рода устройства позволяют выполнять также и чтение, что в сеансе операционной системы обеспечивает пользователя необходимой информацией об используемых частотах.  
Существуют две архитектуры тактовых генераторов:  
* сетка частот транслируется всем потребителям на системной плате  
* клокер формирует необходимые частоты для всех подсистем, кроме памяти, а за обеспечение тактированием слотов DIMM отвечает Clock Buffer, на который клокер передает только код требуемой частоты  
Линии кварцевого генератора на разные элементы развязаны:  
* CPU - подается на процессор  
* SDRAM - подается на память  
* PCI - подается на шину PCI  
* 3V66  
* IOAPIC - подается на прочии элементы  

**ACPI** (Advanced Configuration and Power [management] Interface) — усовершенствованный интерфейс управления конфигурированием и энергопотреблением. Позволяет осуществлять полное управление энергопотреблением (с возможностью включения и отключения отдельных устройств) со стороны ОС, а не BIOS (BIOS имеет возможность только выключить устройство после заданного периода отсутствия активности, а ОС может с помощью ACPI как переходить в режим пониженного энергопотребления, так и включать нормальное энергопотребление). Задача ACPI — обеспечить взаимодействие между операционной системой, аппаратным обеспечением и BIOS материнской платы.  

**PGA** (Pin Grid Array) - корпус с матрицей выводов. Представляет собой квадратный или прямоугольный корпус с расположенными в нижней части штырьковыми контактами.  

**LGA** (Land Grid Array) - представляет собой корпус PGA, в котором штырьковые контакты заменены на контактные площадки (пятачки).  

**BGA** (Ball Grid Array) произошёл от PGA. В BGA выводы заменены шариками припоя, нанесёнными на тыльную сторону микросхемы.  

**Codec AC97** - Кодировщик/декодировщик звукового сигнала (кодек) в стандарте AC97 отличается от прежних реализаций звуковых чипов тем, что подключается по двух-проводной схеме к Южному Мосту чипсета. По этой причине такое решение весьма чувствительно к частоте PCI и может не работать при оверклокинге.  

**DMI** (Desktop Management Interface) - Довольно специфичный стандарт на способы получения и хранения информации о конфигурации компьютера и управления им.  

**GPIO** (General Purpose Input/Ouput) - Являются двунаправленными регистрами ввода\вывода, которые нужны для реализации функций предусмотренных производителем микросхемы (по-умолчанию), или функций задаваемых (описываемых программно) пользователем.  

**GPU** (Graphics Proccesing Unit) — Графический процессор, отдельное устройство персонального компьютера или игровой приставки, выполняющее графический рендеринг. Благодаря специализированной конвейерной архитектуре они намного эффективнее в обработке графической информации, чем типичный центральный процессор.  

**HSI** - переходной мост, разработанный nVidia к своим PCI-Express видеочипам, позволяющий работать им в AGP-слоте. У ATi есть аналогичный переходной чип под названием Rialto.  

**Rialto** - переходной мост, разработанный ATi к своим PCI-Express видеочипам, позволяющий работать им в AGP-слоте. У nVidia есть аналогичный переходной чип под названием HSI.  

**VRAM** (Video Random Access Memory) - ОЗУ для видеоизображений. Оперативная память для временного хранения изображения c произвольным доступом (буфер кадра).  