---
title: 'Lync Server 2013: configurar definições de estacionamento de chamadas'
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
ms.openlocfilehash: 644ec44d4086b0acc326e043cbf63d7ceb2c640c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="ec3be-102">Definir configurações de estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec3be-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec3be-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ec3be-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ec3be-104">Se não quiser usar as configurações de estacionamento de chamadas padrão, você pode personalizá-las.</span><span class="sxs-lookup"><span data-stu-id="ec3be-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="ec3be-105">Quando você instala o aplicativo de estacionamento de chamada, as configurações globais são configuradas por padrão.</span><span class="sxs-lookup"><span data-stu-id="ec3be-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="ec3be-106">É possível modificar as configurações globais e também especificar configurações específicas do site.</span><span class="sxs-lookup"><span data-stu-id="ec3be-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="ec3be-107">Use o cmdlet **New-CsCpsConfiguration** para criar configurações específicas do site.</span><span class="sxs-lookup"><span data-stu-id="ec3be-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="ec3be-108">Use o cmdlet **Set-CsCpsConfiguration** para modificar as configurações existentes.</span><span class="sxs-lookup"><span data-stu-id="ec3be-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec3be-109">No mínimo, recomendamos configurar a opção <STRONG>OnTimeoutURI</STRONG> para o destino de fallback a ser usado quando uma chamada estacionada excede o tempo limite e o retorno de toque falha.</span><span class="sxs-lookup"><span data-stu-id="ec3be-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="ec3be-110">Use os cmdets **New-CsCpsConfiguration** ou **Set-CsCpsConfiguration** para definir qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="ec3be-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec3be-111">Esta opção:</span><span class="sxs-lookup"><span data-stu-id="ec3be-111">This option:</span></span></th>
<th><span data-ttu-id="ec3be-112">Especifica:</span><span class="sxs-lookup"><span data-stu-id="ec3be-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec3be-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="ec3be-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="ec3be-114">A quantidade de tempo que passa após uma chamada ser estacionada antes que ela toque de volta no telefone no qual foi atendida.</span><span class="sxs-lookup"><span data-stu-id="ec3be-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="ec3be-p102">O valor deve ser inserido no formato hh:mm:ss para especificar horas, minutos e segundos. O valor mínimo é 10 segundos e o valor máximo é 10 minutos. O padrão é 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="ec3be-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec3be-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="ec3be-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="ec3be-119">Se a música é reproduzida para um chamador enquanto uma chamada está estacionada.</span><span class="sxs-lookup"><span data-stu-id="ec3be-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="ec3be-p103">Os valores são True ou False. O padrão é True.</span><span class="sxs-lookup"><span data-stu-id="ec3be-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec3be-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="ec3be-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="ec3be-p104">O número de vezes que uma chamada estacionada retorna o toque para o telefone de resposta antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback que é especificado para <strong>OnTimeoutURI</strong>. O padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="ec3be-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec3be-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="ec3be-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="ec3be-126">O endereço SIP do usuário ou grupo de resposta para o qual uma chamada estacionada não atendida é roteada quando <strong>MaxCallPickupAttempts</strong> é excedido.</span><span class="sxs-lookup"><span data-stu-id="ec3be-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="ec3be-p105">O valor deve ser um URI do SIP que começa com a cadeia de caracteres sip:. Por exemplo, sip:bob@contoso.com. O padrão é nenhum endereço de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="ec3be-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="ec3be-130">Para definir as configurações de estacionamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="ec3be-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="ec3be-131">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ec3be-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ec3be-132">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ec3be-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ec3be-133">Sejam</span><span class="sxs-lookup"><span data-stu-id="ec3be-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ec3be-134">Use o cmdlet <STRONG>Get-CsSite</STRONG> para identificar o site.</span><span class="sxs-lookup"><span data-stu-id="ec3be-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="ec3be-135">Para obter detalhes, consulte Lync Server Management Shell Documentation.</span><span class="sxs-lookup"><span data-stu-id="ec3be-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="ec3be-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ec3be-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ec3be-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ec3be-137">See Also</span></span>


[<span data-ttu-id="ec3be-138">Personalizar o estacionamento de chamada música em espera no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec3be-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="ec3be-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec3be-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="ec3be-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec3be-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="ec3be-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="ec3be-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

