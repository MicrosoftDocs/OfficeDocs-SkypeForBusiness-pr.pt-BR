---
title: 'Lync Server 2013: Resumo de porta-conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16430849221631d9b540f5ee51b0a07758a38b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Resumo de portabilidade-conectividade de mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-16_

Para configurar o seu firewall para portas e protocolos necessários para dar suporte à conectividade de mensagens instantâneas públicas, primeiro Observe que SIP/MTLS/TCP 5061 é bidirecional para a conta da capacidade dos contatos no provedor de IM públicos entrarem em contato com os clientes do Lync ou para que o Lync entre em contato com contatos públicos de mensagens instantâneas.

O Windows Live Messenger pode participar de comunicações de áudio/vídeo com clientes do Lync. Isso conta com uma configuração de protocolo e porta de firewall muito parecidas que você normalmente teria no firewall para dar suporte a clientes Lync como usuários externos.

<div>


> [!IMPORTANT]  
> Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer mais licenças de usuário/dispositivo além da licença de acesso de cliente padrão do Lync (CAL). A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.<BR>A Federação com contatos de cliente do Messenger será encerrada oficialmente em 15 de março de 2013, exceto para a China continental. O Skype se tornará o cliente de Federação para usuários federados que usaram anteriormente o Messenger.



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumo do Firewall – Conectividade de mensagens instantâneas públicas


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Parceiros de conectividade de mensagens de chat públicas</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Para conectividade de mensagem de chat pública e federada que usa SIP.</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Parceiros de conectividade de mensagens de chat públicas</p></td>
<td><p>Para conectividade de mensagem de chat pública e federada que usa SIP.</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Clientes</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Tráfego SIP do cliente ao servidor para o acesso do usuário externo.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000 A 59.999</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Clientes do Live Messenger</p></td>
<td><p>Usado para sessões de A/V com o Windows Live Messenger se a conectividade de mensagem de chat pública estiver configurada.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Clientes do Live Messenger</p></td>
<td><p>Necessário para conectividade de IM pública com o Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes do Live Messenger</p></td>
<td><p>Interface de acesso do servidor de borda</p></td>
<td><p>Necessário para conectividade de IM pública com o Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Cenários de acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar firewall A/V externo e requisitos de porta para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

