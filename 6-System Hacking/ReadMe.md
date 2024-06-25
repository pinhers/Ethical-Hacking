![image](https://github.com/pinhers/Ethical-Hacking/assets/145346889/40e3de55-1c76-484c-9af9-4a0b68053ba8)

### Imagens e Configurações de Instâncias

- **win11 c5large 65gb**
- **Parrot OS c5 65gb**
- **ubuntu24 c5 65gb**
- **win2016 server base c5 65gb**

### Configuração do Ubuntu

#### Passos para Instalar o Ambiente Gráfico:

1. **Atualizar os repositórios:**
    ```bash
    sudo apt update
    ```

2. **Instalar XFCE e outros componentes necessários:**
    ```bash
    sudo apt install -y xfce4 xfce4-goodies
    sudo apt install -y xrdp chromium-browser filezilla
    ```

3. **Adicionar usuário xrdp ao grupo ssl-cert:**
    ```bash
    sudo adduser xrdp ssl-cert
    ```

4. **Adicionar novo usuário (maria):**
    ```bash
    sudo adduser maria
    ```

5. **Efetuar login como usuário maria:**
    ```bash
    login maria
    ```

6. **Configurar a sessão do XFCE:**
    ```bash
    echo xfce4-session > ~/.xsession
    ```
