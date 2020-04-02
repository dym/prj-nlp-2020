## Заголовки новин

### 1. Форматування

[The Associated Press Stylebook](https://www.amazon.com/Associated-Press-Stylebook-2017-Briefing/dp/0465093043/) - це посібник зі стилю, яким часто послуговуються журналісти по всьому світу. Він рекомендує такі правила форматування заголовків:
1. З великої літери потрібно писати слова довжиною 4 чи більше літер.
2. З великої літери потрібно писати перше і останнє слово заголовку, незалежно від частини мови.
3. З великої літери потрібно писати іменники, займенники, дієслова, прикметники, прислівники та підрядні сполучники.
4. Якщо слово написане через дефіс, велику літеру потрібно додати для кожної частинки слова (наприклад, правильно "Self-Reflection", а не "Self-reflection").
5. З маленької літери потрібно писати всі інші частини мови: артиклі/визначники, сурядні сполучники, прийменники, частки, вигуки.

**Завдання:**
1. напишіть програму, яка форматує заголовки за вказаними правилами
2. перевірте якість роботи програми на [валідаційній вибірці](data/headlines-test-set.json)
3. проженіть вашу програму на [корпусі заголовків з The Examiner](data/examiner-headlines.txt) і вирахуйте, скільки заголовків там відформатовано за правилами (скільки заголовків залишились незмінними після форматування)
4. збережіть програму та числові результати у директорії з вашим іменем

Якщо потрібно продебажити роботу програми, робіть це на [корпусі заголовків з The Examiner](data/examiner-headlines.txt), а не на валідаційній вибірці. Спробуйте досягти хоча б 90% якості на валідаційній вибірці. Якість рахуємо за повним збігом відформатованого заголовка.

Підказка: ваша програма повинна правильно розрізняти прийменники та підрядні сполучники. Наприклад, `Do as you want` => `Do As You Want` (бо "as" тут є сполучником), but `How to use a Macbook as a table` => `How to Use a Macbook as a Table` (бо "as" тут є прийменником).

### 2. Вірусні новини

У статті [Automatic Extraction of News Values from Headline Text](http://www.aclweb.org/anthology/E17-4007) описано основні ознаки заголовків, які кидаються в очі і змушують читача таки прочитати новину:
1. іменовані сутності (імена людей, назви компаній тощо)
2. емоційне забарвлення
3. вищий і найвищий ступені порівняння
4. близькість до читача
5. елемент несподіванки
6. унікальність

**Завдання:**
1. Напишіть програму, яка аналізує заголовок за першими трьома ознаками (у спрощеній формі)
   * Чи є в заголовку іменовані стуності?
   * Чи є заголовок позитивно чи негативно забарвлений?
   * Чи є в заголовку прикметники та прислівники вищого і найвищого ступенів порівняння?
2. Проженіть вашу програму на [корпусі заголовків з The Examiner](data/examiner-headlines.txt). Для кожної з трьох ознак визначте відсоток заголовків у корпусі, які її мають.
3. Збережіть програму та пораховану статистику в директорії з вашим іменем.

Додаткова інформація:
- Типи сутностей, які впливають на "вірусність" заголовка, виберіть самостійно.
- Для визначення емоційного забарвлення, використайте [SentiWordNet](https://github.com/aesuli/sentiwordnet). Наприклад, можна перевірити, що середнє значення позитивності/негативності слова у заголовку перевищує 0.5. Для визначення середнього значення можна брати до п'яти перших значень слова з такою частиною мови. Будьте креативними та експериментуйте. Можна користуватися SentiWordNet з бібліотеки [NLTK](http://www.nltk.org/howto/sentiwordnet.html).

### Джерела

Ви можете використати будь-яку мову програмування та будь-яку NLP-бібліотеку.

Набір заголовків взятий із https://www.kaggle.com/therohk/examine-the-examiner.