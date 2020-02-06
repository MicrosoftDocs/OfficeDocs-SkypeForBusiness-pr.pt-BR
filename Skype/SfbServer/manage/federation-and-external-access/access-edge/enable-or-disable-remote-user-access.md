---
title: Habilitar ou desabilitar acesso de usuário remoto
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se você habilitar o acesso de usuários remotos para usuários remotos, os usuários remotos compatíveis se conectarem pela Internet e não precisarão se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.
ms.openlocfilehash: b562dbe7a849ca4266a45303008ff9081903658d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818372"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="e2bd5-103">Habilitar ou desabilitar o acesso de usuários remotos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2bd5-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="e2bd5-104">Usuários remotos são usuários de sua organização que têm uma identidade persistente do Active Directory dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="e2bd5-105">Usuários remotos geralmente se conectam ao Skype for Business Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="e2bd5-106">Os usuários remotos incluem funcionários que trabalham em casa ou em trânsito e outros trabalhadores remotos, como fornecedores confiáveis, que receberam credenciais da empresa.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="e2bd5-107">Se você habilitar o acesso de usuários remotos para usuários remotos, os usuários remotos compatíveis se conectarem pela Internet e não precisarão se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="e2bd5-108">Para dar suporte ao acesso de usuário remoto, você deve habilitar o acesso de usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="e2bd5-109">Ao habilitar o acesso de usuário remoto, habilite-o para toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="e2bd5-110">Se, mais tarde, você quiser impedir temporariamente ou permanentemente o acesso do usuário remoto, você pode desabilitá-lo para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="e2bd5-111">Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários remotos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="e2bd5-112">Habilitar o acesso de usuários remotos especifica que os servidores que executam o serviço de borda de acesso dão suporte a comunicações com usuários remotos, mas os usuários remotos não podem participar de mensagens instantâneas (IM) nem conferências em sua organização até você também configurar ao mesmo tempo. menos uma política para gerenciar o uso de acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="e2bd5-113">As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="e2bd5-114">A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="e2bd5-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="e2bd5-115">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="e2bd5-116">Para obter detalhes sobre a configuração de políticas para o uso de acesso de usuário remoto, consulte [Configurar políticas para controlar o acesso de usuários remotos no Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e2bd5-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="e2bd5-117">Para habilitar ou desabilitar o acesso de usuários remotos para sua organização</span><span class="sxs-lookup"><span data-stu-id="e2bd5-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="e2bd5-118">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2bd5-119">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e2bd5-120">Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="e2bd5-121">Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e2bd5-122">Em **Editar configuração de borda de acesso**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e2bd5-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="e2bd5-123">Para habilitar o acesso de usuário remoto para sua organização, marque a caixa de seleção **habilitar acesso do usuário remoto** .</span><span class="sxs-lookup"><span data-stu-id="e2bd5-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="e2bd5-124">Para desabilitar o acesso de usuário remoto para sua organização, desmarque a caixa de seleção **habilitar acesso de usuário remoto** .</span><span class="sxs-lookup"><span data-stu-id="e2bd5-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="e2bd5-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-125">Click **Commit**.</span></span>

<span data-ttu-id="e2bd5-126">Para permitir que os usuários remotos entrem em seus servidores que executam o Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="e2bd5-127">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários remotos no Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e2bd5-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e2bd5-128">Habilitar ou desabilitar o acesso de usuário remoto usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2bd5-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e2bd5-129">O acesso do usuário remoto pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="e2bd5-130">Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2bd5-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="e2bd5-131">Para habilitar o acesso de usuários remotos</span><span class="sxs-lookup"><span data-stu-id="e2bd5-131">To enable remote user access</span></span>

  - <span data-ttu-id="e2bd5-132">Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como True ($true):</span><span class="sxs-lookup"><span data-stu-id="e2bd5-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="e2bd5-133">Para desabilitar o acesso de usuários remotos</span><span class="sxs-lookup"><span data-stu-id="e2bd5-133">To disable remote user access</span></span>

  - <span data-ttu-id="e2bd5-134">Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como False ($false):</span><span class="sxs-lookup"><span data-stu-id="e2bd5-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


