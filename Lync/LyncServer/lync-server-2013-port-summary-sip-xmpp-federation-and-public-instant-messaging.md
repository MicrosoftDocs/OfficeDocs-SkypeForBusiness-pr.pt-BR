---
title: Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7119bfd6209ac9a7d8eb2c4adfddb75c3601116d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508748"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-15_

Requisitos de porta, protocolo e firewall para federação com o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server são semelhantes aos do servidor de borda implantado. Os clientes iniciam a comunicação com o serviço de borda de acesso por TLS/SIP/TCP 443. Parceiros federados no entanto, iniciarão comunicações com o serviço de borda de acesso sobre MTLS/SIP/TCP 5061.

Para configurar seu firewall para portas e protocolos necessários para dar suporte à conectividade de mensagens instantâneas públicas, primeiro Observe que SIP/MTLS/TCP 5061 é bidirecional para considerar a capacidade de os contatos no provedor de IM público entrarem em contato com os clientes do Lync ou para o Lync entrarem em contato com contatos públicos de IM.

O Windows Live Messenger pode participar de comunicações de áudio/vídeo com clientes Lync. Isso conta para a porta de firewall muito parecida e a configuração de protocolo que você normalmente teria no firewall para dar suporte aos clientes do Lync como usuários externos.

<div>


> [!IMPORTANT]
> Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer nenhuma licença adicional de usuário/dispositivo além da licença de acesso para cliente (CAL) do Lync Standard. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.<BR>A Federação com contatos do cliente do Messenger será oficialmente termina em 15 de março de 2013, exceto para a China continental. O Skype se tornará o cliente de Federação para usuários federados que usavam o Messenger anteriormente.



</div>

As portas e os protocolos definidos para o proxy XMPP (Extensible Messaging and Presence Protocol) implantado no servidor de borda permitem que as comunicações do parceiro federado do XMPP ao servidor de borda, além de permitir a comunicação do servidor de borda com o parceiro federado do XMPP. Uma regra também é definida no firewall de face interna do servidor front-end ou do pool de front-ends para o servidor de borda ou o pool de borda.

<div>

## <a name="firewall-summary---sip-federation"></a>Resumo do firewall-Federação SIP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Endereço IP público do serviço da Borda de Acesso</p></td>
<td><p>Qualquer</p></td>
<td><p>Para conectividade a redes públicas e federadas de IM usando SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumo do firewall – Conectividade pública de mensagens instantâneas


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Parceiros de conectividade pública de IM</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Para conectividade federada e pública de IM que usam SIP.</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Parceiros de conectividade pública de IM</p></td>
<td><p>Para conectividade federada e pública de IM que usam SIP.</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Clientes</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Tráfego SIP de cliente para servidor para acesso de usuário externo.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Clientes Live Messenger</p></td>
<td><p>Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Clientes Live Messenger</p></td>
<td><p>Necessário para conectividade pública de IM com o Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes Live Messenger</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Necessário para conectividade pública de IM com o Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Resumo do firewall-protocolo de presença e mensagens extensíveis (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP ou UDP/Porta</th>
<th>Origem (endereço IP)</th>
<th>Destino (endereço IP)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço IP da interface de serviço de borda de acesso</p></td>
<td><p>Porta padrão de comunicação entre servidores para XMPP. Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Endereço IP da interface de serviço de borda de acesso</p></td>
<td><p>Qualquer</p></td>
<td><p>Porta padrão de comunicação entre servidores para XMPP. Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Qualquer</p></td>
<td><p>IP da interface de servidor de borda interna</p></td>
<td><p>Tráfego XMPP interno do Gateway XMPP no servidor front-end ou no pool de front-ends para o servidor de borda</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Gerenciar parceiros federados do XMPP no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

