---
title: 'Lync Server 2013: habilitar ou desabilitar o acesso de usuário remoto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f02281bdb47fc043d372f5b6e3842a70fe39316
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515540"
---
# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="77f2f-102">Habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f2f-102">Enable or disable remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77f2f-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="77f2f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="77f2f-104">Usuários remotos são usuários em suas organizações com uma identidade do Active Directory persistente dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="77f2f-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="77f2f-105">Os usuários remotos freqüentemente entram no Lync Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="77f2f-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="77f2f-106">Os usuários remotos incluem funcionários trabalhando em casa ou na estrada e outros trabalhadores remotos, como vendedores confiáveis, que foram concedidos com credenciais empresariais.</span><span class="sxs-lookup"><span data-stu-id="77f2f-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="77f2f-107">Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos suportados se conectam pela Internet e não precisam se conectar usando uma VPN para colaborar com usuários internos usando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77f2f-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="77f2f-p102">Para suportar acesso de usuário remoto, você deve habilitar o acesso de usuário remoto. Ao habilitar o acesso de usuário remoto, você o habilita para toda sua organização. Se posteriormente você quiser impedir temporariamente ou permanentemente o acesso dos domínios federados pelos usuários, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso do usuário federado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="77f2f-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77f2f-112">Habilitar o acesso de usuário remoto apenas especifica que seus servidores executando as comunicações de suporte do serviço de Borda de Acesso com usuário remotos, mas os usuários remotos não podem participar de mensagem instantânea (IM) ou conferências em sua organização até que você também configure pelo menos uma política para gerenciar o uso do acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="77f2f-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="77f2f-113">As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política.</span><span class="sxs-lookup"><span data-stu-id="77f2f-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="77f2f-114">A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência).</span><span class="sxs-lookup"><span data-stu-id="77f2f-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="77f2f-115">Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="77f2f-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="77f2f-116">Para obter detalhes sobre como configurar políticas para o uso de acesso de usuário remoto, consulte <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure Policies to Control Remote User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77f2f-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="77f2f-117">Para habilitar ou desabilitar o acesso do usuário federado na sua organização</span><span class="sxs-lookup"><span data-stu-id="77f2f-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="77f2f-118">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="77f2f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="77f2f-119">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77f2f-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="77f2f-120">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="77f2f-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="77f2f-121">Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="77f2f-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="77f2f-122">Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="77f2f-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="77f2f-123">Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="77f2f-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="77f2f-124">Para habilitar o acesso ao usuário remoto para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="77f2f-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="77f2f-125">Para desabilitar o acesso ao usuário remoto para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="77f2f-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="77f2f-126">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="77f2f-126">Click **Commit**.</span></span>

<span data-ttu-id="77f2f-127">Para permitir que os usuários remotos entrem em seus servidores que executam o Lync Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário remoto.</span><span class="sxs-lookup"><span data-stu-id="77f2f-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="77f2f-128">Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) na documentação de implantação ou na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="77f2f-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="77f2f-129">Habilitando ou desabilitando o acesso de usuário remoto usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77f2f-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="77f2f-130">O acesso de usuário remoto pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="77f2f-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="77f2f-131">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77f2f-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="77f2f-132">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="77f2f-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="77f2f-133">Para habilitar o acesso de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="77f2f-133">To enable remote user access</span></span>

  - <span data-ttu-id="77f2f-134">Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para True ($True):</span><span class="sxs-lookup"><span data-stu-id="77f2f-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="77f2f-135">Para desabilitar o acesso de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="77f2f-135">To disable remote user access</span></span>

  - <span data-ttu-id="77f2f-136">Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para False ($False):</span><span class="sxs-lookup"><span data-stu-id="77f2f-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

