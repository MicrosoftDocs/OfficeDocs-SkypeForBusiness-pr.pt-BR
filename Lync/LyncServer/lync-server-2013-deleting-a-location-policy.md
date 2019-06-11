---
title: 'Lync Server 2013: excluindo uma política de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="1f72b-102">Excluindo uma política de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f72b-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f72b-103">_**Tópico da última modificação:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="1f72b-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="1f72b-104">No Lync Server 2013, você pode usar a política de localização para aplicar configurações relacionadas à funcionalidade Enhanced 9-1-1 (E9-1-1) e às configurações de localização para usuários ou contatos.</span><span class="sxs-lookup"><span data-stu-id="1f72b-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="1f72b-105">A política de localização determina se um usuário está habilitado para E9-1-1 e, em caso afirmativo, qual é o comportamento de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="1f72b-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="1f72b-106">Por exemplo, você pode usar a política de localização para definir qual número constitui uma chamada de emergência (por exemplo, 911 nos Estados Unidos), se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.</span><span class="sxs-lookup"><span data-stu-id="1f72b-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="1f72b-107">Você pode configurar as políticas de localização do grupo de **configuração de rede** no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f72b-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="1f72b-108">No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de localização.</span><span class="sxs-lookup"><span data-stu-id="1f72b-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="1f72b-109">Use os procedimentos a seguir para excluir uma política de localização.</span><span class="sxs-lookup"><span data-stu-id="1f72b-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="1f72b-110">Para obter detalhes sobre como criar ou modificar as políticas de localização, consulte [criando ou modificando uma política de localização no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="1f72b-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="1f72b-111">Para excluir uma política de localização</span><span class="sxs-lookup"><span data-stu-id="1f72b-111">To delete a location policy</span></span>

1.  <span data-ttu-id="1f72b-112">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1f72b-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1f72b-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f72b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1f72b-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1f72b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1f72b-115">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **política de localização**.</span><span class="sxs-lookup"><span data-stu-id="1f72b-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="1f72b-116">Na página **política de localização** , selecione a política de localização que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="1f72b-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f72b-117">Você pode excluir mais de uma política de localização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="1f72b-117">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="1f72b-118">Para fazer isso, pressione CTRL e selecione várias políticas enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="1f72b-118">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="1f72b-119">Ou, para selecionar todas as políticas, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1f72b-119">Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="1f72b-120">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="1f72b-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="1f72b-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f72b-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f72b-122">Não é possível excluir a política de localização global.</span><span class="sxs-lookup"><span data-stu-id="1f72b-122">You cannot delete the Global location policy.</span></span> <span data-ttu-id="1f72b-123">Se você tentar excluir a política global, receberá uma mensagem de aviso e essa política será redefinida para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="1f72b-123">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f72b-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="1f72b-124">See Also</span></span>


[<span data-ttu-id="1f72b-125">Criando ou modificando uma política de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f72b-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="1f72b-126">Exibindo informações de política de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f72b-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

