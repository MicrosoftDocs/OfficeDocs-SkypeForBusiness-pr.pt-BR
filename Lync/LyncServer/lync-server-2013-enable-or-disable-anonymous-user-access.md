---
title: 'Lync Server 2013: habilitar ou desabilitar o acesso de usuário anônimo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ab7d0f3d47da8bae3df94c3c83b1eae0059e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501078"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="f32bf-102">Habilitar ou desabilitar o acesso de usuário anônimo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f32bf-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f32bf-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f32bf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f32bf-104">Usuários anônimos são usuários que não possuem uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência local.</span><span class="sxs-lookup"><span data-stu-id="f32bf-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="f32bf-105">Ao permitir a participação anônima em reuniões, você habilita os usuários anônimos (isto é, usuários cuja identidade é verificada apenas por meio da chave de reunião ou conferência) a participarem de reuniões.</span><span class="sxs-lookup"><span data-stu-id="f32bf-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="f32bf-106">Para permitir a participação anônima em sua organização, é necessário que você habilite esse recurso.</span><span class="sxs-lookup"><span data-stu-id="f32bf-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="f32bf-p102">Se mais tarde você quiser prevenir o acesso de usuários anônimos temporariamente ou permanentemente, é possível desabilitar esse acesso à sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários anônimos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="f32bf-p102">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization. Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f32bf-109">Habilitar o acesso de usuários anônimos à sua organização apenas especifica que seus servidores que estão executando o serviço de Borda de Acesso dão suporte ao acesso de usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="f32bf-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="f32bf-110">Os usuários anônimos não podem participar de nenhuma reunião da sua organização até que seja configurada ao menos uma política de conferência e que esta seja aplicada a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="f32bf-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="f32bf-111">Os únicos usuários que podem convidar usuários anônimos para reuniões são aqueles com uma política de conferência designada configurada para dar suporte aos usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="f32bf-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="f32bf-112">Para obter detalhes sobre como configurar as políticas de conferência para suportar o convite de usuários anônimos, consulte <A href="lync-server-2013-conferencing-policies.md">políticas de conferência no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f32bf-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="f32bf-113">Para habilitar ou desabilitar o acesso de usuários anônimos à sua organização</span><span class="sxs-lookup"><span data-stu-id="f32bf-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="f32bf-114">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f32bf-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f32bf-115">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f32bf-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f32bf-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f32bf-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f32bf-117">No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="f32bf-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f32bf-118">Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f32bf-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f32bf-119">Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="f32bf-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="f32bf-120">Para habilitar o acesso de usuários anônimos à sua organização, marque a caixa de seleção **Habilitar comunicações com usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="f32bf-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="f32bf-121">Para desabilitar o acesso de usuários anônimos à sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="f32bf-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="f32bf-122">Clique em **Confirmar**</span><span class="sxs-lookup"><span data-stu-id="f32bf-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f32bf-123">Habilitando ou desabilitando o acesso de usuário anônimo usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f32bf-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f32bf-124">Você pode gerenciar o acesso de usuários anônimos usando o Windows PowerShell e o cmdlet **set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f32bf-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="f32bf-125">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f32bf-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f32bf-126">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f32bf-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="f32bf-127">Para habilitar o acesso de usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="f32bf-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="f32bf-128">Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="f32bf-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="f32bf-129">Para desabilitar o acesso de usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="f32bf-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="f32bf-130">Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="f32bf-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f32bf-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="f32bf-131">See Also</span></span>


[<span data-ttu-id="f32bf-132">Referência de configurações de política de conferência para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f32bf-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

