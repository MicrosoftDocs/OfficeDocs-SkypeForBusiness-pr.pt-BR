---
title: 'Lync Server 2013: atribuir políticas de conferência para dar suporte a usuários anônimos'
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
ms.openlocfilehash: de154fca02470003fdedd0ff29cc8c879d1865aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523188"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="02a53-102">Atribuir políticas de conferência para dar suporte a usuários anônimos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a53-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02a53-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="02a53-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="02a53-104">Por padrão, todos os usuários são impedidos de convidar usuários anônimos a participar de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="02a53-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="02a53-105">Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="02a53-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="02a53-106">Para obter detalhes sobre como configurar as políticas de conferência para dar suporte a usuários anônimos, consulte [create or Modify a Conferencing Policy in Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="02a53-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="02a53-107">Use o procedimento nesta seção para aplicar uma política de conferência que você já criou a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="02a53-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02a53-108">Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="02a53-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="02a53-109">Para obter detalhes, consulte <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure Policies to Control Public User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02a53-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="02a53-110">Para configurar uma política de usuário para participação anônima em reuniões</span><span class="sxs-lookup"><span data-stu-id="02a53-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="02a53-111">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="02a53-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02a53-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02a53-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02a53-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="02a53-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02a53-114">Na barra de navegação esquerda, clique em \*\*Conferência \*\* e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="02a53-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="02a53-115">Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="02a53-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="02a53-116">Crie um nome exclusivo no campo **nome** que indique o que a política de usuário abrange (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).</span><span class="sxs-lookup"><span data-stu-id="02a53-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="02a53-117">Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="02a53-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="02a53-118">Na caixa de diálogo **políticas de conferência** , marque a caixa de seleção **permitir que os participantes convidem usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="02a53-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="02a53-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="02a53-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="02a53-120">Na barra de navegação esquerda, clique em **usuários**, procure a conta de usuário que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="02a53-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="02a53-121">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="02a53-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="02a53-122">Em **Editar usuário do Lync Server** na **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.</span><span class="sxs-lookup"><span data-stu-id="02a53-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02a53-123">As configurações <STRONG> &lt; automáticas &gt; </STRONG> aplicam as configurações de instalação padrão do servidor e são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="02a53-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="02a53-124">Para habilitar usuários para convidar usuários anônimos para conferências, você também deve habilitar o suporte para usuários anônimos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="02a53-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="02a53-125">Para obter detalhes, consulte [Configure Policies to Control Public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="02a53-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

