# Configuração de Túneis EoIP para Transporte de Redes Mikrotik

Este documento descreve o processo de criação de um túnel EoIP em roteadores Mikrotik e a vinculação do túnel a uma bridge para transportar redes entre dois pontos.

## Passo 1: Criar um Túnel EoIP

1. Acesse o menu **Interfaces** no seu roteador Mikrotik.
2. Clique em **Add New** (+) e selecione **EoIP Tunnel**.
3. Preencha os seguintes campos para configurar o túnel EoIP:

   - **Remote Address**: IP do roteador Mikrotik do outro lado do túnel.
   - **Tunnel ID**: Um número único para identificar o túnel. Deve ser o mesmo nos dois lados.
   - **MTU**: Use o valor padrão ou ajuste conforme a necessidade da sua rede (normalmente 1500).

4. Clique em **OK** para salvar.

> **Nota**: O ID do túnel deve ser o mesmo em ambos os lados para garantir que o túnel funcione corretamente.

## Passo 2: Criar uma Bridge e Vincular Interfaces

1. Acesse o menu **Bridge** e clique em **Add New** (+).
2. Nomeie a bridge (por exemplo, `bridge1`) e clique em **OK** para salvar.
3. Selecione a **aba Ports** dentro do menu Bridge.
4. Adicione o túnel EoIP e a interface de saída (por exemplo, uma VLAN ou porta Ethernet) à bridge:
   - Clique em **Add New** (+).
   - Selecione **Interface** como a interface `EoIP Tunnel` e associe-a à bridge.
   - Repita o processo para adicionar a interface física (por exemplo, `ether5` ou `vlan200`).

> Na imagem, vemos o túnel EoIP sendo vinculado à `bridge1`, junto com a interface `vlan200` para transporte de dados.

## Passo 3: Configuração do Outro Lado do Túnel

Na outra RB (roteador) no outro lado do túnel, repita os passos acima:

1. Crie um túnel EoIP usando o mesmo **Tunnel ID** e configure o IP local como o **Remote Address**.
2. Crie uma bridge e adicione o túnel EoIP e a interface de transporte (pode ser outra VLAN ou interface Ethernet).

## Passo 4: Adicionar PPPoE Client

No roteador do cliente (RB do outro lado), configure o cliente PPPoE para que ele possa se conectar ao servidor central.

1. Acesse o menu **Interfaces** e clique em **Add New** (+).
2. Selecione **PPPoE Client**.
3. Preencha os dados conforme necessário:

   - **Service Name**: Deixe em branco ou coloque o nome do serviço PPPoE.
   - **User**: Coloque o nome de usuário fornecido para o cliente.
   - **Password**: Coloque a senha fornecida.

4. Na aba **Dial Out**, configure o **Remote Address** e as credenciais de autenticação.

## Considerações Finais

- Utilize endereços IP da pool `172.23.160.xx` ou `172.23.161.xx` para a configuração de IPs no túnel EoIP.
- Sempre use máscara de sub-rede `/32` para o transporte, garantindo que o tráfego seja direcionado corretamente entre os túneis.

![Tunnel EoIP](img/EoIP.jpg)
