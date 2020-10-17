---
title: 'Lync Server 2013: gerenciamento de usuário do Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504198"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Gerenciamento de usuários do Exchange hospedado no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Para fornecer serviços de caixa postal para os usuários do Lync Server 2013 cujas caixas de correio estão localizadas em um serviço do Exchange hospedado, você deve habilitar suas contas de usuário para caixa postal hospedada.

<div>


> [!NOTE]  
> Antes que um usuário do Lync Server 2013 possa ser habilitado para caixa postal hospedada, uma política de caixa postal hospedada que se aplica à conta de usuário correspondente deve ser implantada. A política pode ser global, site ou por usuário no escopo, contanto que se aplique ao usuário que você deseja habilitar. Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>O atributo msExchUCVoiceMailSettings

O Lync Server 2013 introduz um novo atributo de usuário chamado **msExchUCVoiceMailSettings**, que é criado como parte da preparação do esquema do Active Directory 2013 do Lync Server. Este atributo com vários valores contém as configurações de caixa postal que são compartilhadas pelo Lync Server 2013 e o serviço do Exchange hospedado.

O serviço do Exchange hospedado pode, em alguns casos, definir o valor do atributo msExchUCVoiceMailSettings no processo de habilitar a UM do Exchange, ou durante o processo de transferência de caixas de correio para um servidor Exchange hospedado. Se esse atributo não for definido pelo Exchange, o administrador do Lync Server 2013 deverá defini-lo executando o cmdlet Set-CsUser, conforme descrito anteriormente neste tópico.

Os pares de chave/valor do atributo e seus autores são mostrados na tabela a seguir.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Os pares de chave/valor do atributo msExchUCVoiceMailSettings

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor</th>
<th>Autor</th>
<th>Significado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>O usuário foi habilitado para o acesso de UM hospedado pelo Exchange Server. O aplicativo de roteamento de UM do Exchange verificará a política de caixa postal hospedada do usuário para obter detalhes de roteamento.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>O usuário foi desabilitado para acesso de UM hospedado pelo Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>O usuário foi habilitado para o acesso de UM hospedado pelo Lync Server 2013. O aplicativo de roteamento ExUM do Lync Server 2013 fará a verificação da política de caixa postal hospedada do usuário para obter detalhes de roteamento.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>O usuário foi desabilitado para acesso de UM hospedado pelo Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Se o atributo já tiver valores diferentes de um dos pares chave/valor do Lync Server 2013 (CSHostedVoiceMail = 0 ou CSHostedVoiceMail = 1), um aviso indicará que o atributo pode ser gerenciado por um aplicativo diferente. Por exemplo, um aviso será exibido se o par chave/valor ExchangeHostedVoiceMail = 0 ou ExchangeHostedVoiceMail = 1 já estiver presente. Nesse caso, você pode alterar o valor editando-o como o Active Directory ou executar o cmdlet a seguir para definir o valor como nulo:<BR>Set-CsUser – usuário de identidade – HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Habilitando usuários para caixa postal hospedada

Para habilitar as chamadas de caixa postal de um usuário para serem encaminhadas para o UM do Exchange hospedado, você deve executar o cmdlet Set-CsUser para definir o valor do parâmetro *HostedVoiceMail* . Esse parâmetro também informa ao Lync Server 2013 para acender o indicador "Call de caixa postal".

  - O exemplo a seguir habilita a conta de usuário de pilar Ackerman para caixa postal hospedada:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    O cmdlet verifica se uma política de caixa postal hospedada (global, no nível do site ou por usuário) se aplica a esse usuário. Se nenhuma política for aplicada, o cmdlet falhará.

  - O exemplo a seguir desabilita a conta de usuário de pilar Ackerman para caixa postal hospedada:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    O cmdlet verifica se nenhuma política de caixa postal hospedada (global, no nível do site ou por usuário) se aplica a esse usuário. Se uma política for aplicada, o cmdlet falhará.

Para obter detalhes sobre como usar o cmdlet Set-CsUser, consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

