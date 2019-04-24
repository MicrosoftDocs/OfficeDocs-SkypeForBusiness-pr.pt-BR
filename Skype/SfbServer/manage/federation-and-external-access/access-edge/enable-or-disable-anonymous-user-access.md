---
title: Habilitar ou desabilitar acesso de usuário anônimo
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a68790f870a6c62b513caab559580695763cd4df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199945"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="fb630-102">Habilitar ou desabilitar o acesso de usuário anônimo no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="fb630-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="fb630-103">Usuários anônimos são usuários que não têm uma conta de usuário no Active Directory Domain Services da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência no local.</span><span class="sxs-lookup"><span data-stu-id="fb630-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="fb630-104">Permitindo a participação anônima em reuniões permitir que usuários anônimos (ou seja, os usuários cuja identidade é confirmada através a chave de reunião ou conferência somente) para participar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="fb630-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="fb630-105">Permitindo a participação anônima requer ativá-lo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fb630-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="fb630-106">Se você quiser mais tarde temporária ou permanentemente impedir o acesso por usuários anônimos, você pode desabilitá-lo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fb630-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="fb630-107">Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuário anônimo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fb630-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="fb630-108">Habilitando o acesso de usuário anônimo para sua organização estiver apenas especificando que os servidores que executam o serviço de borda de acesso para suportam o acesso por usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="fb630-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="fb630-109">Usuários anônimos não podem participar de qualquer reuniões em sua organização até que você também configurar pelo menos uma política de conferência e aplicá-la a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="fb630-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="fb630-110">Os usuários só podem convidar usuários anônimos para reuniões são os usuários que estão atribuídos a uma política de conferência que está configurada para oferecer suporte a usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="fb630-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="fb630-111">Para obter detalhes sobre como configurar políticas de conferência para suportar convidem usuários anônimos, consulte [Gerenciar políticas de conferência](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fb630-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="fb630-112">Para habilitar ou desabilitar o acesso de usuário anônimo para sua organização</span><span class="sxs-lookup"><span data-stu-id="fb630-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="fb630-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fb630-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb630-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fb630-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fb630-115">Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Configuração de borda de acesso**.</span><span class="sxs-lookup"><span data-stu-id="fb630-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="fb630-116">Na página **Configuração de borda de acesso** , clique em **Global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="fb630-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fb630-117">Em **Editar configuração de borda de acesso**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fb630-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="fb630-118">Para habilitar o acesso de usuário anônimo para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="fb630-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="fb630-119">Para desabilitar o acesso de usuário anônimo para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="fb630-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="fb630-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fb630-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fb630-121">Habilitar ou desabilitar o acesso de usuário anônimo usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb630-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="fb630-122">Você pode gerenciar o acesso de usuário anônimo usando o Windows PowerShell e o cmdlet **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fb630-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="fb630-123">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb630-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="fb630-124">Para habilitar o acesso de usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="fb630-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="fb630-125">Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="fb630-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="fb630-126">Para desabilitar o acesso de usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="fb630-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="fb630-127">Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para FALSO ($False):</span><span class="sxs-lookup"><span data-stu-id="fb630-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="fb630-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb630-128">See Also</span></span>

[<span data-ttu-id="fb630-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="fb630-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
