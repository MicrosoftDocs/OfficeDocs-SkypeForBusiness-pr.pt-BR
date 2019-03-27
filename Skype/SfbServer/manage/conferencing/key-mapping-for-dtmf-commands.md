---
title: Gerenciar o mapeamento de teclas para comandos DTMF no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Resumo: Saiba como gerenciar o mapeamento de teclas dos comandos de multifrequência de tom DTMF (Multifrequência) no Skype para Business Server.'
ms.openlocfilehash: 33ab031e6032b6246dd637bc55c9ec6b600f0c82
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898068"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gerenciar o mapeamento de teclas para comandos DTMF no Skype para Business Server
 
**Resumo:** Saiba como gerenciar o mapeamento de teclas dos comandos de multifrequência de tom DTMF (Multifrequência) no Skype para Business Server.
  
Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual). Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone. 
  
Para gerenciar as teclas usadas para os comandos DTMF, use o Skype do Shell de gerenciamento de servidor de negócios com o **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**e ** New-CsDialinConferencingDtmfConfiguration** cmdlets.
  
Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gerenciar o mapeamento de teclas dos comandos DTMF

1. Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para exibir as configurações de DTMF usadas para conferência discada, execute o seguinte comando no prompt de comando:
    
   ```
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Para modificar as configurações de DTMF usadas para conferência discada, execute o seguinte cmdlet e especifique a tecla a ser pressionada para cada opção que você deseja alterar:
    
   ```
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site.
    
O seguinte exemplo troca a tecla pressionada para habilitar ou desabilitar os anúncios e a tecla pressionada para ativar ou desativar o opção Mudo de todos os participantes. Como nenhuma Identidade é especificada, essas alterações se aplicam às configurações DTMF globais:
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Para obter mais informações, consulte [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

