---
title: 'Lync Server 2013: usuários domésticos em um servidor ou aparelho de filial persistente'
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
ms.openlocfilehash: c6efd5991260ffeec3c6279857625eadfe34eca4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="c2788-102">Usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2788-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2788-103">_**Última modificação do tópico:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="c2788-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="c2788-104">O processo de Hospedagem de usuários em um aparelho de filial persistente ou servidor de filial persistente é semelhante ao processo de Hospedagem de usuários em um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c2788-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="c2788-105">Execute o processo de aparelho de filial persistente ou servidor de filial persistente no site central.</span><span class="sxs-lookup"><span data-stu-id="c2788-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="c2788-106">Para usuários domésticos no Servidor ou Aplicativo de Filial Persistente ou Servidor de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="c2788-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="c2788-107">Antes de mover os usuários para o servidor de filial persistente ou servidor de filial persistente, abra o Shell de gerenciamento do Lync Server e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2788-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="c2788-108">Execute o cmdlet **Test-CsPstnOutboundCall** para verificar se o servidor de filial persistente está em execução e se a conectividade PSTN (rede telefônica pública comutada) está configurada.</span><span class="sxs-lookup"><span data-stu-id="c2788-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="c2788-109">Se você precisar modificar as propriedades do gateway PSTN, use o cmdlet **Set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="c2788-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="c2788-110">Execute o cmdlet **Get-CsVoicePolicy** para verificar se os usuários que serão hospedados no servidor de filial persistente têm a política de roteamento VoIP apropriada.</span><span class="sxs-lookup"><span data-stu-id="c2788-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="c2788-111">Se você precisar modificar a política VoIP, use o cmdlet **Set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="c2788-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="c2788-112">Execute o cmdlet **Get-CsVoicemailReroutingConfiguration** para verificar se as configurações de redirecionamento de caixa postal estão configuradas.</span><span class="sxs-lookup"><span data-stu-id="c2788-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="c2788-113">Se você precisar modificar o configurações de redirecionamento de caixa postal, use o cmdlet **Set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c2788-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="c2788-114">No Shell de gerenciamento do Lync Server, execute o cmdlet **move-CsUser** para mover usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="c2788-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2788-115">Você também pode usar o painel de controle do Lync Server para verificar os pré-requisitos e usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="c2788-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c2788-116">Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="c2788-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2788-117">Confira Também</span><span class="sxs-lookup"><span data-stu-id="c2788-117">See Also</span></span>


[<span data-ttu-id="c2788-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="c2788-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="c2788-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="c2788-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="c2788-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c2788-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="c2788-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="c2788-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

