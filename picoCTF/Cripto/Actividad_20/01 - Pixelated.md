## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://challenge-files.cylabacademy.net/library/5d582e313e019eefa2385b079dac13cc187060301fb28ae53d6cdeb2d5ac2af2/scrambled1.png) [scrambled2.png](https://challenge-files.cylabacademy.net/library/5d582e313e019eefa2385b079dac13cc187060301fb28ae53d6cdeb2d5ac2af2/scrambled2.png)

Hints

1

[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)

2

Think of different ways you can "stack" images
## Solución
```
Dark23-academy@webshell:~$ wget -O scrambled1.png "https://challenge-files.cylabacademy.net/library/5d582e313e019eefa2385b079dac13cc187060301fb28ae53d6cdeb2d5ac2af2/scrambled1.png"

Dark23-academy@webshell:~$ wget -O scrambled2.png "https://challenge-files.cylabacademy.net/library/5d582e313e019eefa2385b079dac13cc187060301fb28ae53d6cdeb2d5ac2af2/scrambled2.png"


Dark23-academy@webshell:~$ cat > combine.py << 'EOF'
> from PIL import Image, ImageChops
> 
> img1 = Image.open("scrambled1.png").convert("RGB")
> img2 = Image.open("scrambled2.png").convert("RGB")
> 
> # XOR en RGB (byte a byte)
> xor = ImageChops.difference(img1, img2)
> xor.save("flag_xor.png")
> 
> # OR (lighter = max de cada canal)
> or_img = ImageChops.lighter(img1, img2)
> or_img.save("flag_or.png")
> 
> # AND (darker = min de cada canal)
> and_img = ImageChops.darker(img1, img2)
> and_img.save("flag_and.png")
> 
> print("Guardados: flag_xor.png, flag_or.png, flag_and.png")
> 
> # ASCII preview de las 3
> for fname in ["flag_xor.png", "flag_or.png", "flag_and.png"]:
>     img = Image.open(fname).convert("L")
>     small = img.resize((80, 24))
>     print(f"\n--- {fname} ---")
>     for y in range(small.height):
>         row = ""
>         for x in range(small.width):
>             p = small.getpixel((x, y))
>             row += "#" if p < 128 else " "
>         print(row)
> EOF


Dark23-academy@webshell:~$ python3 combine.py
Guardados: flag_xor.png, flag_or.png, flag_and.png

--- flag_xor.png ---
 ######   # #####  #           ##  # #    ## ## ###   #  # ## #   #   ##  # ### 
 ### ##  # #  ####   ###   ## #####    #    ### #######    ####  ##   ##    ### 
  #   #   ##   #     ### #      ### ## # ######  #     #  ## #### ### ##  # # ##
#   # #   # ##           ##    #     #   #    ##    #   #####   ### # #  ##     
#  #### ##   ## #    #  # #### # #      ##  ##  # # # ##  #  # # ##  # #  #    #
 #    ##### ### ###### ###  ######  ### ####### ##### ########### #######   ##  
# ## ## ####### ####################### ### ### ######### #### ###### ##  ## # #
####  ##   # ######  ###        ######  #####    #   #  #  ## ## ##   # # ##### 
  ## ###        #####  #   ##    ### ## ##   # ###  ##  #####  ####   ###    ## 
 #   #  ##   ## #   ## ###   #########  #### #####      ##   #      ### ###  # #
    ## #   ###  #  #     # ##### ####    #  #    #    #####  ###   # ### #   #  
## ###  ##     ##     #  ##### # #     #   #### # #     ###  ##   ###  # # #####
#####     #   ###### #        # ##  ####  # ##  #### # ####  ## ##  ##   ###### 
      #   #  #  #  # #    #   #   # ### # # ## ####   #### #  # ####    #   ### 
  # # #   #     ###      # ###  #   ##     #   ## # #  ##  #    ## ###   #  # # 
##   # #  # ###    # #  ##        ## ###  # #   #   ##   #### # #  #    ##  # # 
     # ##    #    #     ####   ##  # #  ###   ####   # ##   ##    ###        ## 
# # ### ##    ### #   ######  # #    #  ## ##   ##  ##   #######     ##  ## ### 
# # #### #  # ###  ##  ###   #   #   #  ## ## ##### #     ## ####  ##  ##    # #
 # #    #     #  # #        ## #   #      ##   # ###      # # #     ### ## #### 
   ##  # #### #  # #     #  ##### ## ###    ## #### ###  ##### #  ##  # ## #    
  ##   # #  ### ##### ##     #   #   ##### ###       ### ##    # # ## # #       
#    ####   ####  ####  #    ##  #  # # ###       ## #  # # ## ###  # ###  # #  
 ##   ### # #  ##  ##  ###  ## ## # #   ####    ###     ### #  ## #######    #  

--- flag_or.png ---
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                
                                                                                

--- flag_and.png ---
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################
################################################################################

Dark23-academy@webshell:~$ python3 << 'EOF'
> from PIL import Image
> import numpy as np
> 
> img1 = np.array(Image.open("scrambled1.png").convert("L"))
> img2 = np.array(Image.open("scrambled2.png").convert("L"))
> 
> # Visual crypto: OR (apilar = OR de los pixels)
> stacked = np.bitwise_or(img1, img2)
> 
> # Mostrar con umbral adaptativo
> result = Image.fromarray(stacked.astype("uint8"))
> small = result.resize((128, 48))
> 
> for y in range(small.height):
>     row = ""
>     for x in range(small.width):
>         p = small.getpixel((x, y))
>         row += "#" if p > 127 else " "
>     print(row)
> EOF
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################
################################################################################################################################

Dark23-academy@webshell:~$ python3 -c "
> import base64
> with open('flag_final.png','rb') as f:
>     data = base64.b64encode(f.read()).decode()
> print('data:image/png;base64,' + data)
> "
data:image/png;base64,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


academy{2f16d0c4}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/5d582e313e019eefa2385b079dac13cc187060301fb28ae53d6cdeb2d5ac2af2/scrambled1.png

https://challenge-files.cylabacademy.net/library/5d582e313e019eefa2385b079dac13cc187060301fb28ae53d6cdeb2d5ac2af2/scrambled2.png