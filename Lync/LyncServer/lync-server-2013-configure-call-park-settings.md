---
title: 'Lync Server 2013: configurar as configurações do estacionamento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee4f12ccf614816e27262f8b393cdc1dac4a7a5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Configurar as definições do estacionamento de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Se não quiser usar as configurações padrão de estacionamento de chamadas, você poderá personalizá-las. Quando você instala o aplicativo de estacionamento de chamada, as configurações globais são configuradas por padrão. É possível modificar as configurações globais e também especificar configurações específicas do site. Use o cmdlet **New-CsCpsConfiguration** para criar configurações específicas do site. Use o cmdlet **Set-CsCpsConfiguration** para modificar as configurações existentes.

<div>


> [!NOTE]  
> No mínimo, recomendamos configurar a opção <STRONG>OnTimeoutURI</STRONG> para o destino de fallback a ser usado quando uma chamada estacionada excede o tempo limite e o retorno de toque falha.



</div>

Use os cmdets **New-CsCpsConfiguration** ou **Set-CsCpsConfiguration** para definir qualquer uma das seguintes configurações:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Esta opção:</th>
<th>Especifica:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>A quantidade de tempo que passa após uma chamada ser estacionada antes que ela toque de volta no telefone no qual foi atendida.</p>
<p>O valor deve ser inserido no formato hh:mm:ss para especificar horas, minutos e segundos. O valor mínimo é 10 segundos e o valor máximo é 10 minutos. O padrão é 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Se a música é reproduzida para um chamador enquanto uma chamada está estacionada.</p>
<p>Os valores são True ou False. O padrão é True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>O número de vezes que uma chamada estacionada retorna o toque para o telefone de resposta antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback que é especificado para <strong>OnTimeoutURI</strong>. O padrão é 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>O endereço SIP do usuário ou grupo de resposta para o qual uma chamada estacionada não atendida é roteada quando <strong>MaxCallPickupAttempts</strong> é excedido.</p>
<p>O valor deve ser um URI do SIP que começa com a cadeia de caracteres sip:. Por exemplo, sip:bob@contoso.com. O padrão é nenhum endereço de encaminhamento.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>Para configurar as configurações do estacionamento de chamadas

1.  Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > Use o cmdlet <STRONG>Get-CsSite</STRONG> para identificar o site. Para obter detalhes, consulte documentação do Shell de gerenciamento do Lync Server.

    
    </div>
    
    Por exemplo:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>Confira também


[Personalizar a chamada de música do parque em espera no Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  


[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

