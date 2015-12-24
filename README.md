<h1>Скрипт интеграции amoCRM с Justclick, и не только</h1>

<h3>Зачем нужен этот скрипт:</h3>
Этот скрипт автоматически создает связанные сделку и контакт в amoCRM при заказе товара в Justclick.
<br>А при оплате заказа - статус в amoCRM меняется на "Успешно реализовано".

С помощью небольших корректировок этот скрипт легко можно адаптировать для интеграции amoCRM <b><u>с любой другой системой</u></b>, отправляющей массив данных при заказе.

<h3>Особенности работы:</h3>
<b>Привязка контакта к сделке</b>
<br>Все контакты привязываются к соответствующим сделкам.
<br>В случае, если контакт с таким email уже существует, сделка привязывается к уже существующему контакту. Новый не создается.
<br>Однако есть небольшой баг в алгоритме поиска контактов. Если в email до или после собачки @ меньше 3 знаков, то эти знаки в поиске не учитываются, и сделка может привязаться к похожему контакту. К счастью ошибки из-за этой особенности возникают крайне редко.

<h3>Настройка:</h3>
1. В файле prepare.php отредактируйте данные и переменные из полученного массива, которые вы хотите использовать;
2. В файле auth.php замените данные для авторизации на ваши данные amoCRM: Логин (email), Хэш (ключ API) и субдомен;
2. В файле leads_info.php в верхней части скрипта отредактируйте список переменных для дополнительных полей, как вам нужно;
3. В файлах lead_add.php и lead_update.php отредактируйте id дополнительных полей и какие переменные вы хотите в них отправлять.

<h3>Тестирование:</h3>
В это скрипте уже заложена удобная функция тестирования. 
<br>Вам не нужно каждый раз заполнять форму и делать заказ на интегрируемом сервисе. 
<br>Просто откройте корневую папку (файл index.html) после загрузки скрипта на Ваш хостинг, и вы увидите 2 кнопки: Order (Заказать) и Paid (Оплачено). Нажав на любую из них, Вы сымитируете отправку массива сервисом.
<br>Чтобы воспользоваться функцией тестирования, уберите на время тестирования значок # перед последней строкой в файле prepare.php, и замените массив в файле test/prepare.php на тот, который отправляет при заказе и оплате сторонний сервер.

<h3>Техподдержка:</h3>
Если у вас что-то не получается или появились какие-то вопросы, пишите мне в личку. 
<br>С удовольствием Вам помогу!
