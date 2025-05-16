## Installing Ubuntu 24.04 LTS via WSL on Windows 11 with PowerShell

``` PowerShell
# Enable WSL feature (requires admin rights)
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux -NoRestart

# Enable Virtual Machine Platform (required for WSL 2)
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -NoRestart

# Install WSL
wsl --install

# Download Ubuntu 24.04 LTS package
Invoke-WebRequest -Uri https://aka.ms/wslubuntu2404 -OutFile ~/Ubuntu_2404.appx -UseBasicParsing

# Install Ubuntu 24.04 LTS
Add-AppxPackage -Path ~/Ubuntu_2404.appx

# Remove the downloaded package
Remove-Item -Path ~/Ubuntu_2404.appx

# Launch Ubuntu 24.04 to complete setup
wsl ~ -d Ubuntu-24.04
```
