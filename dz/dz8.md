## Домашнее задание №8 (факультативное PRO). Код на Python для оффлайн поиска в английско-амхарском параллельном корпусе.

*Для выполнения этого задания требуются навыки, выходящие за рамки программы данного курса. Если Вы сдадите работу, оценка за нее будет иметь вес двух обычных ДЗ. Если Вы не сдадите эту работу, на итоговую оценку это никак не повлияет*.  
  
  ### Задача
Дан [корпус параллельных предложений на амхарском и английском](https://www.findke.ovgu.de/findke/en/Research/Data+Sets/Amharic_English+Parallel+Corpus-p-1144.html). Необходимо написать такой код, который принимал бы на вход введенную пользователем строку на английском языке (слово или цепочку слов в конкретной форме) и выдавал бы (либо сохранял в отдельный файл) все предложения в корпусе, где встретилась эта строка, вместе с их амхарским переводом.

### Структура данных

Корпус был создан для машинного обучения и состоит из 6 текстовых файлов (их можно вручную открыть в текстовом редакторе типа Brackets и сохранить с указанием расширения .txt). Два из них — test_ и test_ не выровнены по предложениям и непригодны для нашей задачи. Две другие пары — train.am-en.base и dev.am-en.base можно объединить и использовать (добавить содержимое файла dev.am-en.base.amh в конец файла train.am-en.base.amh, а содержимое файла dev.am-en.base.en – в конец файла train.am-en.base.en.  

У Вас должно получиться два текстовых файла. В одном их них хранятся предложения на английском, а во втором — те же предложения на амхарском. Порядок у них одинаковый, то есть, у перевода каждого из английских предложений будет тот же номер строки в амхарском файле.  

### Требования к результату

При запуске кода в диалоговом окне должно появляться сообщение, предлагающее ввести запрос. После ввода строки программа должна отобразить число найденных в корпусе вхождений и либо показать на экране, либо выгрузить в специальный файл примеры этих вхождений.

**Примеры работы программы**

``` Введите запрос
university
Число вхождений:  5 

ቡርኪና ፋሶ ውስጥ አንድን የዩኒቨርሲቲ ተማሪ ቤቱ በር ላይ የመጽሃፍ ቅዱስ ጥናት አስጀምሬው ነበር፤ ከዚያም ለአንድ ወንድም ሰጠሁት።
i had started a doorstep bible study with a university student in burkina faso and had turned it over to a brother. 

ኤስሊ ሁለተኛ ደረጃ ትምህርቷን እንደጨረሰች ነጻ የዩኒቨርሲቲ ትምህርት እድል አገኘች።
upon completing high school, essly was offered a university scholarship. 

የመጀመሪያው የአውሮፓ ዩኒቨርሲቲ እንደሆነ የሚነገርለት ይህ ትምህርት ቤት የሂሳብና የፍልስፍና ምርምር ማእከል በመሆን አገልግሏል።
often referred to as europe's first university, the academy became a focal point for mathematical and philosophical research. 

ዩኒቨርሲቲ ከገባሁ በኋላም ቢሆን ለሂሳብ ያለኝ አድናቆት አልቀነሰም፤ በተለይ ሂሳብና ፕሮባቢሊቲ መማር ያስደስተኝ ነበር።
this fascination continued when i went to university, where i especially enjoyed courses in mathematics and probability. 

"በዩኒቨርሲቲ ሊገኙ የማይችሉ በረከቶች" የሚለውን ተመልከት።
see the box "gaining benefits unattainable at the university." 

>>> ```

``` Введите запрос
moscow
Число вхождений:  1 

ዛሬ የሞስኮ ፍ/ቤት በአሜሪካዊው ነጋዴ በኤድመንድ ፓፕ ላይ የ 20 አመት እስራት ፈረደበት ወደ ወህኒ ቤት ወርዷል።
a court in moscow today sentenced american businessman edmund pope to 20 years in jail. 

>>> 
```
Введите запрос
exchange
Число вхождений:  3 

በኤርትራ በኩል ሁለቱም ብሮች እኩል ዋጋ እንዲኖራቸው ሃሳብ የቀረበ ቢሆንም ኢትዮጵያ ግን ታላላቅ ንግዶችን በተመለከተ በዶላር ብቻ መገበያየት እንዳለባቸው ሃሳብ ቀርቧል።
although eritrea proposed for both currencies to have equal exchange value, ethiopia proposed that they should conduct commercial transactions with (american) dollar when they deal with big business. 

እንደ ዩ.ኤስ ባለስልጣናት ገለጻ ከሆነ በምትኩ የደሃንነት ዋስትናና ኢኮኖሚያዊ እርዳታ ከተሰጣት ሰሜን ኮሪያ የኒውክሊየርና የሚሳይል ፕሮግራሟን ለመተው ፈቃደኛ ናት።
north korea offered to drop its nuclear and missile programs in exchange for security guarantees and economic aid, according to u.s. officials. 

ኢትዮጵያንና ሴባን በአንተ ምትክ ሰጥቻለሁ።
ethiopia and seba in exchange for you. 
```

>Вам могут понадобиться: 
>
>Массивы
>Словари
>Модуль re для работы с регулярными выражениями
