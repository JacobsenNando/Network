### 1. **Verifique se o SSH está instalado e ativo**

- **Verifique se o SSH está instalado**:

  - Execute o seguinte comando para verificar se o SSH está instalado:
    ```bash
    dpkg -l | grep openssh-server
    ```
  - Se o SSH não estiver instalado, você pode instalá-lo com:
    ```bash
    apt update
    apt install openssh-server
    ```

- **Verifique o status do serviço SSH**:
  - Certifique-se de que o serviço SSH está ativo:
    ```bash
    systemctl status ssh
    ```
  - Se o serviço não estiver ativo, inicie-o com:
    ```bash
    systemctl start ssh
    ```

### 2. **Verifique as configurações de rede**

- **Confirme o IP do container**:

  - Verifique o IP com o comando:
    ```bash
    ip a
    ```
  - Certifique-se de que o IP está correto e que você está tentando acessar o IP correto via SSH.

- **Verifique as regras de firewall**:
  - Verifique se há regras de firewall que possam estar bloqueando o acesso SSH.
  - Se você estiver usando o `ufw` (Uncomplicated Firewall), pode verificar as regras com:
    ```bash
    ufw status
    ```
  - Permita o acesso SSH, se necessário:
    ```bash
    ufw allow ssh
    ```

### 3. **Verifique as permissões do arquivo `sshd_config`**

- **Verifique as configurações do SSH**:

  - Abra o arquivo de configuração do SSH:
    ```bash
    nano /etc/ssh/sshd_config
    ```
  - Certifique-se de que as linhas abaixo estão configuradas corretamente:
    ```bash
    PermitRootLogin yes  # (ou no, se preferir desabilitar root e usar outro usuário)
    PasswordAuthentication yes
    ```
  - Depois de fazer as alterações, salve e saia do editor (`Ctrl + O`, `Enter`, `Ctrl + X`).

- **Reinicie o serviço SSH**:
  - Reinicie o serviço para aplicar as alterações:
    ```bash
    systemctl restart ssh
    ```

### 4. **Testar a conexão SSH novamente**

Agora, tente se conectar ao container via SSH novamente. Use o comando abaixo substituindo `user` pelo nome do usuário e `IP_DO_CONTAINER` pelo IP do container:

```bash
ssh user@IP_DO_CONTAINER
```
