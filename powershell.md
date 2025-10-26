https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.4

## Networking
### Test network connection 
```
tnc mubengsf.ddc.teliasonera.net -Port 443
```

### Download file 
```
Invoke-WebRequest -Uri "https://download/DataMigrationAssistant.msi" -OutFile ".\DataMigrationAssistant.msi"
```

## Splatting

Splatting is a method of passing a collection of parameter values to a command as a unit. PowerShell associates each value in the collection with a command parameter. Splatted parameter values are stored in named splatting variables, which look like standard variables, but begin with an At symbol `@` instead of a dollar sign `$`. The At symbol tells PowerShell that you are passing a collection of values, instead of a single value.

#### Example 1
```
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```
#### Example 2
```
if ($Force)
{
    $Splat['Confirm'] = $false
}
Do-Stuff @Splat
```
#### Example 3
```
$a = @{
    Message         = 'Hello', 'World!'
}
$b = @{
    Separator       = '|'
}
$c = @{
    BackgroundColor = 'Cyan'
    ForegroundColor = 'Black'
}
Write-Host @a @b @c
```
