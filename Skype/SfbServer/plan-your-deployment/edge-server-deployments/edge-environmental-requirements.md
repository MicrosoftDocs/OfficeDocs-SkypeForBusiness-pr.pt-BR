---
title: Requisitos de ambiente de servidor de borda no Skype para Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Resumo: Saiba sobre os requisitos de ambientais para o servidor de borda no Skype para Business Server.'
ms.openlocfilehash: 2fbe4f617a9a3d7fa0adebb65141596bd0c94fbe
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295337"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Requisitos de ambiente de servidor de borda no Skype para Business Server
 
**Resumo:** Saiba mais sobre os requisitos de ambientais para o servidor de borda no Skype para Business Server.
  
Muito planejamento e preparação deve ocorrer fora do Skype para ambiente de servidor de borda do servidor de negócios em si. Neste artigo, vamos rever as preparações que precisam ser feitas no ambiente organizacional, de acordo com nossa lista abaixo:
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Planejamento de topologia
<a name="TopoPlan"> </a>

Skype para topologias de servidor de borda do Business Server estejam aptos a usar:
  
- Endereços IP públicos roteáveis
    
- Endereços IP privados não roteáveis, se a tradução de endereço de rede **simétrica** (NAT) for usada.
    
> [!TIP]
> O servidor de borda podem ser configurado para usar um único endereço IP com portas distintas para cada serviço, ou usar endereços IP distintos para cada serviço, mas usam a mesma porta padrão (que, por padrão, será TCP 443). Temos mais informações na seção de requisitos do Endereço IP, abaixo. 
  
Se você escolher endereços IP privados não roteáveis com NAT, lembre-se destes aspectos:
  
- Você deve usar endereços IP privados roteáveis em **todas as três** interfaces externas.
    
- Você precisa configurar NAT **simétrico** para tráfego de entrada e de saída. NAT simétrico é que a única suportada NAT, você pode usar com Skype para servidor de borda do servidor de negócios.
    
- Configure seu NAT para não alterar endereços de origem de entrada. A / V Edge serviço precisa ser capazes de receber o endereço de origem de entrada para localizar o caminho de mídia ideal.
    
- Os servidores de borda precisarão ser capazes de se comunicar umas com as outras da seu pública / endereços IP de borda V. Seu firewall deve permitir esse tráfego.
    
- NAT pode **somente** ser usado para servidores de borda consolidada em escala, se você usar o balanceamento de carga do DNS. Se você usar o balanceamento de carga de hardware (HLB), será necessário usar endereços IP roteáveis publicamente **sem** NAT.
    
Você não terá nenhum problema ter seu acesso, webconferência e A / V Edge interfaces por trás de um roteador ou firewall executando NAT simétrico para única ou escalonável consolidada topologias de servidor de borda (desde que você não estiver usando o balanceamento de carga de hardware).
  
### <a name="summary-of-edge-server-topology-options"></a>Resumo das opções de topologia de servidor de borda

Temos várias opções de topologia disponíveis para Skype para implantações de servidor de borda do servidor de negócios:
  
- Borda única consolidada com endereços IP privados e NAT
    
- Borda única consolidada com endereços IP públicos
    
- Borda dimensionada consolidada com endereços IP privados e NAT
    
- Borda dimensionada consolidada com endereços IP públicos
    
- Borda dimensionada consolidada com balanceadores de carga de hardware
    
Para ajudá-lo a escolher uma, temos a tabela a seguir que apresenta um resumo das opções que você tem para cada topologia:
  
|**Topologia**|**Alta disponibilidade**|**Registros DNS adicionais necessários para o servidor de borda externa no pool de borda?**|**Failover de borda para Skype para sessões do servidor de negócios**|**Failover de borda para Skype para sessões de Federação do servidor de negócios**|
|:-----|:-----|:-----|:-----|:-----|
|Borda única consolidada com endereços IP privados e NAT  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Borda única consolidada com endereços IP públicos  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |Não  <br/> |
|Borda dimensionada consolidada com endereços IP privados e NAT (balanceamento de carga DNS)  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim & sup1;  <br/> |
|Borda dimensionada consolidada com endereços IP públicos (balanceamento de carga DNS)  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim & sup1;  <br/> |
|Borda dimensionada consolidada com balanceadores de carga de hardware  <br/> |Sim  <br/> |Não (um registro DNS A por VIP)  <br/> |Sim  <br/> |Sim  <br/> |
   
& sup1; Failover de usuário remoto do Exchange Unified Messaging (UM) usando o balanceamento de carga do DNS exige o Exchange 2013 ou mais recente.
  
### <a name="ip-address-requirements"></a>Requisitos de Endereço IP

