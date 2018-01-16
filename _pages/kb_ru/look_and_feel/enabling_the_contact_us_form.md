---
lang: ru
layout: article_with_sidebar
updated_at: '2018-01-16 11:24 +0400'
title: Создание контактной формы в магазине
order: 190
published: false
identifier: ref_contactus
---
Покупатели обращаются за помощью к администратору магазина или в отдел по работе с клиентами через страницу обратной связи:

![]({{site.baseurl}}/attachments/6389780/7602634.png)

Бесплатный модуль** Contact us** активирует на сайте контактную форму. Проверьте, числится ли **Contact us** в списке установленных модулей на странице **Мои модули**:

![]({{site.baseurl}}/attachments/6389780/8716626.png)

Если нет, {% link "установите" ref_gpeZtm28 %} модуль из Маркетплейса и активируйте.

Настройки модуля отвечают за работу формы обратной связи:

![]({{site.baseurl}}/attachments/6389780/7602635.png)

*   **Включить форму**: настройка активирует контактную форму на сайте, она будет доступна по ссылке _/?target=contact_us_. Например, если адрес магазина _http://www.magazin.ru/_, покупатели найдут страничку обратной связи по адресу  _http://www.magazin.ru/?target=contact_us_. Если форма обратной связи отключена, покупатели увидят ошибку _К сожалению, у вас нет прав доступа к этой странице. Пожалуйста, свяжитесь с администратором_.
*   **Электронный адрес получателя**: адрес, на который будут приходить сообщения, отправленные покупателями через форму обратной связи. Если в этом поле не указан никакой адрес, сообщения будут направляться на адрес администратора магазина.

Функция _reCAPTCHA_ помогает обезопасить страницу обратной связи. _reCAPTCHA_ - это бесплатный веб-сервис, предотвращающий использование контактной формы автоматическими ботами. Т.к. при отправке сообщения требуется ввести [код с картинки](http://www.google.com/recaptcha#captcha), только человек может использовать контактную форму. 

Защита _reCAPTCHA_ требует настройки публичного и приватного ключей. [Зарегистрируйтесь в сервисе и получите ключи](https://www.google.com/recaptcha/admin/create).

Если в магазине работает модуль **Simple CMS**, ссылка на страницу обратной связи находится в главном меню: 

![]({{site.baseurl}}/attachments/6389780/7602632.png)

Ссылку можно удалить из главного меню на странице **Содержание / Меню**:

![]({{site.baseurl}}/attachments/6389780/8716627.png)

_Дополнительная информация:_

*   {% link "Создание новых пунктов меню" ref_newmenuitem %}
