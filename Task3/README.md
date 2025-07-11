### <a name="_b7urdng99y53"></a>**Название задачи:** Открытие депозитов онлайн
### <a name="_hjk0fkfyohdk"></a>**Автор:** Команда цифровой трансформации
### <a name="_uanumrh8zrui"></a>**Дата:** 07.2025
### <a name="_3bfxc9a45514"></a>**Функциональные требования**
Опишите здесь верхнеуровневые Use Cases. Их нужно оформить в виде таблицы с пошаговым описанием:

|**№**|**Действующие лица или системы**|**Use Case**|**Описание**|
| :-: | :- | :- | :- |
| UC1 | - Бэк-офис <br> - АБС | Расчет и публикация ставок депозиторв | Сотрудник кредитного отдела на основе данных о текущем балансе банка, взятых из АБС, рассчитывает ставки депозитов и публикует их в АБС. | 
| UC2 | - Клиент <br> - сайт <br> - SMS-платформа <br> - АБС| Подача заявки на сайте| Клиент заполняет форму на сайте, указывая ФИО, номер телефона и одну из предложенных ставок депозита. Заявка подтверждается SMS-кодом и отправляется в АБС в статус "Создана" |
| UC3 | - клиент <br> - call-центр <br> - АБС| Предложение оформления депозита | АБС подсчитывает черновые индивидуальные предложения и передает заявку в систему call-центра со статусом "Обработка". Сотрудник call-центра звонит клиенту, рассказывает об условиях оформления и назначает визит в банк. По итогам звонка заявка в call-центре переводится в статус "Обработана". | 
| UC4 | - клиент <br> - front-офис <br> - АБС <br> - SMS | Идентификация и подтверждение | Клиент приходит в банк, сотрудник отделения удостоверяет личность клиента в АБС и переводит заявку клиента в статус "Оформление" | 
| UC5 | - бэк-офис <br> - АБС <br> - SMS | Оформление депозита | Сотрудник бэк-офиса подтверждает заявку клиента и оформляет депозит. Заявка переводится в статус "Исполнена" |

### <a name="_u8xz25hbrgql"></a>**Нефункциональные требования**
Опишите здесь нефункциональные требования и архитектурно значимые требования.

|**№**|**Требование**|
| :-: | :- |
| 1 | Корпоративный стиль |
| 2 | Доступность 99.9 |
| 3 | TLS |
| 4 | Асинхронная связь с АБС |
| 5 | Горизонтальное масштабирование |
| 6 | Распределение в нескольких датацентрах |

### <a name="_qmphm5d6rvi3"></a>**Решение**

![context](context.svg)

### <a name="_bjrr7veeh80c"></a>**Альтернативы**

Очевидно, что текущее решение возникает из-за ограничений имеющейся Автоматизированной Банковской Системы. На каком-то этапе будет целесообразнее модернизировать или заменить ее, решив проблемы масштабирования и простоты внешней интеграции.

**Недостатки, ограничения, риски**

- Итоговый процесс все еще требует ручного участия
- Процесс зависит от работоспособности нескольких систем, в том числе внедряемого механизма очередей (Kafka)
- требуется дообучение ИТ-персонала работе с нвоыми системами
