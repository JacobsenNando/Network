# Manual Introdutório de Redes para Suporte Técnico

## Índice
1. [Introdução](#introdução)
2. [Conceitos Básicos de Rede](#conceitos-básicos-de-rede)
   - [Tipos de Redes](#tipos-de-redes)
   - [Endereçamento IP](#endereçamento-ip)
   - [Sub-redes e Máscara de Rede](#sub-redes-e-máscara-de-rede)
   - [Portas e Protocolos](#portas-e-protocolos)
3. [Equipamentos de Rede](#equipamentos-de-rede)
   - [Roteadores](#roteadores)
   - [Switches](#switches)
   - [Modems e ONTs](#modems-e-onts)
4. [Noções Básicas de Troubleshooting](#noções-básicas-de-troubleshooting)
   - [Comandos Básicos de Diagnóstico](#comandos-básicos-de-diagnóstico)
   - [Resolução de Problemas Comuns](#resolução-de-problemas-comuns)
5. [Segurança de Rede](#segurança-de-rede)
   - [Conceitos Básicos de Firewall](#conceitos-básicos-de-firewall)
   - [Boas Práticas de Segurança](#boas-práticas-de-segurança)
6. [Conclusão](#conclusão)

## Introdução
Este manual tem como objetivo fornecer uma introdução básica aos conceitos de redes, fundamentais para o trabalho de suporte em um provedor de internet. Ele abordará tópicos como os tipos de redes, endereçamento IP, equipamentos, e noções de troubleshooting, preparando você para lidar com os desafios diários no suporte técnico.

## Conceitos Básicos de Rede

### Tipos de Redes
- **LAN (Local Area Network)**: Rede local que conecta dispositivos dentro de um espaço limitado, como uma residência ou escritório.
- **WAN (Wide Area Network)**: Rede ampla que abrange uma área geográfica extensa, conectando múltiplas LANs.
- **MAN (Metropolitan Area Network)**: Rede que cobre uma cidade ou área metropolitana, sendo maior que uma LAN, mas menor que uma WAN.

### Endereçamento IP
- **IPv4**: Padrão de endereçamento de 32 bits, representado por quatro octetos separados por pontos (ex: 192.168.0.1).
- **IPv6**: Padrão mais recente de 128 bits, com notação hexadecimal (ex: 2001:0db8:85a3:0000:0000:8a2e:0370:7334).

### Sub-redes e Máscara de Rede
- **Máscara de Rede**: Define a porção de um endereço IP que pertence à rede e a porção que pertence aos hosts. Exemplo: 255.255.255.0.
- **Sub-rede**: Divisão de uma rede maior em redes menores, facilitando o gerenciamento e a segurança.

### Portas e Protocolos
- **Portas**: Pontos finais de comunicação em um dispositivo de rede. Exemplo: HTTP (porta 80), HTTPS (porta 443).
- **Protocolos**: Regras que definem como os dados são transmitidos na rede. Exemplo: TCP, UDP, ICMP.

## Equipamentos de Rede

### Roteadores
Dispositivos que encaminham pacotes de dados entre diferentes redes, determinando a melhor rota para o tráfego.

### Switches
Equipamentos que conectam dispositivos dentro de uma rede local (LAN), permitindo a comunicação entre eles.

### Modems e ONTs
- **Modem**: Converte sinais digitais em analógicos (e vice-versa) para conexão à internet.
- **ONT (Optical Network Terminal)**: Dispositivo que termina a conexão de fibra óptica e fornece acesso à rede para o cliente.

## Noções Básicas de Troubleshooting

### Comandos Básicos de Diagnóstico
- **ping**: Verifica a conectividade entre dois dispositivos.
- **tracert/traceroute**: Mostra o caminho percorrido pelos pacotes até o destino.
- **ipconfig/ifconfig**: Exibe as configurações de rede do dispositivo.

### Resolução de Problemas Comuns
- **Problemas de Conectividade**: Verificar cabos, conexões físicas e configurações IP.
- **Quedas de Rede**: Analisar logs de erro e verificar a configuração do roteador.

## Segurança de Rede

### Conceitos Básicos de Firewall
Um firewall monitora e controla o tráfego de rede, filtrando pacotes com base em regras definidas para proteger a rede de acessos não autorizados.

### Boas Práticas de Segurança
- Atualizar regularmente firmware e software de dispositivos.
- Utilizar senhas fortes e autenticidade multifatorial.
- Configurar corretamente firewalls e outros dispositivos de segurança.

## Conclusão
Compreender os fundamentos de redes é essencial para prestar um suporte técnico eficaz em um provedor de internet. Este manual deve servir como ponto de partida para aprofundar seus conhecimentos e melhorar sua prática no dia a dia.

