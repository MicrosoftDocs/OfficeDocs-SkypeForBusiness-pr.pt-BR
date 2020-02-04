---
title: 'Lync Server 2013: exibindo informações de política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f68ad38ffbc8bb1b4abdfbf8119add7d9f965e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="e4204-102">Exibindo informações de política de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4204-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4204-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e4204-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e4204-104">No Lync Server 2013, você pode usar a política de localização para aplicar configurações relacionadas à funcionalidade Enhanced 9-1-1 (E9-1-1) e às configurações de localização para usuários ou contatos.</span><span class="sxs-lookup"><span data-stu-id="e4204-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="e4204-105">A política de localização determina se um usuário está habilitado para E9-1-1 e, em caso afirmativo, qual é o comportamento de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="e4204-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="e4204-106">Por exemplo, você pode usar a política de localização para definir qual número constitui uma chamada de emergência (por exemplo, 911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.</span><span class="sxs-lookup"><span data-stu-id="e4204-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="e4204-107">Você pode configurar as políticas de localização do grupo de **configuração de rede** no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4204-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="e4204-108">No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de localização.</span><span class="sxs-lookup"><span data-stu-id="e4204-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="e4204-109">Use o procedimento a seguir para exibir informações sobre as políticas de localização.</span><span class="sxs-lookup"><span data-stu-id="e4204-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="e4204-110">Para obter detalhes sobre como criar ou modificar as políticas de localização, consulte [criando ou modificando uma política de localização no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e4204-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="e4204-111">Para exibir informações sobre uma política de localização</span><span class="sxs-lookup"><span data-stu-id="e4204-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="e4204-112">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e4204-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e4204-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4204-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4204-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e4204-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4204-115">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **política de localização**.</span><span class="sxs-lookup"><span data-stu-id="e4204-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="e4204-116">Na página **política de localização** , selecione a política de localização que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="e4204-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="e4204-117">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e4204-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4204-118">Você só pode exibir informações sobre uma política de localização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="e4204-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="e4204-119">Uma única política, chamada global, existe por padrão e não pode ser excluída ou renomeada.</span><span class="sxs-lookup"><span data-stu-id="e4204-119">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="e4204-120">No entanto, você pode modificar a política global.</span><span class="sxs-lookup"><span data-stu-id="e4204-120">However, you can modify the Global policy.</span></span> <span data-ttu-id="e4204-121">Esta política será aplicada a todos os usuários e contatos, a menos que você crie políticas de site ou políticas por usuário.</span><span class="sxs-lookup"><span data-stu-id="e4204-121">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="e4204-122">Políticas por usuário devem ser aplicadas a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="e4204-122">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4204-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="e4204-123">See Also</span></span>


[<span data-ttu-id="e4204-124">Criando ou modificando uma política de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4204-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="e4204-125">Criar políticas de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4204-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="e4204-126">Criar ou modificar um site da rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4204-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="e4204-127">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="e4204-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="e4204-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="e4204-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="e4204-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="e4204-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="e4204-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="e4204-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

