# Lab Environment Documentation

## Azure

| Field          | Value |
|----------------|-------|
| Resource group | rg-lab-ad |
| Region         | Sweden Central |
| VM size        | Standard B2als v2 (2 vcpus, 4 GiB memory)|
| Auto-shutdown  | 17:00 UTC+1 |



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

## Active Directory — Initial State

| Object                | Count / Detail |
|-----------------------|----------------|
| OUs (default)         | Domain Controllers |
| Containers (default)  | Builtin, Computers, ForeignSecurityPrincipals, Managed Service Accounts, Users |
| User accounts         | Administrator, Guest, krbtgt, azureadmin |
| Security groups       | Domain Admins, Domain Users, Domain Computers, Domain Controllers, Enterprise Admins, Schema Admins, Key Admins, Enterprise Key Admins, Protected Users, Group Policy Creator Owners, etc. |
| Domain Admins members | Administrator, azureadmin |

## DNS Verification

| Check                        | Result |
|------------------------------|------------|
| Forward zone `becode.corp.lab` | Present |
| `_msdcs.becode.corp.lab` zone | Present |
| Reverse lookup zone          | No (not created yet) |
| SRV records (`_ldap`, etc.)  | Present (created automatically by AD) |
| `nslookup becode.corp.lab`   | OK |
| `nslookup dc01.becode.corp.lab` | FAIL (actual hostname is `max-dc01`) |

## Kerberos

| Field | Value |
|------|------|
| TGT issuer | krbtgt/BECODE.CORP.LAB |
| TGT expiry time | 3/20/2026 00:00 |
| Default TGT lifetime | ~10 hours |

Additional Kerberos details observed:

| Field | Value |
|------|------|
| Kerberos encryption | AES-256 |
| KDC server | max-dc01 |

## Event Log Check

| Log | Errors found | Notes |
|------------------|--------------|-------|
| Directory Service | No | Domain Controller promoted successfully; no critical errors observed |

