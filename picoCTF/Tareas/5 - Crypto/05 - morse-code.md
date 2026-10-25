## Descripción
Morse code is well known. Can you decrypt this? Download the file [here](https://challenge-files.cylabacademy.net/library/3728bfa4e8314fddd6b7e9f3fae9cb453b459a0bd4b3a29a9224701152f0cd89/morse_chal.wav).

Wrap your answer with academy{}, put underscores in place of pauses, and use all uppercase.

Hints

1

Audacity is a really good program to analyze morse code audio.

## Solución
```
Dark23-academy@webshell:~$ wget -O morse_chal.wav "https://challenge-files.cylabacademy.net/library/3728bfa4e8314fddd6b7e9f3fae9cb453b459a0bd4b3a29a9224701152f0cd89/morse_chal.wav"

Dark23-academy@webshell:~$ pip install numpy scipy

Dark23-academy@webshell:~$ cat > decode_morse.py << 'EOF'
> import numpy as np
> from scipy.io import wavfile
> 
> MORSE = {
>     '.-':'A','-...':'B','-.-.':'C','-..':'D','.':'E','..-.':'F','--.':'G',
>     '....':'H','..':'I','.---':'J','-.-':'K','.-..':'L','--':'M','-.':'N',
>     '---':'O','.--.':'P','--.-':'Q','.-.':'R','...':'S','-':'T','..-':'U',
>     '...-':'V','.--':'W','-..-':'X','-.--':'Y','--..':'Z',
>     '-----':'0','.----':'1','..---':'2','...--':'3','....-':'4',
>     '.....':'5','-....':'6','--...':'7','---..':'8','----.':'9'
> }
> 
> rate, data = wavfile.read("morse_chal.wav")
> if data.ndim > 1:
>     data = data[:, 0]
> data = data.astype(np.float64)
> 
> # Envolvente de amplitud
> amp = np.abs(data)
> threshold = amp.max() * 0.3
> on = amp > threshold
> 
> # Detectar segmentos (encendido/apagado) con sus duraciones
> segments = []
> cur = on[0]
> count = 1
> for v in on[1:]:
>     if v == cur:
>         count += 1
>     else:
>         segments.append((cur, count))
>         cur = v
>         count = 1
> segments.append((cur, count))
> 
> durations_on = [c for state, c in segments if state]
> if not durations_on:
>     print("No se detectaron tonos, ajusta el threshold.")
>     exit()
> 
> unit = min(durations_on)  # duración de un "punto"
> 
> morse = ""
> for state, count in segments:
>     units = round(count / unit)
>     if state:
>         morse += "." if units <= 1 else "-"
>     else:
>         if units >= 7:
>             morse += "   "   # espacio entre palabras
>         elif units >= 3:
>             morse += " "     # espacio entre letras
>         # si es más corto, es solo la separación normal entre símbolos (no se añade nada)
> 
> words = morse.strip().split("   ")
> decoded_words = []
> for w in words:
>     letters = w.strip().split(" ")
>     decoded_words.append("".join(MORSE.get(l, "") for l in letters if l))
> 
> result = "_".join(decoded_words)
> print("Morse:", morse)
> print("Flag: academy{" + result.upper() + "}")
> EOF
Dark23-academy@webshell:~$ python3 decode_morse.py
Traceback (most recent call last):
  File "/home/Dark23-academy/decode_morse.py", line 13, in <module>
    rate, data = wavfile.read("morse_chal.wav")
  File "/usr/local/lib/python3.10/dist-packages/scipy/io/wavfile.py", line 705, in read
    fmt_chunk = _read_fmt_chunk(fid, is_big_endian)
  File "/usr/local/lib/python3.10/dist-packages/scipy/io/wavfile.py", line 389, in _read_fmt_chunk
    raise ValueError("WAV header is invalid: nAvgBytesPerSec must"
ValueError: WAV header is invalid: nAvgBytesPerSec must equal product of nSamplesPerSec and nBlockAlign, but file has nSamplesPerSec = 44100, nBlockAlign = 2, and nAvgBytesPerSec = 176400





Dark23-academy@webshell:~$ nano decode_morse.py

import numpy as np
from scipy.io import wavfile

MORSE = {
    '.-':'A','-...':'B','-.-.':'C','-..':'D','.':'E','..-.':'F','--.':'G',
    '....':'H','..':'I','.---':'J','-.-':'K','.-..':'L','--':'M','-.':'N',
    '---':'O','.--.':'P','--.-':'Q','.-.':'R','...':'S','-':'T','..-':'U',
    '...-':'V','.--':'W','-..-':'X','-.--':'Y','--..':'Z',
    '-----':'0','.----':'1','..---':'2','...--':'3','....-':'4',
    '.....':'5','-....':'6','--...':'7','---..':'8','----.':'9'
}

rate, data = wavfile.read("morse_fixed.wav")

if data.ndim > 1:
    data = data[:, 0]
data = data.astype(np.float64)

# Envolvente de amplitud

# Envolvente RMS por ventanas de 10 ms
frame_size = int(rate * 0.01)

usable = len(data) // frame_size * frame_size
frames = data[:usable].reshape(-1, frame_size)

rms = np.sqrt(np.mean(frames ** 2, axis=1))

# Umbral para distinguir tonos y silencios
threshold = rms.max() * 0.20
on = rms > threshold

# Suavizar peque  as interrupciones de la se  al
for i in range(1, len(on) - 1):
    if on[i - 1] == on[i + 1]:
        on[i] = on[i - 1]
        
# Detectar segmentos en unidades de ventanas
segments = []
cur = bool(on[0])
count = 1

for v in on[1:]:
    v = bool(v)
    if v == cur:
        count += 1
    else:
        segments.append((cur, count))
        cur = v
        count = 1

segments.append((cur, count))

durations_on = [c for state, c in segments if state]
if not durations_on:
    print("No se detectaron tonos, ajusta el threshold.")
    exit()

unit = min(durations_on)  # duraci  n de un "punto"

morse = ""
for state, count in segments:
    units = round(count / unit)
    if state:
        morse += "." if units <= 1 else "-"
    else:
        if units >= 7:
            morse += "   "   # espacio entre palabras
        elif units >= 3:
            morse += " "     # espacio entre letras
        # si es m  s corto, es solo la separaci  n normal entre s  mbolos (no se a  ade nada)

words = morse.strip().split("   ")
decoded_words = []
for w in words:
    letters = w.strip().split(" ")
    decoded_words.append("".join(MORSE.get(l, "") for l in letters if l))

result = "_".join(decoded_words)
print("Morse:", morse)
print("Flag: academy{" + result.upper() + "}")

Morse: .-- .... ....- --...   .... ....- --... ....   ----. ----- -..   .-- ..--- ----- ..- ----. .... --...
Flag: academy{WH47_H47H_90D_W20U9H7}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/3728bfa4e8314fddd6b7e9f3fae9cb453b459a0bd4b3a29a9224701152f0cd89/morse_chal.wav