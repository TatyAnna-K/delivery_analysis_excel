# Развитие сервиса доставки еды

## Описание бизнес – задачи
Владельцу кафе индийской кухни необходимо решить, какой транспорт лучше закупить для самостоятельной доставки заказов, чтобы не потерять клиентов и выручку. Условия и ограничения:
*	бизнес рассматривает возможность покупки только велосипедов или только автомобилей;
*	на одном автомобиле можно увезти 10 заказов по 16 блюд, а на одном велосипеде — 4 заказа по 10 блюд;
*	транспорт может совершить только 1 рейс в день;
*	чтобы транспорт выехал на доставку, он должен быть полностью загружен;
*	у клиента нет возможности заказать блюд больше, чем вмещает в себя транспорт;
*	в расчет брать только данные за 2018 г.

## Как я решала эту задачу
1.	Проверила данные на наличие ошибок и исправила их: с помощью фильтров удалила данные за 2015 г., смещенные значения вернула в их ячейки, исправила некоторые названия блюд с помощью функции «Найти и заменить».
2.	Создала сводную таблицу «Статистики» для расчета базовых статистических показателей:  среднего значения, медианы, моды, дисперсии, стандартного отклонения, а также посчитала общее число заказов.
3.	На основе этой же сводной таблицы с помощью функции «СЧЁТЕСЛИ» посчитала количество заказов, в которых блюд меньше или равно 10, а затем количество заказов, в которых блюд меньше или равно 16. А также посчитала долю этих заказов от общего количества заказов.
4.	С помощью функции «СУММЕСЛИ» посчитала сумму заказов, в которых блюд меньше или равно 10, а затем сумму заказов, в которых блюд меньше или равно 16.
5.	Далее создала сводную таблицу с датами и количеством заказов «Дата и кол.свод» и скопировала ее значения в обычную таблицу «Дата и кол.».
6.	На основе таблицы «Дата и кол.» создала еще две сводных таблицы «Расчет транспорта». Здесь я сгруппировала данные по датам и количеству заказов, отфильтровав их по количеству блюд в заказе: по 10 и 16 соответственно.
7.	Затем я поделила количество заказов за каждый день на максимальное число заказов на один рейс, то есть на 4 заказа для велосипедов и на 10 для автомобилей, и округлила полученные значения в большую сторону с помощью функции «ОКРВВЕРХ.МАТ».
8.	Из полученных значений я нашла максимальное число рейсов за день в течение года с помощью функции «МАКС». Это число показывает максимальную потребность в велосипедах и автомобилях.
Файл «Results» в Excel  со всеми расчетами можно посмотреть здесь: [Results.xlsx](./Results.xlsx)

## Для анализа использовала данные
 Для анализа данных были использованы материалы Академии Eduson. В качестве исходных данных был дан файл Excel со следующей информацией: 
- о номере заказа (Order Number);
- о времени заказов за год (Order Data);
- о заказанных блюдах (Item Name);
- о количестве блюд (Quantity);
- о цене каждого блюда (Product Price);
- о количестве блюд в заказе (Total Products).  
Исходный файл «data_analysis» можно посмотреть здесь: [data_analysis.xlsx](./data_analysis.xlsx)

## Результаты
По результатам анализа я составила аналитическую записку («analytical_note»). Ее можно посмотреть здесь: [analytical_note.docx](./analytical_note.docx)

## Выводы
Исходя из проведенного анализа, расходы на приобретение велосипедов и автомобилей имеют небольшую разницу: 3 336 руб. в пользу велосипедов, но доля потерянной выручки при покупке велосипедов значительная и составляет 25%. При этом доля потерянной выручки при закупке автомобилей гораздо меньше – 8 %. Также при покупке велосипедов доля потерянных клиентов составит 14%, в то время, как при покупке автомобилей, всего 3%.

## Рекомендации
Владельцу кафе выгоднее приобрести автомобили для доставки заказов. Несмотря на незначительную экономию бюджета при покупке велосипедов, потери выручки и клиентской базы оказываются значительными и существенно превышают выгоду от экономии расходов. Выбор автомобилей обеспечит стабильное развитие бизнеса, сохранение лояльности клиентов и максимизацию прибыли.  
**Дополнительная рекомендация**  
Стоит рассмотреть возможность постепенного увеличения автопарка, начиная с небольшого количества машин, постепенно оценивая эффективность и потребности рынка. Таким образом, владелец сможет оптимизировать затраты и обеспечить гибкость в управлении доставкой.


