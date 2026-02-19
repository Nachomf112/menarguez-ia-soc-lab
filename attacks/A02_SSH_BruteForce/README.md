# A02 - SSH Brute Force Detection

## Objective
Simulate repeated SSH authentication attempts using a non-existent user and validate detection and correlation in Wazuh.

## Target
Ubuntu Wazuh Agent - 192.168.100.235

## Attack (Kali)

```bash
for i in {1..10}; do ssh fakeuser@192.168.100.235; done
