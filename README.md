# hackathon
ТЗ для Хакатона.

В качестве преобразователя данных в фичи используем Word2Vec
Будем тестировать разные предподготовленные модели:

(ссылка - https://github.com/3Top/word2vec-api#where-to-get-a-pretrained-models)

1- Google News	300	Google News (100B)
2- Wikipedia+Gigaword 5	100	Wikipedia+Gigaword 5 (6B)
3- Wikipedia+Gigaword 5	200	Wikipedia+Gigaword 5 (6B)
4- Wikipedia+Gigaword 5	300	Wikipedia+Gigaword 5 (6B)
5- Common Crawl 42B	300	Common Crawl (42B)
6- Common Crawl 840B	300	Common Crawl (840B)
7- Twitter (2B Tweets)	50	Twitter (27B)
8- Twitter (2B Tweets)	100	Twitter (27B)
9- Twitter (2B Tweets)	200	Twitter (27B)

После этого идет преобразование нашего датасета в фичи:
Фичи 1-3 : word2vec similarity между словами 1-2 2-3 1-3 
Фичи 4-5 : Можно потестировать фичи из бейслайна - встречаемость маркера (слово номер 3) в статьях с википедии про слова 1 и 2 (за примером см бейслайн)
Фича 6 : показатель 0/1 является ли "третьим лишним" маркер (0 - нет 1 - да)

После этого датасет делится на части как в бейслайне и тренируется модель. я бы выбрал  Линейную регрессию, прияем взял бы на себя тесты ее Характеристик

По итогам встраиваем evaluation script и по нему (важно, тк может отличаться от склерна) проводим тесты всего на свете
