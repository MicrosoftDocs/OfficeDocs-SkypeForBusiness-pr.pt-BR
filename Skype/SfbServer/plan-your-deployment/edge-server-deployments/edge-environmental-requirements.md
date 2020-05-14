---
title: Requisitos de ambiente do servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: Saiba mais sobre os requisitos de ambiente do servidor de borda no Skype for Business Server.'
ms.openlocfilehash: 8e2ec6d2afc53648fe50af4cd5ab02ad21d11643
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219921"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisitos de ambiente do servidor de borda no Skype for Business Server
 
**Resumo:** Saiba mais sobre os requisitos de ambiente do servidor de borda no Skype for Business Server.
  
Uma grande quantidade de planejamento e preparação precisa ocorrer fora do próprio ambiente de servidor de borda do Skype for Business Server. Neste artigo, vamos rever as preparações que precisam ser feitas no ambiente organizacional, de acordo com nossa lista abaixo:
  
- [Planejamento de topologia](edge-environmental-requirements.md#TopoPlan)
    
- [Planejamento de DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Planejamento de certificado](edge-environmental-requirements.md#CertPlan)
    
- [Planejamento de porta e firewall](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planejamento de topologia
<a name="TopoPlan"> </a>

As topologias do servidor de borda do Skype for Business Server podem usar:
  
- Endereços IP públicos roteáveis.
    
- Endereços IP privados não roteáveis, se a conversão de endereços de rede **simétrico** (NAT) for usada.
    
> [!TIP]
> O servidor de borda pode ser configurado para usar um único endereço IP com portas distintas para cada serviço ou pode usar endereços IP distintos para cada serviço, mas usar a mesma porta padrão (que por padrão será TCP 443). Temos mais informações na seção requisitos de endereço IP, abaixo. 
  
Se você escolher endereços IP privados não roteáveis com NAT, lembre-se destes pontos:
  
- Você precisa usar endereços IP privados roteáveis em **todas as três** interfaces externas.
    
- Você precisa configurar o NAT **simétrico** para tráfego de entrada e saída. O NAT simétrico é o único NAT com suporte que você pode usar com o servidor de borda do Skype for Business Server.
    
- Configure o NAT para não alterar os endereços de origem de entrada. O serviço de borda A/V precisa ser capaz de receber o endereço de origem de entrada para encontrar o caminho de mídia ideal.
    
- Os servidores de borda precisam ser capazes de se comunicar uns com os outros de seus endereços IP de borda de A/V públicos. O firewall precisa permitir esse tráfego.
    
- O NAT **só** poderá ser usado para servidores de borda consolidados em escala se você usar o balanceamento de carga DNS. Se você usar o balanceamento de carga de hardware (HLB), será necessário usar endereços IP roteáveis publicamente **sem** NAT.
    
Você não terá problemas com o acesso, Webconferência e interfaces de borda A/V por trás de um roteador ou firewall executando o NAT simétrico para topologias de servidor de borda consolidadas simples e em escala (desde que não esteja usando o balanceamento de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumo das opções de topologia do servidor de borda

Temos várias opções de topologia disponíveis para implantações do servidor de borda do Skype for Business Server:
  
- Única borda consolidada com endereços IP privados e NAT
    
- Única borda consolidada com endereços IP públicos
    
- Borda consolidada dimensionada com endereços IP privados e NAT
    
- Borda consolidada dimensionada com endereços IP públicos
    
- Borda consolidada em escala com balanceadores de carga de hardware
    
Para ajudá-lo a escolher uma, temos a tabela a seguir, que fornece um resumo das opções que você tem para cada topologia:
  
|**Topologia**|**Alta disponibilidade**|**Registros DNS adicionais necessários para o servidor de borda externo no pool de borda?**|**Failover de borda para sessões do Skype for Business Server**|**Failover de borda para sessões de Federação do Skype for Business Server**|
|:-----|:-----|:-----|:-----|:-----|
|Única borda consolidada com endereços IP privados e NAT  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Única borda consolidada com endereços IP públicos  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Borda consolidada em escala com endereços IP privados e NAT (balanceamento de carga DNS)  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim&SUP1;  <br/> |
|Borda consolidada em escala com endereços IP públicos (balanceamento de carga DNS)  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim&SUP1;  <br/> |
|Borda consolidada em escala com balanceadores de carga de hardware  <br/> |Sim  <br/> |Não (um registro DNS A por VIP)  <br/> |Sim  <br/> |Sim  <br/> |
   
&SUP1; O failover de usuário remoto da UM (Unificação de mensagens) do Exchange usando o balanceamento de carga DNS requer o Exchange 2013 ou mais recente.
  
### <a name="ip-address-requirements"></a>Requisitos de endereço IP

Em um nível fundamental, três serviços precisam de endereços IP; Serviço de borda de acesso, serviço de borda de Webconferência e serviço de borda A/V. Você tem a opção de usar três endereços IP, um para cada um dos serviços ou pode usar um e optar por colocar cada serviço em uma porta diferente (Confira a seção de [planejamento de porta e firewall](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações sobre alguns dos outros). Para um único ambiente de borda consolidado, isso é muito importante.
  
> [!NOTE]
> Conforme observado acima, você pode optar por ter um endereço IP para todos os três serviços e executá-los em diferentes portas. Mas, para ser claro, não recomendamos isso. Se os seus clientes não puderem acessar as portas alternativas que você usaria nesse cenário, eles não poderão acessar a funcionalidade completa do ambiente de borda. 
  
Pode ser um pouco mais complicado com topologias consolidadas em escala, então vamos ver algumas tabelas que formam os requisitos de endereço IP, tendo em mente que os principais pontos de decisão para a seleção de topologia são alta disponibilidade e balanceamento de carga. As necessidades de alta disponibilidade podem influenciar sua opção de balanceamento de carga (falaremos mais sobre isso depois das tabelas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de endereço IP para borda consolidada em escala (endereço IP por função)

|**Número de Servidores de Borda por pool**|**Número de endereços IP necessários para o balanceamento de carga DNS**|**Número de endereços IP necessários para o balanceamento de carga de hardware**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3 (1 por VIP) + 6  <br/> |
|3   <br/> |9   <br/> |3 (1 por VIP) + 9  <br/> |
|4   <br/> |12   <br/> |3 (1 por VIP) + 12  <br/> |
|5   <br/> |15   <br/> |3 (1 por VIP) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de endereço IP para borda consolidada de escala (endereço IP único para todas as funções)

|**Número de Servidores de Borda por pool**|**Número de endereços IP necessários para o balanceamento de carga DNS**|**Número de endereços IP necessários para o balanceamento de carga de hardware**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1 (1 por VIP) + 2  <br/> |
|3   <br/> |3   <br/> |1 (1 por VIP) + 3  <br/> |
|4   <br/> |4   <br/> |1 (1 por VIP) + 4  <br/> |
|5   <br/> |0,5  <br/> |1 (1 por VIP) + 5  <br/> |
   
Vamos ver algumas coisas adicionais a serem consideradas durante o planejamento.
  
- **Alta disponibilidade**: se você precisar de alta disponibilidade em sua implantação, você deve implantar pelo menos dois servidores de borda em um pool. É importante observar que um único pool de borda suportará até 12 servidores de borda (embora o construtor de topologia permita que você adicione até 20, que não é testado ou suportado, portanto, aconselhamos você não fazer isso). Se você precisar de mais de 12 servidores de borda, crie pools de borda adicionais para eles.
    
- **Balanceamento de carga de hardware**: Recomendamos o balanceamento de carga DNS para a maioria dos cenários. O balanceamento de carga de hardware também é suportado, obviamente, mas é necessário para um único cenário em relação ao balanceamento de carga DNS:
    
  - Acesso externo ao Exchange 2007 ou ao Exchange 2010 (sem SP) Unificação de mensagens (UM).
    
- **Balanceamento de carga DNS**: para um, o Exchange 2010 SP1 e versões mais recentes podem ser suportados pelo balanceamento de carga DNS. Observe que, se você precisar usar o balanceamento de carga DNS para uma versão anterior do Exchange, ele funcionará, mas todo o tráfego para isso vai para o primeiro servidor no pool e, se não estiver disponível, o tráfego falhará subseqüentemente.
    
    O balanceamento de carga DNS também é recomendado se você estiver se Federando com empresas que usam:
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

Quando se trata de implantação do servidor de borda do Skype for Business Server, é vital preparar o DNS corretamente. Com os registros corretos no local, a implantação será muito mais simples. Espero que você tenha escolhido uma topologia na seção acima, como faremos uma visão geral e, em seguida, liste algumas tabelas que descrevem os registros DNS desses cenários. Também teremos um planejamento de [DNS avançado de servidor de borda para o Skype for Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para uma leitura mais detalhada, se necessário.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros DNS para cenários de servidor de borda consolidado único

Eles serão os registros DNS que você precisará para um servidor de borda única usando IPs públicos ou IPs privados com NAT. Como estes são dados de exemplo, forneceremos um IPs de exemplo para que você possa trabalhar com suas próprias entradas com mais facilidade:
  
- Adaptador de rede interna: 172.25.33.10 (nenhum gateway padrão atribuído)
    
    > [!NOTE]
    > Verifique se há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores executando o Skype for Business Server ou clientes do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - IPs públicos:
    
  - Borda de acesso: 131.107.155.10 (este é o principal, com o gateway padrão definido para seu roteador público, ex: 131.107.155.1)
    
  - Borda de Webconferência: 131.107.155.20 (secundário)
    
  - Borda A/V: 131.107.155.30 (secundário)
    
  Webconferência e endereços IP públicos de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - IPs privados:
    
  - Borda de acesso: 10.45.16.10 (este é o principal, com o gateway padrão definido para seu roteador, ex: 10.45.16.1)
    
  - Borda de Webconferência: 10.45.16.20 (secundário)
    
  - Borda A/V: 10.45.16.30 (secundário)
    
Webconferência e endereços IP públicos de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
  
> [!TIP]
>Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externo. Não recomendamos isso, pois você precisará diferenciar entre os serviços do thee usando diferentes portas (que você pode fazer no Skype for Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a seção sobre [planejamento de porta e firewall](edge-environmental-requirements.md#PortFirewallPlan) para saber mais sobre isso.
    
- Você pode ter três adaptadores de rede externa em vez de um e atribuir um dos IPs de serviço a cada um. Por que isso? Ele separaria os serviços e se algo errar, isso facilitaria a solução de problemas e permitiria que seus outros serviços continuem funcionando enquanto você resolver um problema.
    
|**Localização**|**Tipo**|**Port**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 <br/> **particular:** 10.45.16.10 <br/> |Uma interface externa para o serviço de borda de acesso. Você precisará de um para cada domínio SIP com usuários do Skype for Business.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 <br/> **particular:** 10.45.16.20 <br/> |Uma interface externa para o serviço de borda de Webconferência.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 <br/> **particular:** 10.45.16.30 <br/> |Uma interface externa para o serviço de borda A/V.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Este registro SRV é necessário para que os clientes do Skype for Business Server, Lync Server 2013 e Lync Server 2010 funcionem externamente. Você precisará de um para cada domínio com usuários do Skype for Business.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Este registro SRV é necessário para a descoberta automática de DNS de parceiros federados chamados domínios SIP permitidos. Você precisará de um para cada domínio com usuários do Skype for Business.  <br/> |
|DNS Interno  <br/> |Um registro  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |A interface interna da sua borda consolidada.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros DNS para cenários de servidor de borda de hardware e DNS em escala

Eles serão os registros DNS que você precisará para um servidor de borda única usando IPs públicos ou IPs privados com NAT. Como estes são dados de exemplo, forneceremos um IPs de exemplo para que você possa trabalhar com suas próprias entradas com mais facilidade:
  
- Adaptador de rede interna:
    
  - Nó 1:172.25.33.10 (nenhum gateway padrão atribuído)
    
  - Nó 2:172.25.33.11 (nenhum gateway padrão atribuído)
    
    > [!NOTE]
    > Verifique se há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores executando o Skype for Business Server ou clientes do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - Nó 1
    
     - IPs públicos:
    
        - Borda de acesso: 131.107.155.10 (este é o principal, com o gateway padrão definido para seu roteador público, ex: 131.107.155.1)
    
        - Borda de Webconferência: 131.107.155.20 (secundário)
    
        - Borda A/V: 131.107.155.30 (secundário)
    
          Webconferência e endereços IP públicos de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
    - IPs privados:
    
         - Borda de acesso: 10.45.16.10 (este é o principal, com o gateway padrão definido para seu roteador, ex: 10.45.16.1)
    
         - Borda de Webconferência: 10.45.16.20 (secundário)
    
         - Borda A/V: 10.45.16.30 (secundário)
    
      Webconferência e endereços IP públicos de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - Nó 2
    
    - IPs públicos:
    
      - Borda de acesso: 131.107.155.11 (este é o principal, com o gateway padrão definido para seu roteador público, ex: 131.107.155.1)
    
      - Borda de Webconferência: 131.107.155.21 (secundário)
    
      - Borda A/V: 131.107.155.31 (secundário)
    
      Webconferência e endereços IP públicos de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
  - IPs privados:
    
    - Borda de acesso: 10.45.16.11 (este é o principal, com o gateway padrão definido para seu roteador, ex: 10.45.16.1)
    
    - Borda de Webconferência: 10.45.16.21 (secundário)
    
    - Borda A/V: 10.45.16.31 (secundário)
    
      Webconferência e endereços IP públicos de borda A/V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol version 6 (TCP/IPv6) das propriedades de conexão de área local no Windows Server.
    
Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externo. Não recomendamos isso, pois você precisará diferenciar entre os serviços do thee usando diferentes portas (que você pode fazer no Skype for Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a seção sobre [planejamento de porta e firewall](edge-environmental-requirements.md#PortFirewallPlan) para saber mais sobre isso.
    
- Você pode ter três adaptadores de rede externa em vez de um e atribuir um dos IPs de serviço a cada um. Por que isso? Ele separaria os serviços e se algo errar, isso facilitaria a solução de problemas e permitiria que seus outros serviços continuem funcionando enquanto você resolver um problema.
    
|**Localização**|**Tipo**|**Port**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 e 131.107.155.11 <br/> **particular:** 10.45.16.10 e 10.45.16.11 <br/> |Uma interface externa para o serviço de borda de acesso. Você precisará de um para cada domínio SIP com usuários do Skype for Business.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 e 131.107.155.21 <br/> **particular:** 10.45.16.20 e 10.45.16.21 <br/> |Uma interface externa para o serviço de borda de Webconferência.  <br/> |
|DNS externo  <br/> |Um registro  <br/> |NA  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 e 131.107.155.31 <br/> **particular:** 10.45.16.30 e 10.45.16.31 <br/> |Uma interface externa para o serviço de borda A/V.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip. _tls. contoso. com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Este registro SRV é necessário para que os clientes do Skype for Business Server, Lync Server 2013 e Lync Server 2010 funcionem externamente. Você precisará de um para cada domínio com o Skype for Business.  <br/> |
|DNS externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls. _tcp. contoso. com  <br/> |sip.contoso.com  <br/> |Uma interface externa para o serviço de borda de acesso. Este registro SRV é necessário para a descoberta automática de DNS de parceiros federados chamados domínios SIP permitidos. Você precisará de um para cada domínio com o Skype for Business.  <br/> |
|DNS Interno  <br/> |Um registro  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 e 172.25.33.11  <br/> |A interface interna da sua borda consolidada.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para Federação (todos os cenários)

|**Localização**|**Tipo**|**Port**|**FQDN**|**Registro de host FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp. contoso. com  <br/> |sip.contoso.com  <br/> |A interface externa de borda de acesso SIP necessária para descoberta de DNS automática. Usada por seus outros parceiros de Federação potenciais. Também é conhecido como "permitir domínios SIP." Você precisará de um deles para cada domínio SIP com usuários do Skype for Business.  <br/><br/> **Observação:** Você precisará desse registro SRV para mobilidade e a notificação por push da câmara de compensação. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Registros DNS para protocolo de presença e mensagens extensíveis

|**Localização**|**Tipo**|**Port**|**FQDN**|**Endereço IP ou registro de host FQDN**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-Server. _tcp. contoso. com  <br/> |xmpp.contoso.com  <br/> |A interface de proxy do XMPP no serviço de borda de acesso ou no pool de borda. Você precisa repetir isso conforme necessário para todos os domínios SIP internos com usuários habilitados para o Skype for Business Server, onde contato com contatos do XMPP é permitido por meio de:  <br/> • uma política global  <br/> • uma política de site onde o usuário habilitou  <br/> • uma política de usuário aplicada ao usuário habilitado para o Skype for Business Server  <br/> Uma política de XMPP permitida também precisa ser configurada na política de usuários federados do XMPP.  <br/> |
|DNS externo  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o serviço de proxy do XMPP  <br/> |Isso aponta para o serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o serviço de proxy do XMPP. Normalmente, o registro SRV que você cria apontará para este registro de host (A ou AAAA).  <br/> |
   
> [!NOTE]
> Os gateways e proxies do XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.

## <a name="certificate-planning"></a>Planejamento de certificado
<a name="CertPlan"> </a>

O Skype for Business Server usa certificados para comunicações seguras e criptografadas entre servidores e de servidor para cliente. Como você poderia esperar, seus certificados precisarão que os registros DNS de seus servidores correspondam a qualquer nome de entidade (SN) e ao nome alternativo de entidade (SAN) em seus certificados. Isso executará o trabalho agora, na fase de planejamento, para garantir que você tenha os FQDNs corretos registrados no DNS para as entradas SN e SAN dos seus certificados.
  
Discutiremos as necessidades de certificados externos e internos separadamente e, em seguida, examinaremos uma tabela que fornece os requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados externos

No mínimo, o certificado atribuído às suas interfaces de servidor de borda externas precisará ser fornecido por uma autoridade de certificação pública (AC). Não é possível recomendar uma autoridade de certificação específica, mas temos uma lista de [parceiros de certificados de comunicações unificadas](/SkypeForBusiness/certification/services-ssl) do CAS que você pode examinar para ver se sua autoridade de certificação preferida está listada.
  
Quando você precisará enviar uma solicitação para uma autoridade de certificação para este certificado público e como fazer isso? Há algumas maneiras de fazer isso:
  
- Você pode percorrer a instalação do Skype for Business Server e, em seguida, a implantação do servidor de borda. O assistente de implantação do Skype for Business Server terá uma etapa para gerar uma solicitação de certificado, que você pode enviar para a autoridade de certificação escolhida.
    
- Você também pode usar os comandos do Windows PowerShell para gerar essa solicitação, se estiver mais alinhado com suas necessidades comerciais ou estratégia de implantação.
    
- Por fim, sua autoridade de certificação pode ter seu próprio processo de envio, que também pode envolver o Windows PowerShell ou outro método. Nesse caso, você precisará contar com sua documentação, além das informações fornecidas aqui para sua referência.
    
Depois de ter chegado ao certificado, você precisará prosseguir e atribuí-lo a esses serviços no Skype for Business Server:
  
- Interface de serviço de borda de acesso
    
- Interface de serviço de borda de Webconferência
    
- Serviço de autenticação de áudio/vídeo (não confunda isso com o serviço de borda A/V, pois isso não usa um certificado para criptografar fluxos de áudio e vídeo)
    
> [!IMPORTANT]
> Todos os servidores de borda (se eles pertencem ao mesmo pool de servidores de borda) precisam ter exatamente o mesmo certificado com a mesma chave privada para o serviço de autenticação de retransmissão de mídia. 
  
### <a name="internal-certificates"></a>Certificados internos

Para a interface do servidor de borda interna, você pode usar um certificado público de uma autoridade de certificação pública ou um certificado emitido pela autoridade de certificação interna da sua organização. O que deve ser lembrado sobre o certificado interno é que ele usa uma entrada SN e sem entradas SAN, para que você não precise se preocupar com a SAN no CERT interno.
  
### <a name="required-certificates-table"></a>Tabela de certificados necessários

Temos uma tabela aqui para ajudá-lo com suas solicitações. As entradas de FQDN aqui são apenas para domínios de exemplo. Você precisará fazer solicitações com base em seus próprios domínios públicos e particulares, mas aqui está um guia para o que utilizamos:
  
- Contoso <span></span> . com: FQDN público
    
- Fabrikam <span></span> . com: segundo FQDN público (adicionado como uma demonstração do que solicitar se você tiver vários domínios SIP)
    
- Contoso <span></span> .net: domínio interno
    
#### <a name="edge-certificate-table"></a>Tabela de certificados de borda

Independentemente de você estar fazendo um único servidor de borda ou um pool de borda, isso é o que você precisará para o seu certificado:
  
|**Componente**|**Nome da entidade (SN)**|**Nomes alternativos da entidade (SAN)/ordem**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Borda externa  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Este é o certificado que você precisa solicitar de uma AC pública. Ele precisará ser atribuído às interfaces de borda externa para o seguinte:  <br/> • Borda de acesso  <br/> • Borda de Webconferência  <br/> • Autenticação de áudio/vídeo  <br/> <br/>A boa notícia é que as SANs são automaticamente adicionadas à solicitação de certificado e, portanto, o certificado após o envio da solicitação, com base no que você definiu para esta implantação no construtor de topologias. Você só precisará adicionar entradas de SAN para qualquer domínio SIP adicional ou outras entradas que você precisa suportar. Por que o sip.contoso.com é replicado nessa instância? Isso acontece automaticamente, e é necessário que as coisas funcionem corretamente.  <br/><br/> **Observação:** Este certificado também pode ser usado para conectividade de mensagens instantâneas públicas. Você não precisa fazer nada diferente, mas nas versões anteriores desta documentação, ele foi listado como uma tabela separada e, em seguida, não é. <br/> |
|Borda interna  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Você pode obter esse certificado de uma autoridade de certificação pública ou interna. Ele precisará conter o EKU do servidor (uso avançado de chave) e você o atribuirá à interface de borda interna.  <br/> |
   
Se você precisar de um certificado para Extensible Messaging and Presence Protocol (XMPP), ele será idêntico às entradas da tabela de borda externa acima, mas terá as duas entradas da SAN adicionais a seguir:
  
- XMPP. <span></span> Contoso <span></span> . com
    
- \*. contoso <span></span> . com
    
Lembre-se de que atualmente o XMPP só tem suporte no Skype for Business Server para Google Talk, se você deseja ou precisa usá-lo para qualquer outra coisa, você precisa confirmar essa funcionalidade com o fornecedor de terceiros envolvido.
  
## <a name="port-and-firewall-planning"></a>Planejamento de porta e firewall
<a name="PortFirewallPlan"> </a>

Obter o direito de planejamento para portas e firewalls para implantações do servidor de borda do Skype for Business Server pode economizar dias ou semanas de solução de problemas e estresse. Como resultado, vamos listar algumas tabelas que indicarão o uso do protocolo e quais portas você precisa ter abertas, entrada e saída, tanto para cenários de NAT quanto de IP público. Também temos tabelas separadas para cenários com balanceamento de carga de hardware (HLB) e algumas orientações adicionais sobre isso. Para ler mais sobre lá, também temos alguns [cenários de servidor de borda no Skype for Business Server](scenarios.md) , que você pode fazer o check-out para obter suas preocupações de implantação específicas.
  
### <a name="general-protocol-usage"></a>Uso do protocolo geral

Antes de examinarmos as tabelas de Resumo de firewalls internos e externos, considere também a tabela a seguir:
  
|**Transporte de áudio/vídeo**|**Usage**|
|:-----|:-----|
|VIA  <br/> |O protocolo de camada de transporte preferencial para áudio e vídeo.  <br/> |
|TCP  <br/> |O protocolo de camada de transporte de fallback para áudio e vídeo.  <br/> O protocolo de camada de transporte necessário para compartilhamento de aplicativos para o Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> O protocolo de camada de transporte necessário para transferência de arquivo para o Skype for Business Server, Lync Server 2013 e Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabela de Resumo de firewall de porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para os usuários que estão usando endereços IP privados com NAT, além de pessoas que usam endereços IP públicos. Isso abrange todas as permutações em nossos [cenários de servidor de borda na seção do Skype for Business Server](scenarios.md) .
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de destino ou intervalo de portas**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Sem suporte no Skype for Business Server 2019 |TCP  <br/> |5269  <br/> |Qualquer tamanho  <br/> |Serviço de proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso  <br/> |O serviço de proxy do XMPP aceita o tráfego de contatos do XMPP em federações XMPP definidas.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Qualquer tamanho  <br/> |Revogação de certificado e verificação e recuperação de CRL.  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Qualquer tamanho  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acesso/DNS  <br/> |VIA  <br/> |53  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Qualquer tamanho  <br/> |Consulta DNS sobre UDP.  <br/> |
|Acesso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Tráfego SIP de cliente para servidor para acesso de usuário externo.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Para conectividade federada e pública de IM usando SIP.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Qualquer tamanho  <br/> |Para conectividade federada e pública de IM usando SIP.  <br/> |
|Webconferência/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda de Webconferência da servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de Webconferência do servidor de borda <br/> |Mídia de Webconferência.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Qualquer tamanho  <br/> |Isso é usado para retransmitir tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |VIA  <br/> |50000-59999  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Qualquer tamanho  <br/> |Isso é usado para retransmitir tráfego de mídia.  <br/> |
|A/V/STUN. MSTURN  <br/> |VIA  <br/> |3478  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Qualquer tamanho  <br/> |3478 a saída é:  <br/> • Usado pelo Skype for Business Server para determinar a versão do servidor de borda com o qual está se comunicando.  <br/> • Usado para tráfego de mídia entre servidores de borda.  <br/> • Necessário para federação com o Lync Server 2010.  <br/> • Necessário se vários pools de borda estiverem implantados em sua organização.  <br/> |
|A/V/STUN. MSTURN  <br/> |VIA  <br/> |3478  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Negociação de candidatos STUN/TURN sobre UDP na porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Negociação de candidatos STUN/TURN sobre TCP na porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Qualquer tamanho  <br/> |Negociação de candidatos STUN/TURN sobre TCP na porta 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabela de Resumo de firewall de porta interna

|**Protocolo**|**TCP ou UDP**|**Port**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> |Interface interna do servidor de borda  <br/> |Tráfego XMPP de saída do serviço de gateway do XMPP em execução no servidor front-end ou no pool de front-ends.  <br/> **Observação:** Os gateways e proxies do XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Haja  <br/> • Diretor  <br/> • Pool de diretores  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> |Interface interna do servidor de borda  <br/> |Tráfego SIP de saída do diretor, pool de diretores, servidor front-end ou pool de front-ends para a interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interna do servidor de borda  <br/> |Haja  <br/> • Diretor  <br/> • Pool de diretores  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> |Tráfego SIP de entrada para seu diretor, pool de diretores, servidor front-end ou pool de front-ends da interface interna do servidor de borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Haja  <br/> • Servidor front-end  <br/> • Cada servidor de front-end  <br/>  em seu pool de front-ends <br/> |Interface interna do servidor de borda  <br/> |Tráfego de Webconferência do servidor front-end ou de cada servidor front-end (se você tiver um pool de front-ends) para a interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Haja  <br/> • Servidor front-end  <br/> • Pool de front-ends  <br/> • Qualquer aparelho de filial persistente usando este servidor de borda  <br/> • Qualquer servidor de filial persistente usando este servidor de borda  <br/> |Interface interna do servidor de borda  <br/> |Autenticação de usuários A/V do servidor front-end ou pool de front-ends, ou seu aparelho de filial persistente ou servidor de filial persistente, usando seu servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |VIA  <br/> |3478  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente, se a comunicação UDP não funcionar. O TCP é usado para transferência de arquivos e compartilhamento de área de trabalho.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Haja  <br/> • Servidor front-end que mantém o repositório de gerenciamento central  <br/> • Pool de front-ends que mantém o repositório de gerenciamento central  <br/> |Interface interna do servidor de borda  <br/> |Replicação de alterações do repositório de gerenciamento central para o servidor de borda.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |O controle de log centralizado usando o Shell de gerenciamento do Skype for Business Server e os cmdlets do serviço de registro em log centralizado, a linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |O controle de log centralizado usando o Shell de gerenciamento do Skype for Business Server e os cmdlets do serviço de registro em log centralizado, a linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |O controle de log centralizado usando o Shell de gerenciamento do Skype for Business Server e os cmdlets do serviço de registro em log centralizado, a linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Balanceadores de carga de hardware para tabelas de porta de borda

Estamos dando aos balanceadores de carga de hardware (HLBs) e portas de borda sua própria seção, pois as coisas são um pouco mais complicadas com o hardware adicional. Confira as tabelas abaixo para obter diretrizes para este cenário específico:
  
#### <a name="external-port-firewall-summary-table"></a>Tabela de Resumo de firewall de porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para os usuários que estão usando endereços IP privados com NAT, além de pessoas que usam endereços IP públicos. Isso abrange todas as permutações em nossos [cenários de servidor de borda na seção do Skype for Business Server](scenarios.md) .
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de destino ou intervalo de portas**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |Endereço IP público do serviço de borda de acesso do servidor de borda  <br/> |Qualquer tamanho  <br/> |Revogação de certificado e verificação e recuperação de CRL.  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |Endereço IP público do serviço de borda de acesso do servidor de borda  <br/> |Qualquer tamanho  <br/> |Consulta DNS sobre TCP.  <br/> |
|Acesso/DNS  <br/> |VIA  <br/> |53  <br/> |Endereço IP público do serviço de borda de acesso do servidor de borda  <br/> |Qualquer tamanho  <br/> |Consulta DNS sobre UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Endereço IP do serviço de borda de A/V do servidor de borda  <br/> |Qualquer tamanho  <br/> |Isso é usado para retransmitir tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |VIA  <br/> |50000-59999  <br/> |Endereço IP público do serviço de borda A/V do servidor de borda  <br/> |Qualquer tamanho  <br/> |Isso é usado para retransmitir tráfego de mídia.  <br/> |
|A/V/STUN. MSTURN  <br/> |VIA  <br/> |3478  <br/> |Endereço IP público do serviço de borda A/V do servidor de borda  <br/> |Qualquer tamanho  <br/> |3478 a saída é:  <br/> • Usado pelo Skype for Business Server para determinar a versão do servidor de borda com o qual está se comunicando.  <br/> • Usado para tráfego de mídia entre servidores de borda.  <br/> • Necessário para a Federação.  <br/> • Necessário se vários pools de borda estiverem implantados em sua organização.  <br/> |
|A/V/STUN. MSTURN  <br/> |VIA  <br/> |3478  <br/> |Qualquer tamanho  <br/> |Endereço IP público do serviço de borda A/V do servidor de borda  <br/> |Negociação de candidatos STUN/TURN sobre UDP na porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |Endereço IP público do serviço de borda A/V do servidor de borda  <br/> |Negociação de candidatos STUN/TURN sobre TCP na porta 443.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Endereço IP público do serviço de borda A/V do servidor de borda  <br/> |Qualquer tamanho  <br/> |Negociação de candidatos STUN/TURN sobre TCP na porta 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabela de Resumo de firewall de porta interna

|**Protocolo**|**TCP ou UDP**|**Port**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-ends executando o serviço de Gateway XMPP  <br/> |Interface interna do servidor de borda  <br/> |Tráfego XMPP de saída do serviço de gateway do XMPP em execução no servidor front-end ou no pool de front-ends.  <br/><br/> **Observação:** Os gateways e proxies do XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrating XMPP Federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Haja  <br/> • Servidor front-end que mantém o repositório de gerenciamento central  <br/> • Pool de front-ends que mantém o repositório de gerenciamento central  <br/> |Interface interna do servidor de borda  <br/> |Replicação de alterações do repositório de gerenciamento central para o servidor de borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Haja  <br/> • Servidor front-end  <br/> • Cada servidor de front-end em seu pool de front-ends  <br/> |Interface interna do servidor de borda  <br/> |Tráfego de Webconferência do servidor front-end ou de cada servidor front-end (se você tiver um pool de front-ends) para a interface interna do servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |VIA  <br/> |3478  <br/> |Haja  <br/> • Servidor front-end  <br/> • Cada servidor de front-end em seu pool de front-ends  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Haja  <br/> • Servidor front-end  <br/> • Cada servidor de front-end no pool  <br/> |Interface interna do servidor de borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente, se a comunicação UDP não funcionar. O TCP é usado para transferência de arquivos e compartilhamento de área de trabalho.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |O controle de log centralizado usando o Shell de gerenciamento do Skype for Business Server e os cmdlets do serviço de registro em log centralizado, a linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |O controle de log centralizado usando o Shell de gerenciamento do Skype for Business Server e os cmdlets do serviço de registro em log centralizado, a linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |O controle de log centralizado usando o Shell de gerenciamento do Skype for Business Server e os cmdlets do serviço de registro em log centralizado, a linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IPs virtuais de interface externa

|**Função ou protocolo**|**TCP ou UDP**|**Porta de destino ou intervalo de portas**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Sem suporte no Skype for businesss Server 2019 |TCP  <br/> |5269  <br/> |Qualquer tamanho  <br/> |Serviço de proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso)  <br/> |O serviço de proxy do XMPP aceita o tráfego de contatos do XMPP em federações XMPP definidas.  <br/> |
|XMPP  <br/>Sem suporte no Skype for businesss Server 2019 |TCP  <br/> |5269  <br/> |Serviço de proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso)  <br/> |Qualquer tamanho  <br/> |O serviço de proxy do XMPP envia o tráfego de contatos do XMPP em federações XMPP definidas.  <br/> |
|Acesso/SIP (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Tráfego SIP de cliente para servidor para acesso de usuário externo.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Para conectividade federada e pública de IM usando SIP.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privado usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de acesso do servidor de borda <br/> |Qualquer tamanho  <br/> |Para conectividade federada e pública de IM usando SIP.  <br/> |
|Webconferência/PSOM (TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda de Webconferência da servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda de Webconferência do servidor de borda <br/> |Mídia de Webconferência.  <br/> |
|A/V/STUN. MSTURN  <br/> |VIA  <br/> |3478  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Negociação de candidatos STUN/TURN sobre UDP na porta 3478.  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |**IP privado usando NAT:** Serviço de borda A/V do servidor de borda <br/> **IP público:** Endereço IP público do serviço de borda A/V do servidor de borda <br/> |Negociação de candidatos STUN/TURN sobre TCP na porta 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IPs virtuais de interface interna

Nossas orientações aqui serão um pouco diferentes. Na realidade, em uma situação HLB, recomendamos que você só tenha roteamento por meio de um VIP interno sob as seguintes circunstâncias:
  
- Se você estiver usando a UM (Unificação de mensagens) do Exchange 2007 ou do Exchange 2010.
    
- Se você tiver clientes herdados usando a borda.
    
A tabela a seguir fornece orientações para esses cenários, mas, caso contrário, você deverá ser capaz de depender do repositório de gerenciamento central (CMS) para rotear o tráfego para o servidor de borda individual em que está ciente (isso exige que o CMS seja mantido atualizado sobre as informações do servidor de borda, naturalmente).
  
|**Protocolo**|**TCP ou UDP**|**Port**|**Endereço IP de origem**|**Endereço IP de destino**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Haja  <br/> • Diretor  <br/> • Endereço VIP do pool de diretores  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-ends  <br/> |Interface interna do servidor de borda  <br/> |Tráfego SIP de saída do diretor, endereço VIP do pool de diretores, servidor front-end ou endereço VIP do pool de front-ends para a interface interna do servidor de borda.  <br/> |
|Access/SIP (MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface VIP interna do servidor de borda  <br/> |Haja  <br/> • Diretor  <br/> • Endereço VIP do pool de diretores  <br/> • Servidor front-end  <br/> • Endereço VIP do pool de front-ends  <br/> |Tráfego SIP de entrada para seu diretor, endereço VIP do pool de diretores, servidor front-end ou endereço VIP do pool de front-ends da interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Haja  <br/> • Endereço IP do servidor front-end  <br/> • Endereço IP do pool de front-ends  <br/> • Qualquer aparelho de filial persistente usando este servidor de borda  <br/> • Qualquer servidor de filial persistente usando este servidor de borda  <br/> |Interface interna do servidor de borda  <br/> |Autenticação de usuários A/V do servidor front-end ou pool de front-ends, ou seu aparelho de filial persistente ou servidor de filial persistente, usando seu servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |VIA  <br/> |3478  <br/> |Qualquer tamanho  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferencial para transferência de mídia A/V entre seus usuários internos e externos.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer tamanho  <br/> |Interface VIP interna do servidor de borda  <br/> |Caminho de fallback para transferência de mídia A/V entre seus usuários internos e externos se a comunicação UDP não funcionar. O TCP é usado para transferência de arquivos e compartilhamento de área de trabalho.  <br/> |
