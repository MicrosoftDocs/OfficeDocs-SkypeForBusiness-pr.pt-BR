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
ms.openlocfilehash: 3f6fb176025dd7f075429833e48b53eb1f7a5b07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="eae1a-102">Usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae1a-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae1a-103">_**Última modificação do tópico:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="eae1a-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="eae1a-104">O processo de Hospedagem de usuários em um aparelho de filial persistente ou servidor de filial persistente é semelhante ao processo de Hospedagem de usuários em um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="eae1a-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="eae1a-105">Execute o processo de aparelho de filial persistente ou servidor de filial persistente no site central.</span><span class="sxs-lookup"><span data-stu-id="eae1a-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="eae1a-106">Para usuários domésticos no Servidor ou Aplicativo de Filial Persistente ou Servidor de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="eae1a-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="eae1a-107">Antes de mover os usuários para o servidor de filial persistente ou servidor de filial persistente, abra o Shell de gerenciamento do Lync Server e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eae1a-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="eae1a-108">Execute o cmdlet **Test-CsPstnOutboundCall** para verificar se o servidor de filial persistente está em execução e se a conectividade PSTN (rede telefônica pública comutada) está configurada.</span><span class="sxs-lookup"><span data-stu-id="eae1a-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="eae1a-109">Se você precisar modificar as propriedades do gateway PSTN, use o cmdlet **Set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="eae1a-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="eae1a-110">Execute o cmdlet **Get-CsVoicePolicy** para verificar se os usuários que serão hospedados no servidor de filial persistente têm a política de roteamento VoIP apropriada.</span><span class="sxs-lookup"><span data-stu-id="eae1a-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="eae1a-111">Se você precisar modificar a política VoIP, use o cmdlet **Set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="eae1a-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="eae1a-112">Execute o cmdlet **Get-CsVoicemailReroutingConfiguration** para verificar se as configurações de redirecionamento de caixa postal estão configuradas.</span><span class="sxs-lookup"><span data-stu-id="eae1a-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="eae1a-113">Se você precisar modificar o configurações de redirecionamento de caixa postal, use o cmdlet **Set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="eae1a-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="eae1a-114">No Shell de gerenciamento do Lync Server, execute o cmdlet **move-CsUser** para mover usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="eae1a-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eae1a-115">Você também pode usar o painel de controle do Lync Server para verificar os pré-requisitos e usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="eae1a-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="eae1a-116">Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="eae1a-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eae1a-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="eae1a-117">See Also</span></span>


[<span data-ttu-id="eae1a-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="eae1a-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="eae1a-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="eae1a-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="eae1a-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eae1a-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="eae1a-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="eae1a-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

