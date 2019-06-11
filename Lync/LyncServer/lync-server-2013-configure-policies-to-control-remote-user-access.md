---
title: 'Lync Server 2013: Configurar políticas para controle de acesso de usuário remoto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="96e39-102">Configurar políticas para controle de acesso de usuário remoto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e39-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96e39-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="96e39-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="96e39-104">Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários remotos podem colaborar com usuários internos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96e39-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="96e39-105">Para controlar o acesso do usuário remoto, você pode configurar políticas nos níveis global, de site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="96e39-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="96e39-106">Políticas de site substituem a política global e as políticas de usuário substituem políticas globais e do site.</span><span class="sxs-lookup"><span data-stu-id="96e39-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="96e39-107">Para obter detalhes sobre os tipos de diretivas que você pode configurar, consulte [Gerenciamento de Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="96e39-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="96e39-108">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="96e39-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="96e39-109">A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="96e39-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="96e39-110">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="96e39-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96e39-111">Você pode configurar políticas para controlar o acesso do usuário remoto, mesmo se você não tiver habilitado o acesso de usuário remoto para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="96e39-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="96e39-112">No entanto, as políticas que você configura são efetivadas apenas quando você tem acesso de usuário remoto habilitado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="96e39-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="96e39-113">Para obter detalhes sobre como habilitar o acesso do usuário remoto, consulte <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">habilitar ou desabilitar a conectividade de mensagens de chat pública e de Federação no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96e39-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="96e39-114">Além disso, se você especificar uma política de usuário para controlar o acesso do usuário remoto, a política se aplicará somente aos usuários habilitados para o Lync Server e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="96e39-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="96e39-115">Para obter detalhes sobre como especificar os usuários que podem entrar no Lync Server de locais remotos, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96e39-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="96e39-116">Use o procedimento a seguir para configurar cada política de acesso externo que você deseja usar para controlar o acesso do usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="96e39-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96e39-117">Este procedimento descreve como configurar uma política somente para permitir comunicações com usuários remotos, mas cada política que você configura para dar suporte ao acesso de usuário remoto também pode configurar o acesso de usuário federado e acesso de usuário público.</span><span class="sxs-lookup"><span data-stu-id="96e39-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="96e39-118">Para obter detalhes sobre como configurar políticas para dar suporte a usuários federados, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96e39-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="96e39-119">Para obter detalhes sobre como configurar políticas para dar suporte a usuários públicos, consulte <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">criar ou editar provedores federados SIP públicos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96e39-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="96e39-120">Para configurar uma política de acesso externo para dar suporte ao acesso de usuários remotos</span><span class="sxs-lookup"><span data-stu-id="96e39-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="96e39-121">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="96e39-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96e39-122">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96e39-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96e39-123">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="96e39-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96e39-124">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="96e39-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="96e39-125">Na página **política de acesso externo** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="96e39-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="96e39-126">Para configurar a política global para dar suporte ao acesso de usuário remoto, clique na política global, clique em **Editar**e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="96e39-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="96e39-127">Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**.</span><span class="sxs-lookup"><span data-stu-id="96e39-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="96e39-128">Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="96e39-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="96e39-129">Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="96e39-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="96e39-130">Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indique a capa da política do usuário (por exemplo, **EnableRemoteUsers** para uma política de usuário que permita comunicações para usuários remotos).</span><span class="sxs-lookup"><span data-stu-id="96e39-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="96e39-131">Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="96e39-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="96e39-132">Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="96e39-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="96e39-133">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="96e39-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="96e39-134">Para habilitar o acesso de usuário remoto para a política, marque a caixa de seleção **habilitar comunicações com usuários remotos** .</span><span class="sxs-lookup"><span data-stu-id="96e39-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="96e39-135">Para desabilitar o acesso de usuário remoto para a política, desmarque a caixa de seleção **habilitar comunicações com usuários remotos** .</span><span class="sxs-lookup"><span data-stu-id="96e39-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="96e39-136">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="96e39-136">Click **Commit**.</span></span>

<span data-ttu-id="96e39-137">Para habilitar o acesso de usuário remoto, você também deve habilitar o suporte ao acesso de usuários remotos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="96e39-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="96e39-138">Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) na documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="96e39-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="96e39-139">Se esta for uma política de usuário, você também deverá aplicar a política aos usuários para os quais você deseja poder se conectar remotamente.</span><span class="sxs-lookup"><span data-stu-id="96e39-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="96e39-140">Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) na documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="96e39-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

