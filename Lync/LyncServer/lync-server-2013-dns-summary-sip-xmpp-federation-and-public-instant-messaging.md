---
title: Resumo de DNS-SIP, Federação XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 253a00a07d1d76e77c9a753f6442151beda7c801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumo de DNS-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-03-09_

Os registros de DNS (sistema de nomes de domínio) que serão necessários para definir uma federação com os parceiros do Office Communications Server ou do Lync Server são determinados pela sua decisão de permitir a descoberta automática de DNS do seu domínio por outros parceiros de perspectiva. Se você publicar o \_sipfederationtls. \_TCP. * \<Nome\> do domínio SIP* Registro SRV, qualquer outro domínio federado SIP poderá "descobrir" sua Federação. Você pode controlar quais domínios federados podem se comunicar com você usando as configurações permitir domínios e domínios bloqueados no painel de controle do Lync Server ou definindo a configuração de domínios permitidos ou bloqueados usando o Shell de gerenciamento do Lync Server e os cmdlets **Get**, **set**, **New**, **Remove-CsAllowedDomain** e **-CsBlockedDomain** do PowerShell. Para obter informações adicionais sobre como definir as configurações de contratação e o uso dos cmdlets do PowerShell, consulte **Tópicos relacionados** no final deste tópico.

A tabela de resumo dos registros DNS exibe as entradas necessárias para uma federação aberta ou descoberta. Se não quiser implementar a descoberta de Federação, você pode decidir não configurar o \_sipfederationtls. \_TCP. Registro de *nome\> de domínio SIP. \<*

<div>


> [!IMPORTANT]
> Há cenários específicos nos quais você deve ter o _sipfederationtls. _tcp. <EM> &lt;Nome&gt; do domínio SIP</EM> Registro SRV, mas você não deseja ter uma federação detectável. Uma instância é onde você implantou mobilidade para seus usuários. O Mobility Push Notification Clearinghouse (PNCH) é um tipo especial de Federação que é usado para clientes móveis do Microsoft Lync em Apple iPhone ou iPad usando o cliente móvel do Lync 2010 ou o Windows Phone usando os clientes móveis do Lync 2010 Mobile ou Lync 2013. O _sipfederationtls. _tcp. <EM> &lt;Nome&gt; do domínio SIP</EM> O registro SRV é usado no caso de mobilidade e notificação por push. Para reduzir esse problema e controlar a sua descoberta, desmarque a configuração <STRONG>habilitar descoberta de domínio de parceiro</STRONG> para desativar a descoberta.



</div>

Para configurar o XMPP (Extensible Messaging and Presence Protocol) para sua implantação, você cria dois registros de DNS (sistema de nomes de domínio) em um servidor DNS externo que resolverá os registros para o serviço de borda de acesso do servidor de borda ou do pool de borda.

Ao configurar o DNS (sistema de nomes de domínio) para conectividade de mensagens instantâneas públicas, você verá que a configuração que dá suporte a usuários externos oferecerá suporte à conectividade de IM pública. Se você já configurou o servidor de borda ou o pool de borda, deverá ter os registros de DNS necessários para dar suporte à conectividade de IM pública.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Resumo de DNS-Federação SIP, incluindo conectividade de mensagens instantâneas públicas


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>FQDN</th>
<th>Endereço IP/registro de host FQDN</th>
<th>Mapeia para/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Externo/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>A interface externa do serviço de borda de acesso necessária para a descoberta automática de DNS da sua Federação para outros parceiros de Federação potenciais e é conhecido como "domínios SIP permitidos" (chamado de Federação avançada em versões anteriores). Repetir conforme necessário para todos os domínios SIP com usuários habilitados para Lync</p>



> [!IMPORTANT]
> Este registro SRV é necessário para mobilidade e o push notification clearing house. Nos casos em que há mais de um domínio SIP, crie e publique um registro SRV para cada domínio que terá clientes móveis do Lync. O serviço de notificação por push e o serviço de notificação por push da Apple podem não funcionar conforme o esperado se não houver um registro SRV explícito para cada domínio SIP para o qual a implantação oferece suporte.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Resumo de DNS-protocolo de presença e mensagens extensíveis (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>FQDN</th>
<th>Endereço IP/registro de host FQDN</th>
<th>Mapeia para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Externo/SRV/5269</p></td>
<td><p>_xmpp-Server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário habilitado para Lync. Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP. Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/A</p></td>
<td><p>xmpp.contoso.com (por exemplo)</p></td>
<td><p>Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o proxy do XMPP</p></td>
<td><p>Aponta para o serviço de borda de acesso ou o pool de borda que hospeda o serviço de proxy XMPP. Tipicamente, o registro SRV que você criar apontará para este host (A ou AAAA) record</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando a Federação XMPP no Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurando notificações por push no Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gerenciar domínios federados SIP para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

