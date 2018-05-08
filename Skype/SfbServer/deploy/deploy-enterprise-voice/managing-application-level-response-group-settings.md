---
title: Gerenciando as configurações do Grupo de Resposta no nível do aplicativo no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gerenciando configurações de grupo de resposta de nível de aplicativo, como configurações de música de espera e chamada de retorno, no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: eaf31904958997561be056da728ff3b0b31f9d8b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business-2015"></a><span data-ttu-id="2286a-103">Gerenciando as configurações do Grupo de Resposta no nível do aplicativo no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="2286a-103">Managing application-level Response Group settings in Skype for Business 2015</span></span>
 
<span data-ttu-id="2286a-104">Gerenciando configurações de grupo de resposta de nível de aplicativo, como configurações de música de espera e chamada de retorno, no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2286a-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="2286a-105">Configurações de nível de aplicativo para o aplicativo grupo de resposta incluem a configuração de música de espera padrão, o arquivo de áudio de música de espera padrão, o período de cortesia de chamada de retorno do agente e a configuração do contexto da chamada.</span><span class="sxs-lookup"><span data-stu-id="2286a-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="2286a-106">Você pode definir apenas um conjunto de configurações do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="2286a-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="2286a-107">Para exibir as configurações de nível de aplicativo, use o cmdlet **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2286a-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="2286a-108">Para modificar as configurações de nível de aplicativo, use o cmdlet **Set-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2286a-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="2286a-p102">A música de espera padrão é tocada quando uma chamada é coloca em espera, apenas se nenhuma música de espera personalizada for definida. O contexto de chamada está disponível somente para filas atribuídas aos fluxos de trabalho interativos. Se o contexto de chamada for ativado, um agente poderá ver informações como o tempo de espera do chamador ou perguntas e respostas do fluxo de trabalho quando a chamada for recebida.</span><span class="sxs-lookup"><span data-stu-id="2286a-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="2286a-112">Para modificar as configurações de nível de aplicativo do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="2286a-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="2286a-113">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="2286a-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="2286a-114">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="2286a-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2286a-115">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="2286a-115">At the command line, run:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="2286a-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2286a-116">For example:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="2286a-p103">Para especificar um arquivo de áudio para ser usado como a música de espera padrão, você precisa primeiro importar o arquivo de áudio. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2286a-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="2286a-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2286a-119">See also</span></span>

#### 

[<span data-ttu-id="2286a-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="2286a-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="2286a-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="2286a-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="2286a-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="2286a-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

