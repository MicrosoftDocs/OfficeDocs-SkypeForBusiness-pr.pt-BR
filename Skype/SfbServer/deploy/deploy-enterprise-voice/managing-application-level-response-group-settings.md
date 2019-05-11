---
title: Gerenciando configurações de grupo de resposta de nível de aplicativo no Skype para negócios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gerenciando configurações de grupo de resposta de nível de aplicativo, como configurações de música de espera e chamada de retorno, no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 41daedd21c5d7ea6f210594c66e3f20906ad90a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892332"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gerenciando configurações de grupo de resposta de nível de aplicativo no Skype para negócios
 
Gerenciando configurações de grupo de resposta de nível de aplicativo, como configurações de música de espera e chamada de retorno, no Skype para Business Server Enterprise Voice.
  
Configurações de nível de aplicativo para o aplicativo grupo de resposta incluem a configuração de música de espera padrão, o arquivo de áudio de música de espera padrão, o período de cortesia de chamada de retorno do agente e a configuração do contexto da chamada. Você pode definir apenas um conjunto de configurações do aplicativo por pool. Para exibir as configurações do aplicativo, use o cmdlet **Get-CsRgsConfiguration**. Para modificar as configurações do aplicativo, use o cmdlet **Set-CsRgsConfiguration**.
  
A música de espera padrão é tocada quando uma chamada é coloca em espera, apenas se nenhuma música de espera personalizada for definida. O contexto de chamada está disponível somente para filas atribuídas aos fluxos de trabalho interativos. Se o contexto de chamada for ativado, um agente poderá ver informações como o tempo de espera do chamador ou perguntas e respostas do fluxo de trabalho quando a chamada for recebida.
  
### <a name="to-modify-response-group-application-level-settings"></a>Para modificar as configurações de nível de aplicativo do grupo de resposta

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Na linha de comando, execute:
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Por exemplo:
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Para especificar um arquivo de áudio para ser usado como a música de espera padrão, você precisa primeiro importar o arquivo de áudio. Por exemplo:
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Confira também

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
