# Lab Environment Documentation

## Azure

| Field          | Value |
|----------------|-------|
| Resource group | rg-lab-ad |
| Region         | Sweden Central |
| VM size        | Standard B2als v2 (2 vcpus, 4 GiB memory)|
| Auto-shutdown  | 17:00 UTC+1 |

## Domain Controller

| Field | Value |
|------|------|
| VM name / Hostname | max-dc01 |
| Private IP | 10.0.0.4 |
| OS | Windows Server 2025 |
| Role | Domain Controller (pending installation) |
| Domain | (to be configured) |
| DSRM password | stored in password manager |

## Domain Controller

| Field          | Value               |
|----------------|---------------------|
| VM name / Hostname | dc01            |
| Private IP     | 10.0.0.4            |
| OS             | Windows Server 2025 |
| Role           | Domain Controller   |
| Domain         | becode.corp.lab     |
| NetBIOS name   | BECODE              |
| Forest level   | Windows Server 2025 |
| DNS zones      | becode.corp.lab, _msdcs.becode.corp.lab |
| SRV records    | Present             |
| DSRM password  | stored in password manager |
