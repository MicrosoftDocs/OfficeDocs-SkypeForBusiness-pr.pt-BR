---
title: 'Lync Server 2013: determinar requisitos de DNS'
description: 'Lync Server 2013: determinar requisitos de DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a4bfe682314fa4f91826f4bf85f8eac36ea91d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550907"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a>Determinar requisitos de DNS para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

Use o fluxograma a seguir para determinar os requisitos do Sistema de Nomes de Domínio (DNS). Alterações nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro são observadas onde se aplicam.

<div>


> [!IMPORTANT]  
> O Microsoft Lync Server 2013 suporta o uso de endereçamento IPv6. Para usar endereços IPv6, você também deve fornecer suporte para IPv6 DNS e configurar o host DNS AAAA (conhecido como registros "quad-A"). Em implantações nas quais o IPv4 e o IPv6 estão sendo usados, é melhor configurar e manter os registros de host A para IPv4 e o host AAAA para IPv6. Mesmo que sua implantação tenha sido totalmente transicionada para IPv6, os registros de host DNS IPv4 ainda podem ser necessários quando usuários externos ainda estiverem usando IPv4.



</div>

**Fluxograma - Como determinar os requisitos do DNS**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Por padrão, o nome do computador de um computador que não faz parte de um domínio é um nome de host, não um FQDN (nome de domínio totalmente qualificado). O construtor de topologias usa FQDNs, não nomes de host. Portanto, configure um sufixo DNS no nome do computador a ser implantado como um servidor de borda e que não esteja em um domínio. <STRONG>Use somente caracteres padrão</STRONG> (inclusive A–Z, a–z, 0–9 e hifens) quando atribuir FQDNs de seus Lync Servers, servidores de borda e pools. Não use caracteres Unicode ou sublinhados. Os caracteres incompatíveis em um FQDN frequentemente não são suportados no DNS externo e CAs públicos (isto é, quando o FQDN deve ser atribuído ao SN no certificado). Para obter detalhes adicionais, consulte <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS host Records for Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Como os clientes do Lync localizam serviços

O Microsoft Lync 2010, o Lync 2013 e o Lync Mobile são semelhantes em como o cliente encontra e acessa serviços no Lync Server 2013. A exceção notável é o aplicativo Lync da Windows Store que usa um processo de local de serviço diferente. Esta seção detalha dois cenários de como os clientes localizam serviços, primeiro o método tradicional usando uma série de registros SRV e de host, segundo usando apenas os registros do serviço de descoberta automática. Atualizações cumulativas para os clientes da área de trabalho alterar o processo de localização de DNS do Lync Server 2010 para todos os clientes, o processo de consulta DNS continua até que uma consulta bem-sucedida seja retornada ou a lista de possíveis registros de DNS seja esgotada e o erro final é retornado ao cliente.

Para todos os clientes **, exceto** para o aplicativo Lync da Windows Store durante a pesquisa de DNS, os registros SRV são consultados e retornados ao cliente na seguinte ordem:

1.  lyncdiscoverinternal. \<domain\>     Um registro (host) para o serviço de descoberta automática nos serviços Web internos

2.  lyncdiscover. \<domain\>     Um registro (host) para o serviço de descoberta automática nos serviços Web externos

3.  \_sipinternaltls. \_ TCP. \<domain\>     Registro SRV (localizador de serviço) para conexões TLS internas

4.  \_sipinternal. \_ TCP. \<domain\>     Registro SRV (localizador de serviço) para conexões TCP internas (executadas somente se o TCP for permitido)

5.  \_SIP. \_ TLS. \<domain\>     Registro SRV (localizador de serviço) para conexões TLS externas

6.  sipinternal. \<domain\>     Um registro (host) para o pool de front-ends ou diretor, que pode ser resolvido apenas na rede interna

7.  SIP. \<domain\>     Um registro (host) para o pool de front-ends ou diretor na rede interna ou o serviço de borda de acesso quando o cliente é externo

8.  sipexternal. \<domain\>     Um registro (host) para o serviço de borda de acesso quando o cliente é externo

O aplicativo Lync da Windows Store altera o processo completamente porque usa dois registros:

