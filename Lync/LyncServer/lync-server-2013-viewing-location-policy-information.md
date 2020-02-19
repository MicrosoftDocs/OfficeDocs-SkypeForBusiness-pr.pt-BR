---
title: 'Lync Server 2013: exibindo informações de política de local'
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
ms.openlocfilehash: f22f5f218f3b9b97b90b26e1f74ec80cd0572e93
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="07bfb-102">Exibindo informações de política de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07bfb-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07bfb-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="07bfb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="07bfb-104">No Lync Server 2013, você pode usar a política de local para aplicar configurações relacionadas à funcionalidade avançada 9-1-1 (E9-1-1) e às configurações de local para usuários ou contatos.</span><span class="sxs-lookup"><span data-stu-id="07bfb-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="07bfb-105">A política de local determina se o usuário está habilitado para o E9-1-1 e, se estiver, qual vai ser o comportamento de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="07bfb-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="07bfb-106">Por exemplo, é possível usar a política de local para definir o número que constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança da empresa deve ser automaticamente notificada e como a chamada é roteada.</span><span class="sxs-lookup"><span data-stu-id="07bfb-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="07bfb-107">Você pode configurar políticas de local no painel de controle de **rede** do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07bfb-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="07bfb-108">No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de local.</span><span class="sxs-lookup"><span data-stu-id="07bfb-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="07bfb-109">Use o procedimento a seguir para exibir informações sobre políticas de local.</span><span class="sxs-lookup"><span data-stu-id="07bfb-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="07bfb-110">Para obter detalhes sobre como criar ou modificar políticas de local, consulte [criando ou modificando uma política de local no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="07bfb-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="07bfb-111">Para visualizar informações sobre uma política de local</span><span class="sxs-lookup"><span data-stu-id="07bfb-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="07bfb-112">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="07bfb-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07bfb-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07bfb-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="07bfb-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="07bfb-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="07bfb-115">Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de local**.</span><span class="sxs-lookup"><span data-stu-id="07bfb-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="07bfb-116">Na página **Política de local**, selecione a política de local que você quer modificar.</span><span class="sxs-lookup"><span data-stu-id="07bfb-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="07bfb-117">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="07bfb-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="07bfb-118">Você pode visulizar informações apenas de uma política de local por vez.</span><span class="sxs-lookup"><span data-stu-id="07bfb-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="07bfb-p104">Uma política única, chamada de Global, existe por padrão e não pode ser excluída ou renomeada. Porém, você pode modificar a política Global. Essa política será aplicada a todos os usuários e contatos, a não ser que você crie políticas de sites ou políticas por usuário. As políticas por usuário devem ser aplicadas a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="07bfb-p104">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07bfb-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="07bfb-123">See Also</span></span>


[<span data-ttu-id="07bfb-124">Criando ou modificando uma política de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07bfb-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="07bfb-125">Criar políticas de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07bfb-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="07bfb-126">Criar ou modificar um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07bfb-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="07bfb-127">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="07bfb-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="07bfb-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="07bfb-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="07bfb-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="07bfb-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="07bfb-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="07bfb-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

