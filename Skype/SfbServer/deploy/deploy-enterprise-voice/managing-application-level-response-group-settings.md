---
title: Gerenciando configurações do Grupo de Resposta no nível do aplicativo no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gerenciamento de configurações do Grupo de Resposta em nível de aplicativo, como música de espera e configurações de retorno de toque, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: d41211b83e5ce0c27bb9efe1d3d15a6289ae38fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830781"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="b33f3-103">Gerenciando configurações do Grupo de Resposta no nível do aplicativo no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b33f3-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="b33f3-104">Gerenciamento de configurações do Grupo de Resposta em nível de aplicativo, como música de espera e configurações de retorno de toque, no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b33f3-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b33f3-105">As configurações em nível de aplicativo para o aplicativo Grupo de Resposta incluem a configuração de música de espera padrão, o arquivo de áudio de música de espera padrão, o período de carência de retorno de toque do agente e a configuração de contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="b33f3-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="b33f3-106">É possível definir apenas um conjunto de configurações a nível de aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="b33f3-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="b33f3-107">Para exibir as configurações no nível do aplicativo, use o cmdlet **Get-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="b33f3-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="b33f3-108">Para modificar as configurações no nível do aplicativo, use o cmdlet **Set-CsRgsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="b33f3-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="b33f3-109">A música de espera padrão é tocada quando uma chamada é colocada em espera somente se nenhuma música de espera personalizada for definida.</span><span class="sxs-lookup"><span data-stu-id="b33f3-109">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="b33f3-110">O contexto de chamada está disponível apenas para filas atribuídas a fluxos de trabalho interativos.</span><span class="sxs-lookup"><span data-stu-id="b33f3-110">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="b33f3-111">Se o contexto de chamada estiver habilitado, um agente poderá ver informações como tempo de espera do chamador ou perguntas e respostas do fluxo de trabalho quando a chamada for recebida.</span><span class="sxs-lookup"><span data-stu-id="b33f3-111">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="b33f3-112">Para modificar as configurações no nível de aplicativo do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="b33f3-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="b33f3-113">Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="b33f3-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="b33f3-114">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="b33f3-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b33f3-115">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b33f3-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="b33f3-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b33f3-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="b33f3-117">Para especificar um arquivo de áudio a ser usado como a música de espera padrão, você precisa importar o arquivo de áudio primeiro.</span><span class="sxs-lookup"><span data-stu-id="b33f3-117">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="b33f3-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b33f3-118">For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="b33f3-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="b33f3-119">See also</span></span>

[<span data-ttu-id="b33f3-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b33f3-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="b33f3-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b33f3-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="b33f3-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="b33f3-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
