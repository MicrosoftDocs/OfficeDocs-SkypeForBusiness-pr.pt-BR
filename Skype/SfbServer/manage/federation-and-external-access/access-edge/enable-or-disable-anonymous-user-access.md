---
title: Habilitar ou desabilitar acesso de usuário anônimo
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
description: ''
ms.openlocfilehash: 7e828745810bd49f9b8f3ea9e7bee1d023e4fc67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817441"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="3cdd3-102">Habilitar ou desabilitar o acesso de usuário anônimo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3cdd3-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="3cdd3-103">Usuários anônimos são usuários que não têm uma conta de usuário nos Serviços de Domínio Active Directory da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente de uma conferência local.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="3cdd3-104">Ao permitir a participação anônima em reuniões, você habilita os usuários anônimos (isto é, usuários cuja identidade é verificada apenas por meio da chave de reunião ou conferência) a participarem de reuniões.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="3cdd3-105">Para permitir a participação anônima em sua organização, é necessário que você habilite esse recurso.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="3cdd3-p102">Se mais tarde você quiser prevenir o acesso de usuários anônimos temporariamente ou permanentemente, é possível desabilitar esse acesso à sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários anônimos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-p102">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization. Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="3cdd3-108">Habilitar o acesso de usuários anônimos à sua organização apenas especifica que seus servidores que estão executando o serviço de Borda de Acesso dão suporte ao acesso de usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="3cdd3-109">Os usuários anônimos não podem participar de nenhuma reunião da sua organização até que seja configurada ao menos uma política de conferência e que esta seja aplicada a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="3cdd3-110">Os únicos usuários que podem convidar usuários anônimos para reuniões são aqueles com uma política de conferência designada configurada para dar suporte aos usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="3cdd3-111">Para obter detalhes sobre como configurar políticas de conferência para dar suporte a usuários anônimos, consulte [Gerenciar políticas de conferência.](../../conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3cdd3-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="3cdd3-112">Para habilitar ou desabilitar o acesso de usuários anônimos à sua organização</span><span class="sxs-lookup"><span data-stu-id="3cdd3-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="3cdd3-113">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3cdd3-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3cdd3-115">No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3cdd3-116">Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3cdd3-117">Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="3cdd3-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="3cdd3-118">Para habilitar o acesso de usuários anônimos à sua organização, marque a caixa de seleção **Habilitar comunicações com usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="3cdd3-119">Para desabilitar o acesso de usuários anônimos à sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="3cdd3-120">Clique em **Confirmar**</span><span class="sxs-lookup"><span data-stu-id="3cdd3-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3cdd3-121">Habilitando ou desabilitando o acesso de usuário anônimo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cdd3-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3cdd3-122">Você pode gerenciar o acesso de usuário anônimo usando o Windows PowerShell e o cmdlet **Set-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="3cdd3-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="3cdd3-123">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cdd3-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="3cdd3-124">Para habilitar o acesso de usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="3cdd3-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="3cdd3-125">Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="3cdd3-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="3cdd3-126">Para desabilitar o acesso de usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="3cdd3-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="3cdd3-127">Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="3cdd3-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="3cdd3-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="3cdd3-128">See Also</span></span>

[<span data-ttu-id="3cdd3-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3cdd3-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
