---
title: Configure o Skype for Business híbrido
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: saiba como configurar a interoperabilidade entre sua implantação local e Teams.'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305965"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="3f767-103">Configure o Skype for Business híbrido</span><span class="sxs-lookup"><span data-stu-id="3f767-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="3f767-104">Para configurar o Skype for Business híbrido, você precisa:</span><span class="sxs-lookup"><span data-stu-id="3f767-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="3f767-105">[Configure seu serviço de Borda local para federar com](#configure-your-on-premises-edge-service-to-federate-with-teams)Teams .</span><span class="sxs-lookup"><span data-stu-id="3f767-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="3f767-106">[Configure seu ambiente local para confiar Teams e habilitar o espaço de endereço SIP compartilhado.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)</span><span class="sxs-lookup"><span data-stu-id="3f767-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="3f767-107">[Habilitar o espaço de endereço SIP compartilhado em sua Teams organização](#enable-shared-sip-address-space-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="3f767-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="3f767-108">Se você tiver Exchange local, talvez queira configurar o OAuth entre seus ambientes Exchange local e Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3f767-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="3f767-109">Para obter mais informações, consulte [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and Plan to integrate Skype for Business and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="3f767-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="3f767-110">Configure seu serviço de Borda local para federar com Teams</span><span class="sxs-lookup"><span data-stu-id="3f767-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="3f767-111">A federação permite que os usuários em sua implantação local se comuniquem com Teams e Skype for Business online em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3f767-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="3f767-112">Para configurar a federação, execute o seguinte cmdlet no Shell Skype for Business Server Gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="3f767-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="3f767-113">Se o valor '-EnablePartnerDiscovery' estiver definido como $True, o Skype for Business Server usará registros DNS para tentar descobrir domínios de parceiros não listados na lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="3f767-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="3f767-114">Se o valor for definido como $False , Skype for Business Server federará apenas com domínios encontrados na lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="3f767-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="3f767-115">Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS.</span><span class="sxs-lookup"><span data-stu-id="3f767-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="3f767-116">Para obter mais detalhes sobre a habilitação da federação entre usuários de sua implantação Skype for Business local e usuários de uma organização Microsoft 365, consulte [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span><span class="sxs-lookup"><span data-stu-id="3f767-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="3f767-117">Configure seu ambiente local para habilitar o espaço de endereço SIP compartilhado com Teams</span><span class="sxs-lookup"><span data-stu-id="3f767-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="3f767-118">Você também deve configurar seu ambiente local para confiar Teams e habilitar o espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="3f767-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="3f767-119">Essa configuração significa Teams pode hospedar contas de usuário para o mesmo conjunto de domínios SIP do seu ambiente local, e as mensagens podem ser roteadas entre usuários hospedados no local e online.</span><span class="sxs-lookup"><span data-stu-id="3f767-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="3f767-120">Você configura um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f767-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="3f767-121">Primeiro, verifique se você já tem um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3f767-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="3f767-122">Se existir um, remova-o usando o seguinte comando no Shell de Gerenciamento Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="3f767-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="3f767-123">Em seguida, crie um novo provedor de hospedagem usando o cmdlet New-CsHostingProvider da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="3f767-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="3f767-124">Habilitar o espaço de endereço SIP compartilhado em sua organização</span><span class="sxs-lookup"><span data-stu-id="3f767-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="3f767-125">Além da alteração feita em sua implantação local, você precisará fazer a alteração correspondente em sua organização Teams para habilitar o espaço de endereço SIP compartilhado com sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="3f767-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="3f767-126">Para habilitar o espaço de endereço SIP compartilhado em sua organização, estabeleça uma sessão remota do PowerShell com Teams e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3f767-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="3f767-127">O atributo SharedSipAddressSpace precisa permanecer "True" até que a mudança para online seja final e nenhum usuário permaneça no local.</span><span class="sxs-lookup"><span data-stu-id="3f767-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="3f767-128">Para estabelecer uma sessão remota do PowerShell com Teams (ou Skype for Business Online), primeiro você precisa instalar o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="3f767-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="3f767-129">O Teams powershell substitui o Skype para o módulo conector busines online, que foi retirado.</span><span class="sxs-lookup"><span data-stu-id="3f767-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="3f767-130">Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3f767-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="3f767-131">Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Teams e como usar o módulo Teams PowerShell, consulte [Configurar](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)seu computador para Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="3f767-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="3f767-132">Também consulte</span><span class="sxs-lookup"><span data-stu-id="3f767-132">See also</span></span>

[<span data-ttu-id="3f767-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="3f767-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
