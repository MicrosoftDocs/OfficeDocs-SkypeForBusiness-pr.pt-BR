---
title: Gerenciar Configuração de Borda de Acesso para sua organização
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
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
description: Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que serão suportados para sua organização.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817331"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="27195-103">Gerenciar Configuração de Borda de Acesso para sua organização</span><span class="sxs-lookup"><span data-stu-id="27195-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="27195-104">Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso de provedor ou domínio externo, acesso de usuário remoto e acesso de usuário anônimo a conferências por meio dos Servidores de Borda que serão suportados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="27195-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="27195-105">Essas opções incluem os seguintes tipos de acesso que podem ser configurados por meio da página **Configuração de Borda de Acesso**:</span><span class="sxs-lookup"><span data-stu-id="27195-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="27195-106">**Habilitar federação e conectividade pública de IM**   Habilita isso se quiser dar suporte ao acesso de usuário a domínios de parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="27195-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="27195-107">Esta configuração se aplica à federação SIP configurada para escopos globais, de site ou de usuário na **página Política de Acesso** Externo.</span><span class="sxs-lookup"><span data-stu-id="27195-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="27195-108">Para aplicar as configurações de federação, é necessário configurar o suporte à federação em ambas as páginas.</span><span class="sxs-lookup"><span data-stu-id="27195-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="27195-109">Existem duas opções que são configurações opcionais de como os parceiros federados são descobertos e se os avisos de isenção de responsabilidade de arquivamento (notificação a contatos federados que você comunica com que sua implantação está habilitada e que os detalhes das comunicações serão arquivados) serão enviados aos contatos:</span><span class="sxs-lookup"><span data-stu-id="27195-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="27195-110">**Habilitar a descoberta de domínio do parceiro**   Selecionar essa opção permite a descoberta automática de domínios com os qual você pode federar.</span><span class="sxs-lookup"><span data-stu-id="27195-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="27195-111">O Skype for Business Server usa registros DNS (Sistema de Nomes de Domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, quantidade de tráfego e configurações de administrador.</span><span class="sxs-lookup"><span data-stu-id="27195-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="27195-112">Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="27195-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="27195-113">Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado.</span><span class="sxs-lookup"><span data-stu-id="27195-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="27195-114">Para obter detalhes, [consulte Configurar o suporte para domínios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="27195-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="27195-115">**Enviar aviso de isenção de responsabilidade de arquivamento a parceiros federados**   Selecionar essa opção permite o envio de uma mensagem de aviso de isenção de responsabilidade de arquivamento para parceiros federados que os avisa de que os detalhes das comunicações são registrados.</span><span class="sxs-lookup"><span data-stu-id="27195-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="27195-116">Se você arquivar comunicações externas com domínios de parceiro federados, deverá habilitar a notificação de aviso de isenção de responsabilidade de arquivamento a fim de avisar os parceiros de que suas mensagens e comunicações estão sendo arquivadas por sua implantação.</span><span class="sxs-lookup"><span data-stu-id="27195-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="27195-117">Para obter detalhes sobre arquivamento, consulte Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento [para um parceiro federado.](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="27195-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="27195-118">**Habilitar acesso de usuário remoto**   Habilita essa opção se quiser que os usuários em sua organização que estão fora do firewall, como telecomutadores e usuários que estejam viajando, sejam capazes de se conectar ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="27195-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="27195-119">Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="27195-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="27195-120">**Permitir que usuários anônimos acessem conferências**   Habilita essa opção se quiser que os usuários internos convidem usuários anônimos externos para conferências organizadas por eles.</span><span class="sxs-lookup"><span data-stu-id="27195-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="27195-121">A habilitação dessa configuração permite apenas usuários anônimos para conferências.</span><span class="sxs-lookup"><span data-stu-id="27195-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="27195-122">Além de permitir o suporte ao acesso de usuário externo, você também configura políticas para controlar o uso do acesso de usuário remoto em sua organização antes de qualquer tipo de acesso de usuário externo ficar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="27195-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="27195-123">Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte Gerenciar política de acesso [externo para sua organização.](../external-access-policies/manage-external-access-policy-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="27195-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="27195-124">**Exibindo informações de configuração de Borda de Acesso usando cmdlets do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="27195-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="27195-125">As informações de configuração da Borda de Acesso podem ser exibidas usando o Windows PowerShell e o cmdlet **Get-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="27195-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="27195-126">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27195-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="27195-127">Para exibir informações sobre todas as suas definições de configuração de Borda de Acesso, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="27195-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="27195-128">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="27195-128">That will return information similar to this:</span></span>
    
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

