---
title: Requisitos de DNS para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Resumo: revise as considerações de DNS neste tópico antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 3db3641e5b884ef5bca43222fcf001bd4c5a538a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825271"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisitos de DNS para o Skype for Business Server

**Resumo:** Revise as considerações de DNS neste tópico antes de implementar o Skype for Business Server.

Este artigo aborda apenas o planejamento de DNS para implantações do Skype for Business Server na rede local de uma organização. Para o Skype for Business Online, consulte "URLs e intervalos de endereços IP do Office 365" em [https://aka.ms/o365ips](https://aka.ms/o365ips) .

Um servidor dns mapeia nomes de host (como www. <span></span> contoso .com, provavelmente um servidor Web) para <span></span> endereços IP (como 10.10.10.10). Ele ajuda os clientes e servidores interdependentes a se comunicarem entre si na rede. Ao configurar uma implementação do Skype for Business Server 2015, você precisará certificar-se de que o mapeamento de novos nomes de servidor (geralmente refletindo a função que eles estarão desempenhando) corresponde aos endereços IP aos que estão atribuídos.

Embora isso possa parecer um pouco difícil no início, o trabalho pesado para planejar isso pode ser feito usando a Ferramenta de Planejamento do [Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=50357) Depois de ter passado pelas perguntas do assistente sobre quais recursos você planeja usar, para cada site definido, você pode exibir o Relatório dns dentro do Relatório de Administração de Borda e usar as informações listadas lá para criar seus registros DNS. Você também pode fazer ajustes em muitos dos nomes e endereços IP usados, para obter detalhes, [consulte Review the DNS Report](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Lembre-se de que você pode exportar o Relatório de Administração de Borda para uma planilha do Excel, e o Relatório dns será uma das planilhas no arquivo. Embora essa ferramenta inclua recursos preterido do [Skype for Business Server 2019,](../../../SfBServer2019/deprecated.md)ela ainda poderá ser usada para criar um plano inicial se esses recursos não forem selecionados

Ao instalar uma nova implementação, conforme descrito em Criar registros DNS para [o Skype for Business Server](../../deploy/install/create-dns-records.md) e criar sua topologia para o Skype for Business Server, reconhecemos que você pode optar por usar os recursos DNS integrados ao Windows Server 2016 ou a um pacote DNS de terceiros, portanto, manteremos as discussões neste artigo em geral, em vez de específicas. Estamos detalhando o que é necessário, e como você atender a essa necessidade é sua decisão a ser tomada.

Os administradores experientes do Skype for Business, do Lync e do Office Communications Suite provavelmente acharão as tabelas a seguir úteis. Se a tabela for confusa para você, as seções ou artigos posteriores terão alguma luz sobre os seguintes conceitos:

## <a name="summary-tables"></a>Tabelas de resumo
<a name="BK_Summary"> </a>

As tabelas a seguir mostram registros DNS que o Skype for Business Server usa para fornecer serviços aos usuários. Algumas são opcionais porque são necessárias apenas para dar suporte a determinados recursos e podem ser ignoradas se esses recursos não são desejados. Os registros DNS necessários para acesso interno estão apenas na primeira tabela, e uma implantação que permite acesso interno e externo precisará de registros de ambas as tabelas.

**Mapeamentos dns internos**

|Tipo de Registro|Valor|Resolver para|Finalidade|Obrigatório|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN do pool de front-end  <br/> *Pool FE. <span></span> contoso <span></span> .com*   |Endereços IP do servidor do pool de front-end  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*   |Balanceamento de carga DNS de pools de front-end. Mapeia o nome do pool de Front End para um conjunto de endereços IP.  <br/> Consulte [Implantando o balanceamento de carga DNS em pools de front-end e pools de diretores](load-balancing.md#BK_FE_Dir)  |S   |
|A/AAAA   | FQDN de cada servidor front-end ou servidor Standard Edition em um pool ou um servidor autônomo <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |IP correspondente de cada servidor  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Mapeia o nome do servidor para seu endereço IP.   |S   |
|A/AAAA   |FQDN de substituição dos Serviços Web Internos do Pool Empresarial  <br/> *Web-int. <span></span> contoso <span></span> .com*   |VIP HLB para Serviços Web Internos do Servidor front-end  <br/> *192.168.21.120*   |Necessário para habilitar o tráfego web do cliente para o servidor, como baixar o Skype for Business Web App. Também é necessário para clientes móveis.   |S   |
|A/AAAA   |FQDN de substituição de serviços Web externos do pool empresarial  <br/> *Web-ext. <span></span> contoso <span></span> .com*   |VIP HLB para Serviços Web Externos do Servidor Front-End  <br/>*68.123.56.90*   |Necessário para habilitar o tráfego web de cliente para servidor, como baixar o Skype for Business Web App. Obrigatório se os clientes móveis resolverem o DNS internamente. Pode resolver para IP de Proxy Reverso DMZ ou IP de Internet.   ||
|A/AAAA   | FQDN do SQL Server de servidor #A0 <br/> *SQL1. <span></span> contoso <span></span> .com*   |endereço IP do servidor  <br/> *192.168.11.90*   |Mapeia o nome do servidor para um servidor SQL back-end que trabalha com o pool de #A0 para seu endereço IP   ||
|A/AAAA   |FQDN do SQL Server Espelho do Servidor #A0  <br/> *SQL2. <span></span> contoso <span></span> .com*   |endereço IP do servidor  <br/> *192.168.11.91*   |Mapeia o nome do servidor para um servidor espelho SQL back-end que trabalha com o pool de #A0 para seu endereço IP   ||
|A/AAAA   |FQDN do pool de diretores  <br/>**Observação:** Não aplicável ao usar um servidor de Diretor autônomo <br/> *DirPool. <span></span> contoso <span></span> .com*   |Endereços IP do pool de diretores  <br/> DNS LB para *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Balanceamento de carga DNS dos servidores do Pool de Diretores. Mapeia o nome do pool de Diretores para um endereço IP, consulte Implantando o Balanceamento de Carga DNS em Pools de [Front-End e Pools de Diretores](load-balancing.md#BK_FE_Dir) <br/> Um Diretor pode autenticar um usuário e é opcional.   ||
|A/AAAA   |FQDN do Diretor   |Endereço IP do servidor de cada servidor diretor   |Mapeia o nome do pool do Diretor para um endereço IP, consulte Implantando o Balanceamento de Carga DNS em Pools de Diretores e Pools de [Front-End](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN do pool do Servidor de Mediação   |Endereços IP do pool   |A função servidor de mediação é opcional. Você pode co-localizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [Usando o balanceamento de carga DNS em pools de servidor de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do Servidor de Mediação   |Endereço IP do servidor   |Você pode co-localizar os serviços fornecidos por um servidor de mediação para o pool ou servidor front-end. Consulte [Usando o balanceamento de carga DNS em pools de servidor de mediação](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN do Servidor de Chat Persistente   |Endereço IP do Servidor de Chat Persistente   |Um servidor de Chat Persistente é necessário para o recurso de Chat Persistente e é opcional.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |VIP do pool de front-end HLB ou IP do Diretor  <br/>  192.168.21.121  |Serviço De Descoberta Automática Interno1, necessário para suporte à Mobilidade. Se o DNS interno for usado para resolver dispositivos móveis, ele deverá apontar para o IP externo ou VIP DMZ.  <br/> Para serviços Web, exigimos o HLB no pool de Front-End, pois HTTPS não pode aproveitar o DNS. Para pool de Front-End ou pool de Diretores, isso deve ser resolvido para um VIP HLB ou um IP normal para um servidor Standard Edition ou um servidor diretor autônomo.   |S   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |FQDN do Pool FE HLB ou FQDN do Diretor  <br/> Web-int. <span></span> contoso <span></span> .com   |Serviço Interno de Descoberta Automática1 <br/> Você pode implementar isso como um CNAME em vez de um registro A, se desejado.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |Endereços IP do servidor do pool de front-end (ou para cada endereço IP do Diretor)  <br/>  DNS LB para *192.168.21.122 192.168.21.123 192.168.21.124*   |Necessário para a configuração automática, consulte o Passo a passo dos serviços de localização de clientes [do Skype for Business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Um registro ou registros apontando para os servidores do pool de Front-End ou servidores de Diretor na rede interna ou para o serviço de Borda de Acesso quando o cliente é externo   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |VIP do Pool FE HLB ou VIP HLB do Pool de Diretores ou IP do SERVIDOR SE/Diretor  <br/>  192.168.21.121  |Implantar esse registro é opcional &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Porta 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Porta 5061  |FQDN do pool de front-end  <br/>*Pool FE. <span></span> contoso <span></span> .com*  |Habilita o acesso automático do usuário interno 1 ao servidor/pool de front-end ou servidor/pool SE que autentica e redireciona as solicitações de cliente para entrada.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |FQDN do pool de front-end  <br/>_Pool FE. <span></span> contoso <span></span> .com_  |Acesso de usuário interno &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Fonte NTP necessária para dispositivos Lync Phone Edition   |Isso é necessário para dar suporte a fones de mesa.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN do serviço de Borda de Acesso <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Crie um registro SRV para cada domínio SIP que tenha clientes IOS ou Windows Phone Mobile.   |Para suporte ao cliente móvel   |
|A/AAAA   |URL do administrador  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Painel de Controle do Skype for Business Server, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL meet  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Reuniões online, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |URL de discagem  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Conferência discda, consulte [URLs simples](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN de serviços Web internos  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Serviço Web do Skype for Business usado pelo Skype for Business Web App   ||
|A/AAAA   |FQDN do pool do Servidor do Office Web Apps  <br/> OWA. <span></span> contoso <span></span> .com   | Endereço VIP do pool do Servidor do Office Web Apps <br/> 192.168.1.5   |Define o FQDN do pool do Servidor do Office Web Apps   ||
|A/AAAA   | FQDN da Web interno <br/> Web-int. <span></span> contoso <span></span> .com   | Endereço VIP do pool de front-end <br/> 192.168.21.121   |Define o FQDN interno da Web usado pelo Skype for Business Web App  <br/> Se você estiver usando o balanceamento de carga DNS neste pool, seu pool de Front-End e web farm interno não poderão ter o mesmo FQDN.   ||

&#x2776; usado por um cliente para descobrir o Servidor front-end ou pool de front-end e ser autenticado e assinado como um usuário. Mais detalhes sobre isso estão no Passo a passo dos serviços de localização de clientes do [Skype for Business.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)

&#x2777; isso só é necessário para dar suporte a clientes herdados anteriores ao Lync 2013 e fones de mesa.

&#x2778; Na situação em que um dispositivo de Comunicações Unificadas está ligado, mas um usuário nunca fez logoff no dispositivo, o registro A permite que o dispositivo descubra o servidor que hospeda o Serviço Web de Atualização de Dispositivo e obtenha atualizações. Caso contrário, os dispositivos obtêm as informações do servidor através do provisionamento em banda na primeira vez que um usuário faz logon.

O diagrama a seguir mostra um exemplo que inclui registros DNS internos e externos e muitos dos registros mostrados nas tabelas ao redor:

**Diagrama de rede de borda usando endereços IPv4 públicos**

![exemplo de diagrama de rede DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mapeamentos DNS da rede de perímetro (interfaces internas e externas)**

|Tipo de Registro|Valor|Resolver para|Finalidade|Obrigatório|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN do pool de Borda Interno  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |Endereços IP do pool de Borda voltado para o lado interno  <br/> 172.25.33.10, 172.25.33.11   |Endereços IP da interface interna do Pool de Borda Consolidado   |S   |
|A/AAAA   |FQDN do Servidor de Borda  <br/>*Contra-1. <span></span> contoso <span></span> .com*  |IP do servidor voltado para o interno para um servidor no pool de Borda  <br/> 172.25.33.10   |Crie um registro para cada servidor no pool com o FQDN do servidor apontando para seu IP do nó do servidor interno no pool, consulte Balanceamento de Carga DNS em Pools de Servidor de [Borda.](load-balancing.md#BK_Edge)   |S   |
|A/AAAA   |FQDN do Pool de Serviços de Borda de Acesso  <br/>*Access1. <span></span> contoso <span></span> .com*  |Endereços IP externos do Pool de Serviços de Borda de Acesso  <br/> 131.107.16.10, 131.107.16.11   |O Serviço de Borda de Acesso fornece um ponto de conexão único e confiável para o tráfego de saída e de entrada do protocolo SIP.   |S   |
|A/AAAA   |FQDN do Pool de Serviços de Borda de Webconferência  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Endereços IP externos do serviço de Borda de Webconferência  <br/> 131.107.16.90, 131.107.16.91   |O serviço de Borda de Webconferência permite que usuários externos participem de reuniões hospedadas em seu ambiente interno do Skype for Business Server.   |S   |
|A/AAAA   |*av.\<sip-domain\>* FQDN do pool <br/>*AV1. <span></span> contoso <span></span> .com*  |Endereços IP externos da Borda A/V  <br/> 131.107.16.170, 131.107.16.171   |O serviço de Borda A/V disponibiliza o compartilhamento de áudio, vídeo, aplicativo e transferência de arquivos para usuários externos.   |S   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN do Pool de Borda de Acesso Externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Localiza o pool do Servidor de Borda. Consulte [o Passo a passo dos serviços de localização de clientes do Skype for Business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |S   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |FQDN da Borda de Acesso Externo  <br/>_Access1. <span></span> contoso <span></span> .com_  |Usado para acesso de usuário externo. Consulte [o Passo a passo dos serviços de localização de clientes do Skype for Business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |S   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |FQDN da Borda de Acesso Externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Usado para federação e conectividade pública de IM   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN da Borda de Acesso Externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |O serviço proxy XMPP aceita e envia mensagens XMPP (extensible messaging and presence protocol) de e para parceiros federados XMPP configurados.   |Y, para implantar Federação; caso contrário, opcional  <br/> Não está disponível no Skype for Business Server 2019.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN da Borda de Acesso Externo  <br/>*Access1. <span></span> contoso <span></span> .com*  |Para dar suporte ao Serviço de Notificação por Push e ao serviço de Notificação por Push da Apple, crie um registro SRV para cada domínio SIP. &#x2778;  ||
|A/AAAA   |FQDN dos serviços Web do pool de Front-End Externo  <br/>*Web-ext. <span></span> contoso <span></span> .com*  |Endereço IP público do proxy reverso, proxy para o VIP de Serviços Web Externos para seu pool de Front-&#x2776; <br/> 131.107.155.1 proxy para 192.168.21.120   |Interface externa do pool de front-end usada pelo Skype for Business Web App   |S   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |Endereço IP público do proxy reverso, resolve para o VIP de Serviços Web Externos do seu pool de Diretores, se você tiver um, ou para seu pool de Front-End se você não tiver um diretor &#x2777; <br/> 131.107.155.1 proxy para 192.168.21.120   | Registro externo para a Descoberta Automática do cliente, também usado pelo Mobility, Skype for Business Web App e pelo aplicativo Web agendador, resolvido pelo servidor proxy reverso <br/> Para dar suporte ao Serviço de Notificação por Push e ao serviço de Notificação por Push da Apple, crie um registro SRV para cada domínio SIP que tenha clientes do Microsoft Lync Mobile. 3   |S   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Endereço IP público do proxy reverso, resolvido para a interface da Web externa para o pool de Front-End  <br/> 131.107.155.1 proxy para 192.168.21.120   |Proxy para o Serviço Web do Skype for Business  <br/> Consulte [URLs simples](dns.md#BK_Simple)  |S   |
|A/AAAA   |discagem.*\<sipdomain\>* <br/> discagem. *<span></span> contoso <span></span> .com*  |Endereço IP público do proxy reverso, proxy para a interface web externa para o pool de Front-End  <br/> 131.107.155.1 proxy para 192.168.21.120   |Proxy para o Serviço Web do Skype for Business  <br/> Consulte [URLs simples](dns.md#BK_Simple)  |S   |
|A/AAAA   |FQDN do pool do Servidor do Office Web Apps  <br/> OWA. <span></span> contoso <span></span> .com   | Endereço IP público do proxy reverso, proxy para a interface Web externa para o Servidor do Office Web Apps <br/> 131.107.155.1 proxy para 192.168.1.5   | Endereço VIP do pool do Servidor do Office Web Apps <br/> 192.168.1.5   |Define o FQDN do pool do Servidor do Office Web Apps   |

&#x2776; necessário para implantar a Federação, caso contrário, opcional.

&#x2777; usado por um cliente para descobrir o servidor front-end ou o pool de front-end e ser autenticado e assinado como um usuário.

&#x2778; Esse requisito se aplica somente a clientes em dispositivos móveis baseados na Apple ou na Microsoft. Os dispositivos Android e Nokia Symbian não usam notificação por push.

 Para obter mais detalhes sobre servidores de borda e redes de perímetro, consulte o conteúdo de planejamento [de DNS do servidor de](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) Borda.

> [!IMPORTANT]
> O Skype for Business Server dá suporte ao uso de endereçamento IPv6. Consulte [Plano para IPv6 no Skype for Business](ipv6.md) para obter mais detalhes.

> [!IMPORTANT]
> Para obter mais detalhes sobre FQDNs, consulte [noções básicas de DNS.](basics.md)

**DNS de dupla dupla** 
 <a name="BK_split"></a>

O DNS de dupla dupla é uma configuração dns em que você tem duas zonas DNS com o mesmo namespace. A primeira zona DNS lida com solicitações internas, enquanto a segunda zona DNS lida com solicitações externas, conforme mencionado nessas tabelas. Para saber mais sobre isso, [consulte SPLIT-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considerações híbridas
<a name="BK_Hybrid"> </a>

Se você planeja ter alguns usuários online e outros instalados no local, consulte o artigo de planejamento de conectividade híbrida [Skype for Business server 2019.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) Você precisará configurar o DNS normalmente para o Skype for Business Server 2015 e também adicionar registros DNS adicionais.

Você também deve consultar "URLs e intervalos de endereços IP do Office 365" para confirmar que os usuários terão acesso aos recursos [https://aka.ms/o365ips](https://aka.ms/o365ips) online necessários.

## <a name="simple-urls"></a>URLs simples
<a name="BK_Simple"> </a>

Uma URL é uma referência a um recurso da Web que especifica sua localização em uma rede de computador e um protocolo usado para recuperá-lo.

O Skype for Business Server dá suporte ao uso de três URLs "simples" para acessar serviços:

- **Meet** é usado como a URL base para todas as conferências no site. Um exemplo de URL simples Meet é https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com. Uma URL para uma determinada reunião pode ser https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com/_username_/7322994.

    Com a URL Simples Reunir, os links para participar de reuniões são fáceis de entender e de se comunicar.

- **A discagem** habilita o acesso à página da Web configurações de conferência discado. Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência. O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN. Um exemplo da URL simples Discar é https:// <span></span> discagem. <span></span> contoso <span></span> .com.

- **O** administrador habilita o acesso rápido ao Painel de Controle do Skype for Business Server. Em qualquer computador dentro dos firewalls da sua organização, um administrador pode abrir o Painel de Controle do Skype for Business Server digitando a URL simples Admin em um navegador. A URL simples de Admin é interna à organização. Um exemplo da URL simples Admin é https:// <span></span> administrador. <span></span> contoso <span></span> .com.

UrLs simples são discutidas em mais detalhes nos requisitos de DNS para [URLs simples no Skype for Business Server.](simple-urls.md)

## <a name="dns-by-server-role"></a>DNS por função de servidor
<a name="BK_Servers"> </a>

Você pode definir os nomes desses pools e servidores como desejar, mas torná-los memoráveis e refletir sua função no sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Registros DNS para pools ou servidores individuais

Esses requisitos genéricos de registro se aplicam a qualquer função de servidor usada pelo Skype for Business. Um pool é um conjunto de servidores executando os mesmos serviços que trabalham juntos para lidar com solicitações de cliente direcionadas a eles por meio de um balanceador de carga. Confira [os requisitos de balanceamento de carga do Skype for Business](load-balancing.md) para obter detalhes

**Requisitos do registro DNS para funções de servidor/pool (supõe o balanceamento de carga DNS)**

|Cenário da implantação|Requisito de DNS|
|:-----|:-----|
|Um servidor:  <br/> Chat Persistente, Diretor, Servidor de Mediação, Servidor front-end   |Um registro A interno que resolva o FQDN (nome de domínio totalmente qualificado) do servidor como o respectivo endereço IP.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Pool:  <br/> Chat Persistente, Diretor, Servidor de Borda, Servidor de Mediação, Front-end   |Um registro A interno que resolve o FQDN (nome de domínio totalmente qualificado) de cada nó de servidor no pool para seu endereço IP.  <br/>**Exemplo** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Vários registros A internos que resolvem o FQDN (nome de domínio totalmente qualificado) do pool para os endereços IP dos nós do servidor no pool.  <br/>**Exemplo** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Tópicos dns específicos do Servidor de Borda

 Para planejar a implantação do servidor de borda, revise o Plano para implantações do Servidor de Borda no [Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)e o planejamento do DNS do Servidor de Borda Avançado para o Skype for Business Server [2015,](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) que tem as seções a seguir

- [Recuperação de desastre de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Balanceamento de carga DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configuração automática sem DNS de dupla dupla](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS de dupla cabeça](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Passo a passo dos serviços de localização de clientes do Skype for Business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


