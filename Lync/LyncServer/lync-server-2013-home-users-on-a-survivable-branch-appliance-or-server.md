---
title: 'Lync Server 2013: Usuários domésticos em um Home users on a Aparelho de Filial Persistente ou Servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="5eba6-102">Usuários domésticos em um Home users on a Aparelho de Filial Persistente ou Servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5eba6-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eba6-103">_**Tópico da última modificação:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="5eba6-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="5eba6-104">O processo de Hospedagem de usuários em um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes é semelhante ao processo de Hospedagem de usuários em um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="5eba6-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="5eba6-105">Realize o aplicativo de ramificação sobreviventes ou o procedimento do servidor de ramificação sobreviventes no site central.</span><span class="sxs-lookup"><span data-stu-id="5eba6-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="5eba6-106">Para usuários domésticos em um aparelho de ramificação sobreviventes ou em um servidor de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="5eba6-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="5eba6-107">Antes de mover os usuários para o servidor de ramificação sobreviventes ou o servidor de ramificação sobreviventes, abra o Shell de gerenciamento do Lync Server e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5eba6-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="5eba6-108">Execute o cmdlet **Test-CsPstnOutboundCall** para verificar se o servidor de ramificação sobreviventes está em execução e se a conectividade PSTN (rede telefônica pública comutada) está configurada.</span><span class="sxs-lookup"><span data-stu-id="5eba6-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="5eba6-109">Se você precisar modificar as propriedades do gateway PSTN, use o cmdlet **set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="5eba6-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="5eba6-110">Execute o cmdlet **Get-CsVoicePolicy** para verificar se os usuários que serão hospedados no servidor de ramificação sobreviventes têm a política de roteamento de VoIP apropriada.</span><span class="sxs-lookup"><span data-stu-id="5eba6-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="5eba6-111">Se você precisar modificar a política de VoIP, use o cmdlet **set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="5eba6-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="5eba6-112">Execute o cmdlet **Get-CsVoicemailReroutingConfiguration** para verificar se as configurações de redirecionamento da caixa postal estão definidas.</span><span class="sxs-lookup"><span data-stu-id="5eba6-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="5eba6-113">Se precisar modificar as configurações de redirecionamento da caixa postal, use o cmdlet **set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="5eba6-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="5eba6-114">No Shell de gerenciamento do Lync Server, execute o cmdlet **move-CsUser** para mover os usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="5eba6-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5eba6-115">Você também pode usar o painel de controle do Lync Server para verificar pré-requisitos e usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="5eba6-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5eba6-116">Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="5eba6-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5eba6-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="5eba6-117">See Also</span></span>


[<span data-ttu-id="5eba6-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="5eba6-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="5eba6-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="5eba6-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="5eba6-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5eba6-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="5eba6-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="5eba6-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

