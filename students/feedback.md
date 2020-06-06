2-а домашня робота
------------------

Трохи статистики по другій домашці:
[1] Найпопулярніші багатозначні слова: куля і міст. Натомість серце і добро ніхто не розібрав :broken_heart:
[2.1] Найкраща якість форматування заголовків вийшла 99% :clap:
[3.1] Найдовший синонімний ряд до “say” — 54 синоніми :clap:
:medal:

Троє людей отримують зірочку за шміфікатор :clap:
@Yehor Shapanov           @Lera          @Kostiantyn Zuiev
             :star2:                           :star2:                           :star2:

А тут приклади онлайн інструментів для форматування заголовків:
* https://capitalizemytitle.com/
* https://titlecaseconverter.com/
* https://headlinecapitalization.com/

Можете порівняти зі своїм варіантом і навіть свій сервіс зробити :wink:

3-а домашня робота
------------------

Всім привіт!
Ще раз хотів підсумувати результати домашки по обробці даних, бо після заняття ще дійшли деякі нові і цікаві роботи.
1. Отже, по задачі на парсинг Wiktionary. В принципі, всі впорались (з тих, хто надіслав), але у більшої половини був фейл з тим, що ви не дивились на результат і не намагались його проаналізувати :male-teacher:. Рекомендую глянути роботу Ігоря, він взяв найцікавішу мову (китайську) і зробив гарний аналі та тестування: https://github.com/vseloved/prj-nlp-2020/blob/master/students/IgorBurian/03-data/1-wiktionary.ipynb
2. Задача анотацій. Також, звісно, всі справились, хоча й не всі зробили те, чого вимагала інструкція :smile: Кожен з файлів було розмічено двома анотаторами (за винятком двох, де виявились баги) і ось невеличка статистика узгодженості між вами (там мною у деяких випадках).
3. Підрахунок узгодженості між анотаторами. Ця задача була найскладнішою і мала найбільший простір рішень. Мені сподобалось, що багато з вас спробували різні підходи. Найбільш цікаві роботи:
- Дуже ґрунтовно і систематично підійшов до задачі Саша: https://github.com/vseloved/prj-nlp-2020/blob/master/students/OleksandrPetrov/03-data/README.md#problem-3-inter-annotator-agreement-for-text-corrections
- Діма Бабенко таки порахував Каппу Коена: https://github.com/vseloved/prj-nlp-2020/blob/master/students/DmytroBabenko/03-data/I-3-inter-annotator-agreement.ipynb Все вийшло гарно і показово. А також, що важливо, є кореляція з іншими підходами
- Ідея застосувати LCS/diff була реалізована, здається, у двох роботах. Все просто і зрозуміло у Людмили: https://github.com/vseloved/prj-nlp-2020/blob/master/students/LiudmylaSlava/03-data/inter-annotator-agreement.ipynb
4. Курсовий. Менше половини з вас прислали щось по даним. Це не те, щоб пригнічує, але є тривожний дзвіночком для нас. З деким з вас ми спілкувались з приводу курсового особисто. А тих, хто нічого не прислав і з нами не спілкувався — просимо поговорити у найближчий час. Ми завжди відркиті...

4-а домашня робота
------------------
Я померджив всі поданя роботи по 4-й домашці. З різних причин (у когось форс-мажор, а комусь, схоже, не сподобалось завдання) це поки що вийшла найменш популярна зі всіх - тільки 10 спроб. Серед робіт я би знову хотів виділити Ігоря - https://github.com/vseloved/prj-nlp-2020/tree/master/students/IgorBurian/04-nlp-full-circle
гарно показав власне роботу з правилами (в тому числі з використанням дерев зі спейсі)
ще й навчився робити наворочені SPARQL-запити
прикольна тематика



