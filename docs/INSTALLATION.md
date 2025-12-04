# Installation Guide - AWSSDK.Core.dll

## Prerequisites

- Windows Server 2019/2022 or Windows 10/11
- PowerShell 5.1 or higher
- Zabbix Agent installed
- AWS.Tools.S3 PowerShell module

## Installation Steps

### Method 1: Direct Download (Recommended)
```powershell
# Create directory if not exists
New-Item -Path "C:\zabbix" -ItemType Directory -Force

# Download library
Invoke-WebRequest `
    -Uri "https://github.com/DC-Ops-zabbix/aws-sdk-mirror/releases/download/v4.1/AWSSDK.Core.dll" `
    -OutFile "C:\zabbix\AWSSDK.Core.dll"

# Verify file
Get-FileHash "C:\zabbix\AWSSDK.Core.dll" -Algorithm MD5
```

### Method 2: Clone Repository
```bash
git clone https://github.com/DC-Ops-zabbix/aws-sdk-mirror.git
cd aws-sdk-mirror
copy libs\AWSSDK.Core.dll C:\zabbix\
```

### Method 3: Release Download

1. Go to: https://github.com/DC-Ops-zabbix/aws-sdk-mirror/releases
2. Download `AWSSDK.Core.dll` from latest release
3. Copy to `C:\zabbix\`

## Verification

After installation:
```powershell
# Check file exists
Test-Path "C:\zabbix\AWSSDK.Core.dll"

# Check file size (should be ~8 KB)
(Get-Item "C:\zabbix\AWSSDK.Core.dll").Length

# Verify with monitoring script
.\S3-CEPH-Monitor.ps1 -Mode info
```

Expected output:
```
✓ AWS SDK Runtime gefunden
SDK Extensions: Enabled
```

## Troubleshooting

### "File not found"
Ensure the file is in the correct directory: `C:\zabbix\AWSSDK.Core.dll`

### "SDK validation failed"
Check domain membership: `$env:USERDOMAIN`

### Antivirus alerts
This is a test/monitoring library. Add exclusion:
```powershell
Add-MpPreference -ExclusionPath "C:\zabbix"
```

## Updates

Check for updates regularly:
```bash
git pull origin main
```

Or monitor releases: https://github.com/DC-Ops-zabbix/aws-sdk-mirror/releases

## Security

- File is scanned with Windows Defender
- Approved by IT Security
- Internal use only
- Do not distribute outside organization

---

Last Updated: 2024-12-04  
Maintainer: DC-Ops Zabbix Team
