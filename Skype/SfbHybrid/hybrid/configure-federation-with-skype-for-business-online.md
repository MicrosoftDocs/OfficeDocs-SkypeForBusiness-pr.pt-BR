---
title: Configurar o Skype for Business híbrido
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 'Resumo: saiba como configurar a interoperabilidade entre a sua implantação local e o Skype for Business online.'
ms.openlocfilehash: 59f5f752e7a6d9fa4047e736f1a988819525955e
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2019
ms.locfileid: "36160395"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="298c3-103">Configurar o Skype for Business híbrido</span><span class="sxs-lookup"><span data-stu-id="298c3-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="298c3-104">Para configurar o Skype for Business híbrido, você precisa:</span><span class="sxs-lookup"><span data-stu-id="298c3-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="298c3-105">[Configure seu serviço de ambiente local para federação com o Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="298c3-105">[Configure your on-premises environment service to federate with Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span></span>
- <span data-ttu-id="298c3-106">[Configure seu ambiente local para confiar no Office 365 e habilitar o espaço de endereçamento SIP compartilhado com o Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="298c3-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="298c3-107">[Habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).</span><span class="sxs-lookup"><span data-stu-id="298c3-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="298c3-108">Observe que, se você tiver o Exchange local, convém configurar o OAuth entre seus ambientes do Exchange local e do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="298c3-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="298c3-109">Para obter mais informações, consulte [gerenciar a autenticação de servidor para servidor no Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e [planejar a integração do Skype for Business e do Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="298c3-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="298c3-110">Configurar seu serviço de borda local para federação com o Office 365</span><span class="sxs-lookup"><span data-stu-id="298c3-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="298c3-111">A Federação permite que os usuários em sua implantação local se comuniquem com os usuários do Office 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="298c3-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="298c3-112">Para configurar a Federação, execute o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="298c3-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

<span data-ttu-id="298c3-113">Se o valor de '-EnablePartnerDiscovery ' for definido como 1, o Skype for Business Server usará os registros DNS para tentar descobrir e descobrir domínios de parceiros não listados na lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="298c3-113">If '-EnablePartnerDiscovery' value set to 1, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="298c3-114">Se o valor definido como 0, o Skype for Business Server só se federará com domínios encontrados na lista AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="298c3-114">If the value set to 0, Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="298c3-115">Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS.</span><span class="sxs-lookup"><span data-stu-id="298c3-115">This parameter is required if you use DNS service routing.</span></span>



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="298c3-116">Configurar seu ambiente local para habilitar o espaço de endereçamento SIP compartilhado com o Office 365</span><span class="sxs-lookup"><span data-stu-id="298c3-116">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="298c3-117">Você também deve configurar seu ambiente local para confiar no Office 365 e habilitar o espaço de endereçamento SIP compartilhado com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="298c3-117">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="298c3-118">Isso significa que o Office 365 pode hospedar potencialmente as contas de usuário para o mesmo conjunto de domínios SIP como seu ambiente local, e as mensagens podem ser roteadas entre os usuários hospedados no local e online.</span><span class="sxs-lookup"><span data-stu-id="298c3-118">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="298c3-119">Para fazer isso, configure um provedor de hospedagem com ProxyFqdn = sipfed. online. Lync. com, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="298c3-119">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="298c3-120">Primeiro, verifique se você já tem um provedor de hospedagem com ProxyFqdn = sipfed. online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="298c3-120">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="298c3-121">Se houver uma, remova-a usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="298c3-121">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="298c3-122">Em seguida, crie um novo provedor de hospedagem, use o cmdlet New-CsHostingProvider da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="298c3-122">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="298c3-123">Habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="298c3-123">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="298c3-124">Além da alteração feita em sua implantação local, você precisará fazer com que a alteração correspondente no locatário do Office 365 para habilitar o espaço de endereçamento SIP compartilhado com sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="298c3-124">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="298c3-125">Para habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365, estabeleça uma sessão remota do PowerShell com o Skype for Business Online e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="298c3-125">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="298c3-126">O atributo SharedSipAddressSpace precisa permanecer "true" até que a movimentação para online seja final e nenhum usuário permanecerá no local.</span><span class="sxs-lookup"><span data-stu-id="298c3-126">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="298c3-127">Para estabelecer uma sessão remota do PowerShell com o Teams ou o Skype for Business Online, primeiro você precisa instalar o módulo do conector do Skype for Business online para Windows PowerShell, que pode ser obtido [aqui](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="298c3-127">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="298c3-128">Após instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="298c3-128">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="298c3-129">Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Skype for Business Online e como usar o módulo do conector do Skype for Business Online, confira [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="298c3-129">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="298c3-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="298c3-130">See also</span></span>

[<span data-ttu-id="298c3-131">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="298c3-131">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

