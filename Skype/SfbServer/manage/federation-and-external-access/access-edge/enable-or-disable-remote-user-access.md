---
title: Habilitar ou desabilitar acesso de usuário remoto
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos suportados se conectam pela Internet e não têm que se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817391"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="5c10e-103">Habilitar ou desabilitar o acesso de usuário remoto no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c10e-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="5c10e-104">Usuários remotos são usuários em suas organizações com uma identidade do Active Directory persistente dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="5c10e-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="5c10e-105">Os usuários remotos frequentemente fazem login no Skype for Business Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5c10e-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="5c10e-106">Os usuários remotos incluem funcionários trabalhando em casa ou na estrada e outros trabalhadores remotos, como vendedores confiáveis, que foram concedidos com credenciais empresariais.</span><span class="sxs-lookup"><span data-stu-id="5c10e-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="5c10e-107">Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos suportados se conectam pela Internet e não têm que se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c10e-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="5c10e-p102">Para suportar acesso de usuário remoto, você deve habilitar o acesso de usuário remoto. Ao habilitar o acesso de usuário remoto, você o habilita para toda sua organização. Se posteriormente você quiser impedir temporariamente ou permanentemente o acesso dos domínios federados pelos usuários, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso do usuário federado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5c10e-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="5c10e-112">Habilitar o acesso de usuário remoto apenas especifica que seus servidores executando as comunicações de suporte do serviço de Borda de Acesso com usuário remotos, mas os usuários remotos não podem participar de mensagem instantânea (IM) ou conferências em sua organização até que você também configure pelo menos uma política para gerenciar o uso do acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="5c10e-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="5c10e-113">As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="5c10e-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5c10e-114">A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência).</span><span class="sxs-lookup"><span data-stu-id="5c10e-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5c10e-115">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="5c10e-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="5c10e-116">Para obter detalhes sobre como configurar políticas para o uso do acesso de usuário remoto, consulte Configurar políticas para controlar o acesso de usuário remoto [no Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="5c10e-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="5c10e-117">Para habilitar ou desabilitar o acesso do usuário federado na sua organização</span><span class="sxs-lookup"><span data-stu-id="5c10e-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="5c10e-118">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5c10e-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c10e-119">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c10e-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c10e-120">Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="5c10e-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="5c10e-121">Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5c10e-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5c10e-122">Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="5c10e-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="5c10e-123">Para habilitar o acesso ao usuário remoto para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="5c10e-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="5c10e-124">Para desabilitar o acesso ao usuário remoto para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="5c10e-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="5c10e-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5c10e-125">Click **Commit**.</span></span>

<span data-ttu-id="5c10e-126">Para permitir que os usuários remotos se inscrevam em seus servidores que executam o Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="5c10e-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="5c10e-127">Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário remoto no Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="5c10e-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5c10e-128">Habilitando ou desabilitando o acesso de usuário remoto usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c10e-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5c10e-129">O acesso de usuário remoto pode ser gerenciado usando o Windows PowerShell e o Set-CsAccessEdgeConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5c10e-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5c10e-130">Este cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c10e-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="5c10e-131">Para habilitar o acesso de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="5c10e-131">To enable remote user access</span></span>

  - <span data-ttu-id="5c10e-132">Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para True ($True):</span><span class="sxs-lookup"><span data-stu-id="5c10e-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="5c10e-133">Para desabilitar o acesso de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="5c10e-133">To disable remote user access</span></span>

  - <span data-ttu-id="5c10e-134">Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para False ($False):</span><span class="sxs-lookup"><span data-stu-id="5c10e-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


