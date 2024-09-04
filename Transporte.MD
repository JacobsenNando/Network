Aqui está um modelo de `README.md` para suas instruções de configuração:

```markdown
# Configuração de Túnel EoIP e PPPoE

Este documento fornece instruções para configurar um túnel EoIP e vincular a uma porta Ether ou VLAN em uma bridge, bem como adicionar um cliente PPPoE na RB do cliente. Assegure-se de usar as pools de IPs 172.23.160.xx ou 172.23.161.xx e sempre utilizar /32 para transporte.

## Requisitos

- RouterBOARD (RB) com suporte para EoIP
- Acesso à interface web do RouterBOARD ou CLI (Command Line Interface)
- IP Pools: 172.23.160.xx ou 172.23.161.xx
- Sub-rede /32 para transporte

## Configuração do Túnel EoIP

### No Lado do Servidor

1. **Criar o Túnel EoIP:**

   ```plaintext
   /interface eoip
   add name=eoip-tunnel1 remote-address=IP_DO_CLIENTE tunnel-id=ID_DO_TUNNEL
   ```

2. **Criar a Bridge e Adicionar o Túnel e a Porta Ether (ou VLAN):**

   ```plaintext
   /interface bridge
   add name=bridge1
   /interface bridge port
   add bridge=bridge1 interface=eoip-tunnel1
   add bridge=bridge1 interface=ether1
   ```

### No Lado do Cliente

1. **Criar o Túnel EoIP:**

   ```plaintext
   /interface eoip
   add name=eoip-tunnel1 remote-address=IP_DO_SERVIDOR tunnel-id=ID_DO_TUNNEL
   ```

2. **Criar a Bridge e Adicionar o Túnel e a Porta Ether (ou VLAN):**

   ```plaintext
   /interface bridge
   add name=bridge1
   /interface bridge port
   add bridge=bridge1 interface=eoip-tunnel1
   add bridge=bridge1 interface=ether1
   ```

## Configuração do Cliente PPPoE

### Na RB da Ponta do Cliente

1. **Adicionar o Cliente PPPoE:**

   ```plaintext
   /interface pppoe-client
   add name=pppoe-out1 interface=bridge1 user=USERNAME password=PASSWORD
   ```

### Verificar o Voalle
1.**Adicionar PPPoE do cliente e senha no voalle**

## Notas

- Substitua `IP_DO_CLIENTE`, `IP_DO_SERVIDOR`, `ID_DO_TUNNEL`, `USERNAME`, e `PASSWORD` pelos valores apropriados.
- Verifique a conectividade entre o túnel EoIP e a comunicação PPPoE para garantir que estão funcionando corretamente.
- Em caso de problemas, revise as configurações e certifique-se de que todas as interfaces estão configuradas corretamente.

## Imagem

Para mais detalhes, veja a imagem relacionada [aqui](#).

---

Se houver alguma dúvida ou problema com a configuração, entre em contato com o suporte técnico.
```

Sinta-se à vontade para ajustar qualquer parte conforme necessário.
