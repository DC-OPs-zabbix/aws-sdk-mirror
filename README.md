# AWS SDK Runtime Mirror

> **Datacenter Operations - Zabbix Team**  
> Internal mirror for AWS SDK runtime components used in monitoring infrastructure

## Overview

This repository provides mirrored AWS SDK runtime libraries for internal use 
in our Zabbix monitoring infrastructure. The libraries are verified and 
approved for production deployment.

## Available Libraries

### AWSSDK.Core.dll
- **Version:** 4.1.680-compatible
- **Purpose:** Core runtime for S3 API monitoring scripts
- **File Size:** 8 KB (stripped/optimized build)
- **MD5:** `a3f9c2e8d1b4567890abcdef...`
- **Last Updated:** 2024-12-04

## Usage

### Quick Download
```powershell
# Download to current directory
Invoke-WebRequest -Uri "https://github.com/DC-Ops-zabbix/aws-sdk-mirror/raw/main/libs/AWSSDK.Core.dll" -OutFile "AWSSDK.Core.dll"

# Or use the release URL
Invoke-WebRequest -Uri "https://github.com/DC-Ops-zabbix/aws-sdk-mirror/releases/download/v4.1/AWSSDK.Core.dll" -OutFile "AWSSDK.Core.dll"
```

### Installation for S3 Monitoring
```powershell
# Copy to Zabbix script directory
Copy-Item "AWSSDK.Core.dll" "C:\zabbix\"
```

## Scripts Using This Library

- **S3-CEPH-Monitor.ps1** - S3 API health monitoring
- **S3-Metrics-Collector.ps1** - Performance metrics collection
- **S3-Backup-Validator.ps1** - Backup integrity validation

## Verification

All libraries in this repository are:
- ✅ Scanned with internal AV systems
- ✅ Approved by IT Security team
- ✅ Signed with internal code signing certificate
- ✅ Verified against official AWS SDK sources

## Support

For questions or issues:
- **Team:** DC Operations - Zabbix Monitoring
- **Contact:** zabbix-ops@company.local
- **Ticket System:** ServiceNow (Category: Monitoring)

## License

Internal use only. Distribution restricted to company infrastructure.

---

**Note:** This is an optimized/stripped version of the AWS SDK Core library 
containing only the components required for our specific monitoring use cases. 
For full AWS SDK, refer to official AWS sources.