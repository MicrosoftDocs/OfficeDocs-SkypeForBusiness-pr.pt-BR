---
title: Requisitos de DNS para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumo: revise as considerações de DNS neste tópico antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 13dd8b65c52329ff2db0ac3d7d57eeba990e29f6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297061"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos de DNS para o Skype for Business Server

**Resumo:** Examine as considerações de DNS neste tópico antes de implementar o Skype for Business Server.

Este artigo trata apenas do planejamento de DNS para implantações do Skype for Business Server na rede local de uma organização. Para o Skype for Business Online, consulte "URLs e intervalos de endereços IP do Office [https://aka.ms/o365ips](https://aka.ms/o365ips)365" em.

Um servidor DNS (Domain Name Service) mapeia nomes de host (como www<span> </span> . Contoso<span></span>. com, supostamente um servidor Web) para endereços IP (como 10.10.10.10). Ele ajuda os clientes e os servidores interdependentes a se comunicar uns com os outros na rede. Ao configurar uma implementação do Skype for Business Server 2015, você precisará certificar-se de que o mapeamento dos novos nomes de servidor (geralmente refletindo a função que ele vai fazer) corresponda aos endereços IP aos quais eles estão atribuídos.

Embora isso possa parecer um pouco assustador à primeira vez, o trabalho pesado para planejar isso pode ser feito usando a [ferramenta de planejamento do Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Depois que você tiver usado as perguntas do assistente sobre quais recursos você planeja usar, para cada site que você definir, poderá exibir o relatório DNS no relatório de administração de borda e usar as informações listadas ali para criar seus registros DNS. Você também pode fazer ajustes para muitos dos nomes e endereços IP usados, para obter detalhes, consulte [rever o relatório DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Lembre-se de que você pode exportar o relatório de administração de borda para uma planilha do Excel, e o relatório DNS será uma das planilhas no arquivo. Embora essa ferramenta inclua recursos [preteridos do Skype for Business Server 2019](../../../SfBServer2019/deprecated.md), ele ainda pode ser usado para criar um plano inicial se esses recursos não estiverem selecionados

Ao instalar uma nova implementação, conforme descrito em [criar registros DNS para o Skype for Business Server](../../deploy/install/create-dns-records.md) e criar sua topologia para o Skype for Business Server, reconhecemos que você pode optar por usar os recursos DNS integrados ao Windows Server 2016 ou um pacote DNS de terceiros, portanto, manteremos as discussões neste artigo em geral, em vez de específicas. Vamos detalhar o que é necessário, e você decide como vai suprir essas necessidades.

Os administradores do Skype for Business, do Lync e do Office Communications Suite experientes provavelmente encontrarão as seguintes tabelas úteis. Se a tabela parecer confusa, as seções ou os artigos posteriores poderão esclarecer os seguintes conceitos:

## <a name="summary-tables"></a>Tabelas de resumo
<a name="BK_Summary"> </a>

As tabelas a seguir mostram os registros de DNS que o Skype for Business Server usa para fornecer serviços aos usuários. Alguns são opcionais, pois são necessários apenas para dar suporte a determinados recursos, e podem ser ignorados casos esses recursos não sejam desejados. Os registros DNS necessários somente para acesso interno estão na primeira tabela, as implantações que permitem o acesso interno e externo precisarão de registros das duas tabelas.

**Mapeamentos internos de DNS**

|Tipo de registro|Valor|Resolve para|Objetivo|Obrigatório|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN do pool de front-end  <br/> *FE-pool. <span> </span>Contoso<span></span>. com*   |Endereços IP do servidor de pool de front-end  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*   |Balanceamento de carga de DNS de Pools de Front-Ends. Mapeia o nome do Pool de Front-Ends para um conjunto de endereços IP. <br/> Consulte [A implantação do balanceamento de carga DNS em pools do Diretor e pools de Front-End](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | FQDN de cada servidor front-end ou servidor Standard Edition em um pool ou um servidor autônomo <br/>  *FE01. <span> </span>contoso. <span> </span>com FE02. <span> </span>Contoso<span></span>. com FE03. <span> </span>Contoso<span></span>. com*   |IP correspondente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Mapeia o nome do servidor para seu endereço IP.   |Y   |
|A/AAAA   |FQDN de substituição de serviços Web internos do pool Enterprise  <br/> *Web-int.<span></span>Contoso<span></span>. com*   |HLB VIP para serviços Web internos do servidor front-end  <br/> *192.168.21.120*   |Obrigatório para habilitar o tráfego do cliente na Web do servidor, como baixar o Skype for Business Web App. Também é necessário para clientes Mobile.   |Y   |
|A/AAAA   |FQDN de substituição de serviços Web externos do pool Enterprise  <br/> *Web-ext.<span></span>Contoso<span></span>. com*   |HLB VIP para serviços Web externos do servidor front-end  <br/>*68.123.56.90*   |Obrigatório para habilitar o tráfego do cliente na Web do servidor, como baixar o Skype for Business Web App. Necessário caso os clientes móveis resolvam o DNS internamente. Pode resolver para IP da Internet ou IP de proxy reverso DMZ.   ||
|A/AAAA   | FQDN do servidor do SQL Server back-end <br/> *SQL1. <span> </span>Contoso<span></span>. com*   |endereço IP do servidor  <br/> *192.168.11.90*   |Mapeia o nome do servidor para um SQL Server de back-end que trabalha com o pool de front-end em seu endereço IP   ||
|A/AAAA   |FQDN do servidor back-end do SQL Server  <br/> *SQL2. <span> </span>Contoso<span></span>. com*   |endereço IP do servidor  <br/> *192.168.11.91*   |Mapeia o nome do servidor para um servidor de espelho SQL do back-end que trabalha com o pool de front-end para o endereço IP   ||
|A/AAAA   |FQDN do pool do diretor  <br/>**Observação:** Não aplicável ao usar um servidor de diretor autônomo <br/> *DirPool. <span> </span>Contoso<span></span>. com*   |Endereços IP do pool de directors  <br/> DNS LB para *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Balanceamento de carga de DNS dos servidores do pool do diretor. Mapeia o nome do pool para o pool diretor para um endereço IP, consulte Implantando o [balanceamento de carga de DNS em pools de front-end e pools de diretor](load-balancing.md#BK_FE_Dir) <br/> Um Diretor pode autenticar um usuário e é opcional.   ||
|A/AAAA   |FQDN do diretor   |Endereço IP do servidor de cada servidor diretor   |Mapeia o nome do pool para o diretor para um endereço IP, confira implantando o [balanceamento de carga de DNS em pools de front-end e em pools de diretor](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN do pool do servidor de mediação   |Endereços IP do pool   |A função de Servidor de Mediação é opcional. Você pode colocalizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [usando o balanceamento de carga de DNS nos pools do servidor de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do servidor de mediação   |Endereço IP do servidor   |Você pode colocalizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [usando o balanceamento de carga de DNS nos pools do servidor de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do servidor de chat persistente   |Endereço IP do servidor de chat persistente   |Um servidor de Chat Persistente é necessário para o recurso de Chat Persistente; em outros contextos, é opcional.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>Contoso<span></span>. com*   |IP do diretor ou VIP do pool de front-end do HLB  <br/>  192.168.21.121  |Service1 de descoberta automática interna, necessário para suporte à mobilidade. Se o DNS interno for usado para resolver dispositivos móveis, ele deve apontar para o IP externo ou VIP da DMZ.  <br/> Para os serviços Web, precisamos de HLB no pool de front-ends porque HTTPS não pode aproveitar o DNS. Para o pool de front-ends ou o pool de directors, isso deve ser resolvido para um VIP HLB ou um IP regular para um servidor Standard Edition ou um servidor de director autônomo.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>. com*   |FQDN do pool FE HLB ou FQDN do Diretor  <br/> Web-int.<span></span>Contoso<span></span>. com   |Service1 de descoberta automática interna <br/> Se desejar, você poderá implementar isso como um CNAME, em vez de um registro A.   ||
|A/AAAA   |SPI. * \<sipdomain\>* <br/> SPI. * <span> </span>Contoso<span></span>. com*  |Endereços IP do servidor de pool de front-end (ou para um endereço IP de cada diretor)  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*   |Obrigatório para configuração automática, consulte o [passo a passo dos clientes do Skype for Business que localizam serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Um registro ou registros que apontam para servidores de pool de front-end ou servidores de diretor na rede interna ou o serviço de borda de acesso quando o cliente é externo   |&#x2777;  |
|A/AAAA   |ucupdates-r2. * \<sipdomain\>* <br/> ucupdates-r2. * <span> </span>Contoso<span></span>. com*  |VIP do pool FE HBL ou VIP HLB do pool de Diretor ou IP do servidor SE/Diretor  <br/>  192.168.21.121  |A implantação desse registro é opcional & # x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<sipdomain\> * <br/>Porta 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>Contoso<span></span>. com* <br/>Porta 5061  |FQDN do pool de front-end  <br/>*FE-pool. <span> </span>Contoso<span></span>. com*  |Habilita o logon automático de usuários internos1 no servidor/pool front-end ou servidor/pool SE que autentica e redireciona as solicitações de logon de clientes.    |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *Contoso<span></span>. com*  |FQDN do pool de front-end  <br/>_FE-pool. <span> </span>Contoso<span></span>. com_  |Acesso de usuário interno & # x2776;  |&#x2777;  |
|SRV   | \_NTP. \_UDP. * \<sipdomain\> * <br/> \_NTP. \_UDP. <span> </span> *Contoso<span></span>. com*  |FQDN do servidor de horário  <br/> north-america.pool.ntp.org   |Fonte NTP necessária para dispositivos do Lync Phone Edition   |Isso é necessário para dar suporte a aparelhos de mesa.   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  | FQDN do serviço de borda de acesso <br/> EdgePool-int.<span></span>*Contoso<span></span>. com*  |Criar um registro SRV para cada domínio SIP que tem clientes móveis iOS ou Windows Phone.   |Para suporte a clientes móveis   |
|A/AAAA   |URL do administrador  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Painel de controle do Skype for Business Server, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL da reunião  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Reuniões online, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de discagem  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Conferência discada, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN dos serviços Web internos  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Skype for Business Web Service usado pelo Skype for Business Web App   ||
|A/AAAA   |FQDN do pool de servidores do Office Web Apps  <br/> OWA. <span> </span>Contoso<span></span>. com   | Endereço VIP do pool de servidores do Office Web Apps <br/> 192.168.1.5   |Define o FQDN do pool do servidor do Office Web Apps   ||
|A/AAAA   |  FQDN da Web interno <br/> Web-int.<span></span>Contoso<span></span>. com   | Endereço VIP do pool de front-end <br/> 192.168.21.121   |Define o FQDN da Web interno usado pelo Skype for Business Web App  <br/> Se você estiver usando o balanceamento de carga DNS nesse pool, seu pool Front-End e seu web farm interno não poderão ter o mesmo FQDN.   ||

&#x2776; Usado por um cliente para descobrir o servidor front-end ou o pool de front-end e ser autenticado e conectado como um usuário. Mais detalhes sobre isso está em [instruções passo a passo dos clientes do Skype for Business que localizam serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; Isso só é necessário para dar suporte a clientes herdados antes do Lync 2013 e aparelhos de mesa.

&#x2778; Na situação em que um dispositivo de comunicação unificada está ativado, mas um usuário nunca se conectou ao dispositivo, o registro a permite que o dispositivo descubra o serviço Web de Hospedagem de dispositivo de hospedagem do servidor e obtenha atualizações. Caso contrário, os dispositivos obtêm essas informações por meio do provisionamento em banda na primeira vez que o usuário faz logon.

O diagrama a seguir mostra um exemplo que inclui registros DNS internos e externos, e muitos dos registros mostrados nas tabelas ao redor: 

**Diagrama da rede de borda que usa endereços IPv4 públicos**

![exemplo de diagrama de rede DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mapeamentos de DNS da rede de perímetro (interfaces interna e externa)**

|Tipo de registro|Valor|Resolve para|Objetivo|Obrigatório|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN do pool de bordas internas  <br/>*EdgePool-int.<span></span>Contoso<span></span>. com*  |Endereços IP do pool de bordas de face interna  <br/> 172.25.33.10, 172.25.33.11   |Endereços IP da interface interna do pool de borda consolidado   |Y   |
|A/AAAA   |FQDN do servidor de borda  <br/>*Desvantagens-1. <span> </span>Contoso<span></span>. com*  |IP do servidor de face interna para um servidor no pool de bordas  <br/> 172.25.33.10   |Crie um registro para cada servidor no pool com o FQDN do servidor apontando para o IP do nó do servidor interno no pool, consulte [balanceamento de carga de DNS nos pools do servidor de borda](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |Acessar FQDN do pool de serviços de borda  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Acessar os endereços IP externos do pool de serviços da borda  <br/> 131.107.16.10, 131.107.16.11   |O serviço de borda de acesso fornece um ponto de conexão confiável e único para tráfego de protocolo de iniciação de sessão de entrada e saída (SIP).   |Y   |
|A/AAAA   |FQDN do pool de serviços da borda de Webconferência  <br/>*Webcon1. <span> </span>Contoso<span></span>. com*  |Endereços IP externos do serviço de borda de Webconferência  <br/> 131.107.16.90, 131.107.16.91   |O serviço de borda de Webconferência permite que usuários externos ingressem em reuniões hospedadas em seu ambiente interno do Skype for Business Server.   |Y   |
|A/AAAA   |*Av.\<SIP-Domain\> * FQDN do pool <br/>*AV1. <span> </span>Contoso<span></span>. com*  |Endereços IP externos de borda A/V  <br/> 131.107.16.170, 131.107.16.171   |O serviço de borda a/V torna o compartilhamento de áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos disponível para usuários externos.   |Y   |
|CNAME   |SPI. * \<sipdomain\>* <br/> SPI. * <span> </span>Contoso<span></span>. com*  |FQDN do pool de Borda de acesso externo  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Localiza o pool do servidor de borda. Veja o [passo a passo dos clientes do Skype for Business que localizam serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SPI. \_TLS. * \<sipdomain\> * <br/>\_SPI. \_TLS. <span> </span> *Contoso<span></span>. com*  |FQDN de borda de acesso externo  <br/>_Access1. <span> </span>Contoso<span></span>. com_  |Usado para acesso de usuários externos. Veja o [passo a passo dos clientes do Skype for Business que localizam serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  |FQDN de borda de acesso externo  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Usado para federação e conectividade de IM pública   |&#x2776;  |
|SRV   |\_XMPP-Server. \_TCP. *<sipdomain\> * <br/>\_XMPP-Server. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN de borda de acesso externo  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |O serviço de proxy do XMPP aceita e envia mensagens de protocolo de presença e de mensagens extensíveis (XMPP) para e de parceiros federados XMPP configurados.   |Y, para implantar a federação; caso contrário, opcional  <br/> Não está disponível no Skype for Business Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<sipdomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN de borda de acesso externo  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Para dar suporte ao serviço de notificação por push e ao Apple Push Notification Service, crie um registro SRV para cada domínio SIP. &#x2778;  ||
|A/AAAA   |FQDN de serviços Web de pool de front-end externo  <br/>*Web-ext.<span></span>Contoso<span></span>. com*  |Endereço IP público do proxy reverso, proxies para o VIP de serviços Web externos para o seu pool Front-end & # x2776; <br/> proxy 131.107.155.1 para 192.168.21.120   |Interface externa do pool de front-end usado pelo Skype for Business Web App   |Y   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>Contoso<span></span>. com*  |Endereço IP público de proxy reverso, resolve para o VIP de serviços Web externos do seu pool de director, se você tiver um ou para o seu pool de front-end se não tiver um diretor & # x2777; <br/> proxy 131.107.155.1 para 192.168.21.120   | Registro externo para descoberta automática de cliente, também usado pela mobilidade, pelo Skype for Business Web App e pelo Agendador Web App, resolvido pelo servidor de proxy reverso <br/> Para dar suporte ao serviço de notificação por push e ao Apple Push Notification Service, crie um registro SRV para cada domínio SIP que tenha clientes móveis do Microsoft Lync. 3  |Y   |
|A/AAAA   |atendimento. * \<sipdomain\>* <br/> atendimento. * <span> </span>Contoso<span></span>. com*  |Endereço IP público do proxy reverso, resolve para a interface da Web externa do pool de front-ends  <br/> proxy 131.107.155.1 para 192.168.21.120   |Proxy para o serviço Web Skype for Business  <br/> Consulte [URLs simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |discagem.*\<sipdomain\>* <br/> discagem.*<span></span><span></span>contoso. com*  |Endereço IP público do proxy reverso, proxies para a interface da Web externa do pool de front-ends  <br/> proxy 131.107.155.1 para 192.168.21.120   |Proxy para o serviço Web Skype for Business  <br/> Consulte [URLs simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |FQDN do pool de servidores do Office Web Apps  <br/> OWA. <span> </span>Contoso<span></span>. com   | Endereço IP público do proxy reverso, proxies para a interface da Web externa do servidor do Office Web Apps <br/> 131.107.155.1 proxy pra 192.168.1.5   | Endereço VIP do pool de servidores do Office Web Apps <br/> 192.168.1.5   |Define o FQDN do pool do servidor do Office Web Apps   |

&#x2776; É necessário para implantar a Federação, caso contrário, opcional.

&#x2777; Usado por um cliente para descobrir o servidor front-end ou o pool de front-end e ser autenticado e conectado como um usuário.

&#x2778; Este requisito se aplica somente a clientes em dispositivos móveis baseados em Apple ou Microsoft. Dispositivos Android e Nokia Symbian não usam notificação por push.

 Para obter mais detalhes sobre servidores de borda e redes de perímetro, consulte o conteúdo de [planejamento DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) do servidor de borda.

> [!IMPORTANT]
> O Skype for Business Server oferece suporte ao uso de endereçamento IPv6. Veja [Plan for IPv6 in Skype for Business](ipv6.md) para obter detalhes.

> [!IMPORTANT]
> Para obter mais detalhes sobre FQDNs, consulte [DNS basics](basics.md). 

**Split DNS** 
 <a name="BK_split"> </a> de Brain

DNS de dupla personalidade é uma configuração de DNS em que há duas zonas DNS com o mesmo namespace. A primeira zona DNS trata as solicitações internas, enquanto a segunda zona DNS trata as solicitações externas, conforme mencionado nas tabelas. Para saber mais sobre isso, consulte [DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considerações sobre o híbrido
<a name="BK_Hybrid"> </a>

Se você pretende ter alguns usuários online e alguns hospedados no local, consulte o artigo planejamento de conectividade híbrida [Skype for Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Será preciso configurar o DNS normalmente para o Skype for Business Server 2015 e também adicionar outros registros DNS.

Você também deve consultar "URLs e intervalos de endereços IP do Office 365" [https://aka.ms/o365ips](https://aka.ms/o365ips) em para confirmar que os usuários terão acesso aos recursos online necessários.

## <a name="simple-urls"></a>URLs simples 
<a name="BK_Simple"> </a>

A URL (Uniform Resource Locator) é uma referência a um recurso da Web que especifica sua localização em uma rede de computadores e um protocolo usado para recuperá-lo. 

O Skype for Business Server oferece suporte ao uso de três URLs "simples" para acessar serviços:

- **Meet** é usado como URL de base para todas as conferências no site. Um exemplo de uma URL de reunião simples é https<span></span>//<span></span>: encontro. <span> </span>Contoso<span></span>. com. Uma URL para uma reunião específica pode ser https:<span></span>//<span></span>cumpri-la. <span> </span>Contoso<span></span>. com/_nome_do_usuário_/7322994.

    Com a URL simples Meet, é fácil compreender e divulgar links para ingressar em reuniões.

- **Dial-in** permite o acesso à página da Web Configurações de Conferência Discada. Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência. A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias. Um exemplo da URL simples discada é https://<span></span>dial-in. <span> </span>Contoso<span></span>. com.

- O **administrador** permite acesso rápido ao painel de controle do Skype for Business Server. Em qualquer computador dentro dos firewalls da sua organização, um administrador pode abrir o painel de controle do Skype for Business Server digitando a URL simples do administrador em um navegador. A URL simples de Admin é parte interna da sua organização. Um exemplo da URL simples de administrador é o<span></span>administrador do https://. <span> </span>Contoso<span></span>. com.

As URLs simples são discutidas com mais detalhes em [requisitos de DNS para URLs simples no Skype for Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS por função de servidor
<a name="BK_Servers"> </a>

Você pode definir os nomes desses pools e servidores como deseja, mas eles devem ser fáceis de lembrar e refletir sua função no sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS de servidores individuais ou pools

Esses requisitos de registro genéricos se aplicam a qualquer função de servidor usada pelo Skype for Business. Um pool é um conjunto de servidores que executa os mesmos serviços que funcionam juntos para tratar as solicitações de clientes direcionadas a eles por meio de um balanceador de carga. Veja [Load balancing requirements for Skype for Business](load-balancing.md) para obter detalhes.

**Requisitos de registro DNS para funções de servidor/pool (supõe o balanceamento de carga DNS)**

|Cenário da implantação|Requisitos de DNS|
|:-----|:-----|
|Um servidor:  <br/> Chat persistente, diretor, servidor de mediação, servidor front-end   |Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) do servidor para seu endereço IP.  <br/> ServerRole. <span> </span>Contoso<span></span>. com 10.10.10.0   |
|Pool:  <br/> Chat persistente, diretor, servidor de borda, servidor de mediação, front-end    |Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) de cada nó do servidor no pool para seu endereço IP.  <br/>**Exemplo** <br/> ServerRole01. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>Contoso<span></span>. com 10.10.10.2  <br/> Vários registros A internos que resolvem o nome de domínio totalmente qualificado (FQDN) do pool para os endereços IP dos nós do servidor no pool.  <br/>**Exemplo** <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Tópicos sobre DNS específicos do Servidor de Borda

 Para planejar a implantação do servidor de borda, revisar o [plano de implantações do servidor de borda no Skype for Business server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)e o [planejamento de DNS do servidor de borda avançado para o Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , que tem as seguintes seções

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuração automática sem DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


