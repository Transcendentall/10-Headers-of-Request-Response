# 10-Headers-of-Request-Response

# Лабораторная работа № 1 "10-Headers-of-Request-Response" 
# по теме "Протокол HTTP. Основы работы с консолью разработчика в браузере."

# Цель: 
Получить практические навыки работы с HTTP протоколом, отметить заголовки присущие Request и Response с помощью консоли разработчика.

# Постановка задачи: 
Написать эссе, отражающее особенности как минимум 10 уникальных HTTP-заголовков для Request и Response.

# Порядок выполнения:
# Анализ задачи и написание эссе:

Для начала рассмотрим заголовки на сайте https://www.dvfu.ru/ (это было бы самым очевидным поступком). Выбираем первое попавшееся. И... что же мы видим?

<img src="https://github.com/Transcendentall/10-Headers-of-Request-Response/blob/main/100.jpg">

Запрос выглядит так:

    :authority: www.google.com
    :method: POST
    :path: /gen_204?atyp=i&ei=Db9UYYCFApX1rgTg2a3gCA&ct=slh&v=t1&im=M&pv=0.49954816054874907&me=166:1632943889530,V,0,0,0,0:1043,h,1,CE8QBA,i:0,h,1,CE8QAQ,i:0,h,1,CE8QAA,i:0,h,1,CEwQAQ,i:0,h,1,CDsQAA,i:0,h,1,CDoQAA,i:0,h,1,CAEQTA,i:506,h,1,CE8QBA,o:0,h,1,CE8QAQ,o:0,h,1,CE8QAA,o:0,h,1,CEwQAQ,o:0,h,1,CDsQAA,o:0,h,1,CDoQAA,o:0,h,1,CAEQTA,o:9311,h,1,CE8QBA,i:0,h,1,CE8QAQ,i:0,h,1,CE8QAA,i:0,h,1,CEwQAQ,i:0,h,1,CDsQAA,i:0,h,1,CDoQAA,i:0,h,1,CAEQTA,i:10,h,1,CE8QBA,o:0,h,1,CE8QAQ,o:0,h,1,CE8QAA,o:0,h,1,CEwQAQ,o:0,h,1,CDsQAA,o:0,h,1,CDoQAA,o:0,h,1,CAEQTA,o:372,e,H&zx=1632943900772
    :scheme: https
    accept: */*
    accept-encoding: gzip, deflate, br
    accept-language: ru-RU,ru;q=0.9,en-US;q=0.8,en;q=0.7
    content-length: 0
    content-type: text/plain;charset=UTF-8
    cookie: SEARCH_SAMESITE=CgQIsJMB; OGPC=19025836-2:; 1P_JAR=2021-09-29-19; NID=511=Np759kcGfUexRhBu3Y3S2Fy3CVHj8K16YI83zDlWhHQAxHz6uMvOcxWk_UYivrr6DjlgE93vJVvHMtZXDrKQ0ARQ1Kv4h54Y18WRrlF8i8UsKtuHo0cy-4aXUJC6uepvzcWbM3cAkmg0ZcgqLHZv-nFts33nP1jCDJ1Mvse0jsvGp1-EAmRVM0no_zjOs99nU6I; DV=gw73cf21wNsnQIaWaSHSPtDT7qQww9f6dVREdB5duQQAAAA
    origin: https://www.google.com
    referer: https://www.google.com/
    sec-ch-ua: "Chromium";v="94", "Google Chrome";v="94", ";Not A Brand";v="99"
    sec-ch-ua-mobile: ?0
    sec-ch-ua-platform: "Windows"
    sec-fetch-dest: empty
    sec-fetch-mode: no-cors
    sec-fetch-site: same-origin
    user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/94.0.4606.61 Safari/537.36
    x-client-data: CKe1yQEIjbbJAQiltskBCMS2yQEIqZ3KAQj86soBCOryywEI7/LLAQib88sBCJ75ywEI64PMAQjYhMwBCN2EzAEI5oTMAQj5hMwBCLWFzAEI2IXMARiQnssB
    Decoded:
    message ClientVariations {
      // Active client experiment variation IDs.
      repeated int32 variation_id = [3300007, 3300109, 3300133, 3300164, 3313321, 3323260, 3340650, 3340655, 3340699, 3341470, 3342827, 3342936, 3342941, 3342950, 3342969, 3343029, 3343064];
      // Active client experiment variation IDs that trigger server-side behavior.
      repeated int32 trigger_variation_id = [3329808];
    }


Куча заголовков запросов Request. Например, здесь есть:

 1) accept - список допустимых форматов ресурса. Здесь стоит просто */* - видимо, тонкий намёк, что здесь может вместо * быть что угодно - хоть картинка, хоть текст, хоть что-либо ещё.
 2) accept-encoding - список способов кодирования контента, которые поддерживаются. Перечислены gzip, deflate и br.
 3) accept-language - очевидно, список языков, которые поддерживаются. Русский (ru-RU) и американский английский (en-US).
 4) content-length - размер содержимого. У нас оно весит 0 байт. Немного...
 5) content-type - тип контента. Текст и поле, причём кодировка UTF-8.
 6) cookie - список куков. Названия у них довольно сложны для понимания - разве что возможно, что 1P_JAR=2021-09-29-19 - это некоторая дата 19 часов 29 сентября 2021 года... Именно в это время по Гринвичу я и открыл эту страницу.
 7) origin - похоже, показывает, откуда я пришёл. А пришёл я с гугла, что и отображено: https://www.google.com.
 8) referer - показывает, где я сделал предыдущий запрос. Собственно, тоже в гугле. Потому и https://www.google.com.
 9) sec-ch-ua - показывает, что у меня за браузер. Что же, у меня действительно Гугл Хром.
