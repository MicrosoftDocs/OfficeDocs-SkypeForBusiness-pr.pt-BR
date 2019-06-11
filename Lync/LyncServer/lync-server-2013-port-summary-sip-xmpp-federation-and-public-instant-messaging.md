---
title: Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2edcad9806c5e6c8714f3face301211633a53fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-15_

Os requisitos de portabilidade, protocolo e firewall para federação com o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server são semelhantes aos do servidor de borda implantado. Os clientes iniciam a comunicação com o serviço de borda de acesso por TLS/SIP/TCP 443. No entanto, os parceiros federados iniciarão as comunicações com o serviço de borda de acesso sobre MTLS/SIP/TCP 5061.

Para configurar o firewall para portas e protocolos necessários para dar suporte à conectividade de mensagens instantâneas públicas, primeiro Observe que o SIP/MTLS/TCP 5061 é bidirecional para a conta da capacidade dos contatos no provedor de IM públicos entrarem em contato com os clientes do Lync ou do Lync para entre em contato com contatos públicos de mensagens instantâneas.

O Windows Live Messenger pode participar de comunicações de áudio/vídeo com clientes do Lync. Isso conta com uma configuração de protocolo e porta de firewall muito parecidas que você normalmente teria no firewall para dar suporte a clientes Lync como usuários externos.

<div>


> [!IMPORTANT]
> Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer mais licenças de usuário/dispositivo além da licença de acesso de cliente padrão do Lync (CAL). A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.<BR>A Federação com contatos de cliente do Messenger será encerrada oficialmente em 15 de março de 2013, exceto para a China continental. O Skype se tornará o cliente de Federação para usuários federados que usaram anteriormente o Messenger.



</div>

As portas e protocolos definidos para o proxy de protocolo de presença e mensagens extensível (XMPP) implantadas no servidor de borda permitem comunicações do parceiro federado do XMPP com o servidor de borda e também permite a comunicação do servidor de borda com o XMPP parceiro federado. Uma regra também é definida no firewall de face interna do servidor front-end ou do pool de front-ends para o servidor de borda ou o pool de bordas.

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
<th>Função/protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Endereço IP público do serviço de borda do Access</p></td>
<td><p>Qualquer um</p></td>
<td><p>Para conectividade de mensagens de chat públicas e federadas usando SIP</p></td>
</tr>
</tbody>
</table>


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

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Resumo de firewall-mensagens extensíveis e protocolo de presença (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP ou UDP/porta</th>
<th>Fonte (endereço IP)</th>
<th>Destino (endereço IP)</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP da interface do serviço de borda do Access</p></td>
<td><p>Porta de comunicação de servidor para servidor padrão para XMPP. Permite a comunicação com o servidor de borda XMPP o proxy de parceiros de XMPP federado</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Endereço IP da interface do serviço de borda do Access</p></td>
<td><p>Qualquer um</p></td>
<td><p>Porta de comunicação de servidor para servidor padrão para XMPP. Permite a comunicação do proxy do servidor de borda XMPP com parceiros do XMPP federado</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Qualquer um</p></td>
<td><p>IP de interface do servidor de borda interna</p></td>
<td><p>Tráfego de XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-end para o servidor de borda</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Cenários de acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar firewall A/V externo e requisitos de porta para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Gerenciar parceiros XMPP federados no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

