---
title: 'Lync Server 2013: (opcional) modificar mapeamento de teclas para comandos DTMF'
description: 'Lync Server 2013: (opcional) modifique o mapeamento de teclas para comandos DTMF.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7581001c31d929163962378a8734435f6d07c6c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565787"
---
# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="52537-103">Opcion Modificar o mapeamento de teclas para comandos DTMF no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52537-103">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52537-104">_**Última modificação do tópico:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="52537-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="52537-p101">Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual). Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone. É possível usar cmdlets para modificar as teclas usadas para os comandos DTMF. Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="52537-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. You can use cmdlets to modify the keys used for the DTMF commands. This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52537-109">Para obter detalhes sobre esses cmdlets e as opções de DTMF possíveis, consulte Lync Server Management Shell Documentation ou ajuda da linha de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52537-109">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="52537-110">Para modificar o mapeamento principal dos comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="52537-110">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="52537-111">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="52537-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="52537-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="52537-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="52537-113">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="52537-113">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="52537-114">Esse cmdlet retorna as configurações de DTMF usadas para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="52537-114">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="52537-115">Execute o seguinte cmdlet e especifique a tecla a ser pressionada para cada opção que você deseja alterar:</span><span class="sxs-lookup"><span data-stu-id="52537-115">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="52537-116">Esse cmdlet modifica as configurações de DTMF usadas para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="52537-116">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="52537-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="52537-117">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="52537-p102">Esse exemplo troca a tecla pressionada para habilitar ou desabilitar os anúncios e a tecla pressionada para ativar ou desativar o mudo de todos os participantes. Como nenhuma Identidade é especificada, essas alterações se aplicam às configurações DTMF globais.</span><span class="sxs-lookup"><span data-stu-id="52537-p102">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="52537-120">(Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site.</span><span class="sxs-lookup"><span data-stu-id="52537-120">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="52537-121">Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="52537-121">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="52537-122">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server ou a ajuda da linha de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52537-122">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

