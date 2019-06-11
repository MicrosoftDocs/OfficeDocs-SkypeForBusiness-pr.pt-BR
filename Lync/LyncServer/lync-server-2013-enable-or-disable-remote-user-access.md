---
title: 'Lync Server 2013: Habilitar ou desabilitar acesso de usuário remoto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="fe2f1-102">Habilitar ou desabilitar acesso de usuário remoto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe2f1-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe2f1-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fe2f1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fe2f1-104">Usuários remotos são usuários de sua organização que têm uma identidade persistente do Active Directory dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="fe2f1-105">Usuários remotos geralmente se conectam ao Lync Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="fe2f1-106">Os usuários remotos incluem funcionários que trabalham em casa ou em trânsito e outros trabalhadores remotos, como fornecedores confiáveis, que receberam credenciais da empresa.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="fe2f1-107">Se você habilitar o acesso de usuários remotos para usuários remotos, os usuários remotos compatíveis se conectarem pela Internet e não precisarão se conectar usando uma VPN para colaborar com usuários internos usando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="fe2f1-108">Para dar suporte ao acesso de usuário remoto, você deve habilitar o acesso de usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="fe2f1-109">Ao habilitar o acesso de usuário remoto, habilite-o para toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="fe2f1-110">Se, mais tarde, você quiser impedir temporariamente ou permanentemente o acesso do usuário remoto, você pode desabilitá-lo para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="fe2f1-111">Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários remotos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe2f1-112">Habilitar o acesso de usuários remotos especifica que os servidores que executam o serviço de borda de acesso dão suporte a comunicações com usuários remotos, mas os usuários remotos não podem participar de mensagens instantâneas (IM) nem conferências em sua organização até você também configurar ao mesmo tempo. menos uma política para gerenciar o uso de acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="fe2f1-113">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="fe2f1-114">A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima).</span><span class="sxs-lookup"><span data-stu-id="fe2f1-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="fe2f1-115">Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="fe2f1-116">Para obter detalhes sobre a configuração de políticas para o uso de acesso de usuário remoto, consulte <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar políticas para controlar o acesso de usuários remotos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="fe2f1-117">Para habilitar ou desabilitar o acesso de usuários remotos para sua organização</span><span class="sxs-lookup"><span data-stu-id="fe2f1-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="fe2f1-118">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe2f1-119">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe2f1-120">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fe2f1-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe2f1-121">Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="fe2f1-122">Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fe2f1-123">Em **Editar configuração de borda de acesso**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fe2f1-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="fe2f1-124">Para habilitar o acesso de usuário remoto para sua organização, marque a caixa de seleção **habilitar acesso do usuário remoto** .</span><span class="sxs-lookup"><span data-stu-id="fe2f1-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="fe2f1-125">Para desabilitar o acesso de usuário remoto para sua organização, desmarque a caixa de seleção **habilitar acesso de usuário remoto** .</span><span class="sxs-lookup"><span data-stu-id="fe2f1-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="fe2f1-126">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-126">Click **Commit**.</span></span>

<span data-ttu-id="fe2f1-127">Para permitir que os usuários remotos entrem em seus servidores que executam o Lync Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="fe2f1-128">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários remotos no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fe2f1-129">Habilitar ou desabilitar o acesso de usuário remoto usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe2f1-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fe2f1-130">O acesso do usuário remoto pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="fe2f1-131">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fe2f1-132">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="fe2f1-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="fe2f1-133">Para habilitar o acesso de usuários remotos</span><span class="sxs-lookup"><span data-stu-id="fe2f1-133">To enable remote user access</span></span>

  - <span data-ttu-id="fe2f1-134">Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como True ($true):</span><span class="sxs-lookup"><span data-stu-id="fe2f1-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="fe2f1-135">Para desabilitar o acesso de usuários remotos</span><span class="sxs-lookup"><span data-stu-id="fe2f1-135">To disable remote user access</span></span>

  - <span data-ttu-id="fe2f1-136">Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como False ($false):</span><span class="sxs-lookup"><span data-stu-id="fe2f1-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