5-а домашня робота
------------------
@here, перепрошую за затримку з перевіркою п‘ятої домашки і дякую за ваше терпіння. :pray: Ми надолужуємо :muscle:
Я вже проглянула всі рішення і хотіла звернути вашу увагу на кілька пунктів :slightly_smiling_face: Впевнена, що @Seva також додасть коментарів після того, як додивиться.
1. На дані завжди потрібно дивитись і чистити їх :slightly_smiling_face: Навіть якщо про це не написано в завданні.
Що точно можна було почистити у відгуках: запитання, привітання (“добрий день” — тут є слово “добрий“), дублікати повідомлень.
2. У декого вийшло ну зовсім мало даних — до 100 відгуків на цілий клас, з яких 20 пішло на тестування. На такому обсязі складно щось покращувати, тож варто думати про те, де взяти більше даних:
Розбити кожен відгук на три частини: основна частина, переваги і недоліки. Основну частину проанотувати за зірочками, переваги — позитивні, недоліки — негативні (якщо там нема тексту на кшталт “нема” чи “не виявлено“).
Доскрейпити :muscle:
Зробити upsampling.
Перекласти з російської на українську.
3. Схоже, не всі зрозуміли, нащо потрібна кросвалідація.
Тестувальна вибірка — це еталонні дані. Ви на них міряєте якість двічі: коли побудували базове рішення і коли маєте фінальне рішення. Проміжні рішення на ній міряти не треба, бо ви тоді заточитесь на ці дані і їх можна буде викинути (це те, що називається overfitting). На тестувальних даних теж добре порівнювати рішення різних людей, наприклад.
Кросвалідація показує дві речі: як міняється якість на проміжних рішеннях і наскільки ця якість стабільна на нових даних. Якщо кросвалідація на п’яти згортках показує різницю в 10%, то результатам на тестувальній вибірці точно вірити не можна)
Отже, по-хорошому варто перевіряти якість кожного наступного рішення лише через кросвалідацію, вибрати найкраще рішення за показниками кросвалідації, а тоді вже тестувати фінальне рішення на тестувальній вибірці, щоб побачити, як покращилась якість у порівнянні з базовим рішенням.
Звісно, коли часу зооовсім нема, даних ну дуууже багато і це всього лиш домашка, то можна і на тестувальній міряти, але в інших випадках варто таки дотримуватись такої гігієни даних. :slightly_smiling_face: 

Кілька додаткових коментарів :star2:
Більшість ставили затримки, коли скрейпили. Молодці :+1:
Більшість проставляли random_state при поділі даних. Молодці :+1:
Найпопулярніший мовний фільтр — langdetect.
Найпопулярніший клас для трьох зірочок — негативний.
Тут гарний тред про train/validate/test: https://stats.stackexchange.com/questions/19048/what-is-the-difference-between-test-set-and-validation-set і ще Data Robot коротко написав: https://www.datarobot.com/wiki/training-validation-holdout/
Кожна модель має свої гіперпараметри. По-хорошому, їх треба підібрати. Але не руками, звісно :slightly_smiling_face: Для цього існує, наприклад, Random Search та Grid Search. Ось тут можна почитати більше: https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74

Щодо прогону моделей на тестувальній вибірці, я би все-таки не був настільки категоричним. Те, що точно не можна робити на ній — це підбирати гіперпараметри моделі (Random або Grid Search, про які написала Мар'яна вище). Що стосується одного прогону кожної нової моделі, то це не має призводити до overfitting'у, якщо, звісно, ви не підбираєте нові ознаки, роблячи аналіз помилок на валідаційній вибірці. Тобто, якщо ви додали набір нових ознак або якіс перетворення з якихось власних міркувань і проганяєте нову модель на валідаційних даних, то на це нема табу. Але й не треба цим зловживати, роблячи новий прогон на кожну нову ознаку. Особливо, якщо даних мало і зміни у якості можуть бути викликані випадковими співпадіннями, а ви їх сприймете за реальне покращення :slightly_smiling_face:

Скоро вже зможемо змержити все і по 5-й. До коментарів Мар'яни вище я б ще додав наступне:
найбільша складність з класом neutral, і це логічно, бо він чітко не визначений. Якщо брати 4:star: або ще й 3:star:, то нема гарантії, що частина відгуків там не буде досить позитивною. Тут би не завадило подивитись на матрицю плутанини, але, на жаль, цього ніхто не зробив. Також можна було б спробувати пошукати особливі ознаки, які могли б виділити саме нейтральний клас (наприклад, наявність як позитиву, так і негативу у відгуку - скажімо по тональному словнику). В принципі, це могло б вкластись навіть у звичайну bow-модель, якщо заміняти позитивні та негативні слова на спеціальні токени pos/neg, або навіть не заміняти, а, просто, додавати ці токени). Дехто взагалі позбувся цього класу. В принципі, це може бути цілком логічним рішенням (особливо, якщо б воно було підкріплено матрицею плутанини, якби вона була).
Ніхто не спробував класифікувати на 5 класів - для кожної зірочки, хоча Дмитро Будашний і питав про це. Зрозуміло, що даних, загалом, не так багато. Але були варіанти збільшити їх кількість: перекласти з російської, розширити категорії товарів. А було б цікаво подивитись (звісно, гарної якості очікувати не доводиться)
Щодо якості. Майже у всіх загальна якість вийшла в діапазоні 60-80% macro average f1. Для таких досить шумних даних це може бути цілком нормально. Виключення класу neutral дозволяло дійти навіть до 80+. Єдине виключення — Дмитро Сакович, який досяг майже 95% для 3-х класів! з використанням заборонених технік :merman: Насправді, виглядає так, що не заборонених, а просунутих, але в мене все ж є сумніви у достовірності таких гарних оцінок просто через те, що вихідні дані надто шумні для того, щоб на них можна було взагалі сподіватись на подібну якість - тож чекаємо від нього деяких доробок, але можна всім подивтись на його код і пошукати витоки aka data leaks (@Dima Sakovich, сподіваюсь, ти не проти? :wink: )

