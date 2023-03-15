# Installing the Domain Controller

1. Use `sconfig` to:
	- Change the hostname
	- Change the IP address to static
	- Change the DNS server to own IP address

2. Install the Active Directory Windows Feature
```shell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

# Changing DNS on Workstation

```shell
Get-DnsClientServerAddress
```
```shell
Set-DnsClientServerAddress -InterfaceIndex 4 -ServerAddresses 192.168.28.155
```


# Joining the Workstation to the domain

```shell
Add-Compter -DomainName sherlockteen.ru -Credentials sherlockteen\Administrator -Restart -Force
```