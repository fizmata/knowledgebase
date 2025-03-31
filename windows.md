## Setting Windows user inputs
https://learn.microsoft.com/en-us/powershell/module/international/set-winuserlanguagelist?view=windowsserver2022-ps 

```
$NLL= New-WinUserLanguageList -Language "en-US"
$NLL.Add("ka-GE") 
$NLL 
```
Make sure the list has correct languages.
If everything is correct set the input methods by:

```
Set-WinUserLanguageList -LanguageList $NLL
```
## Keyboard shortcuts
* `Win` + `Shift` + `s` - screenshot
* `Win` + `l` - lock screen
* `Win` + `k` - connections/bluetooth devices - no longer works in Win 11 😔
* `Win` + `x` - fast access to system things

## Edge tabs as windows problem
https://www.majorgeeks.com/content/page/alt_tab_edge.html

## Convertinf linux ssh key to Putty for windows and vice versa

To convert a private Mac/Linux (OpenSSH-style) key to a Windows (PPK-style) key:
1. Download PuTTYgen
1. Launch PuTTYgen. Visit Conversions > Import Key.
1. Browse to and open the OpenSSH-style key (id_rsa)
1. Click the Save private key button.
1. When prompted "Are you sure you want to save this key without a passphrase to protect it?" choose Yes.
1. Save the file. Recommended filename: id_rsa.ppk


To convert a private Windows (PPK-style) key to a Mac/Linux (OpenSSH-style) key:
1. Download PuTTYgen
2. Launch PuTTYgen. Visit File > Load private key.
2. Browse to and open the PPK-style private key (id_rsa.ppk)
2. Visit Conversion > Export OpenSSH key
2. When prompted "Are you sure you want to save this key without a passphrase to protect it?" choose Yes.
2. Save the file. Recommended filename: id_rsa
