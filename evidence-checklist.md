# Evidence Collection Checklist & Commands

**Before you collect**: Document time, who collected what, and preserve chain of custody.

## Volatile data (collect first)
- Running processes, network connections, logged-on users
- Memory (if possible) — use trusted forensic tool
- ARP/route table

### Windows quick commands
- Running processes: `tasklist /V`
- Net connections: `netstat -ano`
- Event logs: `wevtutil qe Security /f:text /c:200`
- Save systeminfo: `systeminfo > systeminfo.txt`

### Linux quick commands (run as root)
- Processes: `ps aux > /tmp/ps_aux.txt`
- Network: `ss -tunap > /tmp/ss.txt` or `netstat -tunap`
- Open files: `lsof -i > /tmp/lsof.txt`
- dmesg/logs: `dmesg > /tmp/dmesg.txt` and `journalctl -u ssh -S -1h > /tmp/sshlog.txt`
- Capture pcap: `tcpdump -nni any host <suspicious-ip> -w /tmp/capture.pcap`
- Hash files: `sha256sum suspicious.exe > suspicious.exe.sha256`

## Non-volatile data
- Copy full disk image if required (use forensic tools)
- Collect system logs (`/var/log/`), application logs, AV logs

## Chain of custody
- Create a evidence log with: item ID, collected by, date/time, reason, storage path, hash, owner signature.

## Storage
- Store evidence in a secure, access-limited location (encrypted storage).
