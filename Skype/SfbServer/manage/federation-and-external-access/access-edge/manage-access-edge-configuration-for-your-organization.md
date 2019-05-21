---
title: Gerenciar configuração da borda de acesso para sua organização
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após implantar um ou mais servidores Edge, você deve habilitar os tipos de acesso de domínio externo ou de provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos servidores de borda que terão suporte para sua organização.
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280191"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="62d1a-103">Gerenciar configuração da borda de acesso para sua organização</span><span class="sxs-lookup"><span data-stu-id="62d1a-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="62d1a-104">Após implantar um ou mais servidores Edge, você deve habilitar os tipos de acesso de domínio externo ou de provedor, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos servidores de borda que terão suporte para sua organização.</span><span class="sxs-lookup"><span data-stu-id="62d1a-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="62d1a-105">Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página de **configuração de borda de acesso** :</span><span class="sxs-lookup"><span data-stu-id="62d1a-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="62d1a-106">**Habilite a Federação e a conectividade**   de mensagens de chat pública habilite isso se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="62d1a-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="62d1a-107">Essa configuração se aplica à Federação SIP configurada para escopos global, de site ou de usuário na página **política de acesso externo** .</span><span class="sxs-lookup"><span data-stu-id="62d1a-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="62d1a-108">Para que as configurações de Federação sejam aplicadas, você deve configurar o suporte de Federação em ambas as páginas.</span><span class="sxs-lookup"><span data-stu-id="62d1a-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="62d1a-109">Há duas opções que são configurações opcionais sobre como os parceiros federados são descobertos e se o arquivamento de avisos de isenção de responsabilidade (notificação para contatos federados nos quais você se comunica com a sua implantação tem o arquivamento habilitado e se as comunicações os detalhes serão arquivados) serão enviados aos contatos:</span><span class="sxs-lookup"><span data-stu-id="62d1a-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="62d1a-110">**Habilitar descoberta**   de domínio de parceiro selecionar essa opção permite a descoberta automática de domínios com os quais você pode federar.</span><span class="sxs-lookup"><span data-stu-id="62d1a-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="62d1a-111">O Skype for Business Server usa registros de sistema de nome de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base na confiança nível, quantidade de tráfego e configurações do administrador.</span><span class="sxs-lookup"><span data-stu-id="62d1a-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="62d1a-112">Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para os usuários nos domínios que você incluir na lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="62d1a-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="62d1a-113">Independentemente de você selecionar essa opção, você pode especificar que domínios individuais sejam bloqueados ou permitidos, incluindo a restrição de acesso a servidores específicos que executam o serviço de borda de acesso no domínio federado.</span><span class="sxs-lookup"><span data-stu-id="62d1a-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="62d1a-114">Para obter detalhes, consulte [Configurar o suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="62d1a-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="62d1a-115">**Enviar isenção de isenção de responsabilidade para parceiros**   federados selecionar essa opção permite o envio de uma mensagem de isenção de isenção de responsabilidade para parceiros federados que os aconselha que os detalhes de comunicação sejam gravados.</span><span class="sxs-lookup"><span data-stu-id="62d1a-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="62d1a-116">Se você arquivar comunicações externas com domínios de parceiros federados, habilite a notificação de isenção de isenção de responsabilidade para avisar os parceiros de que suas mensagens e os detalhes de comunicação estão sendo arquivados pela sua implantação.</span><span class="sxs-lookup"><span data-stu-id="62d1a-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="62d1a-117">Para obter detalhes sobre o arquivamento, consulte [habilitar ou desabilitar o envio de uma isenção de arquivamento para parceiro federado](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="62d1a-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="62d1a-118">**Habilitar o acesso**   de usuário remoto Habilite esta opção se você quiser que os usuários de sua organização que estão fora do seu firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="62d1a-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="62d1a-119">Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuários remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="62d1a-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="62d1a-120">**Habilitar usuários anônimos para acessar conferências**   habilite essa opção se você quiser que os usuários internos convidem usuários anônimos externos para conferências que elas organizam.</span><span class="sxs-lookup"><span data-stu-id="62d1a-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="62d1a-121">Habilitar essa configuração só permite usuários anônimos para conferências.</span><span class="sxs-lookup"><span data-stu-id="62d1a-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="62d1a-122">Além de habilitar o suporte a acesso externo do usuário, você também pode configurar políticas para controlar o uso do acesso de usuários remotos em sua organização antes de qualquer tipo de acesso de usuário externo estar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="62d1a-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="62d1a-123">Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso externo a usuários, consulte [gerenciar a política de acesso externo para sua organização](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="62d1a-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="62d1a-124">**Exibindo informações de configuração de borda de acesso usando cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="62d1a-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="62d1a-125">As informações de configuração de borda de acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="62d1a-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="62d1a-126">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62d1a-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="62d1a-127">Para ver informações sobre todas as suas configurações de borda de acesso, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="62d1a-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="62d1a-128">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="62d1a-128">That will return information similar to this:</span></span>
    
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

