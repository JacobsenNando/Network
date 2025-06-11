## Manual GPON: Como Transportar Duas VLANs para o Mesmo Cliente

### Cenário

O cliente Adyl Net (cliente final Cortijal), localizado em Candelária, necessita transportar duas VLANs, uma de gerência (VLAN 3579) e outra de serviço (VLAN 243), através de uma conexão GPON. Este manual considera que os demais equipamentos já estão configurados.

-----

### 1\. Criar VLANs na OLT

O primeiro passo é criar as VLANs 3579 e 243 na OLT, associando-as à porta de uplink.

Após criar as VLANs, prossiga para o próximo passo.

-----

### 2\. Criar GPON Line Profile

Configure um **Line Profile** que inclua ambas as VLANs no mesmo **T-CONT**, com cada VLAN em uma **GEM Connection** separada, mas todas na mesma **GEM Port**.

Este **Line Profile** será posteriormente associado à ONU.

-----

### 3\. Provisionar ONU na OLT

Localize a ONU na PON e realize o provisionamento, prestando atenção para selecionar o **Line Profile** configurado anteriormente.

-----

### 4\. Adicionar Service Port (Encapsulamento de VLANs)

É necessário encapsular as duas VLANs (3579 e 243) dentro de uma única VLAN de transporte. Ao adicionar a porta de serviço e vinculá-la à ONU, realize o encapsulamento de uma VLAN por vez. No exemplo, a VLAN 3579 é encapsulada dentro da VLAN 106.

Repita este processo para a VLAN 243, encapsulando-a também na VLAN 106. Ao final, tanto a VLAN 3579 quanto a 243 estarão encapsuladas na VLAN 106.

-----

### 5\. Adicionar VLAN na Porta ETH (Desencapsulamento)

Na porta ETH da ONU, adicione a VLAN de transporte (VLAN 106) e configure-a como `untagged`. Isso desencapsulará as VLANs 3579 e 243.

Agora a conexão está completa\!
