---
title: 'Lync Server 2013: (Opcional) Modificar mapeamento principal de comandos DTMF'
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
ms.openlocfilehash: 036092f1199ad0e361f8509b36930410685ece21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="ed7ec-102">(Opcional) Modificar mapeamento principal de comandos DTMF no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed7ec-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed7ec-103">_**Tópico da última modificação:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="ed7ec-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="ed7ec-104">Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual).</span><span class="sxs-lookup"><span data-stu-id="ed7ec-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="ed7ec-105">Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="ed7ec-106">Você pode usar cmdlets para modificar as chaves usadas para os comandos DTMF.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="ed7ec-107">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed7ec-108">Para obter detalhes sobre esses cmdlets e as possíveis opções de DTMF, consulte documentação do Shell de gerenciamento do Lync Server ou ajuda da linha de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="ed7ec-109">Para modificar o mapeamento de teclas dos comandos DTMF</span><span class="sxs-lookup"><span data-stu-id="ed7ec-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="ed7ec-110">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função **cs-ServerAdministrator** ou **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="ed7ec-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="ed7ec-111">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ed7ec-112">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ed7ec-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="ed7ec-113">Este cmdlet retorna as configurações de DTMF usadas para a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="ed7ec-114">Execute o cmdlet a seguir e especifique a tecla a ser pressionada para cada opção que você deseja alterar:</span><span class="sxs-lookup"><span data-stu-id="ed7ec-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="ed7ec-115">Esse cmdlet modifica as configurações de DTMF usadas para a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="ed7ec-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ed7ec-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="ed7ec-117">Este exemplo troca a tecla pressionada para habilitar ou desabilitar anúncios e a tecla que é pressionada para ativar e desativar o mudo para todos os participantes.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="ed7ec-118">Como nenhuma identidade é especificada, essas alterações se aplicam às configurações de DTMF globais.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="ed7ec-119">(Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="ed7ec-120">Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="ed7ec-121">Para obter detalhes, consulte documentação do Shell de gerenciamento do Lync Server ou ajuda da linha de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed7ec-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

