---
title: 'Lync Server 2013: Determinar requisitios de DNS'
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
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Determinar requisitios de DNS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Use o fluxograma a seguir para determinar os requisitos do sistema de nomes de domínio (DNS). Alterações nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro são observadas quando elas se aplicam.

<div>


> [!IMPORTANT]  
> O Microsoft Lync Server 2013 oferece suporte ao uso de endereçamento IPv6. Para usar endereços IPv6, você também deve fornecer suporte para o DNS do IPv6 e configurar o host de DNS AAAA (conhecido como registros "quad-A"). Em implantações em que o IPv4 e o IPv6 estão sendo usados, é melhor configurar e manter registros de host A para IPv4 e host AAAA para IPv6. Mesmo que sua implantação tenha sido completada completamente para IPv6, os registros de host DNS IPv4 ainda poderão ser necessários quando usuários externos ainda estiverem usando IPv4.



</div>

**Determinando o fluxograma de requisitos de DNS**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Por padrão, o nome do computador de um computador que não está associado a um domínio é um nome de host, e não um FQDN (nome de domínio totalmente qualificado). O construtor de topologias usa FQDNs, não nomes de host. Portanto, você deverá configurar um sufixo DNS no nome do computador a ser implantado no Servidor de Borda que não ingressou no domínio. <STRONG>Use apenas caracteres padrão</STRONG> (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools. Não use caracteres Unicode ou sublinhados. Normalmente, caracteres não padrão no FQDN não são suportados por DNS externo e CAs públicas (ou seja, quando o FQDN deve ser atribuído ao SN no certificado). Para obter detalhes adicionais, consulte <A href="lync-server-2013-configure-dns-host-records.md">Configurar registros de host DNS para o Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Como os clientes do Lync localizam serviços

O Microsoft Lync 2010, o Lync 2013 e o Lync Mobile são semelhantes em como o cliente localiza e acessa serviços no Lync Server 2013. A exceção notável é o aplicativo Lync da Windows Store que usa um processo de localização de serviço diferente. Esta seção detalha dois cenários de como os clientes localizam serviços, primeiro o método tradicional usando uma série de registros SRV e um host, segundo usando somente os registros de serviço descoberta automática. As atualizações cumulativas para os clientes da área de trabalho alteram o processo de localização do DNS do Lync Server 2010 para todos os clientes, o processo de consulta DNS continua até que uma consulta bem-sucedida seja retornada, ou a lista de possíveis registros de DNS seja esgotada, e o erro final será retornado para o cliente.

Para todos os clientes **, exceto** o aplicativo Lync da Windows Store durante a pesquisa de DNS, os registros SRV são consultados e retornados ao cliente na seguinte ordem:

1.  lyncdiscoverinternal. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web internos

2.  lyncdiscover. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web externos

3.  \_sipinternaltls. \_TCP. \<registro\> SRV do domínio (localizador de serviço) para conexões TLS internas

4.  \_sipinternal. \_TCP. \<registro\> SRV do domínio (localizador de serviços) para conexões TCP internas (executadas somente se o TCP for permitido)

5.  \_SPI. \_TLS. \<registro\> SRV do domínio (localizador de serviço) para conexões TLS externas

6.  sipinternal. \<registro\> de domínio a (host) para o pool ou o diretor de front-end, que é resolvível somente na rede interna

7.  SPI. \<registro\> de domínio a (host) para o pool de front-end ou diretor na rede interna ou o serviço de borda de acesso quando o cliente for externo

8.  sipexternal. \<registro\> de domínio a (host) para o serviço de borda de acesso quando o cliente for externo

O aplicativo Lync da Windows Store altera o processo completamente porque usa dois registros:

1.  lyncdiscoverinternal. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web internos

2.  lyncdiscover. \<registro\> de domínio a (host) para o serviço de descoberta automática nos serviços Web externos

Não há nenhum fallback para os outros tipos de registro.

A diferença entre os métodos usados para clientes mais recentes em comparação com clientes mais antigos é que o serviço de descoberta automática está se tornando o método preferencial para localizar todos os serviços.

Quando uma conexão é bem-sucedida, o serviço descoberta automática retorna todas as URLs de serviços Web do pool primário do usuário, incluindo o serviço de mobilidade (conhecido como MCX pelo diretório virtual criado para o serviço no IIS), URLs do Microsoft Lync Web App e do Web Scheduler do Web App. No entanto, a URL do serviço de mobilidade interna e a URL do serviço de mobilidade externa estão associadas ao FQDN dos serviços Web externos. Portanto, independentemente de um dispositivo móvel ser interno ou externo à rede, o dispositivo sempre se conecta ao serviço de mobilidade externamente por meio do proxy reverso.

Se as atualizações cumulativas do Lync Server 2013:2013 de fevereiro tiverem sido instaladas, o serviço de descoberta automática também retornará referências para interno/UCWA, External/UCWA e UCWA. Essas entradas se referem ao componente da Web da API de comunicação unificada (UCWA). Atualmente, somente a entrada UCWA é usada e fornece uma referência a uma URL para o componente da Web. UCWA é usado pelos clientes móveis do Lync 2013 em vez do serviço de mobilidade do MCX usado pelos clientes móveis do Lync 2010.

<div>


> [!NOTE]  
> Ao criar registros SRV, é importante lembrar que eles devem apontar para um registro DNS A e AAAA (se você estiver usando endereçamento IPv6) no mesmo domínio em que o registro SRV DNS for criado. Por exemplo, se o registro SRV estiver em contoso.com, o registro a e AAAA (se você estiver usando endereçamento IPv6) aponta para não pode estar no fabrikam.com.



</div>

<div>


> [!TIP]  
> A configuração padrão é direcionar todo o tráfego de cliente móvel por meio do site externo. Você pode modificar as configurações para retornar apenas a URL interna, se for mais preferível para atender às suas necessidades. Com essa configuração, os usuários podem usar os aplicativos móveis do Lync em seus dispositivos móveis somente quando estiverem dentro da rede corporativa. Para definir essa configuração, use o cmdlet <STRONG>set-CsMcxConfiguration</STRONG> .



</div>

<div>


> [!NOTE]  
> Embora os aplicativos móveis também possam se conectar a outros serviços do Lync Server 2013, como serviço de catálogo de endereços, solicitações da Web de aplicativo móvel interno acessam o FQDN da Web externa somente para o serviço de mobilidade. Outras solicitações de serviço, como solicitações de catálogo de endereços, não exigem essa configuração.



</div>

Os dispositivos móveis dão suporte à descoberta manual de serviços. Nesse caso, cada usuário deve configurar as configurações do dispositivo móvel com os URIs de serviço de descoberta automática interna e externa, incluindo o protocolo e o caminho, da seguinte maneira:

  - https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root para acesso externo

  - https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root para acesso interno

Recomendamos que você use a descoberta automática, em vez da descoberta manual. No entanto, as configurações manuais podem ser úteis para solucionar problemas de conectividade de dispositivos móveis.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configurando o DNS Split-Brain com o Lync Server

O DNS Split-Brain é conhecido por vários nomes, por exemplo, Split DNS ou Split-Horizon DNS. Simplesmente, ele descreve uma configuração de DNS onde há duas zonas DNS com o mesmo namespace – mas uma única solicitação de serviços de zona DNS e os outros serviços de zona DNS são solicitações somente externas. No entanto, muitos dos SRV DNS e registros contidos no DNS interno não serão contidos no DNS externo e o inverso também será verdadeiro. Nos casos em que o mesmo registro DNS existe no DNS interno e externo (por exemplo, www.contoso.com), o endereço IP retornado será diferente com base em onde (interno ou externo) a consulta foi iniciada.

<div>


> [!IMPORTANT]  
> Atualmente, não há suporte para DNS Split-Brain para a mobilidade ou, mais especificamente, os registros DNS LyncDiscover e LyncDiscoverInternal. LyncDiscover deve ser definido em um servidor DNS externo e LyncDiscoverInternal deve ser definido em um servidor DNS interno.



</div>

Para os fins desses tópicos, o termo divisão-Brain DNS será usado.

Se você estiver configurando o DNS Split-Brain, a seguinte zona interna e externa contém um resumo dos tipos de registros de DNS necessários em cada zona. Para obter detalhes, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interno:**

  - Contém uma zona DNS chamada contoso.com para a qual é autoritativa

  - A zona contoso.com interna contém:
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para configuração automática de cliente do Lync Server 2013 (opcional)
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web do Lync Server 2013 (opcional)
    
      - Registros A e AAAA do DNS (se você estiver usando endereçamento IPv6) para nome do pool de front-end, diretor ou nome do pool do diretor e todos os servidores internos que executam o Lync Server 2013 na rede da empresa
    
      - Registros A e AAAA do DNS (se você estiver usando endereçamento IPv6) para a interface interna de borda de cada servidor do Lync 2013, servidor de borda na rede de perímetro
    
      - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de cada servidor de proxy reverso na rede de perímetro (opcional para o gerenciamento de proxy reverso)
    
      - Todas as interfaces de borda interna do servidor de borda do Lync Server 2013 na rede de perímetro usam a zona DNS interna para a resolução de consultas para o contoso.com
    
      - Todos os servidores que executam o Lync Server 2013 e os clientes que executam o Lync 2013 na rede corporativa apontam para os servidores DNS internos para a resolução de consultas para o contoso.com ou o uso de um arquivo de HOSTs em cada servidor de borda e lista A e AAAA (se você estiver usando os registros de endereçamento IPv6) para próximo servidor de salto, especificamente o diretor do diretor ou diretor, VIP do pool de front-end ou servidor Standard Edition

**DNS externo:**

  - Contém uma zona DNS chamada contoso.com para a qual é autoritativa

  - A zona contoso.com externa contém:
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para configuração automática do cliente do Lync Server 2013 (opcional)
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web do Lync Server 2013 para uso com o Mobility
    
      - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a interface externa Edge de cada Lync Server 2013, servidor de borda ou VIP (IP virtual) do balanceador de carga de hardware na rede de perímetro
    
      - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para a interface externa do servidor proxy reverso ou VIP para um pool de servidores proxy reverso na rede de perímetro

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configuração automática sem divisão-Brain DNS

Usando o DNS Split-Brain, um usuário do Lync Server 2013 que entra internamente pode aproveitar a configuração automática se a zona DNS interna contiver \_um sipinternaltls. \_registro SRV TCP para cada domínio SIP em uso. No entanto, se você não usar DNS Split-Brain, a configuração interna automática de clientes que executa o Lync não funcionará, a menos que uma das soluções alternativas descritas mais adiante nesta seção seja implementada. Isso ocorre porque o Lync Server 2013 exige que o URI SIP do usuário corresponda ao domínio do pool de front-ends designado para configuração automática. Este também era o caso das versões anteriores do Communicator.

Por exemplo, se você tiver dois domínios SIP em uso, os seguintes registros de serviço DNS (SRV) seriam necessários:

  - Se um usuário entrar como bob@contoso.com, o seguinte registro SRV funcionará para configuração automática, porque o domínio SIP do usuário (contoso.com) corresponde ao domínio do pool de front-end de configuração automática):
    
     \_sipinternaltls. \_TCP.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Se um usuário entrar como alice@fabrikam.com, o seguinte registro SRV DNS funcionará para a configuração automática do segundo domínio SIP.
    
     \_sipinternaltls. \_TCP.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Para comparação, se um usuário entrar como tim@litwareinc.com, o seguinte registro SRV DNS não funcionará para configuração automática, porque o domínio SIP do cliente (litwareinc.com) não corresponde ao domínio no qual o pool está (fabrikam.com):

 \_sipinternaltls. \_TCP.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Se a configuração automática for necessária para os clientes que executam o Lync, selecione uma das seguintes opções:

  - **Objetos de política de grupo**   usam objetos de política de grupo (GPOs) para preencher os valores corretos do servidor.
    
    <div>
    

    > [!NOTE]  
    > Essa opção não habilita a configuração automática, mas automatiza o processo de configuração manual, portanto, se essa abordagem for usada, os registros SRV associados à configuração automática não serão necessários.

    
    </div>

  - **Zona interna correspondente**   crie uma zona no DNS interno que corresponda à zona DNS externa (por exemplo, contoso.com) e crie registros DNS a e AAAA (se você estiver usando endereçamento IPv6) correspondentes ao pool do Lync Server 2013 usado para configuração automática. Por exemplo, se um usuário estiver hospedado no pool01.contoso.net, mas entrar no Lync como bob@contoso.com, crie uma zona DNS interna chamada contoso.com e dentro dela, crie um registro DNS A e AAAA (se o endereçamento IPv6 for usado) para pool01.contoso.com.

  - **Zona interna de ponto de fixação**   se você estiver criando uma zona inteira no DNS interno não for uma opção, você pode criar zonas de ponto PIN (ou seja, dedicada) que correspondam aos Registros SRV necessários para a configuração automática e preencher essas zonas usando o DNSCmd. exe. O DNSCmd. exe é necessário porque a interface do usuário DNS não dá suporte à criação de zonas de ponto PIN. Por exemplo, se o domínio SIP for contoso.com e você tiver um pool de front-end chamado pool01 que contém dois servidores front-end, você precisará das seguintes zonas de ponto de fixação e registros no seu DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Se o ambiente contiver um segundo domínio SIP (por exemplo, fabrikam.com), você precisará das seguintes zonas de ponto PIN e registros no seu DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> O FQDN do pool de front-end aparece duas vezes, mas com dois endereços IP diferentes. Isso ocorre porque o balanceamento de carga de DNS é usado, mas se o balanceamento de carga de hardware for usado, haveria apenas uma única entrada de pool de front-end. Além disso, os valores de FQDN do pool de front-end são alterados entre o exemplo contoso.com e o fabrikam.com exemplo, mas os endereços IP permanecem os mesmos. Isso ocorre porque os usuários se conectam de um domínio SIP, usam o mesmo pool de front-end para configuração automática.



