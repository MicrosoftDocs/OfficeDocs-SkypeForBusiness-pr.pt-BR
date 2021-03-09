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
description: 'Resumo: saiba como configurar a interoperabilidade entre sua implantação local e o Skype for Business Online.'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569213"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="c65c1-103">Configure o Skype for Business híbrido</span><span class="sxs-lookup"><span data-stu-id="c65c1-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="c65c1-104">Para configurar o Skype for Business híbrido, você precisa:</span><span class="sxs-lookup"><span data-stu-id="c65c1-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="c65c1-105">Configure seu serviço de Borda local para federar com [o Microsoft 365 ou o Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span><span class="sxs-lookup"><span data-stu-id="c65c1-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="c65c1-106">Configure seu ambiente local para confiar [no Microsoft 365 ou Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)e habilitar o espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c65c1-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="c65c1-107">[Habilitar o espaço de endereço SIP compartilhado em sua organização do Microsoft 365 ou Office 365.](#enable-shared-sip-address-space-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c65c1-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="c65c1-108">Observe que, se você tiver o Exchange local, talvez queira configurar o OAuth entre seus ambientes locais do Exchange e do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="c65c1-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="c65c1-109">Para obter mais informações, consulte  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and Plan to integrate Skype for Business and [Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="c65c1-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="c65c1-110">Configurar seu serviço de Borda local para federar com o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="c65c1-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="c65c1-111">A federação permite que os usuários em sua implantação local se comuniquem com usuários do Microsoft 365 ou Office 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c65c1-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="c65c1-112">Para configurar a federação, execute o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c65c1-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="c65c1-113">Se o valor '-EnablePartnerDiscovery' estiver definido como $True, o Skype for Business Server usará registros DNS para tentar descobrir domínios de parceiros não listados na lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="c65c1-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="c65c1-114">Se o valor for definido como $False, o Skype for Business Server só se federará com domínios encontrados na lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="c65c1-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="c65c1-115">Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS.</span><span class="sxs-lookup"><span data-stu-id="c65c1-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="c65c1-116">Para obter mais detalhes sobre como habilizar a federação entre usuários da implantação local do Skype for Business e usuários de uma organização do Skype for Business Online, consulte [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span><span class="sxs-lookup"><span data-stu-id="c65c1-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="c65c1-117">Configure seu ambiente local para habilitar o espaço de endereço SIP compartilhado com o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="c65c1-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="c65c1-118">Você também deve configurar seu ambiente local para confiar no Microsoft 365 ou Office 365 e habilitar o espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c65c1-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="c65c1-119">Isso significa que o Microsoft 365 ou o Office 365 podem potencialmente hospedar contas de usuário para o mesmo conjunto de domínios SIP do seu ambiente local, e as mensagens podem ser roteadas entre usuários hospedados no local e online.</span><span class="sxs-lookup"><span data-stu-id="c65c1-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="c65c1-120">Você faz isso configurando um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="c65c1-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="c65c1-121">Primeiro, verifique se você já tem um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c65c1-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="c65c1-122">Se houver um, remova-o usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c65c1-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="c65c1-123">Em seguida, crie um novo provedor de hospedagem, use o cmdlet New-CsHostingProvider da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c65c1-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="c65c1-124">Habilitar o espaço de endereço SIP compartilhado em sua organização</span><span class="sxs-lookup"><span data-stu-id="c65c1-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="c65c1-125">Além da alteração feita em sua implantação local, você precisará fazer a alteração correspondente em sua organização do Microsoft 365 ou office 365 para habilitar o espaço de endereço SIP compartilhado com sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="c65c1-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="c65c1-126">Para habilitar o espaço de endereço SIP compartilhado em sua organização, estabeleça uma sessão remota do PowerShell com o Skype for Business Online e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c65c1-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="c65c1-127">O atributo SharedSipAddressSpace precisa permanecer "True" até que a mudança para online seja final e nenhum usuário permaneça no local.</span><span class="sxs-lookup"><span data-stu-id="c65c1-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="c65c1-128">Para estabelecer uma sessão remota do PowerShell com o Teams ou o Skype for Business Online, primeiro você precisa instalar o [módulo do Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="c65c1-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
  
<span data-ttu-id="c65c1-129">Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c65c1-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="c65c1-130">Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Skype for Business Online e como usar o módulo conector do Skype for Business Online, consulte [Configurar](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)seu computador para Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="c65c1-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="c65c1-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="c65c1-131">See also</span></span>

[<span data-ttu-id="c65c1-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c65c1-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
