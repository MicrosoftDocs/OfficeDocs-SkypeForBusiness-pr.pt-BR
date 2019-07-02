---
title: Requisitos ambientais do servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Resumo: Saiba mais sobre os requisitos ambientais do servidor de borda no Skype for Business Server.'
ms.openlocfilehash: 25584c10c8359cb4a3e695cee4838b80bc9643f5
ms.sourcegitcommit: bd50c6239cee414ea9933e9d569fa5a24bc05544
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2019
ms.locfileid: "35414986"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisitos ambientais do servidor de borda no Skype for Business Server
 
**Resumo:** Saiba mais sobre os requisitos ambientais do servidor de borda no Skype for Business Server.
  
Muita necessidade de planejamento e preparação para ocorrer fora do próprio ambiente de servidor de borda do Skype for Business Server. Neste artigo, vamos rever as preparações que precisam ser feitas no ambiente organizacional, de acordo com nossa lista abaixo:
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planejamento de topologia
<a name="TopoPlan"> </a>

As topologias do servidor de borda do Skype for Business Server são capazes de usar:
  
- Endereços IP públicos roteáveis
    
- Endereços IP privados não roteáveis, se a tradução de endereço de rede **simétrica** (NAT) for usada.
    
> [!TIP]
> O servidor de borda pode ser configurado para usar um único endereço IP com portas distintas para cada serviço ou pode usar endereços IP distintos para cada serviço, mas use a mesma porta padrão (que, por padrão, será TCP 443). Temos mais informações na seção de requisitos do Endereço IP, abaixo. 
  
Se você escolher endereços IP privados não roteáveis com NAT, lembre-se destes aspectos:
  
- Você deve usar endereços IP privados roteáveis em **todas as três** interfaces externas.
    
- Você precisa configurar NAT **simétrico** para tráfego de entrada e de saída. O NAT simétrico é o único NAT compatível que você pode usar com o servidor de borda do Skype for Business Server.
    
- Configure seu NAT para não alterar endereços de origem de entrada. O serviço de borda a/V precisa ser capaz de receber o endereço de origem de entrada para encontrar o caminho de mídia ideal.
    
- Seus servidores de borda precisam ser capazes de se comunicar uns com os outros dos endereços IP de borda de A/V públicos. Seu firewall deve permitir esse tráfego.
    
- O NAT **só** poderá ser usado para servidores de borda consolidada em escala se você usar o balanceamento de carga de DNS. Se você usar o balanceamento de carga de hardware (HLB), será necessário usar endereços IP roteáveis publicamente **sem** NAT.
    