</div>

Para obter detalhes, consulte o artigo do blog DMTF, "configuração automática do Communicator e DNS dividido-Brain [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)", em.

<div>


> [!NOTE]  
> O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configurando o sistema de nomes de domínio (DNS) para recuperação de desastres

Para configurar o DNS para redirecionar o tráfego da Web do Lync Server 2013 para seus sites de failover e recuperação de desastres, você deve estar usando um provedor de DNS compatível com GeoDNS. Você pode configurar seus registros DNS para a Web para dar suporte à recuperação de desastres, de modo que os recursos que usam serviços Web continuem mesmo se um pool de front-end inteiro ficar inativo. Este recurso de recuperação de desastres dá suporte à descoberta automática (URL Lyncdiscover), a chamadas e a URLs simples de discagem.

Você define e configura registros de host DNS adicionais (A e AAAA se estiver usando IPv6) para resolução interna e externa de serviços Web em seu provedor de GeoDNS. Os detalhes a seguir pressupõem pools emparelhados, geograficamente dispersos e GeoDNS compatíveis com o seu provedor com o DNS de rodízio, ou configurado para usar o Pool1 como principal, e para fazer failover para Pool2 no caso de perda de comunicações ou falha de hardware.


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
<th>Registros DNS (selecione uma opção)</th>
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

