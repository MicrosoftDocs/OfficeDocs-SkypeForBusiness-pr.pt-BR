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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para oferecer suporte a usuários anônimos e aplicar essa política de conferência para usuários específicos.
ms.openlocfilehash: afb107f7f3d91d634e5adaef4b9d0a2fbc1ee298
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919532"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="eaa35-103">Atribuir políticas de conferência para oferecer suporte aos usuários anônimos Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="eaa35-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="eaa35-104">Por padrão, todos os usuários são impedidos de convidem usuários anônimos para participar de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="eaa35-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="eaa35-105">Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para oferecer suporte a usuários anônimos e aplicar essa política de conferência para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="eaa35-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="eaa35-106">Para obter detalhes sobre como configurar um políticas de conferência para oferecer suporte a usuários anônimos, consulte [criar políticas de conferência no Skype para Business Server](../../conferencing/create-policies.md) e [Managing federação e acesso externo à Skype para Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="eaa35-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="eaa35-107">Use o procedimento desta seção para aplicar uma política de conferência que você criou a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="eaa35-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="eaa35-108">Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="eaa35-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="eaa35-109">Para obter detalhes, consulte [Configure políticas para controlar o acesso de usuário público na Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="eaa35-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="eaa35-110">Para configurar uma política de usuário para participação anônima em reuniões</span><span class="sxs-lookup"><span data-stu-id="eaa35-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="eaa35-111">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="eaa35-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eaa35-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="eaa35-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="eaa35-113">Na barra de navegação à esquerda, clique em **conferência**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="eaa35-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="eaa35-114">Para criar uma nova política de usuário, clique em **novo**e clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="eaa35-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="eaa35-115">Crie um nome exclusivo no campo **nome** que indica o que aborda a política de usuário (por exemplo, **EnableAnonymous** para uma política de usuário que permite a comunicação com usuários anônimos).</span><span class="sxs-lookup"><span data-stu-id="eaa35-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="eaa35-116">Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="eaa35-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="eaa35-117">Na caixa de diálogo **Diretivas de conferência** , marque a caixa de seleção **Permitir que os participantes convidem usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="eaa35-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="eaa35-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eaa35-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="eaa35-119">Na barra de navegação à esquerda, clique em **usuários**e pesquise a conta de usuário que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="eaa35-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="eaa35-120">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="eaa35-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="eaa35-121">Em **Editar Skype para usuário de servidor de negócios** em **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.</span><span class="sxs-lookup"><span data-stu-id="eaa35-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="eaa35-122">O <STRONG> &lt;automática&gt; </STRONG> configurações se aplicam as configurações de instalação de servidor padrão e são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="eaa35-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="eaa35-123">Para permitir que os usuários convidem usuários anônimos para conferências, você também deve habilitar o suporte a usuários anônimos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="eaa35-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="eaa35-124">Para obter detalhes, consulte [Configure políticas para controlar o acesso de usuário público na Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="eaa35-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