І ще одне: дехто застосовував undersampling. Для bow-моделей краще підходить upsampling (тобто збільшувати кількість прикладів недопредставлених класів), адже тоді не втрачаються потенціно цікаві ознаки із переважаючих класів

Ще раз (мабуть, вже в останнє) по 5-й роботі хотів порекомендувати всім зацікавленим подивитись ці роботи:
У Ігоря дуже гарний аналіз даних: https://github.com/vseloved/prj-nlp-2020/blob/master/students/IgorBurian/05-bag-of-words/analysis.ipynb
У Олега гарна передобрбка даних, яка у комбінації з ігнором нейтрального класу :grin: дозволила отимати гарний результат класифікації: https://github.com/vseloved/prj-nlp-2020/blob/master/students/OlehPalianytsia/05-bag-of-words/sentiments.ipynb
У Діми цікава історія експериментів, приклад застосування більш просунутих класифікаторів та т'юнінгу параметрів: https://github.com/vseloved/prj-nlp-2020/tree/master/students/DimaSakovich/05-bag-of-words

6-а домашня робота
------------------

Щодо 6-го домашнього завдання:
Якщо працюватимете з логістичною регресією, передбачення буде на рівні токена.
Якщо працюватимете з умовними випадковими полями (CRF), передбачення буде на рівні речення (ланцюжка токенів).
Просто трішки буде відрізнятися структура вхідних даних.

Щодо 6-го домашнього завдання і енграмів :slightly_smiling_face:
Енграми токенів справді займають багааааато місця #bigdata #комузаразлегко. Якщо у вас місця нема і навіть Google Cloud забитий:
Ви можете викачати частоти тільки потрібних вам енграмів через API з Google Ngrams чи, наприклад, https://phrasefinder.io/. Потрібні вам енграми — це ті, які вам трапляються у ваших тренувальних та тестувальних даних.
Ви можете знайти чи зібрати частиномовні енграми. Вони займатимуть набагато менше місця.
Ви можете обмежитись самими триграмами чи біграмами токенів. Фактично, вам потрібно порівняти ймовірність `word1 word2` vs. `word1 . ` and `<S> Word2`.
Будьте креативними, діліться рішеннями, не відкладайте домашку до суботи :wink:

Для задачі передбачення кінця речення на даних з шостої домашки:
Найкраще рішення: 0.74 F1 для класу True та 0.99 F1 для класу False.
Середнє рішення: 0.5 F1 для класу True та 0.97 F1 для класу False.
    
Чому корисно склеювати речення для тренування: бо інакше такі ознаки, як глибина синтаксичного дерева, будуть неінформативними. Тим не менш, можете пробувати різні варіанти. Я зовсім не проти :slightly_smiling_face:
    