1.  lyncdiscoverinternal. \<domain\>     Um registro (host) para o serviço de descoberta automática nos serviços Web internos

2.  lyncdiscover. \<domain\>     Um registro (host) para o serviço de descoberta automática nos serviços Web externos

Não há fallback para os outros tipos de registro.

A diferença entre os métodos usados para clientes mais recentes em comparação com clientes mais antigos é que o serviço de descoberta automática está se tornando o método preferencial para localizar todos os serviços.

Quando uma conexão é bem-sucedida, o serviço de descoberta automática retorna todas as URLs de serviços Web para o pool inicial do usuário, incluindo o serviço de mobilidade (conhecido como MCX pelo diretório virtual criado para o serviço no IIS), URLs do Microsoft Lync Web App e do Agendador da Web. No entanto, tanto a URL do Serviço de Mobilidade Interno como a URL do Serviço de Mobilidade Externo está associado com o FQDN dos Serviços da Web Externos. Portanto, independente de o dispositivo móvel ser interno ou externo à rede, sempre se conectará ao Serviço de Mobilidade externamente através do proxy reverso.

Se as atualizações cumulativas do Lync Server 2013:2013 de fevereiro foram instaladas, o serviço de descoberta automática também retorna referências para interno/UCWA, External/UCWA e UCWA. Essas entradas se referem ao componente da web da Unified Communications Web API (UCWA). Atualmente, somente a entrada UCWA é usada e fornece uma referência a uma URL para o componente da Web. UCWA é usado por clientes móveis do Lync 2013 em vez do serviço de mobilidade do MCX usado pelos clientes móveis do Lync 2010.

<div>


> [!NOTE]  
> Ao criar registros SRV, é importante lembrar que eles devem apontar para um registro de DNS A e AAAA (se você estiver usando endereçamento IPv6) no mesmo domínio em que o registro SRV DNS é criado. Por exemplo, se o registro SRV estiver em contoso.com, o registro a e AAAA (se você estiver usando endereçamento IPv6) aponta para não pode estar no fabrikam.com.



</div>

<div>


> [!TIP]  
> A configuração padrão é direcionar todo o tráfego do cliente móvel através do site externo. Você pode modificar as configurações para retornar apenas a URL interna, se isso for mais preferível aos seus requisitos. Com esta configuração, os usuários podem usar aplicativos móveis do Lync em seus dispositivos móveis apenas quando estiverem dentro da rede corporativa. Para definir essa configuração, use o cmdlet <STRONG>set-CsMcxConfiguration</STRONG> .



</div>

<div>


> [!NOTE]  
> Embora os aplicativos móveis também possam se conectar a outros serviços do Lync Server 2013, como o serviço de catálogo de endereços, as solicitações da Web do aplicativo móvel interno acessam o FQDN da Web externa somente para o serviço de mobilidade. Outras solicitações de serviços, como solicitações do Catálogo de Endereços, não exigem esta configuração.



</div>

Os dispositivos móveis oferecem suporte à descoberta manual de serviços. Neste caso, cada usuário deve configurar as definições do dispositivo móvel com as URIs do Serviço de Descoberta Automática interna e externa completas, incluindo o protocolo e o caminho, da seguinte forma:

  - https:// \<ExtPoolFQDN\> /autodiscover/autodiscoverservice.svc/root para acesso externo

  - https:// \<IntPoolFQDN\> /autodiscover/autodiscover.svc/root para acesso interno

Recomendamos que você use a descoberta automática, em vez da descoberta manual. No entanto, as configurações manuais podem ser úteis para solucionar problemas de conectividade de dispositivos móveis.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configurando o DNS do Split-Brain com o Lync Server

O DNS de Split-Brain é conhecido por vários nomes, por exemplo, dividir DNS ou DNS de omissão de divisão. Simplesmente, ele descreve uma configuração de DNS onde há duas zonas DNS com o mesmo namespace – mas uma solicitação somente de serviços de zona DNS e os outros serviços de zona DNS são solicitações somente externas. No entanto, muitos dos registros SRV do DNS e DNS A contidos no DNS interno não estarão no DNS externo e o contrário também é verdadeiro. Nos casos em que o mesmo registro DNS existe no DNS interno e externo (por exemplo, www.contoso.com), o endereço IP retornado será diferente com base em onde (interno ou externo) a consulta foi iniciada.

