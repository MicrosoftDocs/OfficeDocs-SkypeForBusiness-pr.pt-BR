---
title: 'Lync Server 2013: requisitos de DNS para pool de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0ace2b05b506b5bbf73177282747a66d212b38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Requisitos de DNS para pool de front-ends no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-07_

To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.

Você precisa configurar os registros de DNS (sistema de nomes de domínio) necessários antes de publicar sua topologia no construtor de topologias. Além disso, alguns dos FQDNs (nomes de domínio totalmente qualificados) usados na configuração de uma implantação do Lync Server 2013 são FQDNs lógicos e não físicos do servidor, portanto, a configuração DNS adicional é necessária antes da publicação.

<div>


> [!WARNING]  
> O Lync Server 2013 não oferece suporte a domínios com rótulo único. Por exemplo, uma floresta com um domínio raiz chamado <STRONG>contoso.local</STRONG> é suportado, mas um domínio raiz chamado <STRONG>local</STRONG> não é suportado. Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento da Microsoft, "informações sobre como configurar o Windows para domínios com nomes DNS de rótulo único" em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> O nome especificado deve ser idêntico ao nome do computador configurado no servidor. Por padrão, o nome de um computador que não é atribuído a um domínio é um nome curto, não um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. <STRONG>Use apenas caracteres padrão</STRONG> (incluindo a – z, A – z, 0 – 9 e hifens) ao atribuir FQDNs de seus servidores que executam o Lync Server, servidores de borda e pools. Não use caracteres Unicode nem sublinhados. Caracteres não padrão em um FQDN normalmente não são suportados por um DNS externo e por autoridades de certificação (ACs) públicas (quando o FQDN deve ser atribuído ao SN no certificado).



</div>

Antes de operar a topologia após ela ter sido implantada, verifique se os seguintes registros DNS e do Active Directory foram criados (conforme suas necessidades de recursos específicos ditam):

  - Cada função de servidor que existirá na topologia será publicada como um objeto do Active Directory (ingressar no computador no domínio realizará isso).

  - Um Registro DNS A existe para cada servidor.

  - Existe um registro SRV DNS para cada domínio SIP se você planeja usar o logon automático para clientes no formato de \_sipinternaltls\_TCP. \<Domínio\>SIP. Este registro não é necessário se você utilizará configuração manual para clientes.

  - Um Registro DNS A para cada URL simples configurada, da qual normalmente existem quatro: meet, dialin, lwa e scheduler. Além disso, há a URL simples do administrador, que é uma URL especial para acessar o painel de controle do Lync Server 2013.

  - O servidor que executa o SQL Server deve ser associado ao domínio e alcançável pelo computador a partir do qual o construtor de topologias está publicando.

A tabela segue as arquiteturas de referência apresentadas na seção Planejamento. Para obter detalhes, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) na documentação de planejamento.

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
<th>Relacionado a/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (balanceamento de carga DNS). Requer um registro A de DNS para o endereço IP de cada servidor de front-end dentro do pool, mapeamento para o FQDN do pool.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (IP virtual (VIP) de balanceamento de carga de hardware).</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Servidor front-end do Pool01 (nó 1).</p>
<p>Servidor front-end do Pool01 (nó 2).</p>
<p>Servidor front-end do Pool01 (nó 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Servidor front-end do Pool01 (nó 2).</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) para tráfego de web de cliente para servidor.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Servidor back-end do Pool01 executando o SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Necessário para o Lync Phone Edition ou o logon automático de clientes sem registros SRV DNS e para correspondência de domínio estrito. Não é obrigatório em todos os casos.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Presume um segundo domínio SIP. Necessário para o Lync Phone Edition, o logon automático de clientes sem registros SRV DNS e para correspondência de domínio estrito. Não é obrigatório em todos os casos.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL simples para conferência discada publicada internamente – o servidor front-end (ou diretor, se instalado) responde a consultas de URL simples.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL simples para conferências publicadas internamente – o servidor front-end (ou diretor, se instalado) responde a consultas de URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>Administração</p></td>
<td><p>Registro opcional, URL simples para o painel de controle do Lync Server 2013 publicado internamente-o servidor front-end (ou diretor, se instalado) responde a consultas de URL simples. Apenas o nome do host (não o de domínio) é exigido.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = Endereço IP virtual para balanceador de carga de hardware



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
<th>FQDN Alvo</th>
<th>Porta</th>
<th>Relacionado a/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Necessário para a configuração automática dos clientes do Lync 2013 para trabalhar internamente.</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Necessário para a configuração automática dos clientes do Lync 2013 para trabalhar internamente.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Interno</p></td>
<td><p>SRV</p></td>
<td><p>_ntp. _udp. contoso. com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Origem do protocolo de tempo de rede (NTP) necessária para dispositivos que executam o Lync Phone Edition. Isso deve indicar o controlador de domínio, internamente. Caso o controlador de domínio não esteja definido, tentará usar o servidor NTP time.windows.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