Всім привіт! Я подивився всі 6-ті домашки. Ще має Мар'яна всі переглянути і змержити. Хотів знову поділитись декількома загальними спостереженнями:
Дані. Як написала Людмила: "Датасет важливий  `¯\_(ツ)_/¯`" Вибачте, що я також не перестаю це повторювати :slightly_smiling_face: Оскільки про тестові дані ми нічого не знали, то мало сенс намагатись створити збалансований датасет з різних жанрів (не тільки худліт, але й публіцистику і т.д.) Дехто з вас це зробив і отримав суттєво кращі рещультати
Загалом, найкращий результат по якості — 75+% по True-класу, що є дуже гарним для цієї задачі, особливо, в умовах обмеженого часу на фічер-інжиніринг. @Dima Sakovich, як завжди, відмітився зі своїм LighGBM :slightly_smiling_face: До речі, на цю задачу, як на мене, класифікатори на основі дерев дуже гарно лягають, бо набір ознак може бути досить обмежений і кожна з ознак - показова. До речі, в них можна було б легше інтегрувати нграми, використовуючи (квантизовану) числову ознаку відношення двох ймовірностей (чого Діма. до речі не робив).
У інших використання CRF, зазвичай, давало перевагу над регресією чи іншими "локальними" класифікаторами
Здається, ні в кого реально не вийшло щось путнє зробити з нграмами. Дехто намагався збирати їх на своїх навчальних корпусах, але на таких невеликих об'ємах вони, як правило, не дають ніяких покращень. Тож варто одразу брати webscale. Всього один хтось зміг знайти і скачати готову модель. Це, власне, найефективніший шлях їх викорстання в цьому контексті.
З робіт, які варто виділити, мені найбільше сподобалось те, що зробила @Liudmyla Slava: https://github.com/vseloved/prj-nlp-2020/blob/debc676ca402febf5692b19d8c8dc615bdc01289/students/LiudmylaSlava/06-language-as-sequence/run_on.ipynb - все гарно структутровано і зрозуміло, досить гарні результати, обґрунтовані висновки

додам кілька слів про шосту домашку.
1. Мало хто скористався ознаками з дерева. Зате ті, хто скористались, виявили, що найближчий спільний предок (lowest common ancestor) — це дуже інформативна ознака :slightly_smiling_face: Те, що дерева на склеєних реченнях виходять поламані, — це нормально. Це якраз і є корисна інформація для класифікатора.
2. Базове рішення треба будувати, щоб знати нижню межу :slightly_smiling_face: Зацініть, наприклад, базове рішення @Kostiantyn Zuiev: https://bit.ly/2WI7LOi. Таке рішення одразу гарно задало нижню межу по якості:
```
    False      0.97      1.00      0.99      4542
    True       0.90      0.24      0.38       155
```
Побити таке базове рішення вже буде складніше.
3. Додам іще два слова про енграми, бо розумію, що всі з ними настраждались :muscle:
У цій задачі просто частотність/ймовірність послідовності слів/тегів не є інформативною для класифікатора. Класифікатору треба знати, що ймовірніше: word1 word2 word3 чи word1 word2 .. Наприклад, можна було додати такі ознаки:
булеву: `ngrams("word1 word2 word3") < ngrams("word1 word2 .")`
окремими ознаками, але нормалізувавши числа (або за шкалою від 0 до 1, або в набір класів low/medium/high):
```
features["3gram"] = normalize(ngrams("word1 word2 word3"))
features["3gram_period"] = normalize(ngrams("word1 word2 ."))
```

а ще, класно було б додати таку нграмну ознаку, як відношення: log(ngrams("word1 word2 word3")/ngrams("word1 word2 .")) І, можливо, пертворит його на категоріальну ознаку, скажімо, таким чином: -∞..-5 - 1, -5..-1 - 2, -1..0- 3, 0..1 - 4, 1..5- 5, 5..∞ -6. Чи щось подібне, це можна вивести з даних. Тобто, ідея в тому, щоб відобразити відношення між цими двома величинами: сильно відрізняються чи слабо і в який бік...

8-а домашня робота
------------------

@here, кілька слів про восьму домашку (покращення парсера залежностей) :deciduous_tree:
Зауваження
Знаю, що всі вже звикли міряти якість усього через classification_report, тому дехто поміряв лише якість визначення правильної дії над стеком і чергою. Проте якість самого парсера міряється таки через метрики UAS та LAS, які міряють точність проставлення залежностей. :straight_ruler:
Граматичні ознаки ("feats") є інформативними для парсера, але їх варто закодовувати по одній, а не збивати в купу. Краще так:
```
for k, v in stack[0]["feats"].items():
    features["s0-" + k] = v
```

Серйозне зауваження щодо витоку даних
Витік даних трапляється, коли ви додаєте ознаку, яка вже містить інформацію про клас. У цій задачі було кілька ознак, які не можна додавати. Тим більше, що на реальних даних цих ознак ніколи не буде:
stack[0]["head"], а також батьки інших вузлів, плюс всі ознаки батьків
stack[0]["deprel"], а також типи зв‘язків інших вузлів до їх батьків
stack[0]["deps"] (див. вище)
кількість дітей stack[0], порахована на цілому дереві, а не на relations
Про що ж писало в книжці та статтях про парсинг? Там же були такі ознаки!
У книжці (та статтях) писало про ознаки залежностей, які ви вже побудували і записали (на занятті це була змінна relations). Наприклад, ви уже раніше побудували зв‘язок від stack[0] до якогось вузла, який уже редюснули, і цей зв’язок потрапив до relations. Тепер його можна використати для збору ознак по stack[0] у новому стані парсера. Також можна порахувати і кількість дітей, які вже має stack[0].
Цікаві роботи
В @Oleh Palianytsia класна робота з ознаками :muscle:  Зацініть.
@Lera і @Igor імплементували SWAP :muscle:  Зацініть.
@Yehor Shapanov імплементував визначення типів залежностей :muscle:  Зацініть.

