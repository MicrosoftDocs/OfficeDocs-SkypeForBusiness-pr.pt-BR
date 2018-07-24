---
title: Gerenciar o mapeamento de teclas para comandos DTMF no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Resumo: Saiba como gerenciar o mapeamento de teclas dos comandos de multifrequência de tom DTMF (Multifrequência) no Skype para Business Server.'
ms.openlocfilehash: 629db0c94b71b9cbf54ebf2c6f6a5074b4b611fa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992679"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="b51c2-103">Gerenciar o mapeamento de teclas para comandos DTMF no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b51c2-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="b51c2-104">**Resumo:** Saiba como gerenciar o mapeamento de teclas dos comandos de multifrequência de tom DTMF (Multifrequência) no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b51c2-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="b51c2-p101">Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual). Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="b51c2-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="b51c2-107">Para gerenciar as teclas usadas para os comandos DTMF, use o Skype do Shell de gerenciamento de servidor de negócios com o **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**e ** New-CsDialinConferencingDtmfConfiguration** cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b51c2-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="b51c2-108">Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="b51c2-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="b51c2-109">Gerenciar o mapeamento de teclas dos comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="b51c2-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="b51c2-110">Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b51c2-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="b51c2-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b51c2-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b51c2-112">Para exibir as configurações de DTMF usadas para conferência discada, execute o seguinte comando no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="b51c2-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
  ```
  Get-CsDialinConferencingDtmfConfiguration
  ```

4. <span data-ttu-id="b51c2-113">Para modificar as configurações de DTMF usadas para conferência discada, execute o seguinte cmdlet e especifique a tecla a ser pressionada para cada opção que você deseja alterar:</span><span class="sxs-lookup"><span data-stu-id="b51c2-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
  ```
  Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
[-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
[-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
[-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
[-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
  ```

5. <span data-ttu-id="b51c2-114">(Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site.</span><span class="sxs-lookup"><span data-stu-id="b51c2-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="b51c2-p102">O seguinte exemplo troca a tecla pressionada para habilitar ou desabilitar os anúncios e a tecla pressionada para ativar ou desativar o opção Mudo de todos os participantes. Como nenhuma Identidade é especificada, essas alterações se aplicam às configurações DTMF globais:</span><span class="sxs-lookup"><span data-stu-id="b51c2-p102">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="b51c2-117">Para obter mais informações, consulte [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b51c2-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

