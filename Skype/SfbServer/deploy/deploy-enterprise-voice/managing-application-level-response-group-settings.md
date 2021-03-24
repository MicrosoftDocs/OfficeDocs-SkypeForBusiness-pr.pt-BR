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
description: Gerenciando configurações do Grupo de Resposta no nível do aplicativo, como configurações de música em espera e toque, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 941164fb3a99f62303b45f587b64e7aff9cb1393
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103467"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gerenciando configurações do Grupo de Resposta no nível do aplicativo no Skype for Business
 
Gerenciando configurações do Grupo de Resposta no nível do aplicativo, como configurações de música em espera e toque, no Skype for Business Server Enterprise Voice.
  
As configurações no nível do aplicativo do Grupo de Resposta incluem a configuração padrão de música em espera, o arquivo de áudio padrão de música em espera, o período de grace de retorno de toque do agente e a configuração de contexto de chamada. É possível definir apenas um conjunto de configurações a nível de aplicativo por pool. Para exibir as configurações no nível do aplicativo, use o cmdlet **Get-CsRgsConfiguration.** Para modificar as configurações no nível do aplicativo, use o cmdlet **Set-CsRgsConfiguration.**
  
A música padrão em espera é tocada quando uma chamada é colocada em espera somente se nenhuma música personalizada em espera for definida. O contexto de chamada está disponível apenas para filas atribuídas a fluxos de trabalho interativos. Se o contexto de chamada estiver habilitado, um agente poderá ver informações como tempo de espera do chamador ou perguntas e respostas de fluxo de trabalho quando a chamada é recebida.
  
### <a name="to-modify-response-group-application-level-settings"></a>Para modificar as configurações de nível de aplicativo do Grupo de Resposta

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**
    
3. Na linha de comando, execute:
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Por exemplo:
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Para especificar um arquivo de áudio a ser usado como a música padrão em espera, você precisa importar o arquivo de áudio primeiro. Por exemplo:
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Confira também

[Get-CsRgsConfiguration](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)