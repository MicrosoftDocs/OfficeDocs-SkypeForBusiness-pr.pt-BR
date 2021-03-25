---
title: Gerenciar mapeamento de chaves para comandos DTMF no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Resumo: saiba como gerenciar o mapeamento de chaves dos comandos DTMF (dual-tone multi-frequency) no Skype for Business Server.'
ms.openlocfilehash: 6b409ccce10128fdd7776e3ea77d6ee17d4a49f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119440"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gerenciar mapeamento de chaves para comandos DTMF no Skype for Business Server
 
**Resumo:** Saiba como gerenciar o mapeamento de chaves de comandos DTMF (multifrequência de tom duplo) no Skype for Business Server.
  
Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual). Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone. 
  
Para gerenciar as chaves usadas para os comandos DTMF, use o Shell de Gerenciamento do Skype for Business Server com os cmdlets **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration** e **New-CsDialinConferencingDtmfConfiguration.**
  
Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gerenciar o mapeamento de chaves de comandos DTMF

1. Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**
    
3. Para exibir as configurações DTMF usadas para conferência discagem, execute o seguinte comando no prompt de comando :
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Para modificar as configurações DTMF usadas para conferência discada, execute o seguinte cmdlet e especifique a tecla a ser pressionada para cada opção que você deseja alterar:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site.
    
O exemplo a seguir troca a tecla pressionada para habilitar ou desabilitar anúncios e a tecla pressionada para mudo e desmute todos os participantes. Como nenhuma Identidade é especificada, essas alterações se aplicam às configurações DTMF globais:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Para obter mais informações, consulte [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