## <a name="dns-load-balancing"></a>DNS Load Balancing

O balanceamento de carga de DNS geralmente é implementado no nível do aplicativo. O aplicativo (por exemplo, um cliente executando o Lync), tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados pela consulta de registro DNS A e AAAA (se o endereçamento IPv6 for usado) para o pool FQDN (nome de domínio totalmente qualificado).

Por exemplo, se houver três servidores front-end em um pool chamado pool01.contoso.com, ocorrerá o seguinte:

  - Clientes que executam o DNS de consulta do Lync para pool01.contoso.com. A consulta retorna três endereços IP e os armazena em cache da seguinte maneira (não necessariamente nesta ordem):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - O cliente tenta estabelecer uma conexão TCP (Transmission Control Protocol) a um dos endereços IP. Se isso falhar, o cliente tentará o próximo endereço IP no cache.

  - Se a conexão TCP for bem -sucedida, o cliente negocia o TLS para se conectar ao Registrador Avançado primário em pool01.contoso.com.

  - Se o cliente tentar todas as entradas armazenadas em cache sem uma conexão bem-sucedida, o usuário será notificado de que nenhum servidor executando o Lync Server 2013 está disponível no momento.

<div>


> [!NOTE]  
> O balanceamento de carga baseado em DNS é diferente do rodízio de DNS (DNS RR) que geralmente se refere ao balanceamento de carga ao confiar no DNS para fornecer uma ordem diferente de endereços IP correspondentes aos servidores em um pool. Normalmente, o RR DNS habilita somente a distribuição de carga, mas não habilita o failover. Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A e AAAA (se você estiver usando endereçamento IPv6) falhar, a conexão falhará. Portanto, o rodízio de DNS por si só é menos confiável do que o balanceamento de carga baseado em DNS. Você pode usar a repetição alternada de DNS em conjunto com o balanceamento de carga de DNS.



