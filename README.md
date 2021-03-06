# Save email data to csv with python
This is my first program that I made in Python.

A program that downloads e-mails from the mailbox, then I select the part of each e-mail that interests me and save it in a selected format to a .csv file

A simple program for the automation and transparent visualization of the status of computer backups.
I used Veeam Backup to make the backup:
https://www.veeam.com/pl
After proper configuration - giving the appropriate name for the copy task, in my case it was the name of the client, setting the sending of e-mails after making a copy with the information:
[SUCCESS], [WARNING], [FAILED]. I configured myself so that the subject of the e-mail is: Client XXX - [FAILED].
I also needed to extract the date of each e-mail.

The first step is to use a ready-made script to download e-mails, there are many of them, I will not paste / show it. Perhaps they are better / easier. However, the one I used downloaded all e-mails with all the data, my program was to extract what I needed from this e-mail:
- customer name
- date of the copy

I wanted to shorten the entry, so I used a condition that put three options 'ok', 'not ok' or 'check' in the 'status' table in case of finding 'success', 'failed' or 'warning' in the e-mail subject.

Then I needed the current date and the difference of dates, because sometimes the copy was not done at all, i.e. the computer was turned off. I needed some simple informer that the copy is not made, for example, for more than 3 days (because, for example, it was not made after the weekend).

The last problem was filtering the content so that one client has only one row in the sheet - I am not interested in whether the client's copy was made a week ago or what status it had at that time, I am interested in its last status or when the last time it was done.

I placed the data arranged in this way in the .csv file, separated by a comma, arranged in the appropriate columns:

Subject; Status; Date; Today's Date; How many days since the last copy

Each new e-mail is written on the next line. For my own, I uploaded a convenient .csv file to the ftp server, where I formatted it with the php language into an html table and used it as a template in Wordpress. Using javascript, I colored the 'status' fields (ok green, not red) and the number over 3 days from the last copy (also red).

I now have an up-to-date inspection of copies with my customers on hand. 


---
Polish version:

To m??j pierwszy program, kt??ry zrobi??em w Pythonie.

Program, kt??ry pobiera maile ze skrzynki, potem wybieram interesuj??c?? mnie cze???? ka??dego maila i zapisuj?? w wybranej formi do pliku .csv

Prosty program do automatyzacji i przejrzystej wizualizacji status??w wykonywanych kopii zapasowych komputer??w.
Do wykonywania kopii u??ywa??em programu Veeam Backup:
https://www.veeam.com/pl
Po odpowiednim skonfigurowaniu - nadaniu odpowiedniej nazwy dla zadania kopii, w moim przypadku by??a to nazwa klienta, ustawieniu wysy??ki maili po wykonaniu kopii z informacj??:
[SUCCESS], [WARNING], [FAILED]. Skonfigurowa??em sobie tak, ??e temat maila to: Klient XXX - [FAILED]. 
Potrzebowa??em tak??e z ka??dego maila wyj???? jego dat??. 

Pierwszy krok to u??ycie gotowego skryptu do pobierania maili, jest ich wiele, nie b??d??go wkleja??/pokazywa??. By?? mo??e s?? lepsze/??atwiejsze. Natomiast ten, kt??ry u??y??em pobiera?? mi wszystkie maile z wszystkimi danymi, m??j program mia?? za zadanie wyj???? z tego maila to co potrzebowa??em:
- nazw?? klienta
- dat?? kopii

Chcia??em skr??ci?? zapis, wi??c zastosowa??em warunek wpisuj??cy do tabeli 'status' trzy mo??liwo??ci 'ok', 'nie ok' lub 'sprawd??' w przypadku znalezienia w temacie maila odpowiednio 'success' , 'failed' lub 'warning'.

Nast??pnie potrzebowa??em aktualnej daty oraz r????nicy dat, bo czasami kopia si?? np. w og??le nie wykona??a tj. komputer by?? wy????czony. Potrzebowa??em jakiego?? prostego informatora, ??e kopia nie wykonuje si?? np. powy??ej 3 dni (bo np. nie zrobi??a si?? po weekendzie). 

Ostatnim problemem by??o odfiltrowanie zawarto??ci tak, by jeden klient mia?? tylko jeden wiersz w arkuszu - nie interesuje mnie czy kopia u danego kllienta wykona??a si?? tydzie?? temu albo jaki mia??a wtedy status, interesuje mnie jej ostatni status albo kiedy ostatni raz si?? wykona??a. 

Tak u??o??one dane umieszcza??em w pliku .csv oddzielone przecinkiem, uporz??dkowane w odpowiednich kolumnach:

Temat;Status;Data;Dzisiejsza data;Ile dni od ostatniej kopii

Ka??dy nowy mail zapisuje si?? w kolejnym wierszu. Dla w??a??nej wygodny plik .csv wrzuca??em jeszcze na serwer ftp, gdzie formatowa??em go za pomoc?? j??zyka php do tabeli w html i u??y??em jako szablon podstorny w Wordpressie. Za pomoc?? javascript pokolorowa??em sobie pola 'status' (ok zielone, nieok czerwone) oraz liczb?? powy??ej 3 dni od ostantniej kopii (te?? czerwono). 

Mam teraz pod r??k?? zawsze dost??pny aktualny przegl??d kopii u klient??w.
