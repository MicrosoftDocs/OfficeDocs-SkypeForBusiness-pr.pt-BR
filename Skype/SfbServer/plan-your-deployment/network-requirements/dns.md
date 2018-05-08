---
title: Requisitos de DNS para o Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumo: Revise as considerações de DNS neste tópico antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: d854c9908211a70b8fe863c9535502ba78c48521
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="dns-requirements-for-skype-for-business-server-2015"></a>Requisitos de DNS para o Skype for Business Server 2015
 
**Resumo:** Revise as considerações de DNS neste tópico antes de implementar Skype para Business Server 2015.
  
Este artigo aborda apenas Planejando o DNS para Skype para implantações de negócios Server 2015 na rede de no local de uma organização. Para Skype para Business Online, consulte a "IP e URLs do Office 365 intervalos de endereços" em [http://aka.ms/o365ips](http://aka.ms/o365ips). 
  
Os servidores de Serviço de Nomes de Domínio (DNS) mapeiam nomes do host (como www.contoso.com, supostamente um servidor Web) para endereços IP (como 10.10.10.10). Eles ajuda na comunicação entre os clientes e servidores interdependentes na rede Quando você configura uma implementação do Skype para Business Server 2015, você precisará certificar-se de que o mapeamento de novos nomes de servidor (geralmente refletindo a função que eles vai ser espalham) coincide com os endereços IP atribuídos a eles.
  
Isso pode parecer desanimador bit em um primeiro momento, o trabalho pesado para o planejamento, isso pode ser feito usando o [Skype para ferramenta de planejamento do Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Depois de responder às perguntas do assistente sobre os recursos que pretende usar, para cada local que definir, você poderá exibir o Relatório de DNS no Relatório de administração de borda e usar as informações fornecidas nele para criar seus registros DNS. Também é possível ajustar muitos dos nomes e endereços IP usados. Para obter detalhes, consulte [Examinar o relatório de DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Lembre-se de que você pode exportar o Relatório de administração de borda em uma planilha do Excel, e o Relatório de DNS será uma das planilhas no arquivo. 
  
Quando você estiver instalando uma nova implementação, conforme descrito em [criar registros DNS para Skype para Business Server 2015](../../deploy/install/create-dns-records.md) e criar sua topologia do Skype para Business Server 2015, reconhecemos que você pode optar por usar os recursos de DNS integrados Windows Servidor 2016 ou um pacote DNS de terceiros, portanto, vamos manter as discussões neste artigo gerais em vez de específicos. Vamos detalhar o que é necessário, e você decide como vai suprir essas necessidades.
  
Skype experiente para administradores corporativos, Lync e Office Communications Suite provavelmente achará as tabelas a seguir úteis. Se a tabela parecer confusa, as seções ou os artigos posteriores poderão esclarecer os seguintes conceitos: 
  
- [Tabelas de resumo](dns.md#BK_Summary)
    
- [Noções básicas DNS](basics.md)
    
- [Considerações sobre o híbrido](dns.md#BK_Hybrid)
    
- [Split brain DNS](dns.md#BK_split)
    
- [URLs simples](dns.md#BK_Simple)
    
- [DNS pela função de servidor](dns.md#BK_Servers)
    
## <a name="summary-tables"></a>Tabelas de resumo
<a name="BK_Summary"> </a>

As tabelas a seguir mostram os registros DNS que Skype para Business Server 2015 usa para fornecer serviços a usuários. Alguns são opcionais, pois são necessários apenas para dar suporte a determinados recursos, e podem ser ignorados casos esses recursos não sejam desejados. Os registros DNS necessários somente para acesso interno estão na primeira tabela, as implantações que permitem o acesso interno e externo precisarão de registros das duas tabelas.
  
**Mapeamentos DNS internos**

|**Tipo de registro**|**Valor**|**Resolve para**|**Finalidade**|**Obrigatório**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |FQDN do pool Front End  <br/>  *FE-pool.contoso.com*  <br/> |Endereços IP servidor do Front End pool  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Balanceamento de carga de DNS de Pools de Front-Ends. Mapeia o nome do Pool de Front-Ends para um conjunto de endereços IP.  <br/> Consulte [A implantação do balanceamento de carga DNS em pools do Diretor e pools de Front-End](load-balancing.md#BK_FE_Dir) <br/> |Y  <br/> |
|A/AAAA  <br/> | FQDN de cada servidor Front-End ou servidor Standard Edition em um pool ou um servidor autônomo <br/>  * Fe01, FE02.contoso.com, FE03.contoso.com*  <br/> |IP correspondente de cada servidor  <br/>  *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Mapeia o nome do servidor para seu endereço IP.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN de substituição de serviços Web internos do pool Enterprise  <br/>  *Int.contoso.com da Web*  <br/> |VIP HLB para serviços de Web internos do servidor Front-End  <br/>  * 192.168.21.120 *  <br/> |Necessário para habilitar o cliente para o tráfego de web server, como baixar o Skype para negócios Web App. Também é necessário para clientes Mobile.  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN de substituição de serviços Web externos do pool Enterprise  <br/>  *Web-ext.contoso.com*  <br/> |VIP HLB para serviços de Web externos do servidor Front-End  <br/>  *68.123.56.90*  <br/> |Necessário para habilitar o cliente para o tráfego de web server, como baixar o Skype para negócios Web App. Necessário caso os clientes móveis resolvam o DNS internamente. Pode resolver para IP da Internet ou IP de proxy reverso DMZ.  <br/> ||
|A/AAAA  <br/> | FQDN do servidor back End do SQL Server <br/>  *SQL1.contoso.com*  <br/> |endereço IP do servidor  <br/>  *192.168.11.90*  <br/> |Mapeia o nome do servidor para um servidor SQL de back-end como trabalhar com o pool de Front-End como o respectivo endereço IP  <br/> ||
|A/AAAA  <br/> |FQDN do servidor back End do servidor espelho SQL  <br/>  *SQL2.contoso.com*  <br/> |endereço IP do servidor  <br/>  *192.168.11.91*  <br/> |Mapeia o nome do servidor para um servidor de espelho do SQL de back-end como trabalhar com o pool de Front-End como o respectivo endereço IP  <br/> ||
|A/AAAA  <br/> |FQDN do pool de diretor  <br/> **Observação:** Não aplicável ao usar um servidor de diretor autônomo <br/>  *DirPool.contoso.com*  <br/> |Endereços IP do pool de diretor  <br/> DNS LB *192.168.21.132, 192.168.21.133* , 192.168.21.134  <br/> |Balanceamento de carga DNS de servidores do Pool de Diretores. Mapeamentos de nome de pool para o pool de diretor para um endereço IP, consulte [Implantando o balanceamento de carga do DNS em Pools de Front-Ends e Pools de diretor](load-balancing.md#BK_FE_Dir) <br/> Um Diretor pode autenticar um usuário e é opcional.  <br/> ||
|A/AAAA  <br/> |FQDN do Diretor  <br/> |Endereço IP do servidor de cada servidor do Diretor  <br/> |Mapeamentos de nome de pool para o Diretor como um endereço IP, consulte [Implantando o balanceamento de carga do DNS em Pools de Front-Ends e Pools de diretor](load-balancing.md#BK_FE_Dir) <br/> ||
|A/AAAA  <br/> |FQDN de pool de servidor de mediação  <br/> |Endereços IP do pool  <br/> |A função de Servidor de Mediação é opcional. Você pode colocalizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [usando o DNS com carga balanceada em Pools de servidor de mediação](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN do servidor de mediação  <br/> |Endereço IP do servidor  <br/> |Você pode colocalizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [usando o DNS com carga balanceada em Pools de servidor de mediação](load-balancing.md#BK_Mediation) <br/> ||
|A/AAAA  <br/> |FQDN do servidor de bate-papo persistente  <br/> |Endereço de IP do servidor de bate-papo persistente  <br/> |Um servidor de Chat Persistente é necessário para o recurso de Chat Persistente; em outros contextos, é opcional.  <br/> ||
|A/AAAA  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *contoso.com*  <br/> |Pool de Front-End do HLB VIP ou IP do Diretor  <br/>  192.168.21.121 <br/> |Obter interno AutoDiscover Service1, necessários para o suporte à mobilidade. Se o DNS interno é usado para resolver para dispositivos móveis, ele deve apontar para o IP externo, ou DMZ VIP.  <br/> Para serviços Web solicitamos HLB no pool de Front-End, como HTTPS não podem utilizar o DNS. Para o pool de Front-End ou pool de diretores, que isso deve resolve um VIP HLB ou um IP regular para um servidor Standard edition ou um servidor de diretor autônomo.  <br/> |Y  <br/> |
|CNAME  <br/> |lyncdiscoverinternal. _\<sipdomain\>_ <br/> lyncdiscoverinternal. *Contoso.com*  <br/> |FQDN do pool FE HLB ou FQDN do Diretor  <br/> Int.contoso.com da Web  <br/> |Service1 de descoberta automática interno <br/> Se desejar, você poderá implementar isso como um CNAME, em vez de um registro A.  <br/> ||
|A/AAAA  <br/> |sip. _\<sipdomain\>_ <br/> sip. _Contoso.com_ <br/> |Pool Front-End server IP (como um cada IP do Diretor endereço ou)  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*  <br/> |Necessário para a configuração automática, consulte [passo a passo do Skype para clientes corporativos localizar serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Um ou mais registros apontando para os servidores do pool de Front-End ou diretor servidores na rede interna ou o serviço de borda de acesso quando o cliente é externo  <br/> |2 <br/> |
|A/AAAA  <br/> |ucupdates-r2. _\<sipdomain\>_ <br/> ucupdates-r2. _Contoso.com_ <br/> |VIP do pool FE HBL ou VIP HLB do pool de Diretor ou IP do servidor SE/Diretor  <br/>  192.168.21.121 <br/> |Implantando a esse registro é opcional 3 <br/> ||
|SRV  <br/> |sipinternaltls. _ \<sipdomain\> _ Porta 5061 <br/> sipinternaltls. _contoso.com_ porta 5061 <br/> |FQDN do pool Front End  <br/>  _FE-Pool.contoso.com_ <br/> |Habilita o usuário interno na entrada automática 1 para o pool/servidor de Front-End ou Sudeste/pool de servidores que autenticar e redirecionar as solicitações de entrada dos clientes. <br/> |2 <br/> |
|SRV  <br/> |_sipinternal. _\<sipdomain\>_ <br/> _sipinternal. _Contoso.com_ <br/> |FQDN do pool Front End  <br/>  _FE-Pool.contoso.com_ <br/> |Acesso de usuário interno 1 <br/> |2 <br/> |
|SRV  <br/> |_ntp._udp. _\<sipdomain\>_ <br/> _ntp._udp. _Contoso.com_ <br/> |FQDN do servidor de horário  <br/> america.pool.ntp.org do Norte  <br/> |Origem NTP necessário para os dispositivos Lync Phone Edition  <br/> |Isso é necessário para dar suporte a aparelhos de telefone da área de trabalho.  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _Contoso.com_ <br/> | FQDN do serviço de borda de acesso <br/> EdgePool-int. _contoso.com_ <br/> |Criar um registro SRV para cada domínio SIP que tem clientes móveis iOS ou Windows Phone.  <br/> |Para suporte a clientes móveis  <br/> |
|A/AAAA  <br/> |URL do administrador  <br/>  _Int.contoso.com da Web_ <br/> |VIP do pool FE HLB  <br/> 192.168.21.121  <br/> |Skype para painel de controle do Business Server, consulte [As URLs simples](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |URL da reunião  <br/>  _Int.contoso.com da Web_ <br/> |VIP do pool FE HLB  <br/> 192.168.21.121  <br/> |Reuniões online, consulte [As URLs simples](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |URL de discagem  <br/>  _Int.contoso.com da Web_ <br/> |VIP do pool FE HLB  <br/> 192.168.21.121  <br/> |Conferência discada, consulte [As URLs simples](dns.md#BK_Simple) <br/> ||
|A/AAAA  <br/> |FQDN dos serviços Web internos  <br/>  _Int.contoso.com da Web_ <br/> |VIP do pool FE HLB  <br/> 192.168.21.121  <br/> |Skype para serviço Web de negócios usado pelo Skype para negócios Web App  <br/> ||
|A/AAAA  <br/> |FQDN do pool do Office Web Apps Server  <br/> OWA.contoso.com  <br/> | Pool do Office Web Apps Server endereço VIP <br/> 192.168.1.5  <br/> |Define o FQDN do pool de servidor do Office Web Apps  <br/> ||
|A/AAAA  <br/> | FQDN da Web interno <br/> Int.contoso.com da Web  <br/> | Pool Front-End endereço VIP <br/> 192.168.21.121  <br/> |Define o FQDN de Web interno usado pelo Skype para negócios Web App  <br/> Se você estiver usando o balanceamento de carga DNS nesse pool, seu pool Front-End e seu web farm interno não poderão ter o mesmo FQDN.  <br/> ||
   
 **1** usado por um cliente para descobrir o pool de Front-End ou de servidor Front-End e ser autenticado e conectado como um usuário. Mais detalhes sobre esse estão em [passo a passo do Skype para clientes corporativos localizar serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).
  
 **2** isso só é necessário para dar suporte a clientes herdados antes do Lync 2013 e fones de área de trabalho.
  
 **3** na situação em que um dispositivo de comunicação unificada é ativado, mas um usuário nunca tiver feito logon no dispositivo, o registro permite ao dispositivo descobrir o servidor que hospeda o serviço Web de atualização de dispositivo e obtenham atualizações. Caso contrário, os dispositivos obtêm essas informações por meio do provisionamento em banda na primeira vez que o usuário faz logon.
  
O diagrama a seguir mostra um exemplo que inclui registros DNS internos e externos, e muitos dos registros mostrados nas tabelas ao redor: 
  
**Diagrama de rede de borda usando endereços IPv4 público**

![exemplo de diagrama de rede de DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
**Mapeamentos de DNS de rede de perímetro (interfaces internas e externas)**

|**Tipo de registro**|**Valor**|**Resolve para**|**Finalidade**|**Obrigatório**|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA  <br/> |FQDN do pool de borda interna  <br/>  _EdgePool-int.contoso.com_ <br/> |Internal voltado para endereços IP de pool de borda  <br/> 172.25.33.10, 172.25.33.11  <br/> |Endereços IP da interface interna do pool de borda consolidado  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN do servidor de borda  <br/>  _Contras-1.contoso.com_ <br/> |IP do servidor interno voltados para um servidor no pool de borda  <br/> 172.25.33.10  <br/> |Criar um registro para cada servidor no pool com o FQDN do servidor apontando para seu IP de nó de servidor interno no pool, consulte [Balanceamento de carga de DNS em Pools de servidor de borda](load-balancing.md#BK_Edge).  <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN do Pool do serviço de borda de acesso  <br/>  _Access1.contoso.com_ <br/> |Endereços de IP de acesso externo de Pool de serviço de borda  <br/> 131.107.16.10, 131.107.16.11  <br/> |O serviço de borda de acesso fornece um ponto de conexão único e confiável para o tráfego de protocolo de iniciação de sessão (SIP) de entrada e saída.  <br/> |Y  <br/> |
|A/AAAA  <br/> |Serviço de borda de webconferência FQDN do Pool da Web  <br/>  _Webcon1.contoso.com_ <br/> |Endereços de IP de Web externa de serviço de borda de webconferência  <br/> 131.107.16.90, 131.107.16.91  <br/> |O serviço de borda de webconferência permite que os usuários externos ingressem em reuniões hospedadas em sua Skype interno para ambiente de servidor de negócios.  <br/> |Y  <br/> |
|A/AAAA  <br/> | _antivírus.\<domínio sip\> _ FQDN do pool <br/>  _AV1.contoso.com_ <br/> |Endereços IP externos de borda A/V  <br/> 131.107.16.170, 131.107.16.171  <br/> |A / serviço de borda V torna áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos disponíveis para usuários externos.  <br/> |Y  <br/> |
|CNAME  <br/> |sip. _\<sipdomain\>_ <br/> sip. _Contoso.com_ <br/> |FQDN do pool de Borda de acesso externo  <br/>  _Access1.contoso.com_ <br/> |Localiza o pool do servidor de borda. Consulte [passo a passo do Skype para clientes corporativos localizando serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sip._tls. _\<sipdomain\>_ <br/> _sip._tls. _Contoso.com_ <br/> |FQDN de borda de acesso externo  <br/>  _Access1.contoso.com_ <br/> |Usado para o acesso de usuários externos Consulte [passo a passo do Skype para clientes corporativos localizando serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> |Y  <br/> |
|SRV  <br/> |_sipfederationtls._tcp. _\<sipdomain\>_ <br/> _sipfederationtls._tcp. _Contoso.com_ <br/> |FQDN de borda de acesso externo  <br/>  _Access1.contoso.com_ <br/> |Usado para federação e conectividade de IM pública  <br/> |1 <br/> |
|SRV  <br/> |_xmpp-server._tcp. _\<sipdomain\>_ <br/> _xmpp-server._tcp. _Contoso.com_ <br/> |FQDN de borda de acesso externo  <br/>  _Access1.contoso.com_ <br/> |O serviço de Proxy XMPP aceita e envia mensagens de protocolo XMPP de presença e mensagem extensível e para parceiros federados XMPP configurados.  <br/> |Y, para implantar a federação; caso contrário, opcional  <br/> |
|SRV  <br/> |_sipfederationtls._tcp.  _\<sipdomain\>_ <br/> _sipfederationtls._tcp.  _Contoso.com_ <br/> |FQDN de borda de acesso externo  <br/>  _Access1.contoso.com_ <br/> |Para suportar o serviço de notificação de Push e Apple Push Notification service, você deve criar um registro SRV para cada domínio SIP. 3 <br/> ||
|A/AAAA  <br/> |FQDN de serviços web externos de pool de Front-End  <br/>  _Web-ext.contoso.com_ <br/> |Reverter o endereço IP público do proxy, proxies para o VIP de serviços Web externos para o pool de Front-End 1 <br/> 131.107.155.1 proxy de para 192.168.21.120  <br/> |Front End pool interface externa usado pelo Skype para negócios Web App  <br/> |Y  <br/> |
|A/AAAA/CNAME  <br/> |lyncdiscover. _\<sipdomain\>_ <br/> lyncdiscover. _Contoso.com_ <br/> |Reverter o endereço IP público do proxy, resolve para o VIP de serviços Web externos para seu pool de diretor, se você tiver um, ou para seu pool de Front-End, se você não tiver um diretor de 2 <br/> 131.107.155.1 proxy de para 192.168.21.120  <br/> | Registro externo para o cliente de descoberta automática, também é usada pelo mobilidade, Skype para negócios Web App e Agendador Web app, resolvido pelo servidor proxy reverso <br/> Para suportar o serviço de notificação de Push e Apple Push Notification service, você deve criar um registro SRV para cada domínio SIP que possui clientes do Microsoft Lync Mobile. 3 <br/> |Y  <br/> |
|A/AAAA  <br/> |meet. _\<sipdomain\>_ <br/> meet. _Contoso.com_ <br/> |Reverter o endereço IP público do proxy, resolve para a interface externa da Web para o pool de Front-End  <br/> 131.107.155.1 proxy de para 192.168.21.120  <br/> |Proxy do Skype para serviço Web de negócios  <br/> Consulte [as URLs simples](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |discada _ \<sipdomain\>_ <br/> discada _contoso.com_ <br/> |Reverter o endereço IP público do proxy, proxies para a interface externa da Web para o pool de Front-End  <br/> 131.107.155.1 proxy de para 192.168.21.120  <br/> |Proxy do Skype para serviço Web de negócios  <br/> Consulte [as URLs simples](dns.md#BK_Simple) <br/> |Y  <br/> |
|A/AAAA  <br/> |FQDN do pool do Office Web Apps Server  <br/> OWA.contoso.com  <br/> | Endereço IP público do proxy reverso, proxies para a interface externa da Web para o Office Web Apps Server <br/> 131.107.155.1 proxy pra 192.168.1.5  <br/> | Pool do Office Web Apps Server endereço VIP <br/> 192.168.1.5  <br/> |Define o FQDN do pool de servidor do Office Web Apps  <br/> |
   
 **1** necessárias para implantar a federação, caso contrário, é opcional.
  
 **2** usado por um cliente para descobrir o servidor front-end ou um pool de Front-End e ser autenticado e conectado como um usuário.
  
 **3** esse requisito só se aplica aos clientes no Apple ou Microsoft com base em dispositivos móveis. Dispositivos Android e Nokia Symbian não usam notificação por push.
  
 Para obter mais detalhes sobre redes de perímetro e servidores de borda, consulte o conteúdo de [planejamento de DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) do servidor de borda.
  
> [!IMPORTANT]
> Skype para Business Server suporta o uso de endereçamento IPv6. Para obter mais detalhes, consulte [Planejar IPv6 no Skype para negócios](ipv6.md) .
  
> [!IMPORTANT]
> Para obter mais detalhes sobre FQDNs, consulte [Noções básicas DNS](basics.md). 
  
 **Dividir brain DNS** 
 <a name="BK_split"> </a>
 
O DNS dividido brain é uma configuração do DNS a onde você tem duas zonas de DNS com o mesmo namespace. A primeira zona DNS trata as solicitações internas, enquanto a segunda zona DNS trata as solicitações externas, conforme mencionado nas tabelas. Para saber mais sobre isso, consulte [DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS). 
  
## <a name="hybrid-considerations"></a>Considerações sobre o híbrido
<a name="BK_Hybrid"> </a>

Se você planeja ter alguns usuários hospedados and e outros hospedados no local, consulte as [Configurações de DNS](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS) híbridas. Você precisará configurar o DNS como de costume para Skype para Business Server 2015 e também adicionar registros DNS adicionais. 
  
Você também deve consultar a "IP e URLs do Office 365 intervalos de endereços" em [http://aka.ms/o365ips](http://aka.ms/o365ips) para confirmar que seus usuários terão acesso aos recursos online que precisarão.
  
## <a name="simple-urls"></a>URLs simples 
<a name="BK_Simple"> </a>

A URL (Uniform Resource Locator) é uma referência a um recurso da Web que especifica sua localização em uma rede de computadores e um protocolo usado para recuperá-lo. 
  
Skype para Business Server suporta o uso de três URLs "simples" para serviços do access:
  
- **Meet** é usado como URL de base para todas as conferências no site. Um exemplo de um simples Meet URL é https://meet.contoso.com. Uma URL para uma reunião específica pode ser https://meet.contoso.com/ _username_/7322994. 
    
    Com a URL simples Meet, é fácil compreender e divulgar links para ingressar em reuniões.
    
- **Dial-in** permite o acesso à página da Web Configurações de Conferência Discada. Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência. A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias. Um exemplo de URL simples Dial-in é https://dialin.contoso.com.
    
- **Admin** permite acesso rápido ao Skype para painel de controle do servidor de negócios. Em qualquer computador dentro dos firewalls da organização, um administrador pode abrir o Skype para painel de controle do Business Server digitando a URL simple do administrador em um navegador. A URL simples de Admin é parte interna da sua organização. Um exemplo de URL simple Admin é https://admin.contoso.com.
    
URLs simples são abordados em mais detalhes [os requisitos de DNS para URLs simples no Skype para Business Server 2015](simple-urls.md).
  
## <a name="dns-by-server-role"></a>DNS por função de servidor
<a name="BK_Servers"> </a>

Você pode definir os nomes desses pools e servidores como deseja, mas eles devem ser fáceis de lembrar e refletir sua função no sistema.
  
### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS de servidores individuais ou pools

Esses requisitos de registro genérico se aplicam a qualquer função de servidor usada pelo Skype para negócios. Um pool é um conjunto de servidores que executa os mesmos serviços que funcionam juntos para tratar as solicitações de clientes direcionadas a eles por meio de um balanceador de carga. Consulte [requisitos do Skype para negócios de balanceamento de carga](load-balancing.md) para obter detalhes
  
**Requisitos de registro de DNS para funções de pool do servidor (partem do princípio de balanceamento de carga DNS)**

|**Cenário de implantação**|**Requisito de DNS**|
|:-----|:-----|
|Um servidor:  <br/> Chat persistente, diretor, servidor de mediação, servidor front-end  <br/> |Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) do servidor para seu endereço IP.  <br/> ServerRole.contoso.com 10.10.10.0  <br/> |
|Pool:  <br/> Chat persistente, diretor, servidor de borda, servidor de mediação, front-end  <br/> |Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) de cada nó do servidor no pool para seu endereço IP.  <br/> **Exemplo** <br/> ServerRole01.contoso.com 10.10.10.1  <br/> ServerRole02.contoso.com 10.10.10.2  <br/> Vários registros A internos que resolvem o nome de domínio totalmente qualificado (FQDN) do pool para os endereços IP dos nós do servidor no pool.  <br/> **Exemplo** <br/> ServerPool.contoso.com 10.10.10.1  <br/> ServerPool.contoso.com 10.10.10.2  <br/> |
   
### <a name="edge-server-specific-dns-topics"></a>Tópicos sobre DNS específicos do Servidor de Borda

 Para planejar a implantação de servidor de borda, examine [Plan para implantações de servidor de borda em Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)e [DNS do servidor de borda avançado planejando Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) que tem as seguintes seções
  
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
- [Configuração automática sem DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    

