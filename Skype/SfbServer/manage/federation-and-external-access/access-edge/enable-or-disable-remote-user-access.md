---
title: Habilitar ou desabilitar acesso de usuário remoto
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se você habilitar o acesso de usuário remoto para usuários remotos, usuários remotos com suporte se conectar à Internet e não precisará conectar usando uma VPN para colaborar com usuários internos usando Skype para o servidor de negócios.
ms.openlocfilehash: 34733c4d1912461090ef868e24ae24dc1c870a94
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222874"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="25b51-103">Habilitar ou desabilitar o acesso de usuário remoto no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="25b51-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="25b51-104">Usuários remotos são usuários em sua organização que têm uma identidade persistente do Active Directory dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="25b51-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="25b51-105">Usuários remotos com frequência entram Skype para Business Server de fora da rede usando uma rede virtual privada (VPN) quando não estiverem conectados à rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="25b51-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="25b51-106">Usuários remotos incluem funcionários que trabalham em casa ou em trânsito e outros trabalhadores remotos, como fornecedores confiáveis, aos quais foram concedidas credenciais da empresa.</span><span class="sxs-lookup"><span data-stu-id="25b51-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="25b51-107">Se você habilitar o acesso de usuário remoto para usuários remotos, usuários remotos com suporte se conectar à Internet e não precisará conectar usando uma VPN para colaborar com usuários internos usando Skype para o servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="25b51-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="25b51-108">Para suportar o acesso de usuário remoto, você deve habilitar o acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="25b51-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="25b51-109">Quando você habilita o acesso de usuário remoto, você pode habilitá-lo para toda sua organização.</span><span class="sxs-lookup"><span data-stu-id="25b51-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="25b51-110">Se você quiser mais tarde temporária ou permanentemente impedir o acesso de usuário remoto, você pode desabilitá-lo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="25b51-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="25b51-111">Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuário remoto para sua organização.</span><span class="sxs-lookup"><span data-stu-id="25b51-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="25b51-112">Permitindo o acesso de usuário remoto especifica apenas que os servidores que executam o serviço de borda de acesso suportam a comunicações com usuários remotos, mas usuários remotos não podem participar de conferências em sua organização ou de mensagens instantâneas (IM) até que você também configurar no pelo menos uma política para gerenciar o uso de acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="25b51-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="25b51-113">Skype para configurações de diretiva de servidor de negócios que são aplicados em um nível de política pode substituir as configurações que são aplicadas no nível de política de outro.</span><span class="sxs-lookup"><span data-stu-id="25b51-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="25b51-114">Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos).</span><span class="sxs-lookup"><span data-stu-id="25b51-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="25b51-115">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="25b51-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="25b51-116">Para obter detalhes sobre como configurar políticas para o uso de acesso de usuário remoto, consulte [Configure políticas para controlar o acesso de usuário remoto no Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="25b51-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="25b51-117">Para habilitar ou desabilitar o acesso de usuário remoto para sua organização</span><span class="sxs-lookup"><span data-stu-id="25b51-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="25b51-118">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="25b51-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="25b51-119">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="25b51-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="25b51-120">Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="25b51-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="25b51-121">Na página **Configuração de borda de acesso** , clique em **Global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="25b51-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="25b51-122">Em **Editar configuração de borda de acesso**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="25b51-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="25b51-123">Para habilitar o acesso de usuário remoto para sua organização, marque a caixa de seleção **Habilitar acesso de usuário remoto** .</span><span class="sxs-lookup"><span data-stu-id="25b51-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="25b51-124">Para desabilitar o acesso de usuário remoto para sua organização, desmarque a caixa de seleção **Habilitar acesso de usuário remoto** .</span><span class="sxs-lookup"><span data-stu-id="25b51-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="25b51-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="25b51-125">Click **Commit**.</span></span>

<span data-ttu-id="25b51-126">Para permitir que usuários remotos entrar em seus servidores executando o Skype para Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="25b51-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="25b51-127">Para obter detalhes, consulte [Configure políticas para controlar o acesso de usuário remoto no Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="25b51-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="25b51-128">Habilitar ou desabilitar o acesso de usuário remoto usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25b51-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="25b51-129">Acesso de usuários remotos pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="25b51-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="25b51-130">Este cmdlet pode ser executado a partir do Skype para Business Server 2013 Management Shell ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25b51-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="25b51-131">Para habilitar o acesso de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="25b51-131">To enable remote user access</span></span>

  - <span data-ttu-id="25b51-132">Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para True ($True):</span><span class="sxs-lookup"><span data-stu-id="25b51-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="25b51-133">Para desabilitar o acesso de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="25b51-133">To disable remote user access</span></span>

  - <span data-ttu-id="25b51-134">Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para False ($False):</span><span class="sxs-lookup"><span data-stu-id="25b51-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


