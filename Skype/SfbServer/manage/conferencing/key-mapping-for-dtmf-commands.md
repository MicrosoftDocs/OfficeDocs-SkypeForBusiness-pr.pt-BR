---
title: Gerenciar o mapeamento de teclas para comandos DTMF no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Resumo: saiba como gerenciar o mapeamento de chave de comandos de multifrequência (DTMF) de dois tons no Skype for Business Server.'
ms.openlocfilehash: fdb9846da81c4029fa67df606fa021397a46b3ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818532"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gerenciar o mapeamento de teclas para comandos DTMF no Skype for Business Server
 
**Resumo:** Saiba como gerenciar o mapeamento de chave de comandos de multifrequência (DTMF) de dois tons no Skype for Business Server.
  
Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual). Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone. 
  
Para gerenciar as chaves usadas para os comandos DTMF, use o Shell de gerenciamento do Skype for Business Server com os cmdlets **Get-CsDialinConferencingDtmfConfiguration**, **set-CsDialinConferencingDtmfConfiguration**e **New-CsDialinConferencingDtmfConfiguration** .
  
Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gerenciar o mapeamento de teclas dos comandos DTMF

1. Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para exibir as configurações de DTMF usadas para conferência discada, execute o seguinte comando no prompt de comando:
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Para modificar as configurações de DTMF usadas para conferência discada, execute o seguinte cmdlet e especifique a tecla a ser pressionada para cada opção que você deseja alterar:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site.
    
O seguinte exemplo troca a tecla pressionada para habilitar ou desabilitar os anúncios e a tecla pressionada para ativar ou desativar o opção Mudo de todos os participantes. Como nenhuma Identidade é especificada, essas alterações se aplicam às configurações DTMF globais:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Para obter mais informações, consulte [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

