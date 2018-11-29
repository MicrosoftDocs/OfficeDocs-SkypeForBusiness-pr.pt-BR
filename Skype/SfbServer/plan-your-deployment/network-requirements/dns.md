---
title: Requisitos de DNS para Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumo: Revise as considerações de DNS neste tópico antes de implementar Skype para Business Server.'
ms.openlocfilehash: 20e520d0ecb43d098855c434db740592eb7c760c
ms.sourcegitcommit: 042717530bffa18ca401ad6665a652212a85bc99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2018
ms.locfileid: "26984745"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos de DNS para Skype para Business Server

**Resumo:** Revise as considerações de DNS neste tópico antes de implementar Skype para Business Server.

Este artigo aborda apenas Planejando o DNS para Skype para implantações de Business Server na rede de no local de uma organização. Para Skype para Business Online, consulte a "IP e URLs do Office 365 intervalos de endereços" em [https://aka.ms/o365ips](https://aka.ms/o365ips).

Um servidor DNS (serviço) do nome de domínio mapeia nomes de host (como www.<span> </span> Contoso<span></span>. com, provavelmente um servidor web) para endereços IP (por exemplo, 10.10.10.10). Eles ajuda na comunicação entre os clientes e servidores interdependentes na rede Quando você configura uma implementação do Skype para Business Server 2015, você precisará certificar-se de que o mapeamento de novos nomes de servidor (geralmente refletindo a função que eles vai ser espalham) coincide com os endereços IP atribuídos a eles.

Isso pode parecer desanimador bit em um primeiro momento, o trabalho pesado para o planejamento, isso pode ser feito usando o [Skype para ferramenta de planejamento do Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Depois de responder às perguntas do assistente sobre os recursos que pretende usar, para cada local que definir, você poderá exibir o Relatório de DNS no Relatório de administração de borda e usar as informações fornecidas nele para criar seus registros DNS. Também é possível ajustar muitos dos nomes e endereços IP usados. Para obter detalhes, consulte [Examinar o relatório de DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Lembre-se de que você pode exportar o Relatório de administração de borda em uma planilha do Excel, e o Relatório de DNS será uma das planilhas no arquivo. Enquanto esta ferramenta inclui recursos [preteridos do Skype para Business Server 2019](../../../SfBServer2019/deprecated.md), ele ainda pode ser usado para criar um plano de inicial, se esses recursos não estão selecionados.

Quando você estiver instalando uma nova implementação, conforme descrito em [criar registros DNS para Skype para Business Server](../../deploy/install/create-dns-records.md) e criar sua topologia para o Skype para Business Server, reconhecemos que você pode optar por usar os recursos DNS feitos no Windows Server 2016 ou um pacote DNS de terceiros, portanto, vamos manter as discussões neste artigo gerais em vez de específicos. Vamos detalhar o que é necessário, e você decide como vai suprir essas necessidades.

Skype experiente para administradores corporativos, Lync e Office Communications Suite provavelmente achará as tabelas a seguir úteis. Se a tabela parecer confusa, as seções ou os artigos posteriores poderão esclarecer os seguintes conceitos:

## <a name="summary-tables"></a>Tabelas de resumo
<a name="BK_Summary"> </a>

As tabelas a seguir mostram os registros DNS que Skype para Business Server usa para fornecer serviços a usuários. Alguns são opcionais, pois são necessários apenas para dar suporte a determinados recursos, e podem ser ignorados casos esses recursos não sejam desejados. Os registros DNS necessários somente para acesso interno estão na primeira tabela, as implantações que permitem o acesso interno e externo precisarão de registros das duas tabelas.

**Mapeamentos internos de DNS**

|Tipo de registro|Valor|Resolve para|Objetivo|Obrigatório|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN do pool Front End  <br/> *FE-pool. <span> </span>contoso<span></span>.com*   |Endereços IP servidor do Front End pool  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*   |Balanceamento de carga de DNS de Pools de Front-Ends. Mapeia o nome do Pool de Front-Ends para um conjunto de endereços IP. <br/> Consulte [A implantação do balanceamento de carga DNS em pools do Diretor e pools de Front-End](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | FQDN de cada servidor Front-End ou servidor Standard Edition em um pool ou um servidor autônomo <br/>  *FE01. <span> </span>contoso. <span> </span>com FE02. <span> </span>contoso<span></span>.com FE03. <span> </span>contoso<span></span>.com*   |IP correspondente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Mapeia o nome do servidor para seu endereço IP.   |Y   |
|A/AAAA   |FQDN de substituição de serviços Web internos do pool Enterprise  <br/> *Web-int.<span></span>contoso<span></span>.com*   |VIP HLB para serviços de Web internos do servidor Front-End  <br/> *192.168.21.120*   |Necessário para habilitar o cliente para o tráfego de web server, como baixar o Skype para negócios Web App. Também é necessário para clientes Mobile.   |Y   |
|A/AAAA   |FQDN de substituição de serviços Web externos do pool Enterprise  <br/> *Ramal de Web<span></span>contoso<span></span>.com*   |VIP HLB para serviços de Web externos do servidor Front-End  <br/>*68.123.56.90*   |Necessário para habilitar o cliente para o tráfego de web server, como baixar o Skype para negócios Web App. Necessário caso os clientes móveis resolvam o DNS internamente. Pode resolver para IP da Internet ou IP de proxy reverso DMZ.   ||
|A/AAAA   | FQDN do servidor back End do SQL Server <br/> *SQL1. <span> </span>contoso<span></span>.com*   |endereço IP do servidor  <br/> *192.168.11.90*   |Mapeia o nome do servidor para um servidor SQL de back-end como trabalhar com o pool de Front-End como o respectivo endereço IP   ||
|A/AAAA   |FQDN do servidor back End do servidor espelho SQL  <br/> *SQL2. <span> </span>contoso<span></span>.com*   |endereço IP do servidor  <br/> *192.168.11.91*   |Mapeia o nome do servidor para um servidor de espelho do SQL de back-end como trabalhar com o pool de Front-End como o respectivo endereço IP   ||
|A/AAAA   |FQDN do pool de diretor  <br/>**Observação:** Não aplicável ao usar um servidor de diretor autônomo <br/> *DirPool. <span> </span>contoso<span></span>.com*   |Endereços IP do pool de diretor  <br/> DNS LB *192.168.21.132, 192.168.21.133* , 192.168.21.134   |Balanceamento de carga DNS de servidores do Pool de Diretores. Mapeamentos de nome de pool para o pool de diretor para um endereço IP, consulte [Implantando o balanceamento de carga do DNS em Pools de Front-Ends e Pools de diretor](load-balancing.md#BK_FE_Dir) <br/> Um Diretor pode autenticar um usuário e é opcional.   ||
|A/AAAA   |FQDN do Diretor   |Endereço IP do servidor de cada servidor do Diretor   |Mapeamentos de nome de pool para o Diretor como um endereço IP, consulte [Implantando o balanceamento de carga do DNS em Pools de Front-Ends e Pools de diretor](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN de pool de servidor de mediação   |Endereços IP do pool   |A função de Servidor de Mediação é opcional. Você pode colocalizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [usando o DNS com carga balanceada em Pools de servidor de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do servidor de mediação   |Endereço IP do servidor   |Você pode colocalizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [usando o DNS com carga balanceada em Pools de servidor de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do servidor de bate-papo persistente   |Endereço de IP do servidor de bate-papo persistente   |Um servidor de Chat Persistente é necessário para o recurso de Chat Persistente; em outros contextos, é opcional.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. * <span> </span>contoso<span></span>.com*   |Pool de Front-End do HLB VIP ou IP do Diretor  <br/>  192.168.21.121  |Obter interno AutoDiscover Service1, necessários para o suporte à mobilidade. Se o DNS interno é usado para resolver para dispositivos móveis, ele deve apontar para o IP externo, ou DMZ VIP.  <br/> Para serviços Web solicitamos HLB no pool de Front-End, como HTTPS não podem utilizar o DNS. Para o pool de Front-End ou pool de diretores, que isso deve resolve um VIP HLB ou um IP regular para um servidor Standard edition ou um servidor de diretor autônomo.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>.com*   |FQDN do pool FE HLB ou FQDN do Diretor  <br/> Web-int.<span></span>contoso<span></span>.com   |Service1 de descoberta automática interno <br/> Se desejar, você poderá implementar isso como um CNAME, em vez de um registro A.   ||
|A/AAAA   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>.com*  |Pool Front-End server IP (como um cada IP do Diretor endereço ou)  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*   |Necessário para a configuração automática, consulte [passo a passo do Skype para clientes corporativos localizar serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Um ou mais registros apontando para os servidores do pool de Front-End ou diretor servidores na rede interna ou o serviço de borda de acesso quando o cliente é externo   |& #x 2777;  |
|A/AAAA   |ucupdates-r2. * \<sipdomain\>* <br/> ucupdates-r2. * <span> </span>contoso<span></span>.com*  |VIP do pool FE HBL ou VIP HLB do pool de Diretor ou IP do servidor SE/Diretor  <br/>  192.168.21.121  |Implantando a esse registro é opcional & #x 2778;  ||
|SRV   |\_sipinternaltls. \_tcp. * \<sipdomain\> * <br/>Porta 5061 <br/>\_sipinternaltls. \_tcp. * <span> </span>contoso<span></span>.com* <br/>Porta 5061  |FQDN do pool Front End  <br/>*FE-Pool. <span> </span>contoso<span></span>.com*  |Habilita o logon automático de usuários internos1 no servidor/pool front-end ou servidor/pool SE que autentica e redireciona as solicitações de logon de clientes.    |& #x 2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *contoso<span></span>.com*  |FQDN do pool Front End  <br/>_FE-Pool. <span> </span>contoso<span></span>.com_  |Acesso de usuário interno & #x 2776;  |& #x 2777;  |
|SRV   | \_NTP. \_udp. * \<sipdomain\> * <br/> \_NTP. \_udp. <span> </span> *contoso<span></span>.com*  |FQDN do servidor de horário  <br/> north-america.pool.ntp.org   |Origem NTP necessário para os dispositivos Lync Phone Edition   |Isso é necessário para dar suporte a aparelhos de telefone da área de trabalho.   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>.com*  | FQDN do serviço de borda de acesso <br/> EdgePool-int.<span></span>*contoso<span></span>.com*  |Criar um registro SRV para cada domínio SIP que tem clientes móveis iOS ou Windows Phone.   |Para suporte a clientes móveis   |
|A/AAAA   |URL do administrador  <br/>*Web-int.<span></span>contoso<span></span>.com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Skype para painel de controle do Business Server, consulte [As URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL da reunião  <br/>*Web-int.<span></span>contoso<span></span>.com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Reuniões online, consulte [As URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de discagem  <br/>*Web-int.<span></span>contoso<span></span>.com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Conferência discada, consulte [As URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN dos serviços Web internos  <br/>*Web-int.<span></span>contoso<span></span>.com*  |VIP do pool FE HLB  <br/> 192.168.21.121   |Skype para serviço Web de negócios usado pelo Skype para negócios Web App   ||
|A/AAAA   |FQDN do pool do Office Web Apps Server  <br/> OWA. <span> </span>contoso<span></span>.com   | Pool do Office Web Apps Server endereço VIP <br/> 192.168.1.5   |Define o FQDN do pool de servidor do Office Web Apps   ||
|A/AAAA   |  FQDN da Web interno <br/> Web-int.<span></span>contoso<span></span>.com   | Pool Front-End endereço VIP <br/> 192.168.21.121   |Define o FQDN de Web interno usado pelo Skype para negócios Web App  <br/> Se você estiver usando o balanceamento de carga DNS nesse pool, seu pool Front-End e seu web farm interno não poderão ter o mesmo FQDN.   ||

& #x 2776; Usado por um cliente para descobrir o pool de Front-End ou de servidor Front-End e ser autenticado e conectado como um usuário. Mais detalhes sobre esse estão em [passo a passo do Skype para clientes corporativos localizar serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

& #x 2777; Isso só é necessário para dar suporte a clientes herdados antes do Lync 2013 e fones de área de trabalho.

& #x 2778; Na situação em que um dispositivo de comunicação unificada é ativado, mas um usuário nunca tiver feito logon no dispositivo, o registro permite que o dispositivo descobrir o servidor que hospeda o serviço Web de atualização de dispositivo e obtenham atualizações. Caso contrário, os dispositivos obtêm essas informações por meio do provisionamento em banda na primeira vez que o usuário faz logon.

O diagrama a seguir mostra um exemplo que inclui registros DNS internos e externos, e muitos dos registros mostrados nas tabelas ao redor: 

**Diagrama da rede de borda que usa endereços IPv4 públicos**

![exemplo de diagrama de rede de DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mapeamentos de DNS da rede de perímetro (interfaces interna e externa)**

|Tipo de registro|Valor|Resolve para|Objetivo|Obrigatório|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN do pool de borda interna  <br/>*EdgePool-int.<span></span>contoso<span></span>.com*  |Internal voltado para endereços IP de pool de borda  <br/> 172.25.33.10, 172.25.33.11   |Endereços IP da interface interna do pool de borda consolidado   |Y   |
|A/AAAA   |FQDN do servidor de borda  <br/>*Contras-1. <span> </span>contoso<span></span>.com*  |IP do servidor interno voltados para um servidor no pool de borda  <br/> 172.25.33.10   |Criar um registro para cada servidor no pool com o FQDN do servidor apontando para seu IP de nó de servidor interno no pool, consulte [Balanceamento de carga de DNS em Pools de servidor de borda](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |FQDN do Pool do serviço de borda de acesso  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Endereços de IP de acesso externo de Pool de serviço de borda  <br/> 131.107.16.10, 131.107.16.11   |O serviço de borda de acesso fornece um ponto de conexão único e confiável para o tráfego de protocolo de iniciação de sessão (SIP) de entrada e saída.   |Y   |
|A/AAAA   |Serviço de borda de webconferência FQDN do Pool da Web  <br/>*Webcon1. <span> </span>contoso<span></span>.com*  |Endereços de IP de Web externa de serviço de borda de webconferência  <br/> 131.107.16.90, 131.107.16.91   |O serviço de borda de webconferência permite que os usuários externos ingressem em reuniões hospedadas em sua Skype interno para ambiente de servidor de negócios.   |Y   |
|A/AAAA   |*antivírus.\<domínio sip\> * FQDN do pool <br/>*AV1. <span> </span>contoso<span></span>.com*  |Endereços IP externos de borda A/V  <br/> 131.107.16.170, 131.107.16.171   |A / serviço de borda V torna áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos disponíveis para usuários externos.   |Y   |
|CNAME   |SIP. * \<sipdomain\>* <br/> SIP. * <span> </span>contoso<span></span>.com*  |FQDN do pool de Borda de acesso externo  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Localiza o pool do servidor de borda. Consulte [passo a passo do Skype para clientes corporativos localizando serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_tls. * \<sipdomain\> * <br/>\_SIP. \_tls. <span> </span> *contoso<span></span>.com*  |FQDN de borda de acesso externo  <br/>_Access1. <span> </span>contoso<span></span>.com_  |Usado para o acesso de usuários externos Consulte [passo a passo do Skype para clientes corporativos localizando serviços](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>.com*  |FQDN de borda de acesso externo  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Usado para federação e conectividade de IM pública   |& #x 2776;  |
|SRV   |\_servidor de XMPP. \_tcp. *<sipdomain\> * <br/>\_servidor de XMPP. \_tcp. * <span> </span>contoso<span></span>.com*  |FQDN de borda de acesso externo  <br/>*Access1. <span> </span>contoso<span></span>.com*  |O serviço de Proxy XMPP aceita e envia mensagens de protocolo XMPP de presença e mensagem extensível e para parceiros federados XMPP configurados.   |Y, para implantar a federação; caso contrário, opcional  <br/> Não está disponível no Skype para Business Server 2019.|
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. * <span> </span>contoso<span></span>.com*  |FQDN de borda de acesso externo  <br/>*Access1. <span> </span>contoso<span></span>.com*  |Para suportar o serviço de notificação de Push e Apple Push Notification service, você deve criar um registro SRV para cada domínio SIP. & #x 2778;  ||
|A/AAAA   |FQDN de serviços web externos de pool de Front-End  <br/>*Ramal de Web<span></span>contoso<span></span>.com*  |Endereço IP público do proxy reverso, proxies para o VIP de serviços Web externos para seu pool de Front-End & #x 2776; <br/> 131.107.155.1 proxy de para 192.168.21.120   |Front End pool interface externa usado pelo Skype para negócios Web App   |Y   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. * <span> </span>contoso<span></span>.com*  |Reverter o endereço IP público do proxy, resolve para o VIP de serviços Web externos para seu pool de diretor, se você tiver um, ou para seu pool de Front-End, se você não tiver um diretor & #x 2777; <br/> 131.107.155.1 proxy de para 192.168.21.120   | Registro externo para o cliente de descoberta automática, também é usada pelo mobilidade, Skype para negócios Web App e Agendador Web app, resolvido pelo servidor proxy reverso <br/> Para suportar o serviço de notificação de Push e Apple Push Notification service, você deve criar um registro SRV para cada domínio SIP que possui clientes do Microsoft Lync Mobile. 3  |Y   |
|A/AAAA   |atende. * \<sipdomain\>* <br/> atende. * <span> </span>contoso<span></span>.com*  |Reverter o endereço IP público do proxy, resolve para a interface externa da Web para o pool de Front-End  <br/> 131.107.155.1 proxy de para 192.168.21.120   |Proxy do Skype para serviço Web de negócios  <br/> Consulte [as URLs simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |dial-in.*\<sipdomain\>* <br/> dial-in.*<span></span>contoso<span></span>.com*  |Reverter o endereço IP público do proxy, proxies para a interface externa da Web para o pool de Front-End  <br/> 131.107.155.1 proxy de para 192.168.21.120   |Proxy do Skype para serviço Web de negócios  <br/> Consulte [as URLs simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |FQDN do pool do Office Web Apps Server  <br/> OWA. <span> </span>contoso<span></span>.com   | Endereço IP público do proxy reverso, proxies para a interface externa da Web para o Office Web Apps Server <br/> 131.107.155.1 proxy pra 192.168.1.5   | Pool do Office Web Apps Server endereço VIP <br/> 192.168.1.5   |Define o FQDN do pool de servidor do Office Web Apps   |

& #x 2776; Necessário para implantar a federação, caso contrário, é opcional.

& #x 2777; Usado por um cliente para descobrir o servidor front-end ou um pool de Front-End e ser autenticado e conectado como um usuário.

& #x 2778; Esse requisito se aplica somente a clientes no Apple ou Microsoft com base em dispositivos móveis. Dispositivos Android e Nokia Symbian não usam notificação por push.

 Para obter mais detalhes sobre redes de perímetro e servidores de borda, consulte o conteúdo de [planejamento de DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) do servidor de borda.

> [!IMPORTANT]
> Skype para Business Server suporta o uso de endereçamento IPv6. Veja [Plan for IPv6 in Skype for Business](ipv6.md) para obter detalhes.

> [!IMPORTANT]
> Para obter mais detalhes sobre FQDNs, consulte [DNS basics](basics.md). 

**Dividir brain DNS** 
 <a name="BK_split"> </a>

DNS de dupla personalidade é uma configuração de DNS em que há duas zonas DNS com o mesmo namespace. A primeira zona DNS trata as solicitações internas, enquanto a segunda zona DNS trata as solicitações externas, conforme mencionado nas tabelas. Para saber mais sobre isso, consulte [DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considerações sobre o híbrido
<a name="BK_Hybrid"> </a>

Se você pretende ter alguns usuários hospedagem online e alguns hospedados no local, consulte a conectividade híbrida artigos de planejamento para [Skype para Business Server 2015](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_DNS) e [Skype para Business server 2019](../../../SfBServer2019/hybrid/hybrid-solutions.md). Você precisará configurar o DNS como de costume para Skype para Business Server 2015 e também adicionar registros DNS adicionais.

Você também deve consultar a "IP e URLs do Office 365 intervalos de endereços" em [https://aka.ms/o365ips](https://aka.ms/o365ips) para confirmar que seus usuários terão acesso aos recursos online que precisarão.

## <a name="simple-urls"></a>URLs simples 
<a name="BK_Simple"> </a>

A URL (Uniform Resource Locator) é uma referência a um recurso da Web que especifica sua localização em uma rede de computadores e um protocolo usado para recuperá-lo. 

Skype para Business Server suporta o uso de três URLs "simples" para serviços do access:

- **Meet** é usado como URL de base para todas as conferências no site. Um exemplo de uma URL reunir simples é https:<span></span>//<span></span>atender. <span> </span>contoso<span></span>. com. Uma URL para uma reunião específica pode ser https:<span></span>//<span></span>atender. <span> </span>contoso<span></span>.com /_username_/7322994.

    Com a URL simples Meet, é fácil compreender e divulgar links para ingressar em reuniões.

- **Dial-in** permite o acesso à página da Web Configurações de Conferência Discada. Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência. A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias. Um exemplo da discagem simple URL é https://<span></span>dialin. <span> </span>contoso<span></span>. com.

- **Admin** permite acesso rápido ao Skype para painel de controle do servidor de negócios. Em qualquer computador dentro dos firewalls da organização, um administrador pode abrir o Skype para painel de controle do Business Server digitando a URL simple do administrador em um navegador. A URL simples de Admin é parte interna da sua organização. Um exemplo de URL simple Admin é https://<span></span>Admin. <span> </span>contoso<span></span>. com.

URLs simples são abordados em mais detalhes [os requisitos de DNS para URLs simples no Skype para Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS por função de servidor
<a name="BK_Servers"> </a>

Você pode definir os nomes desses pools e servidores como deseja, mas eles devem ser fáceis de lembrar e refletir sua função no sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS de servidores individuais ou pools

Esses requisitos de registro genérico se aplicam a qualquer função de servidor usada pelo Skype para negócios. Um pool é um conjunto de servidores que executa os mesmos serviços que funcionam juntos para tratar as solicitações de clientes direcionadas a eles por meio de um balanceador de carga. Veja [Load balancing requirements for Skype for Business](load-balancing.md) para obter detalhes.

**Requisitos de registro DNS para funções de servidor/pool (supõe o balanceamento de carga DNS)**

|Cenário da implantação|Requisitos de DNS|
|:-----|:-----|
|Um servidor:  <br/> Chat persistente, diretor, servidor de mediação, servidor front-end   |Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) do servidor para seu endereço IP.  <br/> ServerRole. <span> </span>contoso<span></span>.com 10.10.10.0   |
|Pool:  <br/> Chat persistente, diretor, servidor de borda, servidor de mediação, front-end    |Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) de cada nó do servidor no pool para seu endereço IP.  <br/>**Exemplo** <br/> ServerRole01. <span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServerRole02. <span> </span>contoso<span></span>.com 10.10.10.2  <br/> Vários registros A internos que resolvem o nome de domínio totalmente qualificado (FQDN) do pool para os endereços IP dos nós do servidor no pool.  <br/>**Exemplo** <br/> ServidorTotal. <span> </span>contoso<span></span>.com 10.10.10.1  <br/> ServidorTotal. <span> </span>contoso<span></span>.com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Tópicos sobre DNS específicos do Servidor de Borda

 Para planejar a implantação de servidor de borda, examine [Plan para implantações de servidor de borda em Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)e [DNS do servidor de borda avançado planejando Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) que tem as seguintes seções

- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuração automática sem DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS de dupla personalidade](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