</div>

O balanceamento de carga de DNS é usado para o seguinte:

  - Balanceamento de carga do servidor para o servidor SIP para os servidores de borda

  - Aplicativos UCAS (serviços de aplicativo de comunicação unificada) de balanceamento de carga, como atendedor automático de conferência, grupo de resposta e estacionamento de chamada

  - Evitando novas conexões para aplicativos do UCAS (também conhecido como "descarga")

  - Balanceamento de carga de todo o tráfego de cliente para servidor entre clientes e servidores de borda

O balanceamento de carga de DNS não pode ser usado para o seguinte:

  - Tráfego da Web de cliente para servidor para director ou servidores front-end

Balanceamento de carga de DNS e tráfego federado:

Se vários registros DNS forem retornados por uma consulta de servidor DNS, o serviço de borda de acesso sempre escolhe o registro SRV DNS com a prioridade numérica mais baixa e a espessura numérica mais alta. O documento da Internet Engineering Task Force "um RR DNS para especificar o local dos serviços (DNS SRV <http://www.ietf.org/rfc/rfc2782.txt> )" especifica que, se houver vários registros SRV DNS definidos, a prioridade será usada primeiro e, em seguida, peso. Por exemplo, o registro SRV DNS A tem uma ponderação de 20 e uma prioridade de 40 e o registro SRV DNS B tem uma ponderação de 10 e prioridade de 50. Registro SRV DNS A with Priority 40 será selecionada. As regras a seguir se aplicam à seleção de registro SRV DNS:

  - A prioridade é considerada primeiro. Um cliente deve tentar contatar o host de destino definido pelo registro SRV DNS com o menor prioridade numerada que ele pode alcançar. Os destinos com a mesma prioridade devem ser testados em uma ordem definida pelo campo peso.

  - O campo peso especifica um peso relativo para entradas com a mesma prioridade. Atribuições maiores devem ter uma probabilidade mais alta proporcional mais alta de ser selecionada. Os administradores de DNS devem usar o peso 0 quando não houver nenhuma seleção de servidor para fazer. Na presença de registros que contêm pesos maiores do que 0, os registros com peso 0 devem ter uma chance muito menor de serem selecionados.

Se vários registros SRV DNS com prioridade e peso iguais forem retornados, o serviço de borda de acesso selecionará o registro SRV que foi recebido primeiro do servidor DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

