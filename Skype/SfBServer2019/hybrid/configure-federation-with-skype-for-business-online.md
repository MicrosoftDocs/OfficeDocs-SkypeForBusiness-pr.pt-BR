---
title: Configurar Skype para o híbrido de negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumo: Saiba como configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.'
ms.openlocfilehash: b71ea92b5f7ce275dc5d1b5d2b7ece5be3c77ffc
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244001"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="d4d18-103">Configurar Skype para o híbrido de negócios</span><span class="sxs-lookup"><span data-stu-id="d4d18-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="d4d18-104">Para configurar o Skype para híbrido de negócios, você precisa:</span><span class="sxs-lookup"><span data-stu-id="d4d18-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="d4d18-105">Configure o ambiente local para estabelecer uma federação com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4d18-105">Configure your on-premises environment to federate with Office 365.</span></span>](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [<span data-ttu-id="d4d18-106">Configurar seu ambiente local para confiar no Office 365 e habilite o espaço de endereçamento SIP compartilhado com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4d18-106">Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span>](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [<span data-ttu-id="d4d18-107">Habilite o espaço de endereçamento SIP compartilhado no seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4d18-107">Enable shared SIP address space in your Office 365 tenant.</span></span>](#configure-server-to-server-authentication-if-required)

<span data-ttu-id="d4d18-108">Observe que se você tiver o Exchange local, convém configurar OAuth entre o Exchange local e Skype para ambientes corporativos on-line.</span><span class="sxs-lookup"><span data-stu-id="d4d18-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="d4d18-109">Para obter mais informações, consulte [Gerenciar a autenticação de servidor-para-servidor no Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e [Planejar a integração do Skype para Exchange e de negócios](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="d4d18-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="d4d18-110">Configurar seu serviço de borda de local para estabelecer uma federação com o Office 365</span><span class="sxs-lookup"><span data-stu-id="d4d18-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="d4d18-111">Federação permite que os usuários em sua implantação no local para se comunicar com usuários do Office 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d4d18-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="d4d18-112">Para configurar a federação, execute o seguinte cmdlet no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="d4d18-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="d4d18-113">Configurar seu ambiente local para habilitar o espaço de endereçamento SIP compartilhado com o Office 365</span><span class="sxs-lookup"><span data-stu-id="d4d18-113">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="d4d18-114">Você também deve configurar seu ambiente local para confiar no Office 365 e habilitar o espaço de endereçamento SIP compartilhado com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4d18-114">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="d4d18-115">Isso significa o Office 365 podem hospedar contas de usuário para o mesmo conjunto de domínios SIP que seu ambiente local e as mensagens podem ser roteados entre usuários hospedados no local e online.</span><span class="sxs-lookup"><span data-stu-id="d4d18-115">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="d4d18-116">Para fazer isso, configurando um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="d4d18-116">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="d4d18-117">Primeiro, verifique se você já tiver um provedor de hospedagem com ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d4d18-117">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="d4d18-118">Se houver, removê-lo usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d4d18-118">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="d4d18-119">Em seguida, crie um novo provedor de hospedagem, use o cmdlet New-CsHostingProvider da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d4d18-119">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="d4d18-120">Habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="d4d18-120">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="d4d18-121">Além da alteração feita na sua implantação no local, você precisará faça a alteração correspondente no seu locatário do Office 365 habilitado espaço de endereçamento SIP compartilhado com sua implantação no local.</span><span class="sxs-lookup"><span data-stu-id="d4d18-121">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="d4d18-122">Para habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365, estabeleça uma sessão PowerShell remota com Skype para Business Online e, em seguida, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d4d18-122">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="d4d18-123">O atributo SharedSipAddressSpace deve permanecer "True" até a mudança para online ser final e não restar usuários locais.</span><span class="sxs-lookup"><span data-stu-id="d4d18-123">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="d4d18-124">Para estabelecer uma sessão PowerShell remota com equipes ou Skype para Business Online, você precisará primeiro instalar o Skype para o módulo de conector Business Online para o Windows PowerShell, que você pode obter [aqui](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="d4d18-124">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="d4d18-125">Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d4d18-125">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="d4d18-126">Para obter mais informações sobre como estabelecer uma sessão PowerShell remota com Skype para Business Online e como usar o Skype para módulo Business Connector Online, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4d18-126">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="d4d18-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d4d18-127">See also</span></span>

[<span data-ttu-id="d4d18-128">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="d4d18-128">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