<div>


> [!IMPORTANT]  
> Atualmente, Split-Brain DNS não tem suporte para a mobilidade ou, mais especificamente, os registros DNS do LyncDiscover e do LyncDiscoverInternal. LyncDiscover deve ser definido em um servidor DNS externo e LyncDiscoverInternal deve ser definido em um servidor DNS interno.



</div>

Para os fins desses tópicos, o termo DNS Split-Brain será usado.

Se você estiver configurando um split-brain DNS, as zonas interna e externa contêm um resumo dos tipos de registros DNS necessários em cada zona. Para obter detalhes, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNA Interno:**

  - Contém uma zona do DNS chamada contoso.com, para a qual é autoritativo

  - A zona contoso.com interna contém:
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para configuração automática do cliente do Lync Server 2013 interna (opcional)
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web do Lync Server 2013 (opcional)
    
      - Registros A e AAAA (se você estiver usando endereçamento IPv6) para o nome do pool de front-end, diretor ou nome do pool de diretores e todos os servidores internos que executam o Lync Server 2013 na rede corporativa
    
      - Registros A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de borda de cada Lync Server 2013, servidor de borda na rede de perímetro
    
      - Registros A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de cada servidor de proxy reverso na rede de perímetro (opcional para o gerenciamento de proxy reverso)
    
      - Todas as interfaces de borda interna do servidor de borda do Lync Server 2013 na rede de perímetro usam a zona DNS interna para resolver consultas para o contoso.com
    
      - Todos os servidores que executam o Lync Server 2013 e clientes que executam o Lync 2013 na rede corporativa apontam para os servidores DNS internos para resolver consultas para o contoso.com ou o uso do arquivo HOSTs em cada servidor de borda e listar a e AAAA (se você estiver usando o endereçamento IPv6) para o próximo servidor de salto, especificamente o diretor ou VIP, VIP ou servidor Standard Edition

**DNS Externo:**

  - Contém uma zona de DNS chamada contoso.com, para a qual é autoritativo

  - A zona contoso.com externa contém:
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a configuração automática do cliente do Lync Server 2013 (opcional)
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web do Lync Server 2013 para uso com mobilidade
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a interface externa de borda de cada Lync Server 2013, servidor de borda ou IP virtual (VIP) do balanceador de carga de hardware na rede de perímetro
    
      - Registros A e AAAA de DNS (se você estiver usando endereçamento IPv6) para a interface externa do servidor de proxy reverso ou VIP para um pool de servidores de proxy reverso na rede de perímetro

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configuração automática sem Split-Brain DNS

Usando o DNS Split-Brain, um usuário do Lync Server 2013 que entra internamente pode aproveitar a configuração automática se a zona DNS interna contiver um \_ sipinternaltls. \_ registro SRV TCP para cada domínio SIP em uso. No entanto, se você não usar o DNS Split-Brain, a configuração automática interna de clientes que executam o Lync não funcionará, a menos que uma das soluções alternativas descritas posteriormente nesta seção seja implementada. Isso ocorre porque o Lync Server 2013 requer que o URI do SIP do usuário corresponda ao domínio do pool de front-ends designado para configuração automática. Isso também se trata de versões anteriores do Communicator.

