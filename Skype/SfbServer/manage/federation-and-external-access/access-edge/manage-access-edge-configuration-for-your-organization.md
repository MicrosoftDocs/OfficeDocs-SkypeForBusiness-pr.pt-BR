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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de implantar um ou mais servidores de borda, você deverá habilitar os tipos de acesso do provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo para conferências por meio dos servidores de borda que serão suportados pela sua organização.
ms.openlocfilehash: ab6f1ac28b375e5fddf9b99226770d92d8236bac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920686"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="68bda-103">Gerenciar configuração da borda de acesso para sua organização</span><span class="sxs-lookup"><span data-stu-id="68bda-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="68bda-104">Depois de implantar um ou mais servidores de borda, você deverá habilitar os tipos de acesso do provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo para conferências por meio dos servidores de borda que serão suportados pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="68bda-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="68bda-105">Essas opções incluem os seguintes tipos de acesso que podem ser configurados através da página de **Configuração de borda de acesso** :</span><span class="sxs-lookup"><span data-stu-id="68bda-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="68bda-106">**Habilita a federação e conectividade de IM pública**   habilite isso se você deseja oferecer suporte ao acesso de usuário para domínios de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="68bda-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="68bda-107">Essa configuração se aplica ao SIP federação configuradas para global, site ou escopos do usuário na página **Política de acesso externo** .</span><span class="sxs-lookup"><span data-stu-id="68bda-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="68bda-108">Para aplicar as configurações de federação, você deve configurar o suporte de Federação em ambas as páginas.</span><span class="sxs-lookup"><span data-stu-id="68bda-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="68bda-109">Existem duas opções que estão definições opcionais, como parceiros federados são descobertos e se o arquivamento de avisos de isenção (notificação para contatos federados que se comunica com que sua implantação tem arquivamento habilitado e que as comunicações detalhes serão arquivadas) serão enviadas aos contatos:</span><span class="sxs-lookup"><span data-stu-id="68bda-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="68bda-110">**Habilitar a descoberta de domínio de parceiro**   esta opção permite a descoberta automática de domínios que você pode federar.</span><span class="sxs-lookup"><span data-stu-id="68bda-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="68bda-111">Skype para Business Server usa os registros de sistema de nome de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando o tráfego de entrada de parceiros federados descobertos automaticamente e limitando ou bloqueando esse tráfego com base em relação de confiança nível, a quantidade de tráfego e as configurações do administrador.</span><span class="sxs-lookup"><span data-stu-id="68bda-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="68bda-112">Se você não selecionar essa opção, o acesso de usuário federado é habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="68bda-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="68bda-113">Se ou não você seleciona essa opção, você pode especificar esse indivíduo domínios ser bloqueada ou permitida, incluindo restringir o acesso aos servidores específicos que executem o serviço de borda de acesso no domínio federado.</span><span class="sxs-lookup"><span data-stu-id="68bda-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="68bda-114">Para obter detalhes, consulte [Configure suporte a domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="68bda-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="68bda-115">**Isenção de responsabilidade de arquivamento de envio para parceiros federados**   selecionar essa opção habilita o envio de uma mensagem de aviso de isenção de arquivamento para parceiros federados que avise-los a se os detalhes de comunicações são registradas.</span><span class="sxs-lookup"><span data-stu-id="68bda-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="68bda-116">Se você arquivar comunicações externas com domínios de parceiro federado, você deve habilitar a notificação de isenção de responsabilidade de arquivamento avisar aos parceiros que seus detalhes de mensagens e comunicações estão sendo arquivadas pela sua implantação.</span><span class="sxs-lookup"><span data-stu-id="68bda-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="68bda-117">Para obter detalhes sobre arquivamento, consulte [Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="68bda-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="68bda-118">**Habilitar o acesso de usuário remoto**   habilite essa opção se quiser que os usuários em sua organização que estão fora do firewall, como funcionários remotos e usuários que estiver viajando, possam se conectar ao Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="68bda-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="68bda-119">Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="68bda-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="68bda-120">**Permitir que usuários anônimos acessem conferências**   habilite essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências que eles organizam.</span><span class="sxs-lookup"><span data-stu-id="68bda-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="68bda-121">A habilitação dessa configuração só permite que usuários anônimos para conferências.</span><span class="sxs-lookup"><span data-stu-id="68bda-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="68bda-122">Além de habilitar o acesso de usuário externo, suporte, você também configurar políticas para controlar o uso de acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo está disponível para usuários.</span><span class="sxs-lookup"><span data-stu-id="68bda-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="68bda-123">Para obter detalhes sobre como criar, configurar e aplicar políticas de acesso de usuário externo, consulte [Gerenciar a política de acesso externo para sua organização](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="68bda-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="68bda-124">**Exibindo informações de configuração de borda de acesso usando cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="68bda-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="68bda-125">Informações de configuração de borda de acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="68bda-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="68bda-126">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68bda-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="68bda-127">Para exibir informações sobre todas as suas definições de configuração de borda de acesso, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="68bda-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="68bda-128">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="68bda-128">That will return information similar to this:</span></span>
    
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

