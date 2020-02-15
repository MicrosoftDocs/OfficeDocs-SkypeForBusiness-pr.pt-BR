---
title: 'Lync Server 2013: Gerenciando configurações do grupo de resposta no nível do aplicativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1dccc404350e10b61ea0917c0bd6b6d7e44b333
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="1225c-102">Gerenciando as configurações do grupo de resposta no nível do aplicativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1225c-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1225c-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1225c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1225c-104">As configurações de nível de aplicativo para o aplicativo de grupo de resposta incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia de retorno de toque do agente e a configuração do contexto da chamada.</span><span class="sxs-lookup"><span data-stu-id="1225c-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="1225c-105">É possível definir apenas um conjunto de configurações a nível de aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="1225c-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="1225c-106">Para exibir as configurações no nível do aplicativo, use o cmdlet **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1225c-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="1225c-107">Para modificar as configurações no nível do aplicativo, use o cmdlet **set-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1225c-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="1225c-108">O padrão de música em espera é tocado quando uma chamada é colocada em espera somente se nenhuma música em espera personalizada é definida.</span><span class="sxs-lookup"><span data-stu-id="1225c-108">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="1225c-109">O contexto de chamada está disponível somente para filas atribuídas a fluxos de trabalho interativos.</span><span class="sxs-lookup"><span data-stu-id="1225c-109">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="1225c-110">Se o contexto de chamada estiver habilitado, um agente poderá ver informações como tempo de espera do chamador ou perguntas e respostas de fluxo de trabalho quando a chamada for recebida.</span><span class="sxs-lookup"><span data-stu-id="1225c-110">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="1225c-111">Para modificar as configurações no nível do aplicativo grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="1225c-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="1225c-112">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="1225c-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="1225c-113">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1225c-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1225c-114">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="1225c-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="1225c-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1225c-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="1225c-116">Para especificar um arquivo de áudio para usar como a música padrão em espera, você precisará importar primeiro o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="1225c-116">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="1225c-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1225c-117">For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1225c-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1225c-118">See Also</span></span>


[<span data-ttu-id="1225c-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="1225c-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="1225c-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="1225c-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="1225c-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="1225c-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

