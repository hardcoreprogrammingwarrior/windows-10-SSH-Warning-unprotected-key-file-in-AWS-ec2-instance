# Windows 10 SSH Warning unprotected key file in AWS ec2 instance

Open up windows powershell  
```cd``` to your pem folder

```sh
$path = ".\laravel8.pem"
```

## Reset to remove explicit permissions


```sh
icacls.exe $path /reset
```

## Give current user explicit read-permission


```sh
icacls.exe $path /GRANT:R "$($env:USERNAME):(R)"
```

## Disable inheritance and remove inherited permissions


```sh
icacls.exe $path /inheritance:r
```
