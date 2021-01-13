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
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Gerenciando configurações do Grupo de Resposta no nível do aplicativo no Skype for Business
 
Gerenciamento de configurações do Grupo de Resposta em nível de aplicativo, como música de espera e configurações de retorno de toque, no Skype for Business Server Enterprise Voice.
  
As configurações em nível de aplicativo para o aplicativo Grupo de Resposta incluem a configuração de música de espera padrão, o arquivo de áudio de música de espera padrão, o período de carência de retorno de toque do agente e a configuração de contexto de chamada. É possível definir apenas um conjunto de configurações a nível de aplicativo por pool. Para exibir as configurações no nível do aplicativo, use o cmdlet **Get-CsRgsConfiguration.** Para modificar as configurações no nível do aplicativo, use o cmdlet **Set-CsRgsConfiguration.**
  
A música de espera padrão é tocada quando uma chamada é colocada em espera somente se nenhuma música de espera personalizada for definida. O contexto de chamada está disponível apenas para filas atribuídas a fluxos de trabalho interativos. Se o contexto de chamada estiver habilitado, um agente poderá ver informações como tempo de espera do chamador ou perguntas e respostas do fluxo de trabalho quando a chamada for recebida.
  
### <a name="to-modify-response-group-application-level-settings"></a>Para modificar as configurações no nível de aplicativo do Grupo de Resposta

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Na linha de comando, execute:
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Por exemplo:
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Para especificar um arquivo de áudio a ser usado como a música de espera padrão, você precisa importar o arquivo de áudio primeiro. Por exemplo:
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Confira também

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
