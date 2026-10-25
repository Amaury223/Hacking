## Descripción
It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher? Download the message [here](https://challenge-files.cylabacademy.net/library/696c6874056837b137b48e23a74d72e27d26def4454fdb690063e6baefa68124/message.txt).

Hints

1

Try refining your frequency attack, maybe analyzing groups of letters would improve your results?
## Solución
```
Dark23-academy@webshell:~$ wget -O message.txt "https://challenge-files.cylabacademy.net/library/696c6874056837b137b48e23a74d72e27d26def4454fdb690063e6baefa68124/message.txt"

Dark23-academy@webshell:~$ cat message.txt
maucuusndmduyucwvkmaucpuvvudmwfvndauianxadbakkvbkhgzmucdubzcnmqbkhgumnmnkednebvzinexbqfucgwmcnkmweizdbqfucbawvvuexumaudubkhgumnmnkedokbzdgcnhwcnvqkedqdmuhdwihnendmcwmnkeozeiwhuemwvdpanbawcuyucqzduozvweihwclumwfvudlnvvdakpuyucpufuvnuyumaugckgucgzcgkdukowanxadbakkvbkhgzmucdubzcnmqbkhgumnmnkendekmkevqmkmuwbaywvzwfvudlnvvdfzmwvdkmkxumdmziuemdnemucudmuineweiusbnmuiwfkzmbkhgzmucdbnuebuiuouednyubkhgumnmnkedwcukomuevwfkcnkzdwoowncdweibkhuikpemkczeenexbaublvndmdweiusubzmnexbkeonxdbcngmdkoouedukemaukmaucaweindauwynvqokbzduikeusgvkcwmnkeweinhgckyndwmnkeweikomueawduvuhuemdkogvwqpufuvnuyuwbkhgumnmnkemkzbanexkemaukoouednyuuvuhuemdkobkhgzmucdubzcnmqndmaucuokcuwfummucyuanbvuokcmubauywexuvndhmkdmziuemdnewhucnbweanxadbakkvdozcmaucpufuvnuyumawmwezeiucdmweinexkokoouednyumubaenrzudndudduemnwvokchkzemnexweuooubmnyuiuoueduweimawmmaumkkvdweibkeonxzcwmnkeokbzduebkzemucuineiuouednyubkhgumnmnkedikudekmvuwidmziuemdmklekpmauncueuhqwduooubmnyuvqwdmuwbanexmauhmkwbmnyuvqmanelvnluwewmmwblucwbwiuhqndwekoouednyuvqkcnuemuianxadbakkvbkhgzmucdubzcnmqbkhgumnmnkemawmduuldmkxueucwmunemucudmnebkhgzmucdbnuebuwhkexanxadbakkvucdmuwbanexmauhuekzxawfkzmbkhgzmucdubzcnmqmkgnrzumauncbzcnkdnmqhkmnywmnexmauhmkusgvkcukemaunckpeweiuewfvnexmauhmkfummuciuoueimaunchwbaneudmauovwxndwbwiuhq{E6C4H_4E41Q515_15_73I10Z5_9O106F2U}


Dark23-academy@webshell:~$ cat > solve_sub2.py << 'EOF'
> import re
> from collections import Counter
> 
> text = open("message.txt").read()
> 
> # La palabra "academy" siempre aparece antes del {
> # Buscar el patrón: xxxxxxx{...}
> match = re.search(r'([a-z]{7})\{', text)
> if match:
>     cipher_word = match.group(1)
>     plain_word  = "academy"
>     mapping = {c: p for c, p in zip(cipher_word, plain_word)}
>     print("Mapa inicial desde 'academy':", mapping)
> 
> # Buscar "bkhgzmucd" o equivalente (computers / security) para ampliar el mapa
> # Frecuencias de letras para refinar
> freq = Counter(c for c in text.lower() if c.isalpha())
> print("\nTop frecuencias:", freq.most_common(10))
> 
> def decrypt(txt, m):
>     result = []
>     for ch in txt:
>         if ch.lower() in m:
>             d = m[ch.lower()]
>             result.append(d.upper() if ch.isupper() else d)
>         else:
>             result.append(ch)
>     return "".join(result)
> 
> # Mapa construido por análisis de los retos anteriores
> # (letras del inglés más comunes mapeadas por frecuencia)
> # Si el mapa inicial no basta, imprimimos el texto parcialmente descifrado
> print("\n--- Texto parcialmente descifrado ---")
> print(decrypt(text, mapping))
> EOF


Dark23-academy@webshell:~$ python3 solve_sub2.py
Mapa inicial desde 'academy': {'w': 'a', 'b': 'c', 'i': 'd', 'u': 'e', 'h': 'm', 'q': 'y'}

Top frecuencias: [('u', 177), ('m', 123), ('n', 101), ('k', 100), ('e', 98), ('d', 83), ('w', 72), ('c', 61), ('b', 61), ('a', 56)]

--- Texto parcialmente descifrado ---
maeceesndmdeyecavkmaecpevvedmafvndaedanxadcakkvckmgzmecdeczcnmyckmgemnmnkednecvzdnexcyfecgamcnkmaedzdcyfeccaavveexemaedeckmgemnmnkedokczdgcnmacnvykedydmemdadmnendmcamnkeozedameemavdpancaaceyecyzdeozvaedmaclemafvedlnvvdakpeyecpefevneyemaegckgecgzcgkdekoaanxadcakkvckmgzmecdeczcnmyckmgemnmnkendekmkevymkmeacayavzafvedlnvvdfzmavdkmkxemdmzdeemdnemecedmedneaedescnmedafkzmckmgzmecdcneecedeoeednyeckmgemnmnkedacekomeevafkcnkzdaooancdaedckmedkpemkczeenexcaeclvndmdaedeseczmnexckeonxdccngmdkooeedekemaekmaecaaedndaeaynvyokczdedkeesgvkcamnkeaednmgckyndamnkeaedkomeeaadevemeemdkogvaypefevneyeackmgemnmnkemkzcanexkemaekooeednyeevemeemdkockmgzmecdeczcnmyndmaeceokceafemmecyeancveokcmecaeyaexevndmmkdmzdeemdneamecncaeanxadcakkvdozcmaecpefevneyemaamaezedecdmaednexkokooeednyemecaenrzedndeddeemnavokcmkzemnexaeeooecmnyedeoeedeaedmaammaemkkvdaedckeonxzcamnkeokczdeeckzemecednedeoeednyeckmgemnmnkeddkedekmveaddmzdeemdmklekpmaenceeemyadeooecmnyevyadmeacanexmaemmkacmnyevymanelvnleaeammaclecacademyndaekooeednyevykcneemedanxadcakkvckmgzmecdeczcnmyckmgemnmnkemaamdeeldmkxeeecamenemecedmneckmgzmecdcneeceamkexanxadcakkvecdmeacanexmaemeekzxaafkzmckmgzmecdeczcnmymkgnrzemaencczcnkdnmymkmnyamnexmaemmkesgvkcekemaenckpeaedeeafvnexmaemmkfemmecdeoeedmaencmacaneedmaeovaxndacademy{E6C4M_4E41Y515_15_73D10Z5_9O106F2E}

Dark23-academy@webshell:~$ cat > verify.py << 'EOF'
> mapping = {
>     'a':'h','b':'c','c':'r','d':'s','e':'n','f':'b','g':'p',
>     'h':'m','i':'d','k':'o','m':'t','n':'i','o':'f','q':'y',
>     'u':'e','v':'l','w':'a','x':'g','z':'u'
> }
> text = open("message.txt").read()
> result = []
> for ch in text:
>     low = ch.lower()
>     if low in mapping:
>         decoded = mapping[low]
>         result.append(decoded.upper() if ch.isupper() else decoded)
>     else:
>         result.append(ch)
> print("".join(result))
> EOF


Dark23-academy@webshell:~$ python3 verify.py | tail -1
thereesistseyeralotherpellestablishedhighschoolcomputersecuritycompetitionsincludingcyberpatriotanduscyberchallengethesecompetitionsfocusprimarilyonsystemsadministrationfundamentalsphichareyeryusefulandmarletableslillshopeyerpebelieyetheproperpurposeofahighschoolcomputersecuritycompetitionisnotonlytoteachyaluableslillsbutalsotogetstudentsinterestedinandescitedaboutcomputersciencedefensiyecompetitionsareoftenlaboriousaffairsandcomedopntorunningchecllistsandesecutingconfigscriptsoffenseontheotherhandisheayilyfocusedonesplorationandimproyisationandoftenhaselementsofplaypebelieyeacompetitiontouchingontheoffensiyeelementsofcomputersecurityisthereforeabetteryehiclefortecheyangelismtostudentsinamericanhighschoolsfurtherpebelieyethatanunderstandingofoffensiyetechniruesisessentialformountinganeffectiyedefenseandthatthetoolsandconfigurationfocusencounteredindefensiyecompetitionsdoesnotleadstudentstolnoptheirenemyaseffectiyelyasteachingthemtoactiyelythinllileanattacleracademyisanoffensiyelyorientedhighschoolcomputersecuritycompetitionthatseelstogenerateinterestincomputerscienceamonghighschoolersteachingthemenoughaboutcomputersecuritytopiruetheircuriositymotiyatingthemtoesploreontheiropnandenablingthemtobetterdefendtheirmachinestheflagis
academy{N6R4M_4N41Y515_15_73D10U5_9F106B2E}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/696c6874056837b137b48e23a74d72e27d26def4454fdb690063e6baefa68124/message.txt