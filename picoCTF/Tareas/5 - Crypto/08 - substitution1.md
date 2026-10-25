## Descripción
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again. Download the message [here](https://challenge-files.cylabacademy.net/library/ceba1af4dd4ee542c226922acd536495ebe14c328fb6766ae3244de7d7deaa2e/message.txt).
## Solución
```
Dark23-academy@webshell:~$ wget -O message.txt "https://challenge-files.cylabacademy.net/library/ceba1af4dd4ee542c226922acd536495ebe14c328fb6766ae3244de7d7deaa2e/message.txt"

Dark23-academy@webshell:~$ cat message.txt
NDQy (yzkjd qkj nbwdaje dze qsbc) bje b dfwe kq nklwadej yenajmdf nklwedmdmki. Nkideydbidy bje wjeyeidev hmdz b yed kq nzbsseicey hzmnz deyd dzemj njebdmxmdf, denzimnbs (biv ckkcsmic) yumssy, biv wjkosel-yksxmic bomsmdf. Nzbsseicey ayabssf nkxej b ialoej kq nbdeckjmey, biv hzei yksxev, ebnz fmesvy b ydjmic (nbssev b qsbc) hzmnz my yaolmddev dk bi kismie ynkjmic yejxmne. NDQy bje b cjebd hbf dk sebji b hmve bjjbf kq nklwadej yenajmdf yumssy mi b ybqe, secbs eixmjkileid, biv bje zkydev biv wsbfev of lbif yenajmdf cjkawy bjkaiv dze hkjsv qkj qai biv wjbndmne. Qkj dzmy wjkosel, dze qsbc my: bnbvelf{QJ3GA3INF_4774NU5_4J3_N001_26B742EO}

Dark23-academy@webshell:~$ cat > solve_sub1.py << 'EOF'
> mapping = {
>     'a':'U','b':'A','c':'G','d':'T','e':'E','f':'Y','g':'Q','h':'W',
>     'i':'N','j':'R','k':'O','l':'M','m':'I','n':'C','o':'B','q':'F',
>     's':'L','u':'K','v':'D','w':'P','x':'V','y':'S','z':'H'
> }
> 
> text = open("message.txt").read()
> 
> def decrypt(ch):
>     if ch.lower() in mapping:
>         d = mapping[ch.lower()]
>         return d if ch.isupper() else d.lower()
>     return ch
> 
> print("".join(decrypt(c) for c in text))
> EOF

Dark23-academy@webshell:~$ python3 solve_sub1.py

CTFs (short for capture the flag) are a type of computer security competition. Contestants are presented with a set of challenges which test their creativity, technical (and googling) skills, and problem-solving ability. Challenges usually cover a number of categories, and when solved, each yields a string (called a flag) which is submitted to an online scoring service. CTFs are a great way to learn a wide array of computer security skills in a safe, legal environment, and are hosted and played by many security groups around the world for fun and practice. For this problem, the flag is: 

academy{FR3QU3NCY_4774CK5_4R3_C001_26A742EB}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/ceba1af4dd4ee542c226922acd536495ebe14c328fb6766ae3244de7d7deaa2e/message.txt

