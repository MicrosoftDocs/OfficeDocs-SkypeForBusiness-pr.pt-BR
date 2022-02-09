---
title: Requisitos dns para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumo: revise as considerações dns neste tópico antes de implementar Skype for Business Server.'
ms.openlocfilehash: 7637a1842c9ebc96eee95aa9e4fac6d3db376240
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400255"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos dns para Skype for Business Server

**Resumo:** Revise as considerações dns neste tópico antes de implementar Skype for Business Server.

Este artigo aborda apenas o planejamento de DNS Skype for Business Server implantações em uma rede local da organização. Para Skype for Business Online consulte "Office 365 URLs e intervalos de endereços IP" em [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges).

Um servidor dns (serviço de nome de domínio) mapeia nomes de host (como www.<span></span> contoso.com<span></span>, provavelmente um servidor Web) para endereços IP (como 10.10.10.10.10). Ele ajuda clientes e servidores interdependentes a se comunicarem uns com os outros na rede. Ao configurar uma implementação do Skype for Business Server 2015, você precisará certificar-se de que o mapeamento de novos nomes de servidor (geralmente refletindo a função que eles assumirão) corresponde aos endereços IP aos que são atribuídos.

Embora isso possa parecer um pouco assustador no início, o trabalho pesado para planejar isso pode ser feito usando a Ferramenta de Planejamento Skype for Business Server [2015](https://www.microsoft.com/download/details.aspx?id=50357). Depois de passar pelas perguntas do assistente sobre quais recursos você planeja usar, para cada site definido, você pode exibir o Relatório DNS no Relatório de Administração de Borda e usar as informações listadas lá para criar seus registros DNS. Você também pode fazer ajustes em muitos dos nomes e endereços IP usados, para obter detalhes em [Revisar o Relatório DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Lembre-se de que você pode exportar o Relatório de Administração de Borda para uma planilha de Excel, e o Relatório DNS será uma das planilhas no arquivo. Embora essa ferramenta inclua recursos [preterido do Skype for Business Server 2019](../../../SfBServer2019/deprecated.md), ela ainda poderá ser usada para criar um plano inicial se esses recursos não forem selecionados

Ao instalar uma nova implementação, conforme descrito em [Create DNS records for Skype for Business Server](../../deploy/install/create-dns-records.md) e building your topology for Skype for Business Server, reconhecemos que você pode optar por usar os recursos DNS integrados para Windows Server 2016  ou um pacote DNS de terceiros, portanto, manteremos as discussões neste artigo em geral, em vez de específicas. Estamos detalhando o que é necessário e como você atender a essa necessidade é sua decisão a ser tomada.

Os administradores Skype for Business, Lync e Office Communications Suite provavelmente acharão as tabelas a seguir úteis. Se a tabela estiver confusa para você, as seções ou artigos posteriores lançarão alguma luz sobre os seguintes conceitos:

## <a name="summary-tables"></a>Tabelas de resumo
<a name="BK_Summary"> </a>

As tabelas a seguir mostram registros DNS Skype for Business Server usos para fornecer serviços aos usuários. Alguns são opcionais, já que são necessários apenas para dar suporte a determinados recursos e podem ser ignorados se esses recursos não são desejados. Os registros DNS necessários para acesso interno estão apenas na primeira tabela, e uma implantação que permite acesso interno e externo precisará de registros de ambas as tabelas.

**Mapeamentos DNS internos**

|Tipo de Registro|Valor|Resolver para|Objetivo|Obrigatório|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN do pool de front-end  <br/> *Fe-pool.<span></span> contoso.com <span></span>*   |Endereços IP do servidor de pool front-end  <br/>  DNS LB *para 192.168.21.122 192.168.21.123 192.168.21.124*   |Balanceamento de carga DNS de pools front-end. Mapas nome do pool front-end para um conjunto de endereços IP.  <br/> Consulte [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir)  |S   |
|A/AAAA   | FQDN de cada servidor front-end ou Edição Standard servidor em um pool ou um servidor autônomo <br/>  *FE01.<span></span> contoso.<span></span> com FE02.<span></span> contoso.com <span></span> FE03.<span></span> contoso.com <span></span>*   |IP correspondente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Mapas nome do servidor para seu endereço IP.   |S   |
|A/AAAA   |Enterprise Web Services Internos do Pool substituem o FQDN  <br/> *Web-int.<span></span> contoso.com <span></span>*   |VIP HLB para Serviços Web Internos do Servidor Front-End  <br/> *192.168.21.120*   |Necessário para habilitar o cliente para o tráfego web do servidor, como baixar o Skype for Business Web App. Também necessário para clientes Móveis.   |S   |
|A/AAAA   |Enterprise Web Services Externos do Pool substituem O FQDN  <br/> *Web-ext.<span></span> contoso.com <span></span>*   |VIP HLB para Serviços Web Externos do Servidor Front-End  <br/>*68.123.56.90*   |Necessário para habilitar o cliente para o tráfego web do servidor, como baixar o Skype for Business Web App. Obrigatório se os clientes móveis resolverem o DNS internamente. Pode resolver para IP de Proxy Reverso do DMZ ou IP da Internet.   ||
|A/AAAA   | FQDN do servidor SQL back-end <br/> *SQL1.<span></span> contoso.com <span></span>*   |endereço IP do servidor  <br/> *192.168.11.90*   |Mapas nome do servidor para um servidor SQL back-end trabalhando com o pool de Front-End para seu endereço IP   ||
|A/AAAA   |FQDN do SQL servidor back-end  <br/> *SQL2.<span></span> contoso.com <span></span>*   |endereço IP do servidor  <br/> *192.168.11.91*   |Mapas nome do servidor para um servidor espelho SQL back-end trabalhando com o pool de Front-End para seu endereço IP   ||
|A/AAAA   |FQDN do pool de diretores  <br/>**Observação:** Não aplicável ao usar um servidor de Diretor autônomo <br/> *DirPool.<span></span> contoso.com <span></span>*   |Endereços IP do pool de diretores  <br/> DNS LB *para 192.168.21.132, 192.168.21.133, 192.168.21.134*   |Balanceamento de carga DNS dos servidores do Pool de Diretores. Mapas nome do pool para o pool de Diretores em um endereço IP, consulte [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir) <br/> Um Diretor pode autenticar um usuário e é opcional.   ||
|A/AAAA   |FQDN do Diretor   |Endereço IP do servidor de cada servidor Diretor   |Mapas nome do pool para o Diretor em um endereço IP, consulte [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN do pool do Servidor de Mediação   |Endereços IP do pool   |A função servidor de mediação é opcional. Você pode co-localizar os serviços fornecidos por um servidor de mediação para o servidor front-end ou pool. Consulte [Usando o balanceamento de carga DNS em pools de servidores de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do Servidor de Mediação   |Endereço IP do servidor   |Você pode co-localizar os serviços fornecidos por um servidor de mediação para o servidor front-end ou pool. Consulte [Usando o balanceamento de carga DNS em pools de servidores de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do Servidor de Chat Persistente   |Endereço IP do Servidor de Chat Persistente   |Um servidor de Chat Persistente é necessário para o recurso Chat Persistente e é opcional.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso.com <span></span>*   |VIP do pool de front-end do HLB ou IP do diretor  <br/>  192.168.21.121  |Serviço De Descoberta Automática Interno1, necessário para suporte à Mobilidade. Se o DNS interno for usado para resolver dispositivos móveis, ele deverá apontar para o IP externo ou VIP DMZ.  <br/> Para serviços Web, exigimos HLB no pool de Front-End, pois HTTPS não pode aproveitar o DNS. Para pool de Front-End ou pool de Diretores, isso deve ser resolvido para um VIP HLB ou um IP regular para um servidor Standard edition ou um servidor diretor autônomo.   |Y   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso.com <span></span>*   |FQDN do Pool FE do HLB ou FQDN do Diretor  <br/> Web-int.<span></span> contoso.com<span></span>   |Serviço De Descoberta Automática Interno1 <br/> Você pode implementá-lo como um CNAME em vez de um registro A, se desejado.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span>contoso.com <span></span>*  |Endereços IP do servidor de pool front-end (ou para cada endereço IP do Diretor)  <br/>  DNS LB *para 192.168.21.122 192.168.21.123 192.168.21.124*   |Obrigatório para configuração automática, consulte Passo a passo [de Skype for Business serviços de localização de clientes](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Um registro ou registros apontando para os servidores de pool front-end ou servidores diretores na rede interna ou o serviço de Borda de Acesso quando o cliente é externo   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span>contoso.com <span></span>*  |VIP do Pool de FE do HLB ou VIP do Pool de Diretores HLB ou IP ES/Diretor Server  <br/>  192.168.21.121  |Implantar esse registro é opcional &#x2778;  ||
|SRV   |\_sipinternaltls.\_ tcp.*\<sipdomain\>* <br/>Porta 5061 <br/>\_sipinternaltls.\_ tcp. *<span></span>contoso.com <span></span>* <br/>Porta 5061  |FQDN do pool de front-end  <br/>*FE-Pool.<span></span> contoso.com <span></span>*  |Habilita a entrada automática do usuário interno 1 para o servidor/pool de front-end ou ES servidor/pool que autentica e redireciona solicitações de cliente para entrada.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal.<span></span> *contoso.com <span></span>*  |FQDN do pool de front-end  <br/>_FE-Pool.<span></span> contoso.com <span></span>_  |Acesso de usuário interno &#x2776;  |&#x2777;  |
|SRV   | \_ntp.\_ udp.*\<sipdomain\>* <br/> \_ntp.\_ udp.<span></span> *contoso.com <span></span>*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Fonte NTP necessária para dispositivos Lync Telefone Edition   |Isso é necessário para dar suporte a handsets da área de trabalho.   |
|SRV   |\_sipfederationtls.\_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls.\_ tcp.<span></span> *contoso.com <span></span>*  | FQDN do serviço de Borda de Acesso <br/> EdgePool-int.<span></span> *contoso.com <span></span>*  |Crie um registro SRV para cada domínio SIP que tenha clientes IOS ou Windows Phone Mobile.   |Para suporte ao cliente móvel   |
|A/AAAA   |URL do administrador  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype for Business Server Painel de Controle, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |atender URL  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Reuniões online, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL discado  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Conferência discda, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN de Serviços Web internos  <br/>*Web-int.<span></span> contoso.com <span></span>*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Skype for Business Web usado por Skype for Business Web App   ||
|A/AAAA   |Office FQDN do pool do Servidor web Apps  <br/> OWA.<span></span> contoso.com<span></span>   | Office endereço VIP do pool do Servidor web Apps <br/> 192.168.1.5   |Define o FQDN do pool Office Web Apps Server   ||
|A/AAAA   | FQDN Da Web Interno <br/> Web-int.<span></span> contoso.com<span></span>   | Endereço VIP do pool front-end <br/> 192.168.21.121   |Define o FQDN Da Web Interno usado por Skype for Business Web App  <br/> Se você estiver usando o balanceamento de carga DNS neste pool, o pool de Front-End e o farm web interno não poderão ter o mesmo FQDN.   ||

&#x2776; usado por um cliente para descobrir o Servidor Front-End ou o pool de Front-End e ser autenticado e entrar como usuário. Mais detalhes sobre isso estão em [Passo a passo dos serviços Skype for Business de localização de clientes](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; Isso só é necessário para dar suporte a clientes herdados antes do Lync 2013 e dos handsets da área de trabalho.

&#x2778; Na situação em que um dispositivo de Comunicações Unificadas está ligado, mas um usuário nunca fez logoff no dispositivo, o registro A permite que o dispositivo descubra o servidor que hospeda o serviço Web de Atualização de Dispositivo e obtenha atualizações. Caso contrário, os dispositivos obtêm as informações do servidor através do provisionamento em banda na primeira vez que um usuário faz logon.

O diagrama a seguir mostra um exemplo que inclui registros DNS internos e externos e muitos dos registros mostrados nas tabelas ao redor:

**Diagrama de rede de borda usando endereços IPv4 públicos**

![exemplo de diagrama de rede DNS.](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mapeamentos DNS de rede de perímetro (interfaces internas e externas)**

|Tipo de Registro|Valor|Resolver para|Objetivo|Obrigatório|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN do pool de borda interno  <br/>*EdgePool-int.<span></span> contoso.com <span></span>*  |Endereços IP do pool de Borda voltados para dentro  <br/> 172.25.33.10, 172.25.33.11   |Endereços IP da interface interna do Pool de Borda Consolidados   |S   |
|A/AAAA   |FQDN do Servidor de Borda  <br/>*Cons-1.<span></span> contoso.com <span></span>*  |IP do servidor voltado para interno para um servidor no pool de Borda  <br/> 172.25.33.10   |Crie um registro para cada servidor no pool com o FQDN do servidor apontando para seu IP do nó do servidor interno no pool, consulte [Dns Load Balancing on Edge Server Pools](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |FQDN do Pool de Serviços de Borda de Acesso  <br/>*Access1.<span></span> contoso.com <span></span>*  |Acessar endereços IP externos do Pool de Serviços de Borda  <br/> 131.107.16.10, 131.107.16.11   |O Serviço de Borda de Acesso fornece um ponto de conexão único e confiável para o tráfego de saída e de entrada do protocolo SIP.   |S   |
|A/AAAA   |FQDN do Pool de Serviços de Borda de WebConferência  <br/>*Webcon1.<span></span> contoso.com <span></span>*  |Endereços IP externos do serviço de Borda de WebConferência  <br/> 131.107.16.90, 131.107.16.91   |O serviço de Borda de WebConferência permite que usuários externos participem de reuniões hospedadas em seu ambiente interno Skype for Business Server ambiente.   |S   |
|A/AAAA   |*av.\<sip-domain\>* FQDN do pool <br/>*AV1.<span></span> contoso.com <span></span>*  |Endereços IP externos de Borda A/V  <br/> 131.107.16.170, 131.107.16.171   |O serviço de Borda A/V disponibiliza áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos para usuários externos.   |S   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span>contoso.com <span></span>*  |FQDN do Pool de Borda de Acesso Externo  <br/>*Access1.<span></span> contoso.com <span></span>*  |Localiza o pool do Servidor de Borda . Consulte [Passo a passo de Skype for Business serviços de localização de clientes](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |S   |
|SRV   |\_sip.\_ tls.*\<sipdomain\>* <br/>\_sip.\_ tls.<span></span> *contoso.com <span></span>*  |FQDN de Borda de Acesso Externo  <br/>_Access1.<span></span> contoso.com <span></span>_  |Usado para acesso de usuário externo. Consulte [Passo a passo de Skype for Business serviços de localização de clientes](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls.\_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls.\_ tcp.<span></span> *contoso.com <span></span>*  |FQDN de Borda de Acesso Externo  <br/>*Access1.<span></span> contoso.com <span></span>*  |Usado para federação e conectividade de IM pública   |&#x2776;  |
|SRV   |\_xmpp-server.\_ tcp. *<sipdomain\>* <br/>\_xmpp-server.\_ tcp. *<span></span>contoso.com <span></span>*  |FQDN de Borda de Acesso Externo  <br/>*Access1.<span></span> contoso.com <span></span>*  |O serviço proxy XMPP aceita e envia mensagens extensíveis e mensagens de protocolo de presença (XMPP) para e de parceiros federados XMPP configurados.   |Y, para implantar Federação, caso contrário, opcional  <br/> Não disponível no Skype for Business Server 2019.|
|SRV   |\_sipfederationtls.\_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls.\_ tcp. *<span></span>contoso.com <span></span>*  |FQDN de Borda de Acesso Externo  <br/>*Access1.<span></span> contoso.com <span></span>*  |Para dar suporte ao Serviço de Notificação por Push e ao serviço de Notificação por Push da Apple, crie um registro SRV para cada domínio SIP. &#x2778;  ||
|A/AAAA   |FQDN do FQDN do pool front-end externo  <br/>*Web-ext.<span></span> contoso.com <span></span>*  |Endereço IP público de proxy reverso, proxies para o VIP de Serviços Web Externos para seu pool de front-end &#x2776; <br/> Proxy 131.107.155.1 para 192.168.21.120   |Interface externa do pool de front-end usada por Skype for Business Web App   |S   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span>contoso.com <span></span>*  |Endereço IP público de proxy reverso, resolve para o VIP de Serviços Web Externos para seu pool de Diretores, se você tiver um ou para seu pool de Front-End se você não tiver um diretor &#x2777; <br/> Proxy 131.107.155.1 para 192.168.21.120   | Registro externo para a Descoberta Automática do cliente, também usado pelo aplicativo Web Mobility, Skype for Business Web App e agendador, resolvido pelo servidor proxy reverso <br/> Para dar suporte ao Serviço de Notificação por Push e ao serviço de Notificação por Push da Apple, crie um registro SRV para cada domínio SIP que tenha clientes do Microsoft Lync Mobile. 3  |Y   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span>contoso.com <span></span>*  |Endereço IP público de proxy reverso, resolvido para a interface da Web externa para o pool de Front-End  <br/> Proxy 131.107.155.1 para 192.168.21.120   |Proxy para Skype for Business Web  <br/> Consulte [URLs simples](dns.md#BK_Simple)  |Y   |
|A/AAAA   |discagem.*\<sipdomain\>* <br/> discagem. *<span></span>contoso.com <span></span>*  |Endereço IP público de proxy reverso, proxies para a interface Web externa para o pool de Front-End  <br/> Proxy 131.107.155.1 para 192.168.21.120   |Proxy para Skype for Business Web  <br/> Consulte [URLs simples](dns.md#BK_Simple)  |S   |
|A/AAAA   |Office FQDN do pool do Servidor web Apps  <br/> OWA.<span></span> contoso.com<span></span>   | Endereço IP público de proxy reverso, proxies para a interface web externa para o servidor Office Web Apps <br/> Proxy 131.107.155.1 para 192.168.1.5   | Office endereço VIP do pool do Servidor web Apps <br/> 192.168.1.5   |Define o FQDN do pool Office Web Apps Server   |

&#x2776; necessário para implantar Federação, caso contrário, opcional.

&#x2777; usado por um cliente para descobrir o servidor front-end ou o pool de Front-End e ser autenticado e assinado como um usuário.

&#x2778; Esse requisito se aplica somente a clientes em dispositivos móveis baseados na Apple ou na Microsoft. Dispositivos Android e Nokia Symbian não usam notificação por push.

 Para obter mais detalhes sobre Servidores de Borda e redes de perímetro, consulte o conteúdo de planejamento [DNS do servidor de](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) Borda.

> [!IMPORTANT]
> Skype for Business Server dá suporte ao uso de endereçamento IPv6. Consulte [Plan for IPv6 in Skype for Business](ipv6.md) para obter mais detalhes.

> [!IMPORTANT]
> Para obter mais detalhes sobre FQDNs, consulte [Noções básicas de DNS](basics.md).

**DNS de cérebro dividido**
 <a name="BK_split"></a>

O DNS de cérebro dividido é uma configuração DNS em que você tem duas zonas DNS com o mesmo namespace. A primeira zona DNS lida com solicitações internas, enquanto a segunda zona DNS lida com solicitações externas, conforme mencionado nessas tabelas. Para saber mais sobre isso, consulte [DNS de cérebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considerações híbridas
<a name="BK_Hybrid"> </a>

Se você planeja ter alguns usuários conectados online e alguns locais, consulte o artigo de planejamento de conectividade [híbrida Skype for Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Você precisará configurar o DNS como normal para Skype for Business Server 2015 e também adicionar registros DNS adicionais.

Você também deve se referir a "Office 365 URLs e intervalos de endereços IP" em [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) para confirmar que seus usuários terão acesso aos recursos online de que precisarão.

## <a name="simple-urls"></a>URLs simples
<a name="BK_Simple"> </a>

Um URL (Uniform Resource Locator) é uma referência a um recurso da Web que especifica sua localização em uma rede de computador e um protocolo usado para recuperá-lo.

Skype for Business Server suporte ao uso de três URLs "simples" para acessar serviços:

- **O** meet é usado como a URL base para todas as conferências no site. Um exemplo de URL simples meet é https:<span></span>//<span></span>meet.<span></span> contoso.com<span></span>. Uma URL para uma reunião específica pode ser https:<span></span>//<span></span>meet.<span></span> contoso.com <span></span>/_username_/7322994.

    Com a URL de Reunião simples, os links para participar de reuniões são fáceis de compreender e de se comunicar.

- **O discagem** habilita o acesso à página da Web Configurações conferência discda. Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência. O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN. Um exemplo da URL simples discagem é https://<span></span> dialin.<span></span> contoso.com<span></span>.

- **O** administrador habilita o acesso rápido ao painel Skype for Business Server controle. Em qualquer computador dentro dos firewalls da sua organização, um administrador pode abrir o Painel de Controle Skype for Business Server digitando a URL simples de Administrador em um navegador. A URL simples de Admin é interna à organização. Um exemplo da URL simples admin é https://<span></span> admin.<span></span> contoso.com<span></span>.

URLs simples são abordadas com mais detalhes em requisitos [DNS para URLs simples em Skype for Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS por função de servidor
<a name="BK_Servers"> </a>

Você pode definir os nomes desses pools e servidores conforme desejar, mas torná-los memoráveis e refletir suas funções no sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para servidores ou pools individuais

Esses requisitos de registro genérico se aplicam a qualquer função de servidor usada por Skype for Business. Um pool é um conjunto de servidores executando os mesmos serviços que trabalham juntos para lidar com solicitações de cliente direcionadas a eles por meio de um balanceador de carga. Consulte [Requisitos de balanceamento de carga para Skype for Business](load-balancing.md) para obter detalhes

**Registros DNS Requisitos para funções de servidor/pool (presume o balanceamento de carga DNS)**

|Cenário da implantação|Requisito de DNS|
|:-----|:-----|
|One Server:  <br/> Chat Persistente, Diretor, Servidor de Mediação, Servidor front-end   |Um registro A interno que resolva o FQDN (nome de domínio totalmente qualificado) do servidor como o respectivo endereço IP.  <br/> ServerRole.<span></span> contoso.com<span></span> 10.10.10.0   |
|Pool:  <br/> Chat Persistente, Diretor, Servidor de Borda, Servidor de Mediação, Front-end   |Um registro A interno que resolve o FQDN (nome de domínio totalmente qualificado) de cada nó de servidor no pool para seu endereço IP.  <br/>**Exemplo** <br/> ServerRole01.<span></span> contoso.com<span></span> 10.10.10.1  <br/> ServerRole02.<span></span> contoso.com<span></span> 10.10.10.2  <br/> Vários registros A internos que resolvem o FQDN (nome de domínio totalmente qualificado) do pool para os endereços IP dos nós do servidor no pool.  <br/>**Exemplo** <br/> ServerPool.<span></span> contoso.com<span></span> 10.10.10.1  <br/> ServerPool.<span></span> contoso.com<span></span> 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Tópicos DNS específicos do Servidor de Borda

 Para planejar a implantação do servidor de borda, revise Plan [for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) e [Advanced Edge Server DNS planning for Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md), que tem as seções a seguir

- [Recuperação de desastre DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Balanceamento de carga DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuração automática sem DNS de cérebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS de cérebro dividido](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Passo a passo de Skype for Business serviços de localização de clientes](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)