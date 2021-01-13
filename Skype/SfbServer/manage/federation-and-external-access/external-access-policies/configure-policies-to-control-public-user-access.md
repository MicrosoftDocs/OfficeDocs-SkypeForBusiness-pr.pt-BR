---
title: Configurar políticas para controlar o acesso de usuário público
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: A conectividade ublic de mensagens instantâneas (IM) permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores de serviços públicos de mensagens instantâneas.
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823582"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a><span data-ttu-id="e8df3-103">Configurar políticas para controlar o acesso de usuário público no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8df3-103">Configure policies to control public user access in Skype for Business Server</span></span>

<span data-ttu-id="e8df3-104">A conectividade pública de mensagens instantâneas (IM) permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores de serviços públicos de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="e8df3-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers.</span></span> <span data-ttu-id="e8df3-105">Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários públicos podem colaborar com usuários internos do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8df3-105">You configure one or more external user access policies to control whether public users can collaborate with internal Skype for Business Server users.</span></span> <span data-ttu-id="e8df3-106">A conectividade de mensagens instantâneas públicas é um recurso adicionado que depende da configuração de sua implantação e dos usuários.</span><span class="sxs-lookup"><span data-stu-id="e8df3-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="e8df3-107">Também depende do provisionamento do serviço no provedor de IM público.</span><span class="sxs-lookup"><span data-stu-id="e8df3-107">It also depends on the provisioning of the service at the public IM provider.</span></span> 

<span data-ttu-id="e8df3-108">Para controlar o acesso do usuário público, é possível configurar políticas no nível global, site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="e8df3-108">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="e8df3-109">As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="e8df3-109">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="e8df3-110">A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência).</span><span class="sxs-lookup"><span data-stu-id="e8df3-110">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="e8df3-111">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="e8df3-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="e8df3-p103">No caso de convites de IM, a resposta depende do software cliente. A solicitação é aceita a menos que remetentes externos sejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações nas listas de cliente **Permitir** e **Bloquear** do usuário). Além disso, os convites de IM podem ser bloqueados se um usuário optar por bloquear toda IM de usuários que não estão na lista **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-p103">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>



> [!NOTE]  
> <span data-ttu-id="e8df3-115">É possível configurar políticas para controlar o acesso ao usuário público, mesmo se você não tiver habilitado a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8df3-115">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="e8df3-116">No entanto, as políticas configuradas entram em vigor somente quando a federação está habilitada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8df3-116">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="e8df3-117">Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="e8df3-117">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="e8df3-118">Além disso, se você especificar uma política de usuário para controlar o acesso de usuário público, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política.</span><span class="sxs-lookup"><span data-stu-id="e8df3-118">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span> <span data-ttu-id="e8df3-119">Para obter detalhes sobre como especificar usuários públicos que podem entrar no Skype for Business Server, consulte Atribuir uma política de acesso de [usuário externo.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="e8df3-119">For details about specifying public users that can sign in to Skype for Business Server, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>


<span data-ttu-id="e8df3-120">Use o procedimento a seguir para configurar uma política para suportar o acesso de usuários de um ou mais provedores de IM público.</span><span class="sxs-lookup"><span data-stu-id="e8df3-120">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="e8df3-121">Para configurar uma política de acesso externo para suportar o acesso de usuário público</span><span class="sxs-lookup"><span data-stu-id="e8df3-121">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="e8df3-122">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e8df3-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8df3-123">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8df3-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e8df3-124">Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e8df3-125">Na página **Política de Acesso Externo**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e8df3-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e8df3-126">Para configurar a política global a fim de suportar o acesso de usuário público, clique na política global, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-126">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="e8df3-p105">Para criar uma nova política de site, clique em **Novo** e clique em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="e8df3-p106">Para criar uma nova política de usuário, clique em **Novo** e clique em **Política de Usuário**. Em **Nova Política de Acesso Externo**, crie um nome exclusivo no campo **Nome** que indica o que a política de usuário cobre (por exemplo, **EnablePublicUsers** para uma política de usuário que permite comunicações para usuários públicos).</span><span class="sxs-lookup"><span data-stu-id="e8df3-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="e8df3-131">Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e8df3-132">(Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="e8df3-133">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e8df3-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="e8df3-134">Para habilitar o acesso de usuários públicos à política, marque a caixa de seleção **Habilitar comunicações com usuários públicos**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-134">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="e8df3-135">Para desabilitar o acesso de usuários públicos à política, desmarque a caixa de seleção **Habilitar comunicações com usuários públicos**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-135">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="e8df3-136">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e8df3-136">Click **Commit**.</span></span>

<span data-ttu-id="e8df3-137">Para habilitar o acesso do usuário público, você também deve habilitar o suporte para federação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8df3-137">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="e8df3-138">Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário federado no Skype for Business Server.](configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="e8df3-138">For details, see [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="e8df3-139">Se for uma política de usuário, também será necessário aplicar a política aos usuários públicos para os quais você deseja permitir a colaboração com usuários públicos.</span><span class="sxs-lookup"><span data-stu-id="e8df3-139">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e8df3-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="e8df3-140">See Also</span></span>

[<span data-ttu-id="e8df3-141">Gerenciar fornecedores SIP federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="e8df3-141">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
