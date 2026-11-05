## Descripción
You will find the flag after analysing this apk Download [here](https://challenge-files.cylabacademy.net/library/b31248aec6287cbe220d0dbfa55e216b87e6175b3561d441062bfdd018f3cacc/timer.apk).

Hints

1

Decompile

2

mobsf or jadx
## Solución
```

mkdir -p ~/picoctf-reverse/timer
cd ~/picoctf-reverse/timer
wget -O timer.apk 'https://challenge-files.cylabacademy.net/library/b31248aec6287cbe220d0dbfa55e216b87e6175b3561d441062bfdd018f3cacc/timer.apk'

jadx -d decompilado timer.apk

grep -nF 'academy{' decompilado/sources/com/example/timer/BuildConfig.java

academy{t1m3r_r3v3rs3d_succ355fully_17496}

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/b31248aec6287cbe220d0dbfa55e216b87e6175b3561d441062bfdd018f3cacc/timer.apk