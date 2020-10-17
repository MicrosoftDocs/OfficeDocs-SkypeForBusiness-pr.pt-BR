---
title: 'Lync Server 2013: gerenciar a configuração de borda de acesso para sua organização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c62e5b03057f09d7489a413456e432e8e08799b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534539"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="f4b21-102">Gerenciar a configuração de borda de acesso para sua organização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b21-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4b21-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f4b21-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f4b21-104">Esta é uma documentação preliminar e está sujeita a alterações.</span><span class="sxs-lookup"><span data-stu-id="f4b21-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="f4b21-105">Tópicos em branco são incluídos como espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="f4b21-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="f4b21-106">Após a implantação de um ou mais servidores de borda, você deve habilitar os tipos de domínio externo ou acesso de provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos servidores de borda que terão suporte para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4b21-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="f4b21-107">Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página **Configuração de Borda de Acesso**:</span><span class="sxs-lookup"><span data-stu-id="f4b21-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="f4b21-108">**Habilitar Federação e conectividade**     de im pública Habilite isso se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="f4b21-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="f4b21-109">Essa configuração se aplica à federação SIP e à federação XMPP configuradas para escopos global, site ou usuário na página **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="f4b21-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="f4b21-110">Para aplicar as configurações de federação, é necessário configurar o suporte à federação em ambas as páginas.</span><span class="sxs-lookup"><span data-stu-id="f4b21-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="f4b21-111">Há duas configurações opcionais para o modo como os parceiros federados são descobertos, e se os avisos de isenção de arquivamento (notificação a contatos federados com os quais você se comunica de que sua implantação tem o arquivamento habilitado e de que os detalhes das comunicações serão arquivados) serão enviados aos contatos</span><span class="sxs-lookup"><span data-stu-id="f4b21-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="f4b21-112">**Habilitar descoberta**     de domínio de parceiro Selecionar essa opção permite a descoberta automática de domínios com os quais você pode federar.</span><span class="sxs-lookup"><span data-stu-id="f4b21-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="f4b21-113">O Lync Server 2013 usa registros de sistema de nomes de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliar automaticamente o tráfego de entrada de parceiros federados descobertos e limitar ou bloquear esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações de administrador.</span><span class="sxs-lookup"><span data-stu-id="f4b21-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="f4b21-114">Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="f4b21-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="f4b21-115">Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado.</span><span class="sxs-lookup"><span data-stu-id="f4b21-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="f4b21-116">Para obter detalhes, consulte [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="f4b21-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="f4b21-117">**Enviar isenção de responsabilidade de arquivamento para parceiros federados**     Selecionar essa opção permite o envio de uma mensagem de isenção de responsabilidade de arquivamento para parceiros federados que os aconselham que os detalhes de comunicação sejam registrados.</span><span class="sxs-lookup"><span data-stu-id="f4b21-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="f4b21-118">Se você arquivar comunicações externas com domínios de parceiro federados, deverá habilitar a notificação de aviso de isenção de responsabilidade de arquivamento a fim de avisar os parceiros de que suas mensagens e comunicações estão sendo arquivadas por sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f4b21-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="f4b21-119">Para obter detalhes sobre arquivamento, consulte [definindo seus requisitos para arquivamento no Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="f4b21-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="f4b21-120">**Habilitar o acesso**     de usuário remoto Habilite essa opção se quiser que os usuários em sua organização que estejam fora do firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4b21-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="f4b21-121">Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f4b21-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="f4b21-122">**Permitir que usuários anônimos acessem conferências**     Habilite essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências que eles organizam.</span><span class="sxs-lookup"><span data-stu-id="f4b21-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="f4b21-123">A habilitação dessa configuração permite apenas usuários anônimos para conferências.</span><span class="sxs-lookup"><span data-stu-id="f4b21-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="f4b21-124">Para configurar a experiência de conferência e as opções que definirão como e o que os usuários podem fazer com conferências e para a inclusão de usuários anônimos, confira detalhes em [criar ou modificar a experiência do usuário de conferência para uma](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) referência de política de site ou de usuários e [conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f4b21-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4b21-125">Além de permitir o suporte ao acesso de usuário externo, você também configura políticas para controlar o uso do acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo ficar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="f4b21-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="f4b21-126">Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gerenciar política de acesso externo no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4b21-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f4b21-127">**Exibindo informações de configuração de borda de acesso usando cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f4b21-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="f4b21-128">As informações de configuração de borda de acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f4b21-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="f4b21-129">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4b21-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f4b21-130">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f4b21-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="f4b21-131">Para exibir informações sobre todas as suas definições de configuração de borda de acesso, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="f4b21-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="f4b21-132">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b21-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="f4b21-133">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f4b21-133">In This Section</span></span>

  - [<span data-ttu-id="f4b21-134">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b21-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="f4b21-135">Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b21-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="f4b21-136">Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b21-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="f4b21-137">Habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b21-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="f4b21-138">Habilitar ou desabilitar o acesso de usuário anônimo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b21-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="f4b21-139">Atribuir políticas de conferência para dar suporte a usuários anônimos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b21-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

