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
* `Win` + `k` - connections/bluetooth devices
* `Win` + `x` - fast access to system things