Por exemplo, se você tem dois domínios SIP em uso, os registros de serviço (SRV) do DNS a seguir serão necessários:

  - Se um usuário entrar como bob@contoso.com, o seguinte registro SRV funcionará para a configuração automática, porque o domínio SIP do usuário (contoso.com) corresponde ao domínio do pool de front-ends de configuração automática):
    
     \_sipinternaltls. \_ tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Se um usuário entrar como alice@fabrikam.com, o seguinte registro SRV DNS funcionará para a configuração automática do segundo domínio SIP.
    
     \_sipinternaltls. \_ tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Para comparação, se um usuário entrar como tim@litwareinc.com, o seguinte registro SRV DNS não funcionará para a configuração automática, porque o domínio SIP do cliente (litwareinc.com) não corresponde ao domínio no qual o pool está (fabrikam.com):

 \_sipinternaltls. \_ tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Se a configuração automática for necessária para clientes que executam o Lync, selecione uma das seguintes opções:

  - Objetos de política de **grupo**     Use objetos de política de grupo (GPOs) para popular os valores de servidor corretos.
    
    <div>
    

    > [!NOTE]  
    > Esta opção não habilita a configuração automática, mas automatiza o processo de configuração manual; assim, se esta abordagem for utilizada, os registros SRV associados à configuração automática não são necessários.

    
    </div>

  - **Zona**     interna correspondente Crie uma zona no DNS interno que corresponda à zona DNS externa (por exemplo, contoso.com) e crie registros DNS A e AAAA (se você estiver usando endereçamento IPv6) correspondentes ao pool do Lync Server 2013 usado para configuração automática. Por exemplo, se um usuário for hospedado no pool01.contoso.net mas entrar no Lync como bob@contoso.com, crie uma zona DNS interna chamada contoso.com e dentro dela, crie um registro DNS A e AAAA (se o endereçamento IPv6 for usado) para pool01.contoso.com.

  - Zona interna de **ponto PIN**     Se você estiver criando uma zona inteira no DNS interno não é uma opção, você pode criar zonas de ponto PIN (ou seja, dedicada) que correspondem aos Registros SRV necessários para a configuração automática e preencher essas zonas usando dnscmd.exe. O dnscmd.exe é necessário porque a interface do usuário do DNS não é compatível com a criação de zonas exatas. Por exemplo, se o domínio SIP for contoso.com e você tiver um pool de Front End chamado pool01 que contém dois Servidores Front End, serão necessárias as seguintes zonas exatas e registros A em seu DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Se seu ambiente possui um segundo domínio SIP (por exemplo, fabrikam.com), as seguintes zonas exatas e registros A são necessários em seu DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> O FQDN do pool de Front End aparece duas vezes, mas com dois endereços IP diferentes. Isso acontece porque o balanceamento de carga do DNS é usado, mas se o balanceamento de carga do hardware for utilizado, existirá apenas uma única entrada do pool de Front End. Além disso, os valores do FQDN do pool de Front End mudam entre os exemplos contoso.com e fabrikam.com, mas os endereços IP permanecem os mesmos. Isso acontece porque usuários entrando a partir do domínio SIP usam o mesmo pool de Front End para a configuração automática.



</div>

Para obter detalhes, consulte o artigo do blog DMTF, "configuração automática do Communicator e Split-Brain DNS" em [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) .

<div>


> [!NOTE]  
> O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configurando o DNS (sistema de nomes de domínio) para recuperação de desastre

Para configurar o DNS para redirecionar o tráfego da Web do Lync Server 2013 para seus sites de recuperação de desastre e failover, você deve estar usando um provedor de DNS que ofereça suporte a GeoDNS. Você pode configurar seus registros DNS para Web para dar suporte à recuperação de desastres, para que os recursos que usam os serviços Web continuem mesmo se um pool de front-ends inteiro for desativado. Esse recurso de recuperação de desastre oferece suporte a URLs simples de descoberta automática (URL de Lyncdiscover), de reunião e discagem.

Você define e configura os registros adicionais de host DNS (A e AAAA se estiver usando IPv6) para resolução interna e externa de serviços Web em seu provedor GeoDNS. Os detalhes a seguir pressupõem pools emparelhados, geograficamente dispersos e GeoDNS com suporte de seu provedor com o DNS de rodízio, ou configurados para usar o Pool1 como principal, e failover para o Pool2 no caso de perda de comunicação ou falha de hardware.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Registro GeoDNS (exemplo)</th>
<th>Registros de pool (exemplo)</th>
<th>Registros CNAME (exemplo)</th>
<th>Configurações de DNS (selecione uma opção)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com para Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com para Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Meet.contoso.com para Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Meet.contoso.com para Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com para Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com para Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Dialin.contoso.com para Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Dialin.contoso.com para Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscoverinternal.contoso.com para Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscoverinternal.contoso.com para Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Lyncdiscover.contoso.com para Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Lyncdiscover.contoso.com para Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com para Pool1InternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com para Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias Scheduler.contoso.com para Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias Scheduler.contoso.com para Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin entre pools</p>
<p>Usar primário, conectar ao secundário se houver falha</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>Balanceamento de carga do DNS