10) sec-ch-ua-platform - показывает, что я виндозник. Я так чувствую, если бы я зашёл с Линукса, тут было бы написано Linux.
11) user-agent - выглядит как штука для идентификации наиболее распространённых браузеров. Чтобы можно было определить, с Мозиллы я зашёл или с Хрома, и подстроиться под текущий браузер.




Время рассмотреть ответ на запрос!


<img src="https://github.com/Transcendentall/10-Headers-of-Request-Response/blob/main/101.jpg">

Имеем:

    access-control-allow-credentials: true
    access-control-allow-origin: https://www.dvfu.ru
    cache-control: private, no-cache, no-store, must-revalidate, max-age=0
    content-length: 43
    content-type: image/gif
    date: Wed, 29 Sep 2021 20:06:53 GMT
    expires: Wed, 29-Sep-2021 20:06:53 GMT
    last-modified: Wed, 29-Sep-2021 20:06:53 GMT
    pragma: no-cache
    strict-transport-security: max-age=31536000
    x-xss-protection: 1; mode=block

Мда, негусто. Заголовков запроса было больше.

 1) access-control-allow-credentials - очевидно, эта штука говорит, следует ли нам предоставлять доступ. Раз true - то следует. 
 2) access-control-allow-origin показывает, может ли ответ сервера быть доступен коду, отправляющему запрос с данного источника. В нашем случае - с https://www.dvfu.ru.
 3) cache-control задаёт инструкции хеширования для ответа, например то, что ответ приватный (т. е. для одного пользователя).
 4) date - текущий момент. По Гринвичу.
 5) expires - дата истечения срока годности страницы. Она за 0 секунд устаревает, что указано было в cache-control с его max-age=0, так что ничего удивительного, что она устарела в ту же секунду, когда и появилась.
 6) last-modified - дата последней модификации. В нашем случае она просто обречена совпадать с двумя предыдущими датами.
 7) pragma. Здесь стоит pragma: no-cache, чтобы подчеркнуть, что запрос каждый раз надо делать заново. Ибо оно всё мгновенно устаревает.
 8) strict-transport-security - этот заголовок позволяет сайту уведомить браузер о том, что доступ к нему (к сайту, есесно) должен быть осуществлён только посредством HTTPS вместо HTTP.
 9) x-xss-protection - эта вещь останавливает загрузку страницы при обнаружении XSS-атаки. На всякий пожарный случай оно нужно, в общем.

Рассмотрим ещё что-нибудь. Например, пару военной кафедры в четверг в расписании в личном кабинете по адресу https://univer.dvfu.ru/schedule.


<img src="https://github.com/Transcendentall/10-Headers-of-Request-Response/blob/main/102.jpg">


<img src="https://github.com/Transcendentall/10-Headers-of-Request-Response/blob/main/103.jpg">

Как видно, тут появилось много новых заголовков - и заголовков Request, и заголовков Responce. Разберём ещё по нескольку тех и других.

