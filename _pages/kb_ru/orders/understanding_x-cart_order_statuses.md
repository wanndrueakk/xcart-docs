---
lang: ru
layout: article_with_sidebar
updated_at: '2018-01-05 12:19 +0400'
title: Статусы заказов в X-Cart
order: 10
published: true
identifier: ref_orderstatus
---
## Системные статусы заказов

Обработка заказа отслеживается по статусу оплаты и статусу исполнения. 

В стандартном X-Cart заказу присваиваются следующие статусы:

**Статус оплаты**

{:.ui.compact.celled.small.padded.table}
| Q | Ожидает оплаты | Заказ создан, но еще  не оплачен. Это первоначальный статус, который получают все заказы, оплаченные оффлайн (по телефону, банковским переводом и т.д.). Также этот статус может быть временно присвоен заказам, оплаченным онлайн. В этом случае статус _Ожидается оплата_ означает, что покупатель ввел платежные данные, но результат транзакции не известен: заказ еще не оплачен и не отклонен. |
| P | Оплачен | Прошла полная оплата заказа. В случае онлайн способов оплаты это означает, что средства поступили на счет продавца. |
| PP | Частично оплачен | Заказ частично оплачен, или был сделан частичный возврат средств. |
| A | Подтвержден | Только платежная система может установить этот статус, администратор не имеет возможности присвоить заказу такой статус вручную. Статус означает, что получено подтверждение наличия на карте покупателя средств, достаточных для оплаты заказа. Банк удержал необходимую сумму, но средства еще не переведены на счет продавца. |
| D | Отклонен | Статус может быть установлен только платежной системой и не может быть установлен администратором магазина вручную. Означает, что банк не подтвердил наличие средств на карте покупателя, и заказ отменен. |
| C | Отменен | Заказ отменен продавцом. Этому статусу предшествует _Подтвержден_ или _Ожидается оплата_. |
| R | Возврат средств | Оплата полностью возвращена покупателю. Статус может быть установлен администратором магазина или платежной системой, поддерживающей отмену платежей. Этому статусу предшествует _Оплачен_. |

Когда заказу присваивается статус _Ожидается оплата_, _Оплачен_ или _Подтвержден_, в магазине уменьшается запас купленного продукта на количество единиц в заказе. При статусах _Возврат средств_, _Отменен_ и _Отклоне_н размер запаса восстанавливается. Статус _Частично оплачен_ не влияет на размер запаса продуктов.

**Статусы обработки заказа**

{:.ui.compact.celled.small.padded.table}
| N | Новый | Первоначальный статус, который присваивается каждому новому заказу. |
| P | В обработке | Продавец обрабатывает заказ. |
| S | Отправлен | Продавец отправил заказ. |
| D | Доставлен | Покупатель получил заказ. |
| WND | Доставка невозможна | Заказ не может быть доставлен покупателю. |
| R | Возвращен | Покупатель возвращает купленные продукты, заказ отправлен обратно продавцу. |
| NF | Не завершен | (Статус появляется только при установленном и активированном модуле Not Finished Orders). Покупатель оплачивает заказ, но платежная система возвращает ответ _отмена_ или _сбой_, и статус оплаты заказа становится _Отклонен_. |

{% note info %}
В первой колонке представлены буквенные коды системных статусов заказов, такое обозначение используется в коде X-Cart.
{% endnote %}

Раздел {% link "Управление статусами заказов" ref_7FIU2sxJ %}  рассказывает о статусах заказов, установленных администратором.

## Жизненный цикл заказа

Процесс обработки заказов, оплаченных оффлайн:

*   Создается новый заказ в статусе _Ожидается оплата_.
*   На разных стадиях обработки заказа администратор изменяет статус заказа вручную. Текущий статус можно изменить на другой в любое время. После получения оплаты администратор меняет статус заказа на _Оплачен_, после отмены заказа - на _Отменен_, в случае возврата  - на _Возврат средств_. Статус _Частично оплачен_ применим, если заказ оплачен не полностью или сделан частичный возврат средств.

После статуса _Оплачен_ рекомендуется выставлять статус _Возврат средств_ (не _Отменен_), а после _Подтвержден_ или _Ожидается оплат_ - _Отменен_ (не _Возврат средств_).


Процесс обработки заказов, оплаченных онлайн:

*   Создается новый заказ в статусе _Ожидается оплата_, _Оплачен_ или _Подтвержден_ - в зависимости от настроек способа оплаты и ответа, полученного от платежной системы.
*   Если первоначальный статус заказа был _Ожидается оплата_ или _Подтвержден_, он может автоматически измениться на _Оплачен_, _Частично оплачен_ или _Отклонен_. Окончательный статус зависит от ответа платежной системы.
*   При статусе заказа _Оплачен_ возможен возврат средств, но только если платежная система осуществляет возвраты. После полного возврата оплаты статус заказа автоматически изменяется на _Возврат средств_, а после неполного - _Частично оплачен_.
*   Обработка заказа происходит автоматически, но в случае необходимости, администратор может изменить статус заказа вручную.

_Дополнительная информация:_

*   {% link "Управление статусами заказов" ref_7FIU2sxJ %}