9-а домашня робота
------------------

@here, по 9-ій роботі було мало рішень, тому висновків особливо нема :slightly_smiling_face:
У всіх був гарний вибір базового рішення:
схожість на векторах дала 0.29-0.38 (macro avg)
різниця довжин дала 0.34 (macro avg)
перетин слів дав до 0.48 (macro avg)
Хочу відзначити роботу @Dima Sakovich. Йому вдалося досягнути 0.77 (macro avg) :muscle: на елегантному наборі ознак:
https://github.com/vseloved/prj-nlp-2020/blob/9429e54b9b1a82f76c0d4ffd5f546a0b6634c4cb/students/DimaSakovich/09-textual-entailment/notebook.ipynb 

Діма :star:
Я ще не все передивився всі роботи, але хотів би додати таку деталь: як я зрозумів, всі чи більшість використовували підхід рахувати тільки ознаки на рівні цілого тексту (перетини множин слів, схожості і т.і.). Але якраз в цій задачі важливу роль відіграє саме структура тексту, яку ці ознаки не вловлюють. Тому у них є певна стеля якості, до якої, можливо, впритул підійшов Діма. (edited) 
2:48
Але щоб обробити складні кейси, як на мене, треба робити не порівняння на рівні всього речення, а вибирати окремі структурки subject-verb-object(s), шукати відповідники і матчити їх, а потім комбінувати результат з використанням додаткової логіки чи моделі

10-а домашня робота
-------------------

@here Всім привіт!
Деякі підсумки 10-ї роботи по векторам.
Я багато робив різних нотаток по ходу прервірки, але останньою перевірив роботу Діми Бабенко, яка, по суті, єдина була повноцінним рішенням. Видно, що він на неї витратив багато часу, але результат довів, що не дарма. Рекомендую переглянути його ноутбук, кому цікаво, як можна було підійти до групування категорій запитів і побудови багаторівневого класифікатора (на що я вам натякав): https://github.com/vseloved/prj-nlp-2020/blob/master/students/DmytroBabenko/10-vectors/10-vectors.ipynb :man-lifting-weights:
Також йому вдалось натренувати fasttext, щоб отримати суттєво кращу якість на ньому, ніж на готових векторах. Плюс багато роботи з даними і їх багаторівневого очищення :) Те, на що більшості не вистачило часу, як я зрозумів.
Що ще хотів сказати:
- Те, що багато з вас страждало з всім цим набором брудних даних — очікувано. В цьому була одна з ідей цієї роботи: попрацювати не з вилизаним корпусом, а з hairy-noisy-dirty real-world(tm) датасетом. Вибачте. І, як видно з роботи Дмитра, треба витратити дуже багато зусиль, щоб пригладити ці шероховатості перед тим, як можна приступити власне до побудови основного рішення. Звісно, там непахане поле для нормалізації (виправлення слів з помилками, приведення до українських, абревіатури типу ХВП, позбування NER'ів, і т.д. і т.п.)
- класно, що майже кожен спробував різні алгоритми кластеризації, з яких, схоже, найкраще спраюцював AffinityClustering у Людмили (https://github.com/vseloved/prj-nlp-2020/blob/master/students/LiudmylaSlava/10-vectors/classification.ipynb). Загалом, вона гарно підійшла до задачі
- ще цікава була ідея у Жені подивитись на виконавця. Це ж логічно, що категорії різних виконавців не мають потрапляти в один кластер. На жаль, до кінця він це не реалізував.
- також, як визначила Лєра, багато важливих слів з комунальної теми (таких як "сміттєзбірник") не мають векторів. І це є проблема, яку, схоже, вдалось подалати лише Дімі.
- що стосується k-nn, то також цікавий результат у Лєри: найкращу якість дало значення n=1 :) Це можна пов'зати, як і показує візуалізація з тим, що класи слабо розділені по векторам.
