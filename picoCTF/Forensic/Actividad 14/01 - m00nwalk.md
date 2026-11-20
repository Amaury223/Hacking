## Descripción
Decode this [message](https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav) from the moon.

Hints

1

How did pictures from the moon landing get sent back to Earth?

2

What is the CMU mascot?, that might help select a RX option
## Solución
```
┌──(kali㉿kali)-[~]
└─$ sudo apt update && sudo apt install -y qsstv pavucontrol
Hit:1 http://http.kali.org/kali kali-rolling InRelease
1150 packages can be upgraded. Run 'apt list --upgradable' to see them.
qsstv is already the newest version (9.5.8-6).
pavucontrol is already the newest version (6.1-1).
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 1150
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ pactl load-module module-null-sink sink_name=virtual-cable
536870916
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ paplay -d virtual-cable message.wav


picoCTF{beep_boop_im_in_space}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav