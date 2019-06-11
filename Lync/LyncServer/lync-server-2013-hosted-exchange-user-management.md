---
title: 'Lync Server 2013: Gerenciamento de usuário no Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Gerenciamento de usuário no Exchange hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Para fornecer serviços de correio de voz para os usuários do Lync Server 2013 cujas caixas de correio estão localizadas em um serviço do Exchange hospedado, você deve habilitar as contas de usuário da caixa postal hospedada.

<div>


> [!NOTE]  
> Para que um usuário do Lync Server 2013 possa ser habilitado para a caixa postal hospedada, uma política de caixa postal hospedada que se aplica à conta de usuário correspondente deve ser implantada. A política pode ser global, site ou por usuário no escopo, desde que se aplique ao usuário que você deseja habilitar. Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">políticas de caixa postal hospedadas no Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>O atributo msExchUCVoiceMailSettings

O Lync Server 2013 introduz um novo atributo de usuário chamado **msExchUCVoiceMailSettings**, que é criado como parte da preparação do esquema do Lync Server 2013 do Lync Server. Este atributo de múltiplos valores contém as configurações de caixa postal que são compartilhadas pelo Lync Server 2013 e o serviço hospedado do Exchange.

O serviço hospedado do Exchange pode, em alguns casos, definir o valor do atributo msExchUCVoiceMailSettings no processo de habilitar o UM Exchange ou durante o processo de transferência de caixas de correio para um servidor do Exchange hospedado. Se esse atributo não for definido pelo Exchange, o administrador do Lync Server 2013 deve defini-lo executando o cmdlet Set-CsUser, conforme descrito anteriormente neste tópico.

Os pares de chave/valor do atributo e seus autores são mostrados na tabela a seguir.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Os pares de chave/valor de atributo msExchUCVoiceMailSettings

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
<td><p>O usuário foi habilitado para o acesso hospedado do UM pelo Exchange Server. O aplicativo de roteamento de UM do Exchange verificará a política de caixa postal hospedada do usuário para obter detalhes de roteamento.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>O usuário foi desativado para o acesso hospedado do UM pelo Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Servidor Lync</p></td>
<td><p>O usuário foi habilitado para o acesso hospedado da UM pelo Lync Server 2013. O aplicativo de roteamento ExUM do Lync Server 2013 verificará a política de caixa postal hospedada do usuário para obter detalhes de roteamento.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Servidor Lync</p></td>
<td><p>O usuário foi desabilitado para o acesso hospedado da UM pelo Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Se o atributo já tiver valores diferentes de um dos pares chave/valor do Lync Server 2013 (CSHostedVoiceMail = 0 ou CSHostedVoiceMail = 1), um aviso indicará que o atributo pode ser gerenciado por um aplicativo diferente. Por exemplo, um aviso será exibido se o par chave/valor ExchangeHostedVoiceMail = 0 ou ExchangeHostedVoiceMail = 1 já estiver presente. Nesse caso, você pode alterar o valor editando-o no Active Directory ou executar o seguinte cmdlet para definir o valor como NULL:<BR>Set-CsUser – usuário da identidade – HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Como habilitar usuários para a caixa postal hospedada

Para permitir que as chamadas de correio de voz de um usuário sejam roteadas para o Exchange UM hospedado, você deve executar o cmdlet Set-CsUser para definir o valor do parâmetro *HostedVoiceMail* . Esse parâmetro também sinaliza o Lync Server 2013 para iluminar o indicador "Call voice mail".

  - O exemplo a seguir habilita a conta de usuário pilar Alverca para a caixa postal hospedada:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    O cmdlet verifica se uma política de caixa postal hospedada (global, em nível de site ou por usuário) se aplica a este usuário. Se nenhuma política for aplicada, o cmdlet falhará.

  - O exemplo a seguir desabilita a conta de usuário pilar Alverca para a caixa postal hospedada:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    O cmdlet verifica se nenhuma política de caixa postal hospedada (global, em nível de site ou por usuário) se aplica a este usuário. Se uma política for aplicada, o cmdlet falhará.

Para obter detalhes sobre como usar o cmdlet Set-CsUser, consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

