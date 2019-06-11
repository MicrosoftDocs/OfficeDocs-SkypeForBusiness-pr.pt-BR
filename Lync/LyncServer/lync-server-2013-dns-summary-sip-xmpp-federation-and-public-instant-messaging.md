---
title: Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumo de DNS-SIP, Federação de XMPP e mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-03-09_

Os registros DNS (sistema de nomes de domínio) que serão necessários para definir uma federação com o Office Communications Server ou com os parceiros do Lync Server são determinados pela sua decisão de permitir a descoberta automática de DNS do seu domínio por outros parceiros de perspectiva. Se você publicar o \_sipfederationtls. \_TCP. * \<Nome\> de domínio SIP* Registro SRV, qualquer outro domínio federado SIP poderá "descobrir" sua Federação. Você pode controlar quais domínios federados podem se comunicar com você usando as configurações permitir domínios e domínios bloqueados no painel de controle do Lync Server, ou definindo a configuração de domínios permitidos ou bloqueados usando o Shell de gerenciamento do Lync Server e o ** **Cmdlets Get, **set**, **New**, **Remove-CsAllowedDomain** e **-CsBlockedDomain** do PowerShell. Para obter informações adicionais sobre como definir as configurações de contratação e o uso dos cmdlets do PowerShell, consulte **Tópicos relacionados** no final deste tópico.

A tabela de Resumo de registros DNS mostra as entradas necessárias para uma federação aberta ou detectável. Se você não quiser implementar a descoberta de Federação, poderá decidir não configurar o \_sipfederationtls. \_TCP. Registro de *nome\> de domínio SIP. \<*

<div>


> [!IMPORTANT]
> Há cenários específicos nos quais você deve ter o sipfederationtls. _ TCP. <EM> &lt;Nome&gt; de domínio SIP</EM> SRV Record, mas você não quer ter uma federação detectável. Uma dessas instâncias é onde você implantou a mobilidade para seus usuários. A PNCH (Mobility Push Notification Clearinghouse) é um tipo especial de Federação usado para clientes móveis do Microsoft Lync no iPhone ou iPad com o Lync 2010 usando o cliente móvel do Lync ou o Windows Phone usando os clientes móveis do Lync 2010 ou Lync 2013. O sipfederationtls. _ TCP. <EM> &lt;Nome&gt; de domínio SIP</EM> O registro SRV é usado no caso de mobilidade e notificação por push. Para reduzir esse problema e controlar sua descoberta, desmarque a configuração <STRONG>habilitar descoberta de domínio parceiro</STRONG> para desativar a descoberta.



</div>

Para configurar o protocolo de presença e mensagens extensíveis (XMPP) para a sua implantação, crie dois registros DNS (sistema de nomes de domínio) em um servidor DNS externo que resolverá os registros para o serviço de borda de acesso do servidor de borda ou do pool de bordas.

Ao configurar o sistema de nomes de domínio (DNS) para conectividade de mensagens instantâneas públicas, você verá que a configuração que dá suporte a usuários externos será compatível com a conectividade de mensagens de chat públicas. Se você já configurou o servidor de borda ou o pool de bordas, deve ter os registros DNS necessários para dar suporte à conectividade de IM pública.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Resumo de DNS-Federação SIP incluindo conectividade de mensagens instantâneas públicas


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
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5061 externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>A interface externa do serviço de borda do Access é necessária para a descoberta automática de DNS da sua Federação para outros parceiros de Federação potenciais e é conhecida como "domínios SIP permitidos" (chamado de Federação aprimorada em versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</p>



> [!IMPORTANT]
> Esse registro SRV é necessário para a mobilidade e a equipe de compensação da notificação por push. Nos casos em que há mais de um domínio SIP, crie e publique um registro SRV para cada domínio que terá clientes móveis do Lync. O serviço de notificação por push e o serviço de notificação por push da Apple podem não funcionar como esperado se não houver um registro SRV explícito para cada domínio SIP compatível com a implantação.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Resumo de DNS-mensagens extensíveis e protocolo de presença (XMPP)


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
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5269 externo</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externa de proxy XMPP no serviço de borda do Access ou no pool de bordas. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync nos quais o contato com contatos do XMPP é permitido pela configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário compatível com o Lync. Um domínio XMPP permitido também deve ser configurado na política de parceiros federados do XMPP. Consulte os tópicos em <strong>Consulte também</strong> para obter detalhes adicionais</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por exemplo)</p></td>
<td><p>Endereço IP do serviço de borda de acesso em seu servidor de borda ou em um pool de bordas que hospeda o proxy XMPP</p></td>
<td><p>Aponta para o serviço de borda de acesso ou o pool de bordas que hospeda o serviço de proxy XMPP. Geralmente, o registro SRV que você cria aponta para esse registro de host (A ou AAAA)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando federação de XMPP no Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurando notificações por push no Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Habilitar ou desabilitar descoberta de parceiros de federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Cenários de acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar requisitios de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gerenciar domínios SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

