---
title: 'Lync Server 2013: Requisitos DNS para pool de Front-Ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Requisitos DNS para pool de Front-Ends no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-07_

Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio minimamente como membro do grupo Domain admins ou um membro do grupo DnsAdmins.

Você precisa configurar os registros de sistema de nomes de domínio (DNS) necessários antes de publicar sua topologia no construtor de topologias. Além disso, alguns dos FQDNs (nomes de domínio totalmente qualificados) usados na configuração de uma implantação do Lync Server 2013 são FQDNs lógicos e não físicos do servidor, portanto a configuração DNS adicional é necessária antes da publicação.

<div>


> [!WARNING]  
> O Lync Server 2013 não é compatível com domínios com rótulo único. Por exemplo, uma floresta com um domínio raiz chamado <STRONG>contoso. local</STRONG> tem suporte, mas não há suporte para um domínio raiz chamado <STRONG>local</STRONG> . Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento Microsoft "informações sobre como configurar o Windows para domínios com nomes DNS de rótulo único" em <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> O nome que você especificar dever ser idêntico ao nome de computador configurado no servidor. Por padrão, o nome do computador de um computador que não está associado a um domínio é um nome curto, e não um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. <STRONG>Usar apenas caracteres padrão</STRONG> (incluindo A – Z, A – Z, 0 – 9 e hifens) ao atribuir FQDNs de seus servidores que executam o Lync Server, servidores de borda e pools. Não use caracteres Unicode ou sublinhados. Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e as autoridades de certificação pública (CAs) (quando o FQDN deve ser atribuído ao SN no certificado).



</div>

Antes de operar a topologia após a implantação, certifique-se de que os seguintes registros de DNS e do Active Directory sejam criados (conforme suas necessidades para recursos específicos exigirem):

  - Cada função de servidor que existirá na topologia será publicada como um objeto do Active Directory (o ingresso no computador para o domínio vai conseguir isso).

  - Existe um registro DNS A para cada servidor.

  - Um registro SRV DNS existe para cada domínio SIP se você planeja usar o logon automático para clientes na forma de \_sipinternaltls\_TCP. \<Domínio\>SIP. Se você usar a configuração manual para clientes, esse registro não será necessário.

  - Um registro de DNS A para cada URL simples configurada, do qual há geralmente quatro: atender, dial-in, LWA e scheduler. Além disso, há a URL simples do administrador, que é uma URL especial para acessar o painel de controle do Lync Server 2013.

  - O servidor que executa o SQL Server deve estar associado ao domínio e alcançável pelo computador do qual o construtor de topologias está publicando.

A tabela segue as arquiteturas de referência apresentadas na seção planejamento. Para obter detalhes, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) na documentação de planejamento.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Registros DNS necessários para o pool de front-ends

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local</th>
<th>Tipo</th>
<th>FQDN</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (balanceamento de carga de DNS). Requer um registro DNS A para o endereço IP de cada servidor front-end dentro do pool, mapeando para o pool FQDN.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (VIP (IP virtual) do balanceador de carga de hardware).</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Servidor front-end Pool01 (nó 1).</p>
<p>Servidor front-end Pool01 (nó 2).</p>
<p>Servidor front-end Pool01 (nó 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Servidor front-end Pool01 (nó 2).</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) para tráfego da Web de cliente para servidor.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Pool01 back-end Server executando o SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Necessário para o Lync Phone Edition ou o logon automático de clientes sem registros SRV DNS e para correspondência de domínio estrito. Não é necessário em todos os casos.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Assume um segundo domínio SIP. Obrigatório para o Lync Phone Edition, o logon automático de clientes sem registros SRV DNS e para correspondência de domínio estrito. Não é necessário em todos os casos.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL simples para conferência discada publicada internamente – o servidor front-end (ou diretor, se instalado) responderá a consultas de URL simples.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL simples para conferências publicadas internamente – front-end Server (ou director, se instalado) responde a consultas de URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>locatário</p></td>
<td><p>Registro opcional, URL simples para o painel de controle do Lync Server 2013 publicada internamente – o servidor front-end (ou director, se instalado) responde às consultas de URL simples. Somente nome do host (nenhum nome de domínio) é recomendado.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = endereço IP virtual para balanceador de carga de hardware



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>Registros SRV DNS para o pool de front-ends


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Local</th>
<th>Tipo</th>
<th>FQDN</th>
<th>FQDN de destino</th>
<th>Porta</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _ TCP. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Obrigatório para a configuração automática de clientes do Lync 2013 trabalhar internamente.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _ TCP. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Obrigatório para a configuração automática de clientes do Lync 2013 trabalhar internamente.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Fonte de protocolo de tempo de rede (NTP) necessária para dispositivos que executam o Lync Phone Edition. Internamente, isso deve apontar para o controlador de domínio. Se o controlador de domínio não estiver definido, ele tentará usar o servidor NTP time.windows.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

