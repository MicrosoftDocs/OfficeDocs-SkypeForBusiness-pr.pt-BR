---
title: 'Lync Server 2013: habilitar ou desabilitar Federação e conectividade de IM pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9281b4dab225ddb336dbc74a5d2892f0f4a015d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="5fc5c-102">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fc5c-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fc5c-103">_**Última modificação do tópico:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="5fc5c-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="5fc5c-104">O suporte para Federação é necessário para permitir que os usuários que têm uma conta com um cliente ou uma organização de parceiro confiável, incluindo domínios de parceiros e usuários de usuários de provedores públicos de mensagens instantâneas (IM) que você suporta, para colaborar com usuários no seu departamento.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="5fc5c-105">A Federação também é necessária para usar um provedor de serviço do Exchange hospedado para fornecer correio de voz para usuários do Enterprise Voice cujas caixas de correio estão localizadas em um serviço do Exchange hospedado, como o Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="5fc5c-106">Quando tiver estabelecido uma relação de confiança com esses domínios externos, você poderá autorizar os usuários nesses domínios a acessar sua implantação e participar de comunicações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="5fc5c-107">Essa relação de confiança é chamada de Federação e não está relacionada ou dependente de uma relação de confiança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="5fc5c-108">Para dar suporte ao acesso por usuários de domínios federados, você deve habilitar a Federação.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="5fc5c-109">Se você habilitar a Federação para sua organização, também deverá especificar se deseja implementar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5fc5c-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="5fc5c-110">**Habilitar descoberta**   de domínio de parceiro se você habilitar essa opção, o Lync Server usará registros de DNS (sistema de nomes de domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, automaticamente avaliando o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações de administrador.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="5fc5c-111">Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="5fc5c-112">Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="5fc5c-113">Para obter detalhes sobre como controlar o acesso por domínios federados, consulte [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="5fc5c-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="5fc5c-114">**Enviar uma isenção de responsabilidade de arquivamento para parceiros**     federados aviso de isenção de responsabilidade é enviado para parceiros federados que o arquivamento em sua implantação está em vigor.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="5fc5c-115">Se você oferecer suporte ao arquivamento de comunicações externas com domínios de parceiros federados, deverá habilitar a notificação de aviso de isenção de responsabilidade para avisar os parceiros de que suas mensagens estão sendo arquivadas.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="5fc5c-116">Se posteriormente você quiser impedir o acesso temporário ou permanente por usuários de domínios federados, poderá desabilitar a Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="5fc5c-117">Use o procedimento nesta seção para habilitar ou desabilitar o acesso de usuário federado à sua organização, incluindo a especificação das opções de Federação apropriadas para ter suporte para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5fc5c-118">Habilitar a Federação para sua organização especifica apenas que os servidores que executam o serviço de borda de acesso dão suporte ao roteamento para domínios federados.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="5fc5c-119">Os usuários de domínios federados não podem participar de IM ou conferências em sua organização até que você também configure pelo menos uma política para dar suporte ao acesso de usuário federado.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="5fc5c-120">Os usuários de provedores de serviço de mensagens instantâneas públicos não podem participar de IM ou conferências em sua organização até que você também configure pelo menos uma política para suportar a conectividade pública de IM.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="5fc5c-121">O Lync Server não pode usar um serviço do Exchange hospedado para fornecer atendimento de chamadas, Outlook Voice Access (incluindo caixa postal) ou serviços de atendedor automático para usuários cujas caixas de correio estão localizadas em um serviço do Exchange hospedado até que você configure uma política de caixa postal hospedada que fornece informações de roteamento.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="5fc5c-122">Para obter detalhes sobre como configurar políticas para comunicação com usuários de domínios federados em outras organizações, consulte <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP Federated Domains for Your Organization in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="5fc5c-123">Além disso, se você quiser dar suporte à comunicação com usuários de provedores de serviços de mensagens instantâneas, configure as políticas para dar suporte a ela e também configure o suporte para os provedores de serviços individuais que você deseja suportar.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="5fc5c-124">Para obter detalhes, consulte <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP Federated Providers for Your Organization no Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="5fc5c-125">Para obter detalhes sobre como criar uma política de caixa postal hospedada, consulte <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage Hosted voice mail Policies in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="5fc5c-126">Para habilitar ou desabilitar o acesso de usuário federado à sua organização</span><span class="sxs-lookup"><span data-stu-id="5fc5c-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="5fc5c-127">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5fc5c-128">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5fc5c-129">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5fc5c-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5fc5c-130">No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="5fc5c-131">Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5fc5c-132">Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="5fc5c-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="5fc5c-133">Para habilitar o acesso de usuário federado à sua organização, marque a caixa de seleção **habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="5fc5c-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="5fc5c-134">Para desabilitar o acesso de usuário federado para sua organização, desmarque a caixa de seleção **habilitar comunicações com usuários federados** .</span><span class="sxs-lookup"><span data-stu-id="5fc5c-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="5fc5c-135">Se você marcou a caixa de seleção **habilitar comunicações com usuários federados** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5fc5c-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="5fc5c-136">Se você quiser oferecer suporte à descoberta automática de domínios de parceiros, marque a caixa de seleção **habilitar descoberta de domínio de parceiro** .</span><span class="sxs-lookup"><span data-stu-id="5fc5c-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="5fc5c-137">Se sua organização oferecer suporte ao arquivamento de comunicações externas, marque a caixa de seleção **Enviar aviso de isenção de arquivamento para parceiros federados** .</span><span class="sxs-lookup"><span data-stu-id="5fc5c-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="5fc5c-138">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-138">Click **Commit**.</span></span>

<span data-ttu-id="5fc5c-139">Para permitir que usuários federados colaborem com usuários em sua implantação do Lync Server 2013, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário federado.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="5fc5c-140">Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="5fc5c-141">Para controlar o acesso de domínios federados específicos, confira [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) na documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5fc5c-142">Habilitando ou desabilitando a Federação e conectividade de IM pública usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fc5c-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5fc5c-143">A Federação e a conectividade de IM pública também podem ser gerenciadas usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5fc5c-144">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5fc5c-145">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="5fc5c-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="5fc5c-146">Para habilitar a Federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="5fc5c-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="5fc5c-147">Para habilitar a Federação e a conectividade de IM pública, defina o valor da propriedade **AllowFederatedUsers** como True ($true):</span><span class="sxs-lookup"><span data-stu-id="5fc5c-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="5fc5c-148">Para desabilitar a Federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="5fc5c-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="5fc5c-149">Para desabilitar a Federação e a conectividade de IM pública, defina o valor da propriedade **AllowFederatedUsers** como False ($false):</span><span class="sxs-lookup"><span data-stu-id="5fc5c-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

