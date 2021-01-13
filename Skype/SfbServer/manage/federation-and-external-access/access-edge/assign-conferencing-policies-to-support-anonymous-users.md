---
title: Atribuir políticas de conferência para dar suporte a usuários anônimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817451"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="1ede1-103">Atribuir políticas de conferência para dar suporte a usuários anônimos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1ede1-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="1ede1-104">Por padrão, todos os usuários são impedidos de convidar usuários anônimos a participar de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="1ede1-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="1ede1-105">Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="1ede1-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="1ede1-106">Para obter detalhes sobre como configurar uma política de conferência para suportar usuários anônimos, consulte Criar políticas de conferência no [Skype for Business Server](../../conferencing/create-policies.md) e gerenciar federação e acesso externo ao Skype for Business [Server.](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="1ede1-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="1ede1-107">Use o procedimento nesta seção para aplicar uma política de conferência que você já tenha criado para um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="1ede1-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="1ede1-108">Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte para usuários anônimos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ede1-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="1ede1-109">Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário público no Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="1ede1-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="1ede1-110">Para configurar uma política de usuário para participação anônima em reuniões</span><span class="sxs-lookup"><span data-stu-id="1ede1-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="1ede1-111">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1ede1-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1ede1-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1ede1-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1ede1-113">Na barra de navegação esquerda, clique em **Conferência** e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="1ede1-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="1ede1-114">Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="1ede1-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="1ede1-115">Crie um nome  exclusivo no campo Nome que indique o que a política de usuário cobre (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).</span><span class="sxs-lookup"><span data-stu-id="1ede1-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="1ede1-116">Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar** e em **Mostrar detalhes.**</span><span class="sxs-lookup"><span data-stu-id="1ede1-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="1ede1-117">Na caixa **de diálogo Políticas** de Conferência, marque a caixa de seleção Permitir que os participantes **convidem usuários anônimos.**</span><span class="sxs-lookup"><span data-stu-id="1ede1-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="1ede1-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1ede1-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="1ede1-119">Na barra de navegação esquerda, clique **em Usuários,** pesquise a conta de usuário que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="1ede1-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="1ede1-120">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="1ede1-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="1ede1-121">Em **Editar Usuário do Skype for Business Server** em **Política** de Conferência, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="1ede1-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="1ede1-122">As <STRONG> &lt; configurações &gt; </STRONG> automáticas aplicam as configurações de instalação padrão do servidor e são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="1ede1-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="1ede1-123">Para habilitar usuários para convidar usuários anônimos para conferências, você também deve habilitar o suporte para usuários anônimos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ede1-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="1ede1-124">Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário público no Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="1ede1-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

