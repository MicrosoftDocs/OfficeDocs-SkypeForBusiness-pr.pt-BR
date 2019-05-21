---
title: Atribuir políticas de conferência para suporte de usuários anônimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você controla quem pode convidar usuários anônimos Configurando uma política de conferência para dar suporte a usuários anônimos e aplicar essa política de conferência a usuários específicos.
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280282"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="49778-103">Atribuir políticas de conferência para dar suporte a usuários anônimos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="49778-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="49778-104">Por padrão, todos os usuários são impedidos de convidar usuários anônimos para participarem de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="49778-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="49778-105">Você controla quem pode convidar usuários anônimos Configurando uma política de conferência para dar suporte a usuários anônimos e aplicar essa política de conferência a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="49778-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="49778-106">Para obter detalhes sobre como configurar uma política de conferência para dar suporte a usuários anônimos, consulte [criar políticas de conferência no Skype for Business Server](../../conferencing/create-policies.md) e [gerenciar Federação e acesso externo ao Skype for Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="49778-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="49778-107">Use o procedimento desta seção para aplicar uma política de conferência que você já tenha criado a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="49778-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="49778-108">Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="49778-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="49778-109">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários públicos no Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="49778-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="49778-110">Para configurar uma política de usuário para a participação anônima em reuniões</span><span class="sxs-lookup"><span data-stu-id="49778-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="49778-111">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="49778-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49778-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49778-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="49778-113">Na barra de navegação à esquerda, clique em **conferência**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="49778-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="49778-114">Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="49778-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="49778-115">Crie um nome exclusivo no campo **nome** que indica a capa da política do usuário (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).</span><span class="sxs-lookup"><span data-stu-id="49778-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="49778-116">Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="49778-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="49778-117">Na caixa de diálogo **políticas de conferência** , marque a caixa de seleção **permitir que os participantes convidem usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="49778-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="49778-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="49778-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="49778-119">Na barra de navegação à esquerda, clique em **usuários**e procure a conta de usuário que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="49778-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="49778-120">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="49778-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="49778-121">Em **Editar o usuário do Skype for Business Server** em **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.</span><span class="sxs-lookup"><span data-stu-id="49778-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="49778-122">As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de instalação do servidor padrão e são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="49778-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="49778-123">Para permitir que os usuários convidem usuários anônimos para conferências, você também deve habilitar o suporte a usuários anônimos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="49778-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="49778-124">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários públicos no Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="49778-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

