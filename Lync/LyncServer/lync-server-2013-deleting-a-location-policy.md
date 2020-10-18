---
title: 'Lync Server 2013: excluindo uma política de local'
description: 'Lync Server 2013: excluindo uma política de local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88935c00a60de377c9812a4d119708fd610338ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575837"
---
# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="c645f-103">Excluindo uma política de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c645f-103">Deleting a location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c645f-104">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="c645f-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="c645f-105">No Lync Server 2013, você pode usar a política de local para aplicar configurações relacionadas à funcionalidade avançada 9-1-1 (E9-1-1) e às configurações de local para usuários ou contatos.</span><span class="sxs-lookup"><span data-stu-id="c645f-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="c645f-106">A política de local determina se o usuário está habilitado para o E9-1-1 e, se estiver, qual vai ser o comportamento de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="c645f-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="c645f-107">Por exemplo, é possível usar a política de local para definir o número que constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança da empresa deve ser automaticamente notificada e como a chamada é roteada.</span><span class="sxs-lookup"><span data-stu-id="c645f-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="c645f-108">Você pode configurar políticas de local no painel de controle de **rede** do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c645f-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c645f-109">No painel de controle do Lync Server, você pode exibir, criar, modificar ou excluir políticas de local.</span><span class="sxs-lookup"><span data-stu-id="c645f-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="c645f-110">Usar os procedimentos a seguir excluirá uma política de local.</span><span class="sxs-lookup"><span data-stu-id="c645f-110">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="c645f-111">Para obter detalhes sobre como criar ou modificar políticas de local, consulte [criando ou modificando uma política de local no Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c645f-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="c645f-112">Para excluir uma política de local</span><span class="sxs-lookup"><span data-stu-id="c645f-112">To delete a location policy</span></span>

1.  <span data-ttu-id="c645f-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c645f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c645f-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c645f-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c645f-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c645f-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c645f-116">Na barra de navegação, clique em **Configuração de rede** e clique em **Política de local**.</span><span class="sxs-lookup"><span data-stu-id="c645f-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="c645f-117">Na página **Política de local**, selecione a política de local que você quer excluir.</span><span class="sxs-lookup"><span data-stu-id="c645f-117">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c645f-p104">Você pode excluir mais que uma política de local ao mesmo tempo. Para isso, mantenha a tecla CTRL e selecione várias políticas. Ou, para selecionar todas as políticas, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c645f-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="c645f-121">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c645f-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c645f-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c645f-122">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c645f-p105">Você não pode excluir uma política de local Global. Se você tentar excluir a política Global, você receberá uma mensagem de aviso, e essa política será redefinida aos seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="c645f-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c645f-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="c645f-125">See Also</span></span>


[<span data-ttu-id="c645f-126">Criando ou modificando uma política de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c645f-126">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="c645f-127">Exibindo informações de política de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c645f-127">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

