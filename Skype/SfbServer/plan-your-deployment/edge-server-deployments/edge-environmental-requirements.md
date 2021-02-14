---
title: Requisitos ambientais do Servidor de Borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Resumo: saiba mais sobre os requisitos ambientais para o Servidor de Borda no Skype for Business Server.'
ms.openlocfilehash: 3757a67d36260cce7d14ddf451a3a436429f24fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813831"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisitos ambientais do Servidor de Borda no Skype for Business Server
 
**Resumo:** Saiba mais sobre os requisitos ambientais para o Servidor de Borda no Skype for Business Server.
  
É necessário ter muito planejamento e preparação fora do próprio ambiente do Skype for Business Server Edge Server. Neste artigo, revisaremos quais preparações precisam ser feitas no ambiente organizacional, de acordo com nossa lista abaixo:
  
- [Planejamento de topologia](edge-environmental-requirements.md#TopoPlan)
    
- [Planejamento de DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Planejamento de certificados](edge-environmental-requirements.md#CertPlan)
    
- [Planejamento de porta e firewall](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planejamento de topologia
<a name="TopoPlan"> </a>

As topologias do Skype for Business Server Edge Server podem usar:
  
- Endereços IP públicos que são reenveláveis.
    
- Endereços IP privados não-rouáveis, **se** NAT (conversão de endereços de rede simétrica) for usado.
    
> [!TIP]
> Seu Servidor de Borda pode ser configurado para usar um único endereço IP com portas distintas para cada serviço ou pode usar endereços IP distintos para cada serviço, mas usar a mesma porta padrão (que, por padrão, será TCP 443). Temos mais informações na seção requisitos de endereço IP, abaixo. 
  
Se você escolher endereços IP privados não-rouáveis com NAT, lembre-se destes pontos:
  
- Você precisa usar endereços IP privados que podem ser **reenveláveis em todas as três** interfaces externas.
    
- Você precisa configurar NAT **simétrico** para tráfego de entrada e saída. NAT simétrico é o único NAT com suporte que você pode usar com o Servidor de Borda do Skype for Business Server.
    
- Configure seu NAT para não alterar os endereços de origem de entrada. O serviço de Borda A/V precisa ser capaz de receber o endereço de origem de entrada para encontrar o caminho de mídia ideal.
    
- Seus Servidores de Borda precisam ser capazes de se comunicar entre si a partir de seus endereços IP de Borda A/V públicos. O firewall precisa permitir esse tráfego.
    
- NAT só **pode** ser usado para Servidores de Borda consolidados em escala se você usar o balanceamento de carga DNS. Se você usar o HLB (balanceamento de carga de hardware), precisará usar endereços IP publicamente rouáveis **sem** NAT.
    
Você não terá problemas em ter suas interfaces de Acesso, Webconferência e Borda A/V atrás de um roteador ou firewall executando NAT simétrico para topologias de Servidor de Borda consolidada única e dimensionada (desde que você não esteja usando balanceamento de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumo das opções de topologia do Servidor de Borda

Temos várias opções de topologia disponíveis para implantações do Skype for Business Server Edge Server:
  
- Borda consolidada única com endereços IP privados e NAT
    
- Borda consolidada única com endereços IP públicos
    
- Borda consolidada em escala com endereços IP privados e NAT
    
- Borda consolidada em escala com endereços IP públicos
    
- Borda consolidada em escala com balanceadores de carga de hardware
    
Para ajudá-lo a escolher uma, temos a tabela a seguir, que fornece um resumo das opções que você tem para cada topologia:
  
|**Topologia**|**Alta disponibilidade**|**Registros DNS adicionais necessários para o Servidor de Borda externo no pool de Borda?**|**Failover de borda para sessões do Skype for Business Server**|**Failover de borda para sessões de federação do Skype for Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Borda consolidada única com endereços IP privados e NAT  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Borda consolidada única com endereços IP públicos  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Borda consolidada em escala com endereços IP privados e NAT (carga DNS balanceada)  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim&sup1;  <br/> |
|Borda consolidada em escala com endereços IP públicos (carga DNS balanceada)  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim&sup1;  <br/> |
|Borda consolidada em escala com balanceadores de carga de hardware  <br/> |Sim  <br/> |Não (um registro DNS A por VIP)  <br/> |Sim  <br/> |Sim  <br/> |
   
&sup1; O failover do usuário remoto da Unificação de Mensagens (UM) do Exchange usando o balanceamento de carga DNS requer o Exchange 2013 ou mais novo.
  
### <a name="ip-address-requirements"></a>Requisitos de endereço IP

Em um nível fundamental, três serviços precisam de endereços IP; Serviço de Borda de Acesso, Serviço de Borda de Webconferência e Serviço de Borda A/V. Você tem a opção de usar três endereços IP, um para cada um dos serviços, ou pode usar um e optar por colocar cada serviço em uma porta diferente (você pode conferir a seção de planejamento de porta e [firewall](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações sobre alguns desses serviços). Para um único ambiente de Borda consolidado, é basicamente isso.
  
> [!NOTE]
> Conforme mencionado acima, você pode optar por ter um endereço IP para todos os três serviços e executar em portas diferentes. Mas para ser claro, não recomendamos isso. Se os clientes não puderem acessar as portas alternativas que você estaria usando nesse cenário, eles também não poderão acessar a funcionalidade completa do seu ambiente de Borda. 
  
Pode ser um pouco mais complicado com topologias consolidadas dimensionadas, portanto, vamos ver algumas tabelas que estabelecem os requisitos de Endereço IP, tendo em mente que os principais pontos de decisão para seleção de topologia são alta disponibilidade e balanceamento de carga. As necessidades de alta disponibilidade podem influenciar sua escolha de balanceamento de carga (vamos falar mais sobre isso após as tabelas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de endereço IP para Borda consolidada em escala (Endereço IP por função)

|**Número de Servidores de Borda por pool**|**Número de endereços IP necessários para balanceamento de carga DNS**|**Número de endereços IP necessários para balanceamento de carga de hardware**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 por VIP) + 6  <br/> |
|3   <br/> |9   <br/> |3 (1 por VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 por VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 por VIP) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de endereço IP para borda consolidada em escala (endereço IP único para todas as funções)

|**Número de Servidores de Borda por pool**|**Número de endereços IP necessários para balanceamento de carga DNS**|**Número de endereços IP necessários para balanceamento de carga de hardware**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 por VIP) + 2  <br/> |
|3   <br/> |3   <br/> |1 (1 por VIP) + 3  <br/> |
|4   <br/> |4   <br/> |1 (1 por VIP) + 4  <br/> |
|5   <br/> |5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Vamos ver algumas coisas adicionais a pensar durante o planejamento.
  
- **Alta disponibilidade:** se você precisar de alta disponibilidade em sua implantação, deverá implantar pelo menos dois Servidores de Borda em um pool. Vale a pena notar que um único pool de Borda dará suporte a até 12 Servidores de Borda (embora o Construtor de Topologias permita que você adicione até 20, o que não é testado ou suportado, portanto, aconselhamos que você não faça isso). Se você precisar de mais de 12 Servidores de Borda, crie pools de Borda adicionais para eles.
    
- **Balanceamento de carga de** hardware: recomendamos o balanceamento de carga DNS para a maioria dos cenários. O balanceamento de carga de hardware também é suportado, é claro, mas, principalmente, é necessário para um único cenário sobre balanceamento de carga DNS:
    
  - Acesso externo à Unificação de Mensagens (UM) do Exchange 2007 ou do Exchange 2010 (sem SP).
    
- **Balanceamento de carga DNS:** para UM, o Exchange 2010 SP1 e mais novo podem ser suportados pelo balanceamento de carga DNS. Observe que, se você precisar ir com o balanceamento de carga DNS para uma versão anterior do Exchange, ele funcionará, mas todo o tráfego para isso irá para o primeiro servidor no pool e, se não estiver disponível, esse tráfego falhará subsequentemente.
    
    O balanceamento de carga DNS também é recomendado se você estiver federando com empresas que usam:
- Skype for Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 ou Office 365
- Skype for Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft 365 ou Office 365
    
## <a name="dns-planning"></a>Planejamento de DNS
<a name="DNSPlan"> </a>

Quando se trata de implantação do Skype for Business Server Edge Server, é essencial se preparar para o DNS corretamente. Com os registros corretos no local, a implantação será muito mais simples. Esperamos que você tenha escolhido uma topologia na seção acima, pois vamos fazer uma visão geral e listar algumas tabelas que destacam os registros DNS para esses cenários. Também temos um planejamento avançado de DNS do Servidor de Borda [para o Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para uma leitura mais detalhada, se necessário.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros DNS para cenários de Servidor de Borda consolidado único

Esses serão os registros DNS necessários para um Servidor de Borda com IPs públicos ou privados com NAT. Como são dados de exemplo, vamos dar exemplos de IPs para que você possa trabalhar com suas próprias entradas com mais facilidade:
  
- Adaptador de rede interna: 172.25.33.10 (sem gateways padrão atribuídos)
    
    > [!NOTE]
    > Verifique se há uma rota da rede que contém a interface interna de Borda para qualquer rede que contenha servidores executando clientes do Skype for Business Server ou do Lync Server 2013 (por exemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - IPs públicos:
    
  - Borda de Acesso: 131.107.155.10 (este é o principal, com gateway padrão definido para seu roteador público, por ex: 131.107.155.1)
    
  - Borda de Webconferência: 131.107.155.20 (secundário)
    
  - Borda A/V: 131.107.155.30 (secundária)
    
  Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Protocolo Internet Versão 4 (TCP/IPv4) e internet protocol versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - IPs privados:
    
  - Borda de Acesso: 10.45.16.10 (esta é a principal, com o gateway padrão definido para seu roteador, por ex: 10.45.16.1)
    
  - Borda de Webconferência: 10.45.16.20 (secundário)
    
  - Borda A/V: 10.45.16.30 (secundária)
    
Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Protocolo Internet Versão 4 (TCP/IPv4) e internet protocol versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
  
> [!TIP]
>Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externo. Não recomendamos isso porque, em seguida, você precisará diferenciar entre os serviços que você usa portas diferentes (o que você pode fazer no Skype for Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a [seção Planejamento de porta e firewall](edge-environmental-requirements.md#PortFirewallPlan) para saber mais sobre isso.
    
- Você pode ter três adaptadores de rede externos em vez de um e atribuir um dos IPs de serviço a cada um deles. Por que fazer isso? Isso separaria os serviços e, se algo der errado, isso facilitaria a solução de problemas e poderia permitir que seus outros serviços continuasse funcionando enquanto você resolvesse um problema.
    
|**Location**|**Tipo**|**Port**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |Uma interface externa para seu serviço de Borda de Acesso. Você precisará de um para cada domínio SIP com usuários do Skype for Business.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 <br/> **private:** 10.45.16.20 <br/> |Uma interface externa para seu serviço de Borda de Webconferência.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 <br/> **private:** 10.45.16.30 <br/> |Uma interface externa para seu serviço de Borda A/V.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de Borda de Acesso. Esse registro SRV é necessário para que os clientes do Skype for Business Server, do Lync Server 2013 e do Lync Server 2010 funcionem externamente. Você precisará de um para cada domínio com usuários do Skype for Business.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de Borda de Acesso. Esse registro SRV é necessário para descoberta de DNS automática de parceiros federados chamados domínios SIP permitidos. Você precisará de um para cada domínio com usuários do Skype for Business.  <br/> |
|DNS Interno  <br/> |Um registro  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |A interface interna da Borda consolidada.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros DNS para cenários de DNS em escala e servidor de borda de hardware

Esses serão os registros DNS necessários para um Servidor de Borda com IPs públicos ou privados com NAT. Como são dados de exemplo, vamos dar exemplos de IPs para que você possa trabalhar com suas próprias entradas com mais facilidade:
  
- Adaptador de rede interno:
    
  - Nó 1: 172.25.33.10 (nenhum gateway padrão atribuído)
    
  - Nó 2: 172.25.33.11 (nenhum gateway padrão atribuído)
    
    > [!NOTE]
    > Verifique se há uma rota da rede que contém a interface interna de Borda para qualquer rede que contenha servidores executando clientes do Skype for Business Server ou do Lync Server 2013 (por exemplo, de 172.25.33.0 a 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - Nó 1
    
     - IPs públicos:
    
        - Borda de Acesso: 131.107.155.10 (este é o principal, com gateway padrão definido para seu roteador público, por ex: 131.107.155.1)
    
        - Borda de Webconferência: 131.107.155.20 (secundário)
    
        - Borda A/V: 131.107.155.30 (secundária)
    
          Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Protocolo Internet Versão 4 (TCP/IPv4) e internet protocol versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
    - IPs privados:
    
         - Borda de Acesso: 10.45.16.10 (esta é a principal, com o gateway padrão definido para seu roteador, por ex: 10.45.16.1)
    
         - Borda de Webconferência: 10.45.16.20 (secundário)
    
         - Borda A/V: 10.45.16.30 (secundária)
    
      Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Protocolo Internet Versão 4 (TCP/IPv4) e internet protocol versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - Nó 2
    
    - IPs públicos:
    
      - Borda de Acesso: 131.107.155.11 (este é o principal, com gateway padrão definido para seu roteador público, por ex: 131.107.155.1)
    
      - Borda de Webconferência: 131.107.155.21 (secundário)
    
      - Borda A/V: 131.107.155.31 (secundária)
    
      Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Protocolo Internet Versão 4 (TCP/IPv4) e internet protocol versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - IPs privados:
    
    - Borda de Acesso: 10.45.16.11 (esta é a principal, com o gateway padrão definido para seu roteador, por ex: 10.45.16.1)
    
    - Borda de Webconferência: 10.45.16.21 (secundário)
    
    - Borda A/V: 10.45.16.31 (secundária)
    
      Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Protocolo Internet Versão 4 (TCP/IPv4) e internet protocol versão 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externo. Não recomendamos isso porque, em seguida, você precisará diferenciar entre os serviços que você usa portas diferentes (o que você pode fazer no Skype for Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a [seção Planejamento de porta e firewall](edge-environmental-requirements.md#PortFirewallPlan) para saber mais sobre isso.
    
- Você pode ter três adaptadores de rede externos em vez de um e atribuir um dos IPs de serviço a cada um deles. Por que fazer isso? Isso separaria os serviços e, se algo der errado, isso facilitaria a solução de problemas e poderia permitir que seus outros serviços continuasse funcionando enquanto você resolvesse um problema.
    
|**Location**|**Tipo**|**Port**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 e 131.107.155.11 <br/> **private:** 10.45.16.10 e 10.45.16.11 <br/> |Uma interface externa para seu serviço de Borda de Acesso. Você precisará de um para cada domínio SIP com usuários do Skype for Business.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 e 131.107.155.21 <br/> **private:** 10.45.16.20 e 10.45.16.21 <br/> |Uma interface externa para seu serviço de Borda de Webconferência.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 e 131.107.155.31 <br/> **private:** 10.45.16.30 e 10.45.16.31 <br/> |Uma interface externa para seu serviço de Borda A/V.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de Borda de Acesso. Esse registro SRV é necessário para que os clientes do Skype for Business Server, do Lync Server 2013 e do Lync Server 2010 funcionem externamente. Você precisará de um para cada domínio com o Skype for Business.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de Borda de Acesso. Esse registro SRV é necessário para descoberta de DNS automática de parceiros federados chamados domínios SIP permitidos. Você precisará de um para cada domínio com o Skype for Business.  <br/> |
|DNS Interno  <br/> |Um registro  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 e 172.25.33.11  <br/> |A interface interna da Borda consolidada.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para federação (todos os cenários)

|**Location**|**Tipo**|**Port**|**FQDN**|**Registro de host FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |A interface externa da Borda de Acesso SIP necessária para descoberta de DNS automática. Usado por outros parceiros de federação em potencial. Também é conhecido como "Permitir domínios SIP". Você precisará de um desses para cada domínio SIP com usuários do Skype for Business.  <br/><br/> **Observação:** Você precisará desse registro SRV para mobilidade e o push notification clearing house. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Registros DNS para protocolo de presença e mensagens extensíveis

|**Location**|**Tipo**|**Port**|**FQDN**|**Endereço IP ou registro de host FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |A interface de proxy XMPP em seu serviço de Borda de Acesso ou pool de Borda. Você precisa repetir isso conforme necessário para todos os domínios SIP internos com usuários habilitados para Skype for Business Server, onde o contato com contatos XMPP é permitido através de:  <br/> • uma política global  <br/> • uma política de site em que o usuário está habilitado  <br/> • uma política de usuário aplicada ao usuário habilitado do Skype for Business Server  <br/> Uma política XMPP permitida também precisa ser configurada na política de usuários federados XMPP.  <br/> |
|DNS externo  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Endereço IP do serviço de Borda de Acesso no Servidor de Borda ou pool de Borda que hospeda seu serviço proxy XMPP  <br/> |Isso aponta para o serviço de Borda de Acesso no Servidor de Borda ou pool de Borda que hospeda o serviço proxy XMPP. Normalmente, o registro SRV que você criar apontará para esse registro de host (A ou AAAA).  <br/> |
   
> [!NOTE]
> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.

## <a name="certificate-planning"></a>Planejamento de certificado
<a name="CertPlan"> </a>

O Skype for Business Server usa certificados para comunicações seguras e criptografadas entre servidores e de servidor para cliente. Como você esperaria, seus certificados precisarão ter registros DNS para seus servidores que se a matchem com qualquer nome de assunto (SN) e nome alternativo da assunto (SAN) em seus certificados. Isso funcionará agora, no estágio de planejamento, para garantir que você tenha os FQDNs corretos registrados no DNS para as entradas SN e SAN para seus certificados.
  
Discutiremos as necessidades de certificados internos e externos separadamente e, em seguida, vamos ver uma tabela que fornece os requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados Externos

No mínimo, o certificado atribuído às interfaces externas do Servidor de Borda precisará ser fornecido por uma Autoridade de Certificação (CA) pública. Não é possível recomendar uma AC específica para você, mas [](/SkypeForBusiness/certification/services-ssl) temos uma lista de CAs, parceiros de certificado de Comunicações Unificadas que você pode dar uma olhada para ver se sua AC preferida está listada.
  
Quando você precisará enviar uma solicitação a uma AC para esse certificado público e como fazer isso? Há algumas maneiras de fazer isso:
  
- Você pode passar pela instalação do Skype for Business Server e, em seguida, pela implantação do Servidor de Borda. O Assistente de Implantação do Skype for Business Server terá uma etapa para gerar uma solicitação de certificado, que você pode enviar para a AC escolhida.
    
- Você também pode usar comandos do Windows PowerShell para gerar essa solicitação, se isso for mais em linha com suas necessidades de negócios ou estratégia de implantação.
    
- Por fim, sua AC pode ter seu próprio processo de envio, que também pode envolver o Windows PowerShell ou outro método. Nesse caso, você precisará contar com a documentação deles, além das informações fornecidas aqui para sua referência.
    
Depois de ter obtido o certificado, você precisará continuar e atribuí-lo a esses serviços no Skype for Business Server:
  
- Interface de serviço de Borda de Acesso
    
- Interface de serviço de Borda de Webconferência
    
- Serviço de Autenticação de Áudio/Vídeo (não confunda isso com o serviço de Borda A/V, pois isso não usa um certificado para criptografar fluxos de áudio e vídeo)
    
> [!IMPORTANT]
> Todos os Servidores de Borda (se pertencem ao mesmo pool de Servidores de Borda) precisam ter exatamente o mesmo certificado com a mesma chave privada para o serviço de Autenticação de Media Relay. 
  
### <a name="internal-certificates"></a>Certificados internos

Para a interface interna do Servidor de Borda, você pode usar um certificado público de uma CA pública ou um certificado emitido pela CA interna da sua organização. Lembre-se de que o certificado interno usa uma entrada SN e nenhuma entrada SAN, portanto, você não precisa se preocupar com SAN no certificado interno.
  
### <a name="required-certificates-table"></a>Tabela Certificados Necessários

Temos uma tabela aqui para ajudá-lo com suas solicitações. As entradas FQDN aqui são apenas para exemplos de domínios. Você precisará fazer solicitações com base em seus próprios domínios privados e públicos, mas aqui está um guia para o que nós fizemos:
  
- contoso <span></span> .com: FQDN público
    
- fabrikam .com: Segundo FQDN público (adicionado como uma demonstração do que solicitar se você tiver <span></span> vários domínios SIP)
    
- Contoso <span></span> .net: Domínio interno
    
#### <a name="edge-certificate-table"></a>Tabela de Certificados de Borda

Independentemente de você estar fazendo um único Servidor de Borda ou um pool de Borda, isso é o que você precisará para seu certificado:
  
|**Componente**|**Nome da entidade (SN)**|**Nomes alternativos de assunto (SAN)/ordem**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Borda Externa  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Esse é o certificado que você precisa solicitar de uma CA pública. Ele precisará ser atribuído às interfaces de Borda externas para o seguinte:  <br/> • Borda de Acesso  <br/> • Borda de Webconferência  <br/> • Autenticação de áudio/vídeo  <br/> <br/>A boa notícia é que os SANs são adicionados automaticamente à sua solicitação de certificado e, portanto, ao certificado depois de enviar a solicitação, com base no que você definiu para essa implantação no Construtor de Topologias. Você só precisará adicionar entradas SAN para quaisquer domínios SIP adicionais ou outras entradas que você precise suportar. Por que sip.contoso.com replicado nesta instância? Isso também acontece automaticamente, e é necessário que as coisas funcionem corretamente.  <br/><br/> **Observação:** Esse certificado também pode ser usado para conectividade de Mensagens Instantâneas Públicas. Você não precisa fazer nada diferente com ela, mas nas versões anteriores desta documentação, ela estava listada como uma tabela separada e agora não é mais. <br/> |
|Borda interna  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Você pode obter esse certificado de uma CA pública ou interna. Ele precisará conter o EKU do servidor (Uso De Chave Aprimorado), e você o atribuirá à interface de Borda interna.  <br/> |
   
Se você precisar de um certificado para XMPP (Extensible Messaging and Presence Protocol), ele será idêntico às entradas da tabela de Borda Externa acima, mas terá as duas entradas SAN adicionais a seguir:
  
- xmpp. <span></span> contoso <span></span> .com
    
- \*.contoso <span></span> .com
    
Lembre-se de que atualmente o XMPP só tem suporte no Skype for Business Server para Google Talk, se você quiser ou precisar usá-lo para qualquer outra coisa, é necessário confirmar essa funcionalidade com o fornecedor terceirizado envolvido.
  
## <a name="port-and-firewall-planning"></a>Planejamento de porta e firewall
<a name="PortFirewallPlan"> </a>

Fazer com que seu planejamento seja correto para portas e firewalls para implantações do Servidor de Borda do Skype for Business Server pode poupar dias ou semanas de solução de problemas e estresse. Como resultado, vamos listar algumas tabelas que indicarão o uso do protocolo e quais portas você precisa abrir, de entrada e de saída, tanto para cenários NAT quanto para cenários de IP público. Também temos tabelas separadas para cenários de carga balanceada de hardware (HLB) e outras orientações sobre isso. Para obter mais leituras a partir daí, também temos alguns [cenários](scenarios.md) de Servidor de Borda no Skype for Business Server que você pode verificar para suas preocupações específicas de implantação.
  
### <a name="general-protocol-usage"></a>Uso geral do protocolo

Antes de analisarmos as tabelas de resumo para firewalls internos e externos, considere também a tabela a seguir:
  
|**Transporte de áudio/vídeo**|**Uso**|
|:-----|:-----|
|UDP  <br/> |O protocolo de camada de transporte preferencial para áudio e vídeo.  <br/> |
|TCP  <br/> |O protocolo de camada de transporte de fallback para áudio e vídeo.  <br/> O protocolo de camada de transporte necessário para o compartilhamento de aplicativos com o Skype for Business Server, o Lync Server 2013 e o Lync Server 2010.  <br/> O protocolo de camada de transporte necessário para transferência de arquivos para o Skype for Business Server, o Lync Server 2013 e o Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabela de resumo do firewall de porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para usuários que estão usando endereços IP privados com NAT, bem como pessoas que usam endereços IP públicos. Isso abrange todas as permutações em nossos cenários de Servidor de Borda [na seção Skype for Business Server.](scenarios.md)
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Sem suporte no Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Qualquer  <br/> |Serviço proxy XMPP (compartilha um endereço IP com o serviço de Borda de Acesso  <br/> |O serviço de Proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Qualquer  <br/> |Revogação de certificado e verificação e recuperação de CRL.  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Qualquer  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acesso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Qualquer  <br/> |Consulta DNS sobre UDP.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Tráfego SIP de cliente para servidor para acesso de usuário externo.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Para conectividade de IM pública e federada usando SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Qualquer  <br/> |Para conectividade de IM pública e federada usando SIP.  <br/> |
|Webconferência/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda de Webconferência do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Webconferência do Servidor de Borda <br/> |Mídia de webconferência.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Qualquer  <br/> |Isso é usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Qualquer  <br/> |Isso é usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Qualquer  <br/> |A saída 3478 é:  <br/> • Usado pelo Skype for Business Server para determinar a versão do Servidor de Borda com a qual está se comunicando.  <br/> • Usado para tráfego de mídia entre Servidores de Borda.  <br/> • Necessário para federação com o Lync Server 2010.  <br/> • Necessário se vários pools de Borda são implantados em sua organização.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Negociação STUN/TURN de candidatos sobre UDP na porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Negociação STUN/TURN de candidatos sobre TCP na porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Qualquer  <br/> |Negociação STUN/TURN de candidatos sobre TCP na porta 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabela de resumo do firewall de porta interna

|**Protocolo**|**TCP ou UDP**|**Port**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor front-end  <br/> • Pool de front-end  <br/> |Interface interna do Servidor de Borda  <br/> |Tráfego XMPP de saída do serviço gateway XMPP em execução no servidor front-end ou pool de front-end.  <br/> **Observação:** Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Pool de Diretores  <br/> • Servidor front-end  <br/> • Pool de front-end  <br/> |Interface interna do Servidor de Borda  <br/> |Tráfego SIP de saída do diretor, pool de diretores, servidor front-end ou pool de front-end para sua interface interna do Servidor de Borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interna do Servidor de Borda  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Pool de Diretores  <br/> • Servidor front-end  <br/> • Pool de front-end  <br/> |Tráfego SIP de entrada para o Diretor, pool de Diretores, Servidor front-end ou pool de front-end da interface interna do Servidor de Borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada servidor front-end  <br/>  em seu pool de Front-End <br/> |Interface interna do Servidor de Borda  <br/> |Tráfego de webconferência do servidor front-end ou de cada servidor front-end (se você tiver um pool de front-end) para sua interface interna do Servidor de Borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Pool de front-end  <br/> • Qualquer Aparelho de FilialVivível usando este Servidor de Borda  <br/> • Qualquer Servidor de Filial Survivível usando este Servidor de Borda  <br/> |Interface interna do Servidor de Borda  <br/> |Autenticação de usuários de A/V de seu Servidor Front-End ou pool de Front-End, ou seu Aparelho de Filial Survivível ou Servidor de FilialVivível, usando seu Servidor de Borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos e seu Aparelho de FilialVivível ou Servidor de FilialVivível.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos e seu Aparelho de Filial Survivível ou Servidor de FilialVivível, se a comunicação UDP não funcionar. O TCP é usado para transferências de arquivos e compartilhamento de área de trabalho.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualquer um:  <br/> • Servidor front-end que mantém o armazenamento de Gerenciamento Central  <br/> • Pool de front-end que mantém o armazenamento de Gerenciamento Central  <br/> |Interface interna do Servidor de Borda  <br/> |Replicação de alterações do seu armazenamento de Gerenciamento Central para o Servidor de Borda.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Controlador do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server e cmdlets do Serviço de Log Centralizado, comandos de linha de comando (ClsController.exe) ou agente (ClsAgent.exe) e conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Controlador do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server e cmdlets do Serviço de Log Centralizado, comandos de linha de comando (ClsController.exe) ou agente (ClsAgent.exe) e conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Controlador do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server e cmdlets do Serviço de Log Centralizado, comandos de linha de comando (ClsController.exe) ou agente (ClsAgent.exe) e conjunto de log.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Balanceadores de carga de hardware para tabelas de porta de Borda

Estamos dando aos balanceadores de carga de hardware (HLBs) e portas de Borda sua própria seção, pois as coisas são um pouco mais complicadas com o hardware adicional. Consulte as tabelas abaixo para obter orientação para este cenário específico:
  
#### <a name="external-port-firewall-summary-table"></a>Tabela de resumo do firewall de porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para usuários que estão usando endereços IP privados com NAT, bem como pessoas que usam endereços IP públicos. Isso abrange todas as permutações em nossos cenários de Servidor de Borda [na seção Skype for Business Server.](scenarios.md)
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda  <br/> |Qualquer  <br/> |Revogação de certificado e verificação e recuperação de CRL.  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda  <br/> |Qualquer  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acesso/DNS  <br/> |UDP  <br/> |53  <br/> |Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda  <br/> |Qualquer  <br/> |Consulta DNS sobre UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Endereço IP do serviço de Borda A/V do Servidor de Borda  <br/> |Qualquer  <br/> |Isso é usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Endereço IP público do serviço de Borda A/V do Servidor de Borda  <br/> |Qualquer  <br/> |Isso é usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Endereço IP público do serviço de Borda A/V do Servidor de Borda  <br/> |Qualquer  <br/> |A saída 3478 é:  <br/> • Usado pelo Skype for Business Server para determinar a versão do Servidor de Borda com a qual está se comunicando.  <br/> • Usado para tráfego de mídia entre Servidores de Borda.  <br/> • Necessário para federação.  <br/> • Necessário se vários pools de Borda são implantados em sua organização.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |Endereço IP público do serviço de Borda A/V do Servidor de Borda  <br/> |Negociação STUN/TURN de candidatos sobre UDP na porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |Endereço IP público do serviço de Borda A/V do Servidor de Borda  <br/> |Negociação STUN/TURN de candidatos sobre TCP na porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Endereço IP público do serviço de Borda A/V do Servidor de Borda  <br/> |Qualquer  <br/> |Negociação STUN/TURN de candidatos sobre TCP na porta 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabela de resumo do firewall de porta interna

|**Protocolo**|**TCP ou UDP**|**Port**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de Front End executando o serviço gateway XMPP  <br/> |Interface interna do Servidor de Borda  <br/> |Tráfego XMPP de saída do serviço gateway XMPP em execução no servidor front-end ou pool de front-end.  <br/><br/> **Observação:** Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualquer um:  <br/> • Servidor front-end que mantém o armazenamento de Gerenciamento Central  <br/> • Pool de front-end que mantém o armazenamento de Gerenciamento Central  <br/> |Interface interna do Servidor de Borda  <br/> |Replicação de alterações do seu armazenamento de Gerenciamento Central para o Servidor de Borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada Servidor front-end em seu pool de front-end  <br/> |Interface interna do Servidor de Borda  <br/> |Tráfego de webconferência do servidor front-end ou de cada servidor front-end (se você tiver um pool de front-end) para sua interface interna do Servidor de Borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada Servidor front-end em seu pool de front-end  <br/> |Interface interna do Servidor de Borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos e seu Aparelho de FilialVivível ou Servidor de FilialVivível.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um:  <br/> • Servidor front-end  <br/> • Cada Servidor front-end em seu pool  <br/> |Interface interna do Servidor de Borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos e seu Aparelho de Filial Survivível ou Servidor de FilialVivível, se a comunicação UDP não funcionar. O TCP é usado para transferências de arquivos e compartilhamento de área de trabalho.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Controlador do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server e cmdlets do Serviço de Log Centralizado, comandos de linha de comando (ClsController.exe) ou agente (ClsAgent.exe) e conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Controlador do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server e cmdlets do Serviço de Log Centralizado, comandos de linha de comando (ClsController.exe) ou agente (ClsAgent.exe) e conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Controlador do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server e cmdlets do Serviço de Log Centralizado, comandos de linha de comando (ClsController.exe) ou agente (ClsAgent.exe) e conjunto de log.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IPs Virtuais da interface externa

|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Sem suporte no Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Qualquer  <br/> |Serviço proxy XMPP (compartilha um endereço IP com o serviço de Borda de Acesso)  <br/> |O serviço de Proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas.  <br/> |
|XMPP  <br/>Sem suporte no Skype for Businesss Server 2019 |TCP  <br/> |5269  <br/> |Serviço proxy XMPP (compartilha um endereço IP com o serviço de Borda de Acesso)  <br/> |Qualquer  <br/> |O serviço de Proxy XMPP envia tráfego de contatos XMPP em federações XMPP definidas.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Tráfego SIP de cliente para servidor para acesso de usuário externo.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Para conectividade de IM pública e federada usando SIP.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privado usando NAT:** Serviço de Borda de Acesso do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Acesso do Servidor de Borda de Borda <br/> |Qualquer  <br/> |Para conectividade de IM pública e federada usando SIP.  <br/> |
|Webconferência/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda de Webconferência do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda de Webconferência do Servidor de Borda <br/> |Mídia de webconferência.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Negociação STUN/TURN de candidatos sobre UDP na porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privado usando NAT:** Serviço de Borda A/V do Servidor de Borda <br/> **IP público:** Endereço IP público do serviço de Borda A/V do Servidor de Borda <br/> |Negociação STUN/TURN de candidatos sobre TCP na porta 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IPs virtuais da interface interna

Nossa orientação aqui será um pouco diferente. Na verdade, em uma situação de HLB, recomendamos que você só tenha roteamento por meio de um VIP interno nas seguintes circunstâncias:
  
- Se você estiver usando a Unificação de Mensagens (UM) do Exchange 2007 ou do Exchange 2010.
    
- Se você tiver clientes herdado usando o Edge.
    
A tabela a seguir orienta esses cenários, mas caso contrário, você poderá depender do CMS (Armazenamento de Gerenciamento Central) para rotear o tráfego para o Servidor de Borda individual que ele reconhece (isso exige que o CMS seja mantido atualizado nas informações do Servidor de Borda, é claro).
  
|**Protocolo**|**TCP ou UDP**|**Port**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Endereço VIP do pool de Diretores  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-end  <br/> |Interface interna do Servidor de Borda  <br/> |Tráfego SIP de saída do Diretor, endereço VIP do pool de Diretores, Servidor Front End ou endereço VIP do pool de Front-End para sua interface interna do Servidor de Borda.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface VIP interna do Servidor de Borda  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Endereço VIP do pool de Diretores  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-end  <br/> |Tráfego SIP de entrada para o Diretor, endereço VIP do pool de Diretores, Servidor Front-End ou endereço VIP do pool de Front-End da interface interna do Servidor de Borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualquer um:  <br/> • Endereço IP do Servidor Front End  <br/> • Endereço IP do pool de front-end  <br/> • Qualquer Aparelho de FilialVivível usando este Servidor de Borda  <br/> • Qualquer Servidor de Filial Survivível usando este Servidor de Borda  <br/> |Interface interna do Servidor de Borda  <br/> |Autenticação de usuários de A/V de seu Servidor Front-End ou pool de Front-End, ou seu Aparelho de Filial Survivível ou Servidor de FilialVivível, usando seu Servidor de Borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |Interface interna do Servidor de Borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |Interface VIP interna do Servidor de Borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos se a comunicação UDP não funcionar. O TCP é usado para transferências de arquivos e compartilhamento de área de trabalho.  <br/> |
