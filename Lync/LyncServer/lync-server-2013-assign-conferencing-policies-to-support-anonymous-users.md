---
title: 'Lync Server 2013: Atribuir políticas de conferência para suporte de usuários anônimos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="e8dfb-102">Atribuir políticas de conferência para suporte de usuários anônimos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8dfb-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8dfb-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e8dfb-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e8dfb-104">Por padrão, todos os usuários são impedidos de convidar usuários anônimos para participarem de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="e8dfb-105">Você controla quem pode convidar usuários anônimos Configurando uma política de conferência para dar suporte a usuários anônimos e aplicar essa política de conferência a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="e8dfb-106">Para obter detalhes sobre como configurar as políticas de conferência para dar suporte a usuários anônimos, consulte [criar ou modificar uma política de conferência no Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [gerenciar Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e8dfb-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="e8dfb-107">Use o procedimento desta seção para aplicar uma política de conferência que você já tenha criado a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8dfb-108">Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="e8dfb-109">Para obter detalhes, consulte <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="e8dfb-110">Para configurar uma política de usuário para a participação anônima em reuniões</span><span class="sxs-lookup"><span data-stu-id="e8dfb-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="e8dfb-111">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8dfb-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8dfb-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e8dfb-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e8dfb-114">Na barra de navegação à esquerda, clique em **conferência**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e8dfb-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="e8dfb-115">Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="e8dfb-116">Crie um nome exclusivo no campo **nome** que indica a capa da política do usuário (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).</span><span class="sxs-lookup"><span data-stu-id="e8dfb-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="e8dfb-117">Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="e8dfb-118">Na caixa de diálogo **políticas de conferência** , marque a caixa de seleção **permitir que os participantes convidem usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="e8dfb-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="e8dfb-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="e8dfb-120">Na barra de navegação à esquerda, clique em **usuários**e procure a conta de usuário que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="e8dfb-121">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="e8dfb-122">Em **Editar o usuário do Lync Server** na **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8dfb-123">As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de instalação do servidor padrão e são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="e8dfb-124">Para permitir que os usuários convidem usuários anônimos para conferências, você também deve habilitar o suporte a usuários anônimos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="e8dfb-125">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="e8dfb-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

