---
title: 'Lync Server 2013: gerenciar configurações de grupo de resposta no nível do aplicativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bac03eaafc40ccd86aca8514319e3bf632ea6a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="ca52d-102">Gerenciando configurações de grupo de resposta no nível do aplicativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca52d-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca52d-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ca52d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ca52d-104">As configurações no nível do aplicativo para o aplicativo de grupo de resposta incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia do agente e a configuração do contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="ca52d-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="ca52d-105">Você pode definir apenas um conjunto de configurações do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="ca52d-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="ca52d-106">Para exibir as configurações do aplicativo, use o cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ca52d-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="ca52d-107">Para modificar as configurações do aplicativo, use o cmdlet **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ca52d-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="ca52d-p102">A música de espera padrão é tocada quando uma chamada é coloca em espera, apenas se nenhuma música de espera personalizada for definida. O contexto de chamada está disponível somente para filas atribuídas aos fluxos de trabalho interativos. Se o contexto de chamada for ativado, um agente poderá ver informações como o tempo de espera do chamador ou perguntas e respostas do fluxo de trabalho quando a chamada for recebida.</span><span class="sxs-lookup"><span data-stu-id="ca52d-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="ca52d-111">Para modificar as configurações em nível de aplicativo de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="ca52d-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="ca52d-112">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="ca52d-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="ca52d-113">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca52d-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ca52d-114">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="ca52d-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="ca52d-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ca52d-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="ca52d-p103">Para especificar um arquivo de áudio para ser usado como a música de espera padrão, você precisa primeiro importar o arquivo de áudio. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ca52d-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca52d-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="ca52d-118">See Also</span></span>


[<span data-ttu-id="ca52d-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca52d-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="ca52d-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca52d-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="ca52d-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="ca52d-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

