Befin.ru JSON Api
=================

Введение
--------

Все вызовы API представляют собой GET или POST запрос вида
http://befin.ru/app/json-api/methodName

Параметры могут передаваться как через GET (query string), так и через POST.
Во избежании проблем с кодировкой, рекомендуется использовать POST. GET стоит
использовать только для отладки.

Пример http://befin.ru/json-api/auth?username=vasya@google.com&password=MD5_HASH

В теле http response содержится JSON. JSON имеет вид: 

Авторизация
-----------

Авторизация пользователя производится вызовом http://befin.ru/json-api/auth. В ответе
выставляется cookie BF_SESSION_ID, кроме того session id будет содержаться в теле ответа
в виде строки. В случае успешной авторизации HTTP Status code будет равен 200.

В дальнейшем session id нужно передавать как cookie или в HTTP-заголовке X-Befin-Session-Id.

Обработка ошибок
----------------

Если произошла ошибка HTTP статус будет равен 403. В теле ответа будет следующий JSON:
{errorCode: XXXX, errorMessage: "Сообщение об ошибке", details: "...."}.

Test


