---
title: 'Lync Server 2013: Habilitar ou desabilitar acesso de usuário anônimo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d07bf27f5424f121c5dcf070f5231e2fd8c324f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="29502-102">Habilitar ou desabilitar acesso de usuário anônimo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29502-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29502-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="29502-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="29502-104">Usuários anônimos são usuários que não têm uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência local.</span><span class="sxs-lookup"><span data-stu-id="29502-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="29502-105">Ao permitir a participação anônima em reuniões, usuários anônimos (ou seja, usuários cuja identidade são verificadas apenas na reunião ou na chave da conferência) para ingressar em reuniões.</span><span class="sxs-lookup"><span data-stu-id="29502-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="29502-106">Permitir a participação anônima exige a habilitação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="29502-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="29502-107">Se, mais tarde, você quiser impedir o acesso temporário ou permanente de usuários anônimos, pode desabilitá-lo para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="29502-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="29502-108">Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários anônimos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="29502-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29502-109">Ao habilitar o acesso de usuários anônimos para sua organização, você está especificando que seus servidores que executam o serviço de borda de acesso oferecem suporte a usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="29502-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="29502-110">Usuários anônimos não podem participar de nenhuma reunião em sua organização até você também configurar pelo menos uma política de conferência e aplicá-la a um ou mais usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="29502-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="29502-111">Os únicos usuários que podem convidar usuários anônimos para reuniões são os usuários que recebem uma política de conferência configurada para dar suporte a usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="29502-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="29502-112">Para obter detalhes sobre como configurar as políticas de conferência para dar suporte ao convite para usuários anônimos, consulte <A href="lync-server-2013-conferencing-policies.md">políticas de conferência no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="29502-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="29502-113">Para habilitar ou desabilitar o acesso de usuários anônimos para a sua organização</span><span class="sxs-lookup"><span data-stu-id="29502-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="29502-114">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="29502-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="29502-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29502-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29502-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="29502-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29502-117">Na barra de navegação à esquerda, clique em **acesso de usuário externo**e, em seguida, clique em **configuração de borda de acesso**.</span><span class="sxs-lookup"><span data-stu-id="29502-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="29502-118">Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="29502-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="29502-119">Em **Editar configuração de borda de acesso**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="29502-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="29502-120">Para habilitar o acesso de usuários anônimos para sua organização, marque a caixa de seleção **habilitar comunicações com usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="29502-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="29502-121">Para desabilitar o acesso de usuários anônimos para sua organização, desmarque a caixa de seleção **habilitar comunicações com usuários anônimos** .</span><span class="sxs-lookup"><span data-stu-id="29502-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="29502-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="29502-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="29502-123">Habilitar ou desabilitar o acesso de usuários anônimos usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29502-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="29502-124">Você pode gerenciar o acesso de usuários anônimos usando o Windows PowerShell e o cmdlet **set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="29502-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="29502-125">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29502-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="29502-126">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="29502-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="29502-127">Para habilitar o acesso de usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="29502-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="29502-128">Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** como True ($true):</span><span class="sxs-lookup"><span data-stu-id="29502-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="29502-129">Para desativar o acesso de usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="29502-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="29502-130">Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** como False ($false):</span><span class="sxs-lookup"><span data-stu-id="29502-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29502-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="29502-131">See Also</span></span>


[<span data-ttu-id="29502-132">Referência de configurações de política de conferência para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29502-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

