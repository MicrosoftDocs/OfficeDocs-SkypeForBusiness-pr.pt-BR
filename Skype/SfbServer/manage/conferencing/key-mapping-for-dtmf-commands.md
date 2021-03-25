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
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="0f364-103">Gerenciar mapeamento de chaves para comandos DTMF no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f364-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="0f364-104">**Resumo:** Saiba como gerenciar o mapeamento de chaves de comandos DTMF (multifrequência de tom duplo) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0f364-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="0f364-105">Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual).</span><span class="sxs-lookup"><span data-stu-id="0f364-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="0f364-106">Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="0f364-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="0f364-107">Para gerenciar as chaves usadas para os comandos DTMF, use o Shell de Gerenciamento do Skype for Business Server com os cmdlets **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration** e **New-CsDialinConferencingDtmfConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="0f364-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="0f364-108">Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="0f364-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="0f364-109">Gerenciar o mapeamento de chaves de comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="0f364-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="0f364-110">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0f364-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="0f364-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0f364-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0f364-112">Para exibir as configurações DTMF usadas para conferência discagem, execute o seguinte comando no prompt de comando :</span><span class="sxs-lookup"><span data-stu-id="0f364-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="0f364-113">Para modificar as configurações DTMF usadas para conferência discada, execute o seguinte cmdlet e especifique a tecla a ser pressionada para cada opção que você deseja alterar:</span><span class="sxs-lookup"><span data-stu-id="0f364-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="0f364-114">(Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site.</span><span class="sxs-lookup"><span data-stu-id="0f364-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="0f364-115">O exemplo a seguir troca a tecla pressionada para habilitar ou desabilitar anúncios e a tecla pressionada para mudo e desmute todos os participantes.</span><span class="sxs-lookup"><span data-stu-id="0f364-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="0f364-116">Como nenhuma Identidade é especificada, essas alterações se aplicam às configurações DTMF globais:</span><span class="sxs-lookup"><span data-stu-id="0f364-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="0f364-117">Para obter mais informações, consulte [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)e [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0f364-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