Você não terá problemas para ter acesso, Webconferência e interfaces de borda A/V atrás de um roteador ou firewall executando o NAT simétrico para topologias de servidor de borda consolidadas simples e dimensionadas (desde que você não esteja usando o balanceamento de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumo das opções de topologia do servidor de borda

Temos várias opções de topologia disponíveis para implantações do servidor de borda do Skype for Business Server:
  
- Borda única consolidada com endereços IP privados e NAT
    
- Borda única consolidada com endereços IP públicos
    
- Borda dimensionada consolidada com endereços IP privados e NAT
    
- Borda dimensionada consolidada com endereços IP públicos
    
- Borda dimensionada consolidada com balanceadores de carga de hardware
    
Para ajudá-lo a escolher uma, temos a tabela a seguir que apresenta um resumo das opções que você tem para cada topologia:
  
|**Topologia**|**Alta disponibilidade**|**Registros DNS adicionais necessários para o servidor de borda externo no pool de bordas?**|**Failover de borda para sessões do Skype for Business Server**|**Failover de borda para sessões de Federação do Skype for Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Borda única consolidada com endereços IP privados e NAT  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Borda única consolidada com endereços IP públicos  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Borda dimensionada consolidada com endereços IP privados e NAT (balanceamento de carga DNS)  <br/> |Sim   <br/> |Sim   <br/> |Sim   <br/> |Sim&SUP1;  <br/> |
|Borda dimensionada consolidada com endereços IP públicos (balanceamento de carga DNS)  <br/> |Sim   <br/> |Sim   <br/> |Sim   <br/> |Sim&SUP1;  <br/> |
|Borda dimensionada consolidada com balanceadores de carga de hardware  <br/> |Sim  <br/> |Não (um registro DNS A por VIP)  <br/> |Sim  <br/> |Sim   <br/> |
   
&SUP1; O failover de usuário remoto do Exchange Unified Messaging (UM) que usa o balanceamento de carga de DNS exige o Exchange 2013 ou versão mais recente.
  
### <a name="ip-address-requirements"></a>Requisitos de Endereço IP

Em um nível fundamental, três serviços precisam de endereços IP; Serviço de borda de acesso, serviço de borda de Webconferência e serviço de borda A/V. Você tem a opção de usar três endereços de IP, um para cada um dos serviços, ou você pode usar um e optar por colocar cada serviço em uma porta diferente (é possível consultar a seção[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações relacionadas). Para um ambiente de Borda única consolidada, isso é o suficiente.
  
> [!NOTE]
> Conforme observado acima, você pode escolher um endereço IP para todos os três serviços e executá-los em diferentes portas. Porém, na realidade, não recomendamos isso. Se os seus clientes não conseguem acessar as portas alternadas que você usaria neste cenário, eles também não podem acessar a funcionalidade total do seu ambiente de Borda. 
  
Pode ser um pouco mais complicado com topologias escalonáveis consolidadas, portanto, vejamos algumas tabelas que apresentam os requisitos de Endereço IP, lembrando-se de que os principais pontos de decisão para seleção da topologia são alta disponibilidade e balanceamento de carga. As necessidades de alta disponibilidade podem influenciar sua escolha de balanceamento de carga (falaremos mais sobre esse assunto depois das tabelas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de endereço IP para Borda dimensionada consolidada (endereço de IP por função)

|**Número de servidores de borda por pool**|**Número de endereços IP necessários para balanceamento de carga de DNS**|**Número de endereços IP necessários para o balanceamento de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 por VIP) + 6  <br/> |
|3  <br/> |222  <br/> |3 (1 por VIP) + 9  <br/> |
|4  <br/> |12  <br/> |3 (1 por VIP) + 12  <br/> |
|5  <br/> |15  <br/> |3 (1 por VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de endereço IP para Borda consolidada dimensionada (endereço de IP único para todas as funções)

|**Número de servidores de borda por pool**|**Número de endereços IP necessários para balanceamento de carga de DNS**|**Número de endereços IP necessários para o balanceamento de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (1 por VIP) + 2  <br/> |
|3  <br/> |3  <br/> |1 (1 por VIP) + 3  <br/> |
|4  <br/> |4  <br/> |1 (1 por VIP) + 4  <br/> |
|5  <br/> |5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Vejamos alguns tópicos adicionais que devem ser considerados no planejamento.
  
- **Alta disponibilidade**: se precisar de alta disponibilidade na sua implantação, você deve implantar pelo menos dois servidores de borda em um pool. Vale a pena observar que um único pool de bordas oferece suporte a até 12 servidores de borda (embora o Topology Builder permita que você adicione até 20, que não é testado ou compatível, então aconselhamos que você não faça isso). Se precisar de mais de 12 servidores de borda, você deve criar mais pools de bordas para eles.
    
- **Balanceamento de carga de hardware**: Recomendamos o balanceamento de carga de DNS para a maioria dos cenários. O balanceamento de carga de hardware também tem suporte, é claro, mas é preciso ter um único cenário do equilíbrio de carga de DNS:
    
  - Acesso externo ao Exchange 2007 ou ao Exchange 2010 (sem SP) mensagens unificadas (uma).
    
- **Balanceamento de carga de DNS**: para o um, o Exchange 2010 SP1 e versões mais recentes podem ser compatíveis com o balanceamento de carga de DNS. Observe que, se você precisar ir com o balanceamento de carga de DNS para uma versão anterior do Exchange, ele funcionará, mas todo o tráfego para ele vai para o primeiro servidor no pool e, se não estiver disponível, o tráfego falhará subseqüentemente.
    
    O balanceamento de carga de DNS também é recomendado se você estiver fazendo a Federação com empresas usando:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office O365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>Planejamento DNS
<a name="DNSPlan"> </a>

Quando se trata de implantação do Skype for Business Server Edge Server, é essencial preparar-se para o DNS corretamente. Com o registros corretos em vigor, a implantação será muito mais simples. Esperamos que você tenha escolhida uma topologia na seção acima, pois vamos fazer uma visão geral e, em seguida, listar algumas tabelas que destacam os registros DNS para os cenários. Também temos um planejamento de [DNS avançado do servidor de perímetro para o Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para obter uma leitura mais profunda, se necessário.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros de DNS para cenários de servidor de borda consolidado únicos

Esses serão os registros DNS necessários para um servidor de borda única usando o IPs público ou IPs privados com NAT. Como estes são dados de amostra, daremos o exemplo de IPs para que você possa encontrar sua própria solução mais facilmente:
  
- Adaptador de rede interna: 172.25.33.10 (nenhum gateway padrão atribuído)
    
    > [!NOTE]
    > Certifique-se de que haja uma rota da rede que contém a interface interna de borda para qualquer rede que contenha servidores executando o Skype for Business Server ou clientes do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - IPs Públicos:
    
  - Edge do Access: 131.107.155.10 (é o principal, com gateway padrão definido para o seu roteador público, por exemplo: 131.107.155.1)
    
  - Borda da webconferência: 131.107.155.20 (secundário)
    
  - Borda A/V: 131.107.155.30 (secundário)
    
  Os endereços IP de borda da Web e de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades de protocolo de Internet versão 4 (TCP/IPv4) e protocolo IP versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - IPs Privadas:
    
  - Borda do Access: 10.45.16.10 (é o principal, com gateway padrão definido para o roteador, por exemplo: 10.45.16.1)
    
  - Borda da webconferência: 10.45.16.20 (secundário)
    
  - Borda A/V: 10.45.16.30 (secundário)
    
Os endereços IP de borda da Web e de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades de protocolo de Internet versão 4 (TCP/IPv4) e protocolo IP versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
  
> [!TIP]
>Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externa. Não recomendamos isso porque então você precisará diferenciar os serviços do existem usando diferentes portas (que você pode fazer no Skype for Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a seção [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações sobre o assunto.
    
- É possível ter três adaptadores de rede externa em vez de um, e atribuir uma das IPs do serviço para cada um. Por que? Isto separaria os serviços e se algo der errado, seria mais fácil solucionar o problema e potencialmente permitiria que seus outros serviços continuassem a funcionar enquanto o problema estivesse sendo resolvido.
    
|**Local**|**Tipo**|**Porta**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 <br/> **particular:** 10.45.16.10 <br/> |Uma interface externa para o serviço de borda de acesso. Você precisará de um para cada domínio SIP com usuários do Skype for Business.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 <br/> **particular:** 10.45.16.20 <br/> |Uma interface externa para o serviço de borda de Webconferência Web.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 <br/> **particular:** 10.45.16.30 <br/> |Uma interface externa para o serviço de borda A/V.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Esse registro SRV é necessário para que os clientes do Skype for Business Server, Lync Server 2013 e Lync Server 2010 funcionem externamente. Você precisará de um para cada domínio com usuários do Skype for Business.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Este registro SRV é necessário para a descoberta de DNS automática de parceiros federados chamado domínios SIP Permitidos. Você precisará de um para cada domínio com usuários do Skype for Business.  <br/> |
|DNS Interno  <br/> |Registro A  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |A interface interna para sua Borda consolidada.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros de DNS para cenários de servidor DNS e borda de hardware em escala

Esses serão os registros DNS necessários para um servidor de borda única usando o IPs público ou IPs privados com NAT. Como estes são dados de amostra, daremos o exemplo de IPs para que você possa encontrar sua própria solução mais facilmente:
  
- Adaptador de rede interna
    
  - Nó 1: 172.25.33.10 (nenhum gateway padrão atribuído)
    
  - Nó 2: 172.25.33.11 (nenhum gateway padrão atribuído)
    
    > [!NOTE]
    > Certifique-se de que haja uma rota da rede que contém a interface interna de borda para qualquer rede que contenha servidores executando o Skype for Business Server ou clientes do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - Nó 1
    
     - IPs Públicos:
    
        - Edge do Access: 131.107.155.10 (é o principal, com gateway padrão definido para o seu roteador público, por exemplo: 131.107.155.1)
    
        - Borda da webconferência: 131.107.155.20 (secundário)
    
        - Borda A/V: 131.107.155.30 (secundário)
    
          Os endereços IP de borda da Web e de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades de protocolo de Internet versão 4 (TCP/IPv4) e protocolo IP versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
    - IPs Privadas:
    
         - Borda do Access: 10.45.16.10 (é o principal, com gateway padrão definido para o roteador, por exemplo: 10.45.16.1)
    
         - Borda da webconferência: 10.45.16.20 (secundário)
    
         - Borda A/V: 10.45.16.30 (secundário)
    
      Os endereços IP de borda da Web e de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades de protocolo de Internet versão 4 (TCP/IPv4) e protocolo IP versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - Nó 2
    
    - IPs Públicos:
    
      - Edge do Access: 131.107.155.11 (é o principal, com gateway padrão definido para o seu roteador público, por exemplo: 131.107.155.1)
    
      - Borda da webconferência: 131.107.155.21 (secundário)
    
      - Borda A/V: 131.107.155.31 (secundário)
    
      Os endereços IP de borda da Web e de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades de protocolo de Internet versão 4 (TCP/IPv4) e protocolo IP versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - IPs Privadas:
    
    - Borda do Access: 10.45.16.11 (é o principal, com gateway padrão definido para o roteador, por exemplo: 10.45.16.1)
    
    - Borda da webconferência: 10.45.16.21 (secundário)
    
    - Borda A/V: 10.45.16.31 (secundário)
    
      Os endereços IP de borda da Web e de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades de protocolo de Internet versão 4 (TCP/IPv4) e protocolo IP versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externa. Não recomendamos isso porque então você precisará diferenciar os serviços do existem usando diferentes portas (que você pode fazer no Skype for Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a seção [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações sobre o assunto.
    
- É possível ter três adaptadores de rede externa em vez de um, e atribuir uma das IPs do serviço para cada um. Por que? Isto separaria os serviços e se algo der errado, seria mais fácil solucionar o problema e potencialmente permitiria que seus outros serviços continuassem a funcionar enquanto o problema estivesse sendo resolvido.
    
|**Local**|**Tipo**|**Porta**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 e 131.107.155.11 <br/> **particular:** 10.45.16.10 e 10.45.16.11 <br/> |Uma interface externa para o serviço de borda de acesso. Você precisará de um para cada domínio SIP com usuários do Skype for Business.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 e 131.107.155.21 <br/> **particular:** 10.45.16.20 e 10.45.16.21 <br/> |Uma interface externa para o serviço de borda de Webconferência Web.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 e 131.107.155.31 <br/> **particular:** 10.45.16.30 e 10.45.16.31 <br/> |Uma interface externa para o serviço de borda A/V.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Esse registro SRV é necessário para que os clientes do Skype for Business Server, Lync Server 2013 e Lync Server 2010 funcionem externamente. Você precisará de um para cada domínio com o Skype for Business.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Este registro SRV é necessário para a descoberta de DNS automática de parceiros federados chamado domínios SIP Permitidos. Você precisará de um para cada domínio com o Skype for Business.  <br/> |
|DNS Interno  <br/> |Registro A  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 e 172.25.33.11  <br/> |A interface interna para sua Borda consolidada.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para federação (todos os cenários)

|**Local**|**Tipo**|**Porta**|**Fully**|**Registro de host FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |A interface externa de borda de acesso SIP necessária para a descoberta automática de DNS. Usada por seus outros parceiros da federação em potencial. É também conhecida como "Domínios SIP permitidos." Você precisará de um deles para cada domínio SIP com usuários do Skype for Business.  <br/><br/> **Observação:** Você precisará desse registro SRV para a mobilidade e a equipe de compensação da notificação por push. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Resumo DNS para protocolo de presença e mensagem extensível

|**Local**|**Tipo**|**Porta**|**Fully**|**Endereço IP ou registro de host FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |A interface de proxy XMPP em seu serviço de borda de acesso ou em um pool de bordas. Você precisa repetir isso conforme necessário para todos os domínios SIP internos com usuários habilitados para o Skype for Business Server, em que o contato com contatos do XMPP é permitido por meio de:  <br/> • uma política global  <br/> • política do site na qual o usuário está habilitado  <br/> • uma política de usuário aplicada ao usuário habilitado para o Skype for Business Server  <br/> Uma política XMPP permitida também deve ser configurada na política de usuários federados XMPP.  <br/> |
|DNS Externo  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de bordas que hospeda seu serviço de proxy XMPP  <br/> |Isso aponta para o serviço de borda de acesso no servidor de borda ou no pool de bordas que hospeda o serviço de proxy XMPP. Normalmente, o registro SRV que você cria apontará para esse registro de host (A ou AAAA).  <br/> |
   
> [!NOTE]
> Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [migrando a Federação do XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.

## <a name="certificate-planning"></a>Planejamento de Certificados
<a name="CertPlan"> </a>

O Skype for Business Server usa certificados para comunicações seguras e criptografadas entre servidores e do servidor com o cliente. Como seria de esperar, seus certificados deverão ter registros DNS para que seus servidores sejam compatíveis com qualquer nome da entidade (SN) e nome alternativo de entidade (SAN) em seus certificados. Isso será trabalhoso na fase de planeamento, para que você certifique-se de que tem os FQDNs corretos registrados no DNS para as inserções de SN e SAN de seus certificados.
  
Abordaremos as necessidades de certificados internos e externos separadamente, e em seguida, examinaremos uma tabela que fornece os requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados Externos

No mínimo, o certificado atribuído às interfaces do servidor de borda externa precisará ser fornecido por uma CA (autoridade de certificação) pública. Não é possível recomendar uma CA específica para você, mas temos uma lista de CAs, [parceiros de comunicações](/SkypeForBusiness/certification/services-ssl) unificadas que você pode examinar para ver se a sua CA preferida está listada.
  
Quando você precisará enviar uma solicitação para um AC para ter este certificado público, e como você fazê-lo? Há várias formas de fazer isso:
  
- Você pode percorrer a instalação do Skype for Business Server e, em seguida, a implantação do servidor de borda. O assistente de implantação do Skype for Business Server terá uma etapa para gerar uma solicitação de certificado, que você poderá enviar para a autoridade de certificação escolhida.
    
- Você também pode usar os comandos do Windows PowerShell para gerar essa solicitação, se isso for mais embutido com suas necessidades comerciais ou estratégia de implantação.
    
- Por fim, sua CA pode ter seu próprio processo de envio, que também pode envolver o Windows PowerShell ou outro método. Nesse caso, você precisará contar com sua documentação, além as informações fornecidas aqui para sua referência.
    
Depois de ter chegado ao certificado, você precisará continuar e atribuí-lo a esses serviços no Skype for Business Server:
  
- Interface do serviço de borda do Access
    
- Interface do serviço de borda de Webconferência
    
- Serviço de autenticação de áudio/vídeo (não confunda isso com o serviço de borda A/V, como isso não usa um certificado para criptografar fluxos de áudio e vídeo)
    
> [!IMPORTANT]
> Todos os servidores de borda (se pertencerem ao mesmo pool de servidores de borda) precisam ter o mesmo certificado com a mesma chave privada para o serviço de autenticação de retransmissão de mídia. 
  
### <a name="internal-certificates"></a>Certificados internos

Para a interface do servidor de borda interna, você pode usar um certificado público de uma autoridade de certificação pública ou um certificado emitido pela CA interna da sua organização. É importante lembrar que o certificado interno é aquele utiliza uma inserção de SN, e nenhuma inserção de SAN, portanto, você  não deve se preocupar com SAN no certificado interno.
  
### <a name="required-certificates-table"></a>Tabela de Certificados Exigidos

Temos uma tabela aqui para ajudá-lo com os seus pedidos. As entradas de FQDN são apenas exemplos de domínios. Você precisará fazer solicitações com base em seus próprios domínios privados e públicos, mas aqui está a orientação sobre o procedimento que temos seguido:
  
- Contoso<span></span>. com: FQDN público
    
- Fabrikam<span></span>. com: segundo FQDN público (adicionado como uma demonstração do que solicitar se você tiver vários domínios SIP)
    
- Contoso<span></span>.net: domínio interno
    
#### <a name="edge-certificate-table"></a>Tabela de Certificado de Borda

Não importa se você está fazendo um único servidor de borda ou um pool de bordas, isso é o que você precisará para o seu certificado:
  
|**Componente**|**Nome da entidade (SN)**|**Nomes alternativos de entidade (SAN)/ordem**|**Observações**|
|:-----|:-----|:-----|:-----|
|Borda Externa  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Esse é o certificado que você precisa solicitar de uma AC pública. Ele precisará ser atribuído às interfaces de Borda externa para o seguinte:<br/> • Borda do Access  <br/> • Borda de Webconferência  <br/> • Autenticação de áudio/vídeo  <br/> <br/>A boa notícia é que as SANs são automaticamente adicionadas à sua solicitação de certificado e, portanto, seu certificado depois que você envia a solicitação, com base no que você definiu para esta implantação no construtor de topologias. Basta adicionar entradas de SAN para quaisquer domínios SIP adicionais ou outras entradas às quais você precisa dar suporte. Por que o sip.contoso.com é replicado nessa instância? Isso também acontece automaticamente e é necessário para que as coisas funcionem adequadamente.  <br/><br/> **Observação:** Este certificado também pode ser usado para conectividade de mensagens instantâneas públicas. Não será necessário fazer nada diferente com ele, pois as versões anteriores desta documentação foram listadas como uma tabela separada, e agora não são mais. <br/> |
|Borda Interna  <br/> |sfbedge.contoso.com  <br/> |N/D  <br/> |É possível obter este certificado a partir de uma AC pública ou interna. Ele precisará conter o EKU do servidor (Uso Avançado de Chave), e você precisará atribuí-lo à interface de borda interna.  <br/> |
   
Se você precisa de um certificado para XMPP (Extensible Messaging and Presence Protocol), ele será idêntico às entradas da tabela de Borda Externa acima, mas terá as duas entradas adicionais de SAN indicadas abaixo:
  
- xmpp. <span> </span>Contoso<span></span>. com
    
- \*. contoso<span></span>. com
    
Lembre-se de que atualmente o XMPP só é compatível com o Skype for Business Server para Google Talk, se você quiser ou precisar usá-lo para qualquer outra coisa, você precisará confirmar essa funcionalidade com o fornecedor de terceiros envolvido.
  
## <a name="port-and-firewall-planning"></a>Planejamento de porta e de firewall
<a name="PortFirewallPlan"> </a>

Obter o direito de planejamento para portas e firewalls para implantações do servidor Edge do Skype for Business Server pode economizar dias ou semanas de solução de problemas e estresse. Como resultado, vamos listar algumas tabelas que indicarão nosso uso do protocolo e quais portas você precisa abrir, internas e externas, tanto para cenários NAT e de IP público. Também temos tabelas separadas para cenários com balanceamento de carga de hardware (HLB) e mais algumas orientações sobre isso. Para obter mais leituras a partir daí, também temos alguns [cenários de servidor de borda no Skype for Business Server](scenarios.md) que você pode fazer check-out para obter as preocupações específicas com a implantação.
  
### <a name="general-protocol-usage"></a>Uso Geral do Protocolo

Antes de observarmos as tabelas de resumo para firewalls internos e externos, vejamos a tabela a seguir:
  
|**Transporte de áudio/vídeo**|**Uso**|
|:-----|:-----|
|UDP  <br/> |Protocolo de camada de transporte preferido para áudio e vídeo.  <br/> |
|TCP  <br/> |Protocolo de camada de transporte de fallback para áudio e vídeo.  <br/> O protocolo de camada de transporte necessário para compartilhamento de aplicativos com o Skype for Business Server, o Lync Server 2013 e o Lync Server 2010.  <br/> O protocolo de camada de transporte necessário para transferência de arquivo para o Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabela de resumo de firewall da porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para usuários que estão usando endereços IP privados com NAT, bem como para as pessoas que utilizam endereços IP públicos. Isso fará com que todas as permutações sejam abordadas em nossos [cenários de servidor de borda na seção do Skype for Business Server](scenarios.md) .
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Não compatível com o Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Qualquer um  <br/> |Serviço de proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso  <br/> |O serviço de proxy XMPP aceita o tráfego dos contatos do XMPP em agrupamentos XMPP definidos.  <br/> |
|Acesso/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Qualquer um  <br/> |Revocação de certificado e verificação e recuperação de CRL  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Qualquer um  <br/> |Consulta DNS sobre TCP  <br/> |
|Acesso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Qualquer um  <br/> |Consulta DNS sobre UDP  <br/> |
|Acesso/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Tráfego SIP do cliente ao servidor para o acesso do usuário externo.  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer um  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Qualquer um  <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Webconferência/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |**IP privado usando NAT:** Serviço de borda de Webconferência Web Edge Server <br/> **IP público:** Endereço IP público do serviço de borda de Webconferência do Edge Server Web <br/> |Mídia de Webconferência.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Qualquer um  <br/> |Saída 3478 é:  <br/> • Usado pelo Skype for Business Server para determinar a versão do servidor de borda com a qual está se comunicando.  <br/> • Usado para tráfego de mídia entre servidores de borda.  <br/> • Necessário para federação com o Lync Server 2010.  <br/> • Necessário se vários pools de bordas forem implantados em sua organização.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um  <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Negociação de candidatos STUN/TURN sob UDP na porta 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Qualquer um  <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabela de resumo do firewall da porta interna

|**Protocolo**|**TCP ou UDP**|**Porta**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> |Interface interna do servidor de borda  <br/> |Tráfego de XMPP de saída do seu serviço de gateway do XMPP em execução em seu servidor front-end ou pool de front-ends.  <br/> **Observação:** Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [migrando a Federação do XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Pool de diretor  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> |Interface interna do servidor de borda  <br/> |O tráfego SIP de saída do seu diretor, do pool de directors, do servidor front-end ou do pool de front-ends para a interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interna do servidor de borda  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Pool de diretor  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> |Tráfego SIP de entrada para seu diretor, pool de directors, servidor front-end ou pool de front-end da interface interna do servidor de borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada servidor front-end  <br/>  em seu pool de front-ends <br/> |Interface interna do servidor de borda  <br/> |O tráfego de webconferências do seu servidor front-end ou de cada servidor front-end (se você tiver um pool de front-end) para a interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> • Qualquer aparelho de ramificação sobreviventes que use este servidor de borda  <br/> • Qualquer servidor de ramificação sobreviventes que use este servidor de borda  <br/> |Interface interna do servidor de borda  <br/> |Autenticação de usuários de A/V do seu servidor front-end ou pool de front-end, ou seu aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes, usando seu servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de ramificação sobreviventes ou servidor de filial transferível.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |Interface interna do servidor de borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de ramificação sobreviventes ou servidor de filial transferível, se a comunicação UDP não funcionar. Neste caso, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualquer um:  <br/> • Servidor front-end que mantém o repositório central de gerenciamento  <br/> • Pool de front-end que mantém o repositório central de gerenciamento  <br/> |Interface interna do servidor de borda  <br/> |Replicação de alterações do repositório de gerenciamento central para o servidor de borda.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Controle centralizado do serviço de registro em log usando o Shell de gerenciamento do Skype for Business Server e cmdlets do serviço de registro centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Controle centralizado do serviço de registro em log usando o Shell de gerenciamento do Skype for Business Server e cmdlets do serviço de registro centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Controle centralizado do serviço de registro em log usando o Shell de gerenciamento do Skype for Business Server e cmdlets do serviço de registro centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e a coleção de logs.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Balanceadores de carga de hardware para tabelas da porta da Borda

Preparamos uma seção apenas para balanceadores de carga de hardware (HLBs) e portas da Borda, uma vez que o assunto é um pouco mais complicado em se tratando de hardware adicional. Consulte as tabelas abaixo para obter orientação para este cenário específico:
  
#### <a name="external-port-firewall-summary-table"></a>Tabela de resumo de firewall da porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para usuários que estão usando endereços IP privados com NAT, bem como para as pessoas que utilizam endereços IP públicos. Isso fará com que todas as permutações sejam abordadas em nossos [cenários de servidor de borda na seção do Skype for Business Server](scenarios.md) .
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acesso/HTTP  <br/> |TCP  <br/> |80  <br/> |Endereço IP público do serviço de borda do acesso ao servidor de borda  <br/> |Qualquer um  <br/> |Revocação de certificado e verificação e recuperação de CRL  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |Endereço IP público do serviço de borda do acesso ao servidor de borda  <br/> |Qualquer um  <br/> |Consulta DNS sobre TCP  <br/> |
|Acesso/DNS  <br/> |UDP  <br/> |53  <br/> |Endereço IP público do serviço de borda do acesso ao servidor de borda  <br/> |Qualquer um  <br/> |Consulta DNS sobre UDP  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Endereço IP do serviço de borda do servidor de borda A/V  <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Endereço IP público do serviço de borda do servidor de borda A/V  <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Endereço IP público do serviço de borda do servidor de borda A/V  <br/> |Qualquer um  <br/> |Saída 3478 é:  <br/> • Usado pelo Skype for Business Server para determinar a versão do servidor de borda com a qual está se comunicando.  <br/> • Usado para tráfego de mídia entre servidores de borda.  <br/> • Necessário para a Federação.  <br/> • Necessário se vários pools de bordas forem implantados em sua organização.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um  <br/> |Endereço IP público do serviço de borda do servidor de borda A/V  <br/> |Negociação de candidatos STUN/TURN sob UDP na porta 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um  <br/> |Endereço IP público do serviço de borda do servidor de borda A/V  <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Endereço IP público do serviço de borda do servidor de borda A/V  <br/> |Qualquer um  <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabela de resumo do firewall da porta interna

|**Protocolo**|**TCP ou UDP**|**Porta**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-end executando o serviço de Gateway XMPP  <br/> |Interface interna do servidor de borda  <br/> |Tráfego de XMPP de saída do seu serviço de gateway do XMPP em execução em seu servidor front-end ou pool de front-ends.  <br/><br/> **Observação:** Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [migrando a Federação do XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualquer um:  <br/> • Servidor front-end que mantém o repositório central de gerenciamento  <br/> • Pool de front-end que mantém o repositório central de gerenciamento  <br/> |Interface interna do servidor de borda  <br/> |Replicação de alterações do repositório de gerenciamento central para o servidor de borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada servidor front-end em seu pool Front-end  <br/> |Interface interna do servidor de borda  <br/> |O tráfego de webconferências do seu servidor front-end ou de cada servidor front-end (se você tiver um pool de front-end) para a interface interna do servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada servidor front-end em seu pool Front-end  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de ramificação sobreviventes ou servidor de filial transferível.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada servidor front-end no pool  <br/> |Interface interna do servidor de borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de ramificação sobreviventes ou servidor de filial transferível, se a comunicação UDP não funcionar. Neste caso, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Controle centralizado do serviço de registro em log usando o Shell de gerenciamento do Skype for Business Server e cmdlets do serviço de registro centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Controle centralizado do serviço de registro em log usando o Shell de gerenciamento do Skype for Business Server e cmdlets do serviço de registro centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Controle centralizado do serviço de registro em log usando o Shell de gerenciamento do Skype for Business Server e cmdlets do serviço de registro centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e a coleção de logs.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IPs virtuais da interface externa

|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Não compatível com o Skype for businesss Server 2019 |TCP  <br/> |5269  <br/> |Qualquer um  <br/> |Serviço de proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso)  <br/> |O serviço de proxy XMPP aceita o tráfego dos contatos do XMPP em agrupamentos XMPP definidos.  <br/> |
|XMPP  <br/>Não compatível com o Skype for businesss Server 2019 |TCP  <br/> |5269  <br/> |Serviço de proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso)  <br/> |Qualquer um  <br/> |O serviço de proxy XMPP envia o tráfego de contatos do XMPP em agrupamentos XMPP definidos.  <br/> |
|Acesso/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Tráfego SIP do cliente ao servidor para o acesso do usuário externo.  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer um  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda do acesso ao servidor de borda <br/> |Qualquer um  <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Webconferência/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |**IP privado usando NAT:** Serviço de borda de Webconferência Web Edge Server <br/> **IP público:** Endereço IP público do serviço de borda de Webconferência do Edge Server Web <br/> |Mídia de Webconferência.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um  <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Negociação de candidatos STUN/TURN sob UDP na porta 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |**IP privado usando NAT:** Serviço Edge Server A/V Edge <br/> **IP público:** Endereço IP público do serviço de borda do servidor de borda A/V <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IPs virtuais da interface interna

Nossa orientação aqui será um pouco diferente. Na realidade, em uma situação HLB, recomendamos que você tenha apenas roteamento por meio de um VIP interno sob as seguintes circunstâncias:
  
- Se você estiver usando o Exchange 2007 ou o Exchange 2010 Unified Messaging (UM).
    
- Se você tiver clientes herdados usando a Borda.
    
A tabela a seguir dá orientação a esses cenários, mas, caso contrário, você deve ser capaz de depender do CMS (repositório de gerenciamento central) para direcionar o tráfego para o servidor de borda individual com o qual está ciente (isso exige que o CMS seja mantido atualizado no servidor de borda informações, é claro).
  
|**Protocolo**|**TCP ou UDP**|**Porta**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Endereço VIP do pool diretor  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-end  <br/> |Interface interna do servidor de borda  <br/> |Tráfego SIP de saída do seu diretor, endereço VIP do pool do diretor, servidor front-end ou endereço VIP do pool de front-end para a interface interna do servidor de borda.  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface VIP interna do servidor de borda  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Endereço VIP do pool diretor  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-end  <br/> |Tráfego SIP de entrada para seu diretor, endereço VIP do pool do diretor, servidor front-end ou endereço VIP do pool de front-end da interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualquer um:  <br/> • Endereço IP do servidor front-end  <br/> • Endereço IP do pool de front-end  <br/> • Qualquer aparelho de ramificação sobreviventes que use este servidor de borda  <br/> • Qualquer servidor de ramificação sobreviventes que use este servidor de borda  <br/> |Interface interna do servidor de borda  <br/> |Autenticação de usuários de A/V do seu servidor front-end ou pool de front-end, ou seu aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes, usando seu servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferencial para transferência de mídia A/V entre usuários internos e externos  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um   <br/> |Interface VIP interna do servidor de borda  <br/> |Caminho de fallback para transferência de mídia A/V entre usuários internos e externos se a comunicação UDP não for estabelecida, TCP é usado para transferência de arquivos e compartilhamento da área de trabalho  <br/> |