Request:

    Accept: application/json, text/plain, */*
    Accept-Encoding: gzip, deflate, br
    Accept-Language: ru-RU,ru;q=0.9,en-US;q=0.8,en;q=0.7
    Connection: keep-alive
    Cookie: _ga=GA1.2.1154677803.1629866822; _ym_uid=162986682260831964; _ym_d=1629866822; _univer_identity=6ec573ef220bb659ee677629a4880ed00766c398c10cbfe9e2b6a1baf58f55f2a%3A2%3A%7Bi%3A0%3Bs%3A16%3A%22_univer_identity%22%3Bi%3A1%3Bs%3A50%3A%22%5B24766%2C%22zdhp1Q77PgllXAtCvZxPgMvDZ9TY2oOb%22%2C2592000%5D%22%3B%7D; _jwts=31cf74b0aee7041f9c2777e6a16954eead9c5d42e36168642b2dd92dffb5d714a%3A2%3A%7Bi%3A0%3Bs%3A5%3A%22_jwts%22%3Bi%3A1%3Bs%3A175%3A%22eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MzM5MTM0OTEsInVpZCI6MjQ3NjYsInVzZXJuYW1lIjoiYm9seWNoZXYubGkiLCJyb2xlIjoiYWRtaW4ifQ.dN57J6NGqyj2PcWMpasVqh-BZaj5eMVeTMiJZ1Brdcs%22%3B%7D; enter=true; _gid=GA1.2.242962149.1632876390; _ym_isad=2; session-cookie=16a943c41a9d0007d200a252beb261f5250860549261498fe2267ca183442cd1eb7aec0f3899a50f4c86ad11c736f935; _gat=1; _gat_gtag_UA_167081626_2=1; _ym_visorc=w; _univer_session=i42l1jgsjfbg59ktg1gg5tki7n; LtpaToken2=7fQj9Y7fTHpoN1MkiYuBuLAZxoS65YDhrEd1CtHbnt+Nkayc30DfCgmNvgBviBNx28JGyM3gQGmJOZomQ6tNr+8WHFUHw83onFfX2XNx3Y9aETLTY5P6G3fQ1oLgKi87WixzKAwULsEqb+NIaTjIVDscJmUbOcxQWq7SLfMclQXz4sP+5sMmbATMZG+j5nT9jj1iodYJ/cyF1FegmNt14ngUB4tUuqb5hYbcL4PXGJofMMbqffVCnUfdTsX1hdgpFwfjk3yIizrGjOo37NzlDetbjqUpNNu85FzUznubOFUDN6Mhz+kwKRhun9gYQIYbAY78mBYDwZAKR/FfioVJfjYjSilVpgS6pSiRh4XL1/Vwaoo2dBcVYKw6/l9hQJ1SXETgvu84qOiWqzlZlty6ug==; _csrf_univer=7a2e8329002e279049b104b0ef61c30fcb9622424a989a4a7ae2f4036464890ca%3A2%3A%7Bi%3A0%3Bs%3A12%3A%22_csrf_univer%22%3Bi%3A1%3Bs%3A32%3A%22KoS-EwTqDouEjTLQ5pNO9fe8Cblpc8Eh%22%3B%7D; _gat_gtag_UA_132455446_2=1
    Host: univer.dvfu.ru
    Referer: https://univer.dvfu.ru/schedule
    sec-ch-ua: "Chromium";v="94", "Google Chrome";v="94", ";Not A Brand";v="99"
    sec-ch-ua-mobile: ?0
    sec-ch-ua-platform: "Windows"
    Sec-Fetch-Dest: empty
    Sec-Fetch-Mode: cors
    Sec-Fetch-Site: same-origin
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/94.0.4606.61 Safari/537.36

12) Connection - вид интернет-соединения. В нашем случае оно keep-alive, то есть удерживающееся живым, то есть постоянное.
13) Host - имя домена. То бишь сам "Мой универ" в лице адреса univer.dvfu.ru.


Responce:

    Cache-Control: no-store, no-cache, must-revalidate
    Connection: keep-alive
    Content-Type: application/json; charset=UTF-8
    Date: Wed, 29 Sep 2021 20:25:04 GMT
    Expires: Thu, 19 Nov 1981 08:52:00 GMT
    Pragma: no-cache
    Set-Cookie: _univer_identity=6ec573ef220bb659ee677629a4880ed00766c398c10cbfe9e2b6a1baf58f55f2a%3A2%3A%7Bi%3A0%3Bs%3A16%3A%22_univer_identity%22%3Bi%3A1%3Bs%3A50%3A%22%5B24766%2C%22zdhp1Q77PgllXAtCvZxPgMvDZ9TY2oOb%22%2C2592000%5D%22%3B%7D; expires=Fri, 29-Oct-2021 20:25:04 GMT; Max-Age=2592000; path=/; domain=.dvfu.ru; HttpOnly; SameSite=Lax; Secure
    Strict-Transport-Security: max-age=15768000; includeSubDomains; preload;
    Transfer-Encoding: chunked
    X-Content-Type-Options: nosniff
    X-Download-Options: noopen
    X-Permitted-Cross-Domain-Policies: none
    X-Robots-Tag: none
    X-XSS-Protection: 1; mode=block

10) Transfer-Encoding - это механизм передачи данных. В нашем случае он chunked - механизм передачи данных в протоколе передачи гипертекста (HTTP), позволяющий надёжно доставлять данные от сервера клиенту без необходимости заранее знать точный размер всего тела HTTP-сообщения.
11) X-Robots-Tag - этот заголовок с самым интересным названием (казалось бы, причём тут роботы??? Почему не просто "боты"?) позволяет сообщать ботам поисковых систем инструкции по индексации страницы даже без загрузки содержимого самой страницы. none - значит, не показывать страницу в результатах поиска. Потому мы и не можем так просто взять и посмотреть расписание не из личного кабинета.

Как-то так.

# Вывод:
Итак, мы рассмотрели много различных заголовков и более-менее определили, на что они указывают и зачем они нужны. Следовательно, поставленная цель достигнута.