Em um nível fundamental, três serviços precisam endereços IP; Uma, serviço de borda de webconferência e serviço de borda de acesso / serviço de borda V. Você tem a opção de usar três endereços de IP, um para cada um dos serviços, ou você pode usar um e optar por colocar cada serviço em uma porta diferente (é possível consultar a seção[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações relacionadas). Para um ambiente de Borda única consolidada, isso é o suficiente.
  
> [!NOTE]
> Conforme observado acima, você pode escolher um endereço IP para todos os três serviços e executá-los em diferentes portas. Porém, na realidade, não recomendamos isso. Se os seus clientes não conseguem acessar as portas alternadas que você usaria neste cenário, eles também não podem acessar a funcionalidade total do seu ambiente de Borda. 
  
Pode ser um pouco mais complicado com topologias escalonáveis consolidadas, portanto, vejamos algumas tabelas que apresentam os requisitos de Endereço IP, lembrando-se de que os principais pontos de decisão para seleção da topologia são alta disponibilidade e balanceamento de carga. As necessidades de alta disponibilidade podem influenciar sua escolha de balanceamento de carga (falaremos mais sobre esse assunto depois das tabelas).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de endereço IP para Borda dimensionada consolidada (endereço de IP por função)

|**Número de servidores de borda por pool**|**Número de endereços IP necessários para balanceamento de carga de DNS**|**Número de endereços IP necessários para o balanceamento de carga de hardware**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (1 por VIP) + 6  <br/> |
|3  <br/> |9  <br/> |3 (1 por VIP) + 9  <br/> |
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
  
- **Alta disponibilidade**: se você precisar de alta disponibilidade em sua implantação, você deve implantar pelo menos dois servidores de borda em um pool. É importante observar que um único pool de borda dará suporte a até 12 servidores de borda (embora o construtor de topologias permitirá que você adicione até 20, que não tenha testado ou suportado, portanto, é recomendável que você não faça isso). Se precisar de mais de 12 servidores de borda, você deve criar pools de borda adicionais para eles.
    
- **Balanceamento de carga de hardware**: Recomendamos à maioria dos cenários de balanceamento de carga do DNS. Balanceamento de carga de hardware também é suportado, obviamente, mas notadamente requerido para um único cenário sobre o balanceamento de carga DNS:
    
  - Acesso externo ao Exchange 2007 ou Exchange 2010 (com nenhum SP) Unified Messaging (UM).
    
- **Balanceamento de carga DNS**: para UM, Exchange 2010 SP1 e mais recente são capazes de ser suportados pelo balanceamento de carga do DNS. Observe que se você precisar ir com DNS com carga balanceada para uma versão anterior do Exchange, ele vai trabalhar, mas todo o tráfego para que isso serão encaminhadas para o primeiro servidor no pool e se não estiver disponível, esse tráfego subsequentemente falhará.
    
    Balanceamento de carga DNS também é recomendável se você estiver federar as empresas que usam:
- Skype para Business Server 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office O365
- Skype para Business Server 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>Planejamento DNS
<a name="DNSPlan"> </a>

Quando se trata Skype para implantação de servidor de borda do Business Server, é fundamental para preparar adequadamente DNS. Com o registros corretos em vigor, a implantação será muito mais simples. Esperamos que você tenha escolhida uma topologia na seção acima, pois vamos fazer uma visão geral e, em seguida, listar algumas tabelas que destacam os registros DNS para os cenários. Também teremos algum [DNS do servidor de borda avançado planejando Skype para Business Server](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) para a leitura mais aprofundada, se necessário.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>Registros DNS para única consolidada cenários de servidor de borda

Estes serão os registros DNS, que você vai precisar para uma servidor de borda usando um dos público única IPs ou IPs privada com NAT. Como estes são dados de amostra, daremos o exemplo de IPs para que você possa encontrar sua própria solução mais facilmente:
  
- Adaptador de rede interna: 172.25.33.10 (nenhum gateway padrão atribuído)
    
    > [!NOTE]
    > Certifique-se de que haja uma rota da rede contendo a interface interna de borda para quaisquer redes que contenham servidores executando o Skype para clientes Business Server ou o Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - IPs Públicos:
    
  - Borda de acesso: 131.107.155.10 (Este é o principal, com o gateway padrão definido para o roteador público, ex.: 131.107.155.1)
    
  - Borda de webconferência: 131.107.155.20 (secundário)
    
  - A / V Edge: 131.107.155.30 (secundário)
    
  Webconferências e uma / endereços IP públicos de borda V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol Version 6 (TCP/IPv6) as propriedades de Conexão de área Local em Windows Server.
    
  - IPs Privadas:
    
  - Borda de acesso: 10.45.16.10 (Este é o principal, com o gateway padrão definido como roteador, ex.: 10.45.16.1)
    
  - Borda de webconferência: 10.45.16.20 (secundário)
    
  - A / V Edge: 10.45.16.30 (secundário)
    
Webconferências e uma / endereços IP públicos de borda V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol Version 6 (TCP/IPv6) as propriedades de Conexão de área Local em Windows Server.
  
> [!TIP]
>Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externa. Não recomendamos isso porque, em seguida, você vai precisar diferenciar entre o o serviços usando portas diferentes (que você pode fazer em Skype para Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a seção [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações sobre o assunto.
    
- É possível ter três adaptadores de rede externa em vez de um, e atribuir uma das IPs do serviço para cada um. Por que? Isto separaria os serviços e se algo der errado, seria mais fácil solucionar o problema e potencialmente permitiria que seus outros serviços continuassem a funcionar enquanto o problema estivesse sendo resolvido.
    
|**Local**|**Tipo**|**Porta**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**pública:** 131.107.155.10 <br/> **privada:** 10.45.16.10 <br/> |Uma interface externa para seu serviço de borda de acesso. Você precisará um para cada domínio SIP com Skype para usuários comerciais.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**pública:** 131.107.155.20 <br/> **privada:** 10.45.16.20 <br/> |Uma interface externa para seu serviço de borda de webconferência.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |av.contoso.com  <br/> |**pública:** 131.107.155.30 <br/> **privada:** 10.45.16.30 <br/> |Uma interface externa para sua uma / serviço de borda V.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de borda de acesso. Esse registro SRV é necessário para Skype para clientes do Lync Server 2010, Lync Server 2013 e Business Server funcione externamente. Você precisará um para cada domínio com Skype para usuários comerciais.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de borda de acesso. Este registro SRV é necessário para a descoberta de DNS automática de parceiros federados chamado domínios SIP Permitidos. Você precisará um para cada domínio com Skype para usuários comerciais.  <br/> |
|DNS Interno  <br/> |Registro A  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |A interface interna para sua Borda consolidada.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>Registros DNS para cenários de servidor de borda de hardware e DNS dimensionada

Estes serão os registros DNS, que você vai precisar para uma servidor de borda usando um dos público única IPs ou IPs privada com NAT. Como estes são dados de amostra, daremos o exemplo de IPs para que você possa encontrar sua própria solução mais facilmente:
  
- Adaptador de rede interna
    
  - Nó 1: 172.25.33.10 (nenhum gateway padrão atribuído)
    
  - Nó 2: 172.25.33.11 (nenhum gateway padrão atribuído)
    
    > [!NOTE]
    > Certifique-se de que haja uma rota da rede contendo a interface interna de borda para quaisquer redes que contenham servidores executando o Skype para clientes Business Server ou o Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0). 
  
- Adaptador de rede externo:
    
  - Nó 1
    
     - IPs Públicos:
    
        - Borda de acesso: 131.107.155.10 (Este é o principal, com o gateway padrão definido para o roteador público, ex.: 131.107.155.1)
    
        - Borda de webconferência: 131.107.155.20 (secundário)
    
        - A / V Edge: 131.107.155.30 (secundário)
    
          Webconferências e uma / endereços IP públicos de borda V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol Version 6 (TCP/IPv6) as propriedades de Conexão de área Local em Windows Server.
    
    - IPs Privadas:
    
         - Borda de acesso: 10.45.16.10 (Este é o principal, com o gateway padrão definido como roteador, ex.: 10.45.16.1)
    
         - Borda de webconferência: 10.45.16.20 (secundário)
    
         - A / V Edge: 10.45.16.30 (secundário)
    
      Webconferências e uma / endereços IP públicos de borda V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol Version 6 (TCP/IPv6) as propriedades de Conexão de área Local em Windows Server.
    
  - Nó 2
    
    - IPs Públicos:
    
      - Borda de acesso: 131.107.155.11 (Este é o principal, com o gateway padrão definido para o roteador público, ex.: 131.107.155.1)
    
      - Borda de webconferência: 131.107.155.21 (secundário)
    
      - A / V Edge: 131.107.155.31 (secundário)
    
      Webconferências e uma / endereços IP públicos de borda V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol Version 6 (TCP/IPv6) as propriedades de Conexão de área Local em Windows Server.
    
  - IPs Privadas:
    
    - Borda de acesso: 10.45.16.11 (Este é o principal, com o gateway padrão definido como roteador, ex.: 10.45.16.1)
    
    - Borda de webconferência: 10.45.16.21 (secundário)
    
    - A / V Edge: e 10.45.16.31 (secundário)
    
      Webconferências e uma / endereços IP públicos de borda V são endereços IP adicionais (secundários) na seção Avançado das propriedades do Internet Protocol versão 4 (TCP/IPv4) e Internet Protocol Version 6 (TCP/IPv6) as propriedades de Conexão de área Local em Windows Server.
    
Há outras configurações possíveis aqui:
  
- Você pode usar um endereço IP no adaptador de rede externa. Não recomendamos isso porque, em seguida, você vai precisar diferenciar entre o o serviços usando portas diferentes (que você pode fazer em Skype para Business Server), mas há alguns firewalls que podem bloquear as portas alternativas. Consulte a seção [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan) para obter mais informações sobre o assunto.
    
- É possível ter três adaptadores de rede externa em vez de um, e atribuir uma das IPs do serviço para cada um. Por que? Isto separaria os serviços e se algo der errado, seria mais fácil solucionar o problema e potencialmente permitiria que seus outros serviços continuassem a funcionar enquanto o problema estivesse sendo resolvido.
    
|**Local**|**Tipo**|**Porta**|**FQDN ou registro DNS**|**Endereço IP ou FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |sip.contoso.com  <br/> |**público:** 131.107.155.10 e 131.107.155.11 <br/> **privadas:** 10.45.16.10 e 10.45.16.11 <br/> |Uma interface externa para seu serviço de borda de acesso. Você precisará um para cada domínio SIP com Skype para usuários comerciais.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |webcon.contoso.com  <br/> |**público:** 131.107.155.20 e 131.107.155.21 <br/> **privadas:** 10.45.16.20 e 10.45.16.21 <br/> |Uma interface externa para seu serviço de borda de webconferência.  <br/> |
|DNS Externo  <br/> |Registro A  <br/> |N/D  <br/> |av.contoso.com  <br/> |**público:** 131.107.155.30 e 131.107.155.31 <br/> **privadas:** 10.45.16.30 e e 10.45.16.31 <br/> |Uma interface externa para sua uma / serviço de borda V.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de borda de acesso. Esse registro SRV é necessário para Skype para clientes do Lync Server 2010, Lync Server 2013 e Business Server funcione externamente. Você precisará um para cada domínio com Skype para negócios.  <br/> |
|DNS Externo  <br/> |Registro SRV  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Uma interface externa para seu serviço de borda de acesso. Este registro SRV é necessário para a descoberta de DNS automática de parceiros federados chamado domínios SIP Permitidos. Você precisará um para cada domínio com Skype para negócios.  <br/> |
|DNS Interno  <br/> |Registro A  <br/> |N/D  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 e 172.25.33.11  <br/> |A interface interna para sua Borda consolidada.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>Registro DNS para federação (todos os cenários)

|**Local**|**Tipo**|**Porta**|**FQDN**|**Registro de host FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |A interface externa de borda de acesso SIP necessária para a descoberta automática de DNS. Usada por seus outros parceiros da federação em potencial. É também conhecida como "Domínios SIP permitidos." Você precisará um destes procedimentos para cada domínio SIP com Skype para usuários comerciais.  <br/><br/> **Observação:** Você precisará esse registro SRV para mobilidade e a notificação de push a câmara de compensação. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Resumo DNS para protocolo de presença e mensagem extensível

|**Local**|**Tipo**|**Porta**|**FQDN**|**Endereço IP ou registro de host FQDN**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|DNS Externo  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |A interface de proxy XMPP no seu serviço de borda de acesso ou o pool de borda. Você precisará repetir isso conforme necessário para todos os domínios SIP internos com Skype para usuários do servidor de negócios habilitado, onde o contato com contatos XMPP é permitido através de:  <br/> • uma política global  <br/> • uma política de site em que o usuário do habilitado  <br/> • uma política de usuário aplicada ao Skype para Business Server habilitado para o usuário  <br/> Uma política XMPP permitida também deve ser configurada na política de usuários federados XMPP.  <br/> |
|DNS Externo  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |Endereço IP do serviço de borda de acesso no servidor de borda ou pool de borda que hospeda seu serviço de Proxy XMPP  <br/> |Isso aponta para o serviço de borda de acesso no servidor de borda ou pool de borda que hospeda o serviço de Proxy XMPP. Normalmente, o registro SRV que você cria apontará para esse registro de host (A ou AAAA).  <br/> |
   
> [!NOTE]
> Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019. Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.

## <a name="certificate-planning"></a>Planejamento de Certificados
<a name="CertPlan"> </a>

Skype para Business Server usa certificados de criptografadas comunicação segura entre servidores e do servidor ao cliente. Como seria de esperar, seus certificados deverão ter registros DNS para que seus servidores sejam compatíveis com qualquer nome da entidade (SN) e nome alternativo de entidade (SAN) em seus certificados. Isso será trabalhoso na fase de planeamento, para que você certifique-se de que tem os FQDNs corretos registrados no DNS para as inserções de SN e SAN de seus certificados.
  
Abordaremos as necessidades de certificados internos e externos separadamente, e em seguida, examinaremos uma tabela que fornece os requisitos para ambos.
  
### <a name="external-certificates"></a>Certificados Externos

No mínimo, o certificado atribuído ao interfaces externas do servidor de borda precisa ser fornecido por uma autoridade de certificação pública (CA). Não podemos recomendar uma AC específica, mas temos uma lista de ACs, [parceiros de certificado Unified Communications](https://support.microsoft.com/en-us/kb/929395), que você poderá olhar e verificar se a AC que você precisa está listada.
  
Quando você precisará enviar uma solicitação para um AC para ter este certificado público, e como você fazê-lo? Há várias formas de fazer isso:
  
- Você pode passar a instalação do Skype para Business Server e, em seguida, a implantação de servidor de borda. O Skype para o Assistente de implantação do Business Server terá uma etapa para gerar uma solicitação de certificado, você poderá enviar para escolhida para sua autoridade de certificação.
    
- Você também pode usar comandos do Windows PowerShell para gerar a solicitação, caso esteja mais embutida com suas necessidades comerciais ou a estratégia de implantação.
    
- Finalmente, a autoridade de certificação pode ter seu próprio processo de envio, que também pode envolver o Windows PowerShell ou outro método. Nesse caso, você precisará contar com sua documentação, além as informações fornecidas aqui para sua referência.
    
Depois que você tiver chegado o certificado, você precisará prossiga e atribuí-lo para esses serviços no Skype para Business Server:
  
- Interface de serviço de borda de acesso
    
- Interface de serviço de borda de conferência Web
    
- Serviço de autenticação de áudio/vídeo (não confunda isso com A / serviço de borda V, que não usa um certificado para criptografar fluxos de áudio e vídeos)
    
> [!IMPORTANT]
> Todos os Servidores de Borda precisam ter exatamente o mesmo certificado com a mesma chave privada para o serviço de Autenticação de retransmissão de mídia. 
  
### <a name="internal-certificates"></a>Certificados internos

Para a interface interna do servidor de borda, você pode usar um certificado pública de uma autoridade de certificação pública ou um certificado emitido a partir de autoridade de certificação interna da sua organização. É importante lembrar que o certificado interno é aquele utiliza uma inserção de SN, e nenhuma inserção de SAN, portanto, você  não deve se preocupar com SAN no certificado interno.
  
### <a name="required-certificates-table"></a>Tabela de Certificados Exigidos

Temos uma tabela aqui para ajudá-lo com os seus pedidos. As entradas de FQDN são apenas exemplos de domínios. Você precisará fazer solicitações com base em seus próprios domínios privados e públicos, mas aqui está a orientação sobre o procedimento que temos seguido:
  
- Contoso<span></span>.com: FQDN público
    
- Fabrikam<span></span>.com: segunda FQDN público (adicionado como uma demonstração do que solicitar se você tiver vários domínios SIP)
    
- Contoso<span></span>.net: domínio interno
    
#### <a name="edge-certificate-table"></a>Tabela de Certificado de Borda

Independentemente se você estiver fazendo um único servidor de borda ou um pool de borda, isso é o que será necessário para o seu certificado:
  
|**Componente**|**Nome da entidade (SN)**|**Nomes alternativos de entidade (SAN)/ordem**|**Observações**|
|:-----|:-----|:-----|:-----|
|Borda Externa  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Esse é o certificado que você precisa solicitar de uma AC pública. Ele precisará ser atribuído às interfaces de Borda externa para o seguinte:<br/> • Borda de acesso  <br/> • Borda de webconferência  <br/> • Autenticação de áudio/vídeo  <br/> <br/>A boa notícia é que SANs serão automaticamente adicionadas à sua solicitação de certificado e, portanto, o seu certificado depois que você envie a solicitação, com base no que foi definido para esta implantação no construtor de topologia. Basta adicionar entradas de SAN para quaisquer domínios SIP adicionais ou outras entradas às quais você precisa dar suporte. Por que o sip.contoso.com é replicado nessa instância? Isso também acontece automaticamente e é necessário para que as coisas funcionem adequadamente.  <br/><br/> **Observação:** Esse certificado também pode ser usado para conectividade pública de mensagens instantâneas. Não será necessário fazer nada diferente com ele, pois as versões anteriores desta documentação foram listadas como uma tabela separada, e agora não são mais. <br/> |
|Borda Interna  <br/> |sfbedge.contoso.com  <br/> |N/D  <br/> |É possível obter este certificado a partir de uma AC pública ou interna. Ele precisará conter o EKU do servidor (Uso Avançado de Chave), e você precisará atribuí-lo à interface de borda interna.  <br/> |
   
Se você precisa de um certificado para XMPP (Extensible Messaging and Presence Protocol), ele será idêntico às entradas da tabela de Borda Externa acima, mas terá as duas entradas adicionais de SAN indicadas abaixo:
  
- XMPP. <span> </span>contoso<span></span>.com
    
- \*.contoso<span></span>.com
    
Lembre-se de que atualmente XMPP só é suportado no Skype para Business Server para o Google Talk, se você desejar ou precisa usá-lo para qualquer outra coisa, você precisa confirmar que a funcionalidade com o fornecedor terceirizado envolvido.
  
## <a name="port-and-firewall-planning"></a>Planejamento de porta e de firewall
<a name="PortFirewallPlan"> </a>

Obtendo o seu planejamento adequadas para firewalls e portas para Skype para servidor de borda do servidor de negócios implantações podem poupá-lo a dias ou semanas de solução de problemas e sobrecarregar. Como resultado, vamos listar algumas tabelas que indicarão nosso uso do protocolo e quais portas você precisa abrir, internas e externas, tanto para cenários NAT e de IP público. Também temos tabelas separadas para cenários com balanceamento de carga de hardware (HLB) e mais algumas orientações sobre isso. Para mais de leitura a partir daí, também temos alguns [cenários de servidor de borda no Skype para Business Server](scenarios.md) pode fazer o check-out para suas preocupações de implantação específica.
  
### <a name="general-protocol-usage"></a>Uso Geral do Protocolo

Antes de observarmos as tabelas de resumo para firewalls internos e externos, vejamos a tabela a seguir:
  
|**Transporte de áudio/vídeo**|**Uso**|
|:-----|:-----|
|UDP  <br/> |Protocolo de camada de transporte preferido para áudio e vídeo.  <br/> |
|TCP  <br/> |Protocolo de camada de transporte de fallback para áudio e vídeo.  <br/> O protocolo de camada de transporte necessário para compartilhamento de aplicativos para Skype para Business Server, Lync Server 2013 e Lync Server 2010.  <br/> O protocolo de camada de transporte necessária para transferência de arquivos para Skype para Business Server, Lync Server 2013 e Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Tabela de resumo de firewall da porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para usuários que estão usando endereços IP privados com NAT, bem como para as pessoas que utilizam endereços IP públicos. Isso abordará todas as permutas em nossa seção [cenários de servidor de borda no Skype para Business Server](scenarios.md) .
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Não são suportados no Skype para Business Server 2019 |TCP  <br/> |5269  <br/> |Qualquer  <br/> |Serviço de Proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso  <br/> |O serviço de Proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas.  <br/> |
|Acesso/HTTP  <br/> |TCP  <br/> |80  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Qualquer  <br/> |Revocação de certificado e verificação e recuperação de CRL  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Qualquer  <br/> |Consulta DNS sobre TCP  <br/> |
|Acesso/DNS  <br/> |UDP  <br/> |53  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Qualquer  <br/> |Consulta DNS sobre UDP  <br/> |
|Acesso/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Tráfego SIP do cliente ao servidor para o acesso do usuário externo.  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Qualquer  <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Webconferência/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Serviço de borda de webconferência servidor de borda <br/> **IP públicos:** Borda de webconferência Server serviço serviço endereço IP público borda <br/> |Mídia de conferência da Web.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**IP privados usando NAT:** Um servidor de borda a / V Edge serviço serviço <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**IP privados usando NAT:** Um servidor de borda a / V Edge serviço serviço <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**IP privados usando NAT:** Um servidor de borda / serviço de borda V <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Qualquer  <br/> |Saída 3478 é:  <br/> • Usados pelo Skype para Business Server para determinar a versão do servidor de borda está se comunicando com.  <br/> • Usada para o tráfego de mídia entre os servidores de borda.  <br/> • Necessário para federação com o Lync Server 2010.  <br/> • Necessário se vários pools de borda estiverem implantados dentro da sua organização.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Um servidor de borda / serviço de borda V <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Negociação de candidatos STUN/TURN sob UDP na porta 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Um servidor de borda / serviço de borda V <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**IP privados usando NAT:** Um servidor de borda / serviço de borda V <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Qualquer  <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Tabela de resumo do firewall da porta interna

|**Protocolo**|**TCP ou UDP**|**Porta**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor de front-End  <br/> • Pool de front-End  <br/> |Interface interna do servidor de borda  <br/> |Tráfego XMPP de saída no seu serviço de Gateway XMPP executando no seu pool de Front-End ou de servidor Front-End.  <br/> **Observação:** Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019. Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Qualquer um:  <br/> • Diretor  <br/> • O pool de diretores  <br/> • Servidor de front-End  <br/> • Pool de front-End  <br/> |Interface interna do servidor de borda  <br/> |Tráfego SIP de saída do seu diretor, pool de diretor, pool de Front-End ou de servidor Front-End à sua interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Interface interna do servidor de borda  <br/> |Qualquer um:  <br/> • Diretor  <br/> • O pool de diretores  <br/> • Servidor de front-End  <br/> • Pool de front-End  <br/> |Tráfego SIP de entrada para seu pool de diretor, pool diretor, servidor Front-End ou Front-End da sua interface interna do servidor de borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualquer um:  <br/> • Servidor de front-End  <br/> • Cada servidor Front-End  <br/>  em seu pool de Front-End <br/> |Interface interna do servidor de borda  <br/> |Tráfego de webconferência do seu servidor Front-End ou em cada servidor Front-End (se você tiver um pool de Front-End) para sua interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualquer um:  <br/> • Servidor de front-End  <br/> • Pool de front-End  <br/> • Qualquer aparelho de filial persistente, usando este servidor de borda  <br/> • Qualquer servidor de filial persistente, usando este servidor de borda  <br/> |Interface interna do servidor de borda  <br/> |Autenticação do / usuários V de seu pool de Front-End ou de servidor Front-End, ou seu aparelho de filial persistente ou servidor de filial persistente, usando seu servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferido para uma / transferência de mídia de V entre usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Caminho de fallback de A / V de transferência de mídia entre os usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente, se a comunicação UDP não está funcionando. Neste caso, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualquer um:  <br/> • O servidor front-End que contém o repositório de gerenciamento Central  <br/> • Pool de front-End que contém o repositório de gerenciamento Central  <br/> |Interface interna do servidor de borda  <br/> |Repositório de replicação de alterações do seu repositório de gerenciamento Central para seu servidor de borda.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Controlador de serviço de log centralizado usando Skype para cmdlets do Shell de gerenciamento de servidor de negócios e Centralized Logging Service, linha de comando do ClsController (ClsController.exe) ou comandos do agente (ClsAgent.exe) e o conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Controlador de serviço de log centralizado usando Skype para cmdlets do Shell de gerenciamento de servidor de negócios e Centralized Logging Service, linha de comando do ClsController (ClsController.exe) ou comandos do agente (ClsAgent.exe) e o conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Controlador de serviço de log centralizado usando Skype para cmdlets do Shell de gerenciamento de servidor de negócios e Centralized Logging Service, linha de comando do ClsController (ClsController.exe) ou comandos do agente (ClsAgent.exe) e o conjunto de log.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Balanceadores de carga de hardware para tabelas da porta da Borda

Preparamos uma seção apenas para balanceadores de carga de hardware (HLBs) e portas da Borda, uma vez que o assunto é um pouco mais complicado em se tratando de hardware adicional. Consulte as tabelas abaixo para obter orientação para este cenário específico:
  
#### <a name="external-port-firewall-summary-table"></a>Tabela de resumo de firewall da porta externa

O endereço IP de origem e o endereço IP de destino conterão informações para usuários que estão usando endereços IP privados com NAT, bem como para as pessoas que utilizam endereços IP públicos. Isso abordará todas as permutas em nossa seção [cenários de servidor de borda no Skype para Business Server](scenarios.md) .
  
|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acesso/HTTP  <br/> |TCP  <br/> |80  <br/> |Endereço IP público do borda servidor de borda de acesso service  <br/> |Qualquer  <br/> |Revocação de certificado e verificação e recuperação de CRL  <br/> |
|Acesso/DNS  <br/> |TCP  <br/> |53  <br/> |Endereço IP público do borda servidor de borda de acesso service  <br/> |Qualquer  <br/> |Consulta DNS sobre TCP  <br/> |
|Acesso/DNS  <br/> |UDP  <br/> |53  <br/> |Endereço IP público do borda servidor de borda de acesso service  <br/> |Qualquer  <br/> |Consulta DNS sobre UDP  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Um servidor de borda a / V Edge endereço IP do serviço  <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Um servidor de borda a / endereço IP público do serviço de borda de V  <br/> |Qualquer  <br/> |Usado para retransmitir o tráfego de mídia.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Um servidor de borda a / endereço IP público do serviço de borda de V  <br/> |Qualquer  <br/> |Saída 3478 é:  <br/> • Usados pelo Skype para Business Server para determinar a versão do servidor de borda está se comunicando com.  <br/> • Usada para o tráfego de mídia entre os servidores de borda.  <br/> • Necessário para federação.  <br/> • Necessário se vários pools de borda estiverem implantados dentro da sua organização.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |Um servidor de borda a / endereço IP público do serviço de borda de V  <br/> |Negociação de candidatos STUN/TURN sob UDP na porta 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |Um servidor de borda a / endereço IP público do serviço de borda de V  <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Um servidor de borda a / endereço IP público do serviço de borda de V  <br/> |Qualquer  <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Tabela de resumo do firewall da porta interna

|**Protocolo**|**TCP ou UDP**|**Porta**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Qualquer um dos seguintes executando o serviço de Gateway XMPP:  <br/> • Servidor de front-End  <br/> Pool de front-End • endereço VIP executando o serviço de Gateway XMPP  <br/> |Interface interna do servidor de borda  <br/> |Tráfego XMPP de saída no seu serviço de Gateway XMPP executando no seu pool de Front-End ou de servidor Front-End.  <br/><br/> **Observação:** Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019. Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Qualquer um:  <br/> • O servidor front-End que contém o repositório de gerenciamento Central  <br/> • Pool de front-End que contém o repositório de gerenciamento Central  <br/> |Interface interna do servidor de borda  <br/> |Replicação das alterações de seu repositório de gerenciamento Central para seu servidor de borda.  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |Qualquer um:  <br/> • Servidor de front-End  <br/> • Cada servidor Front-End em seu pool de Front-End  <br/> |Interface interna do servidor de borda  <br/> |Tráfego de webconferência do seu servidor Front-End ou em cada servidor Front-End (se você tiver um pool de Front-End) para sua interface interna do servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer um:  <br/> • Servidor de front-End  <br/> • Cada servidor Front-End em seu pool de Front-End  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferido para uma / transferência de mídia de V entre usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer um:  <br/> • Servidor de front-End  <br/> • Cada servidor Front-End em seu pool  <br/> |Interface interna do servidor de borda  <br/> |Caminho de fallback de A / V de transferência de mídia entre os usuários internos e externos e seu aparelho de filial persistente ou servidor de filial persistente, se a comunicação UDP não está funcionando. Neste caso, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Controlador de serviço de log centralizado usando Skype para cmdlets do Shell de gerenciamento de servidor de negócios e Centralized Logging Service, linha de comando do ClsController (ClsController.exe) ou comandos do agente (ClsAgent.exe) e o conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Controlador de serviço de log centralizado usando Skype para cmdlets do Shell de gerenciamento de servidor de negócios e Centralized Logging Service, linha de comando do ClsController (ClsController.exe) ou comandos do agente (ClsAgent.exe) e o conjunto de log.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Controlador de serviço de log centralizado usando Skype para cmdlets do Shell de gerenciamento de servidor de negócios e Centralized Logging Service, linha de comando do ClsController (ClsController.exe) ou comandos do agente (ClsAgent.exe) e o conjunto de log.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>IPs virtuais da interface externa

|**Função ou protocolo**|**TCP ou UDP**|**Porta de Destino ou intervalo de portas**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Não são suportados no Skype para 2019 do servidor de negócio |TCP  <br/> |5269  <br/> |Qualquer  <br/> |Serviço de Proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso)  <br/> |O serviço de Proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas.  <br/> |
|XMPP  <br/>Não são suportados no Skype para 2019 do servidor de negócio |TCP  <br/> |5269  <br/> |Serviço de Proxy XMPP (compartilha um endereço IP com o serviço de borda de acesso)  <br/> |Qualquer  <br/> |O serviço de Proxy XMPP enviará o tráfego de contatos XMPP em federações XMPP definidas.  <br/> |
|Acesso/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Tráfego SIP do cliente ao servidor para o acesso do usuário externo.  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**IP privados usando NAT:** Serviço de serviço de borda de acesso do servidor de borda <br/> **IP públicos:** Endereço IP público do borda servidor de borda de acesso service <br/> |Qualquer  <br/> |Para conectividade a IM federada e pública usando SIP  <br/> |
|Webconferência/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Serviço de borda de webconferência servidor de borda <br/> **IP públicos:** Endereço IP público do Edge Server borda de webconferência service <br/> |Mídia de conferência da Web.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Um servidor de borda / serviço de borda V <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Negociação de candidatos STUN/TURN sob UDP na porta 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |**IP privados usando NAT:** Um servidor de borda / serviço de borda V <br/> **IP públicos:** Um servidor de borda a / endereço IP público do serviço de borda de V <br/> |Negociação de candidatos STUN/TURN sob TCP na porta 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>IPs virtuais da interface interna

Nossa orientação aqui será um pouco diferente. Na realidade, em uma situação HLB, recomendamos que você tenha apenas roteamento por meio de um VIP interno sob as seguintes circunstâncias:
  
- Se você estiver usando o Exchange 2007 ou Exchange 2010 Unified Messaging (UM).
    
- Se você tiver clientes herdados usando a Borda.
    
A tabela a seguir fornecer orientação para esses cenários, mas caso contrário, você deve ser capaz de dependem do repositório de gerenciamento Central (CMS) para rotear o tráfego para o servidor de borda individuais que ele esteja ciente das (Isso exige que CMS é mantido atualizado no servidor de borda informações, obviamente).
  
|**Protocolo**|**TCP ou UDP**|**Porta**|**Endereço IP de Origem**|**Endereço IP de Destino**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Endereço VIP do pool de diretores  <br/> • Servidor de front-End  <br/> Pool de front-End • endereço VIP  <br/> |Interface interna do servidor de borda  <br/> |Tráfego SIP de saída do seu diretor, o endereço VIP, servidor Front-End ou VIP do pool de Front-End do pool de diretores endereços à sua interface interna do servidor de borda.  <br/> |
|Acesso/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Interface VIP interna do servidor de borda  <br/> |Qualquer um:  <br/> • Diretor  <br/> • Endereço VIP do pool de diretores  <br/> • Servidor de front-End  <br/> Pool de front-End • endereço VIP  <br/> |Tráfego SIP diretor, entrada endereço VIP do pool de diretor, servidor Front-End ou endereço VIP do pool de Front-End da sua interface interna do servidor de borda.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Qualquer um:  <br/> • Endereço de IP de servidor front End  <br/> • Endereço IP de pool de front-End  <br/> • Qualquer aparelho de filial persistente, usando este servidor de borda  <br/> • Qualquer servidor de filial persistente, usando este servidor de borda  <br/> |Interface interna do servidor de borda  <br/> |Autenticação do / usuários V de seu pool de Front-End ou de servidor Front-End, ou seu aparelho de filial persistente ou servidor de filial persistente, usando seu servidor de borda.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |Qualquer  <br/> |Interface interna do servidor de borda  <br/> |Caminho preferencial para transferência de mídia A/V entre usuários internos e externos  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |Qualquer  <br/> |Interface VIP interna do servidor de borda  <br/> |Caminho de fallback para transferência de mídia A/V entre usuários internos e externos se a comunicação UDP não for estabelecida, TCP é usado para transferência de arquivos e compartilhamento da área de trabalho  <br/> |