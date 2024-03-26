## Objetivo
How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/128/unknown.zip).

## Pistas
How can you view the information about the picture?

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir CanYouSee

kali@kali:~/Documents/picoCTF/picoCTF2024$ cd CanYouSee/

kali@kali:~/Documents/picoCTF/picoCTF2024/CanYouSee$ wget https://artifacts.picoctf.net/c_titan/128/unknown.zip
--2024-03-19 20:48:52--  https://artifacts.picoctf.net/c_titan/128/unknown.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:24db:3000:16:5ec5:2840:93a1, 2600:9000:24db:9000:16:5ec5:2840:93a1, 2600:9000:24db:3200:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:24db:3000:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2252108 (2.1M) [application/octet-stream]
Saving to: ‘unknown.zip’

unknown.zip                                                100%[=======================================================================================================================================>]   2.15M   899KB/s    in 2.4s    

2024-03-19 20:49:00 (899 KB/s) - ‘unknown.zip’ saved [2252108/2252108]


kali@kali:~/Documents/picoCTF/picoCTF2024/CanYouSee$ unzip unknown.zip
Archive:  unknown.zip
  inflating: ukn_reality.jpg         

kali@kali:~/Documents/picoCTF/picoCTF2024/CanYouSee$ file ukn_reality.jpg
ukn_reality.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 4308x2875, components 3

kali@kali:~/Documents/picoCTF/picoCTF2024/CanYouSee$ exiftool ukn_reality.jpg
ExifTool Version Number         : 12.67
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:03:11 20:05:51-04:00
File Access Date/Time           : 2024:03:19 20:56:06-04:00
File Inode Change Date/Time     : 2024:03:19 20:56:00-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4

kali@kali:~/Documents/picoCTF/picoCTF2024/CanYouSee$ echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg==" | base64 -d
picoCTF{ME74D47A_HIDD3N_3b9209a2}

```
2. La bandera es :
picoCTF{ME74D47A_HIDD3N_3b9209a2}
## Notas adicionales

## Referencias