O balanceamento de carga do DNS normalmente é implementado no nível do aplicativo. O aplicativo (por exemplo, um cliente executando o Lync), tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados da consulta de gravação DNS A e AAAA (se o endereçamento IPv6 for usado) para o nome de domínio totalmente qualificado (FQDN) do pool.

Por exemplo, se houver três servidores front end em um pool chamado pool01.contoso.com, acontecerá o seguinte:

  - Clientes que executam o DNS de consulta do Lync para pool01.contoso.com. A consulta retorna três endereços IP e os armazena em cache da seguinte maneira (não necessariamente nesta ordem):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - O cliente tenta estabelecer uma conexão TCP (Transmission Control Protocol) a um dos endereços IP. Em caso de falha, o cliente tenta o próximo endereço IP em cache.

  - Se a conexão TCP for bem sucedida, o cliente negocia o TLS para se conectar ao registrador principal no pool01.contoso.com.

  - Se o cliente tentar todas as entradas em cache sem uma conexão bem-sucedida, o usuário será notificado de que nenhum servidor executando o Lync Server 2013 está disponível no momento.

<div>


> [!NOTE]  
> O balanceamento de carga baseado em DNS é diferente do round robin de DNS (DNS RR), que normalmente faz referência ao balanceamento de carga confiando no DNS para fornecer uma ordem diferente de endereços IP correspondentes aos servidores em um pool. Normalmente o DNS RR só habilita a distribuição de carga, mas não habilita o failover. Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A e AAAA (se você estiver usando endereçamento IPv6) falhar, a conexão falhará. Portanto, o round robin de DNS por si só é menos confiável do que o balanceamento de carga baseado em DNS. O round robin de DNS pode ser usado em conjunto com o balanceamento de carga do DNS.



</div>

O balanceamento de carga do DNS é usado para:

  - Balanceamento de carga para SIP de servidor para servidor para os servidores de borda

  - Balanceamento de carga de aplicativos de Serviços de Aplicativos de Comunicações Unificadas (UCAS), como o Atendedor Automático de Conferências, Grupo de Resposta e Estacionamento de Chamada

  - Evitar novas conexões a aplicativos UCAS (também conhecido como "drenagem")

  - Balanceamento de carga de todo o tráfego cliente-para-servidor entre clientes e Servidores de Borda

O balanceamento de carga do DNS não pode ser usado para:

  - Tráfego da Web de cliente para servidor para o diretor ou servidores front-end

Balanceamento de carga do DNS e tráfego federado:

Se vários registros DNS forem retornados por uma consulta SRV DNS, o serviço de borda de acesso sempre escolhe o registro SRV DNS com a prioridade numérica mais baixa e a maior espessura numérica. O documento "um RR DNS para especificar o local dos serviços (DNS SRV)" da força de tarefas de engenharia da Internet <http://www.ietf.org/rfc/rfc2782.txt> especifica que, se houver vários registros SRV DNS definidos, a prioridade será usada primeiro e, em seguida, peso. Por exemplo, o registro SRV DNS A tem um peso de 20 e uma prioridade de 40 e o registro de SRV DNS B tem um peso de 10 e prioridade de 50. O registro SRV do DNS A com prioridade 40 será selecionado. As regras a seguir se aplicam à seleção de registro SRV de DNS:

  - A prioridade é considerada primeiro. Um cliente deve tentar entrar em contato com o host de destino definido pelo registro SRV de DNS com a prioridade de número mais baixo possível. Os destinos com a mesma prioridade devem ser tentados em uma ordem definida pelo campo weight.

  - O campo peso especifica um peso relativo para entradas com a mesma prioridade. Pesos maiores devem receber uma maior probabilidade de ser selecionado. Os administradores DNS devem usar peso 0 quando não houver nenhuma seleção de servidor para fazer. Na presença de registros contendo pesos maiores que 0, os registros com peso 0 devem ter uma chance muito pequena de serem selecionados.

Se vários registros SRV DNS com prioridade e peso iguais forem retornados, o serviço de borda de acesso selecionará o registro SRV que foi recebido primeiro do servidor DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

