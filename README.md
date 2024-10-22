<h1>Functional Requirements:</h1><br>
1.Створення нового документа:<br>
Як адміністратор, я хочу додавати нові документи до бази даних.<br>
2.Перегляд списку документів:<br>
Як користувач, я хочу переглядати списко наявних документів.<br>
3.Пошук документів:<br>
Як користувач, я хочу шукати докумен за ключовими словами, датою, категорією, щоб полегшити процес пошуку.<br>
4.Редагування документів:<br>
Як адміністратор, я хочу редагувати документи для виправлення помилок.<br>
5.Видалення документів:<br>
Як адміністратор, я хочу видаляти документи, щоб позбуватись не актуальної, або не потрібної інформації.<br>
6.Категоризація документів:<br>
Як адміністратор, я хочу надавати категорії документам, щоб можна було зручніше сортувати.<br>
7.Архівація документів:<br>
Як адміністратор, я хочу архіювати документи для подальшого перевірки та можливого видалення.<br>
8.Повідомлення про терміни дії документів:<br>
Як користувач, я хочу получати повідомлення про терміни дії документів.<br>
9.Завантаження та збереження документів:<br>
Як користувач, я хочу завантажувати та зберігати документів у форматі файлів.<br>
10.Аудит дій користувачів:<br>
Як адміністратор, я хочу получати аудит дій інших адміністраторів для відстеження всіх змін в документах.<br>
<br><h1>System Behaviours:</h1>
1.Створення нового документа:<br>
Користувач вибирає опцію створення нового документа.<br>
Система відображає форму для введення необхідної інформації (назва документа, категорія, дата тощо).<br>
Після введення користувачем необхідних даних система зберігає новий документ у базі даних.<br>
2.Перегляд списку документів:<br>
Користувач обирає опцію перегляду списку документів.<br>
Система отримує дані про всі документи з бази даних та відображає їх у вигляді списку на екрані користувача.<br>
3.Пошук документів:<br>
Користувач вводить критерії пошуку (ключові слова, дату, категорію тощо).<br>
Система проводить пошук серед документів у базі даних, які відповідають введеним критеріям.<br>
Результати пошуку відображаються користувачеві.<br>
4.Редагування документів:<br>
Користувач вибирає документ, який потрібно відредагувати.<br>
Система відображає форму редагування з поточними даними документа.<br>
Після внесення користувачем змін система зберігає оновлені дані у базі даних.<br>
5.Видалення документів:<br>
Користувач вибирає документ, які потрібно видалити.<br>
Система підтверджує намір видалення вибраних документів користувачем.<br>
Після підтвердження система видаляє вибрані документи з бази даних.<br>
6.Категоризація документів:<br>
Користувач вибирає документ і встановлює йому категорію.<br>
Система зберігає зміни у базі даних.<br>
7.Архівація документів:<br>
Адміністратор вибирає документ, які потрібно архівувати.<br>
Система переміщує вибрані документи в архів.<br>
Користувач може переглядати архівні дані у відповідному розділі.<br>
8.Повідомлення про терміни дії документів:<br>
Система автоматично перевіряє терміни дії документів.<br>
У разі наближення терміну дії система надсилає повідомлення користувачеві.<br>
9.Завантаження та збереження документів:<br>
Користувач завантажує файл документа у систему.<br>
Система зберігає файл у відповідному форматі та пов'язує його з відповідним записом документа у базі даних.<br>
10.Аудит дій користувачів:<br>
Система фіксує всі дії адміністраторів у журналі дій.<br>
Журнал дій доступний для перегляду адміністраторам системи для відстеження всіх змін в документах.<br>
<br>
<h1>REST API endpoints:</h1><br>
1.Створення нового документа:<br>
Метод: POST<br>
URL: /api/documents/create<br>
Параметри: document_name(Назва документа), document_content(Наповнення документа),document_date(Дата документа)<br>
Відповідь: Підтвердження додавання нового документа.
2.Отримання списку документів:<br>
Метод: GET<br>
URL: /api/documents<br>
Відповідь: Список всіх доступних документів.<br>
3.Пошук документів:<br>
Метод: POST<br>
URL: /api/documents/search<br>
Параметри: document_id(Ід документа), document_name(Назва документа), document_date(Дата документа), document_category(Категорія документа)<br>
Відповідь: Список документів з вказаним параметром.<br>
4.Редагування документа:<br>
Метод: PUT<br>
URL: /api/documents/{document_id}/edit<br>
Параметри:document_id(Ід документа), document_name(Назва документа), document_date(Дата документа), document_id(Категорія документа)<br>
Відповідь: Підтвердження зміни в документі.<br>
5.Видалення документа:<br>
Метод: DELETE<br>
URL: /api/documents/{document_id}/delete<br>
Параметри: document_id(Ід документа)<br>
Відповідь: Підтвердження видалення документа.<br>
6.Категоризація документів:<br>
Метод: PUT<br>
URL: /api/documents/{document_id}/category<br>
Параметри: document_id(Ід документа), document_category(Категорія документа)<br>
Відповідь: Підтвердження надання категорії документу.<br>
7.Архівація документів:<br>
Метод: PUT<br>
URL: /api/documents/{document_id}/archive<br>
Параметри: document_id(Ід документа)<br>
Відповідь: Вивід інформації про вдалу архівацію.<br>
8.Повідомлення про терміни дії документів:<br>
Метод: POST<br>
URL: /api/documents/{document_id}/remind<br>
Відповідь: Назва документа та термін актуальності закінчення документа.<br>
9.Завантаження та збереження документів:<br>
Метод: POST<br>
URL: /api/documents/upload<br>
Параметри: document(Файл з документом у текстовому форматі)<br>
Відповідь: Підтвердження завантаження файлу документа.<br>
10.Аудит дій користувачів:<br>
Метод: GET<br>
URL: /api/audit/logs<br>
Відповідь: Вивід логу дій користувачів.<br>
11.Створення нової версії документа:<br>
Метод: POST<br>
URL: /api/documents/{document_id}/version<br>
Параметри: document_id (ID документа), version_notes (замітки до нової версії)<br>
Відповідь: Підтвердження створення нової версії.<br>
12.Отримання всіх версій документа:<br>
Метод: GET<br>
URL: /api/documents/{document_id}/versions<br>
Параметри: document_id (ID документа)<br>
Відповідь: Список всіх версій конкретного документа з датами змін і замітками.<br>
13.Перегляд конкретної версії документа:<br>
Метод: GET<br>
URL: /api/documents/{document_id}/versions/{version_id}<br>
Параметри: document_id (ID документа), version_id (ID версії)<br>
Відповідь: Дані конкретної версії документа.<br>
14.Порівняння двох версій документа:<br>
Метод: POST<br>
URL: /api/documents/{document_id}/versions/compare<br>
Параметри: document_id (ID документа), version_1_id (ID першої версії), version_2_id (ID другої версії)<br>
Відповідь: Відмінності між двома версіями документа.<br>
15.Відновлення документа до попередньої версії:<br>
Метод: PUT<br>
URL: /api/documents/{document_id}/versions/{version_id}/restore<br>
Параметри: document_id (ID документа), version_id (ID версії для відновлення)<br>
Відповідь: Підтвердження відновлення документа до вказаної версії.<br>
