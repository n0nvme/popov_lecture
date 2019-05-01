#### Читает Александр Попов из позитива



# Уязвимости ядра linux



### Отличие монолита от микроядра:

в kernel space исполняются самые важные части ядра, все остальное исполняется в user space

условно kernel space больше в монолите, в микроядре больше user space

По этому поводу был известный спор Танненбаума и Торвальдса

возможно идея микроядра обогнала свое время

linux - монолитный



Андроид - не полноценный линух, он использует только ядро linux



v4.13 - подрядка 25 миллионов строк кода



secure vault на арме



Bruce Schneier - security is risk management



ГОСТ 15408 - переведенная "оранжевая книга" с некоторыми поправками



Три недели на заплатки и сертификацию ядра для гос. дистрибутивов



в upstream где-то полгода-год на чистку багов и закрытие уязвимостей для нового кода



Эмбарго на уязвимость - период ответственного разглашения, для ядра linux - 2 недели

linux distrs mailing list - дистрибутив для людей, отвечающих за безопасность в крупных дистрибутивах, создал некто Пискляк

если найдена уязвимость, необходимо отправить подписанное своим gpg ключом на security@kernel.org



у BSD дистрибутивов нет четкого канала связи между собой



- Угроза - опасность

- Уязвимость - то как осуществится угроза

- Эксплоит - то как эксплуатируется уязвимость



Эксплоит без пэйлода - не вредоносное ПО, 273 УК РФ не действует, писать proof of concept законно



- виртуализация - несколько систем работает на одном хосте используя аппаратные системы виртуализации

- паравиртуализация - система знает, что под ней есть гипервизор, аппаратные системы виртуализации тоже используются
- контейнеризация - аппаратные системы виртуализации не используются



## Метрики CVSS

#### Expoitability metrics:

- AV(Attack vektor) - уровень доступа к устройству
- AC(Attack complexity) - сложность проведения аттаки
- PR(Privileges required) - привилегии пользователя
- UI(User interaction) - необходимость действий пользователя
- S(Scope) - возможность вмешаться в другие компоненты программы 

#### Impact metrics:

- С(Confidentialy impact) - влияет ли атака на конфиденциальные данные
- I(Integrity impact) - 
- A(Availability impact) - 



Дмитрий Вьюгов - "сказка о тысяче ядреных багов", уязвимости появляются быстрее чем исправляются



LSM (Linux security modules) - механизмы разграничения доступа в ядре linux

**LSM не защищают от эсплуатации ядерных уязвимостей(уязвимостей ядра)**

клевая картинка c grsecurity про LSM



Мандатный контроль разграничения доступа - на каждом файле есть метка безопасности, у каждого пользователя есть группа доступа, реализуется с помощью LSM



Цепочка доверенной загрузки - надежда, что под твоим компонентом есть еще одна система которая может засечь атаку



pulseaudio дырявый шо пипец



KSSP(Kernel Self Protection Project) - исправления ошибок недостаточно, чтобы сделать систему безопасной

Цель - устранение классов уязвимостей и методов их эксплуатации



Карта защиты средств ядра Linux - linux-kernel-defence-map, лежит на гитхабе, ссылка есть в презентации

исходник карты написан на языке DOT, GraphViz автоматически генерирует карту

Есть скрипт который проверяет конфиг ядра и советует способы уменьшения периметра атаки -



CVE - идентификатор для конкретной уязвимости

CWE - класс(тип) уязвимостей



Kernel Hack Drill - проект аналог BWAPP но для ядра линукс

OS day - конфа про разработку операционных систем

