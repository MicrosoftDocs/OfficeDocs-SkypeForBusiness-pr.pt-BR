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
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295352"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="e705d-103">Configurar Skype para o híbrido de negócios</span><span class="sxs-lookup"><span data-stu-id="e705d-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="e705d-104">Para configurar o Skype para híbrido de negócios, você precisa:</span><span class="sxs-lookup"><span data-stu-id="e705d-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="e705d-105">Configure a federação</span><span class="sxs-lookup"><span data-stu-id="e705d-105">Configure federation</span></span>](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [<span data-ttu-id="e705d-106">Configurar um espaço de endereçamento compartilhado do protocolo de iniciação de sessão (SIP)</span><span class="sxs-lookup"><span data-stu-id="e705d-106">Configure a shared Session Initiation Protocol (SIP) address space</span></span>](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [<span data-ttu-id="e705d-107">Configurar a autenticação de servidor-para-servidor, se necessário</span><span class="sxs-lookup"><span data-stu-id="e705d-107">Configure server-to-server authentication if required</span></span>](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="e705d-108">Configurar seu serviço de borda de local para federação com Skype para Business Online</span><span class="sxs-lookup"><span data-stu-id="e705d-108">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="e705d-109">Federação permite que os usuários em sua implantação no local para se comunicar com usuários do Office 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e705d-109">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="e705d-110">Para configurar a federação, execute os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="e705d-110">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="e705d-111">Configurar seu Skype para locatário Business Online para um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="e705d-111">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="e705d-112">Um endereço de protocolo SIP (Session Initiation Protocol) é um identificador único para cada usuário em uma rede, semelhante a um número de telefone ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="e705d-112">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="e705d-113">Antes de tentar mover os usuários no local para Skype para Business Online, você precisará configurar seu locatário do Office 365 para compartilhar o espaço de endereço de protocolo de iniciação de sessão (SIP) compartilhados com sua implantação no local.</span><span class="sxs-lookup"><span data-stu-id="e705d-113">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="e705d-114">Se ele não estiver configurado, talvez você veja a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="e705d-114">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="e705d-115">Move-CsUser: Falha de HostedMigration: Error=(510), descrição = (inquilino desse usuário não está habilitado para o espaço de endereçamento sip compartilhado.)</span><span class="sxs-lookup"><span data-stu-id="e705d-115">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="e705d-116">Para configurar um espaço de endereçamento SIP compartilhado, estabeleça uma sessão PowerShell remota com Skype para Business Online e, em seguida, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e705d-116">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="e705d-117">O atributo SharedSipAddressSpace deve permanecer "True" até a mudança para online ser final e não restar usuários locais.</span><span class="sxs-lookup"><span data-stu-id="e705d-117">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="e705d-118">Para estabelecer uma sessão PowerShell remota com Skype para Business Online, você precisará primeiro instalar o Skype para o módulo de conector Business Online para o Windows PowerShell, que você pode obter [aqui](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="e705d-118">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="e705d-119">Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e705d-119">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="e705d-120">Para obter mais informações sobre como estabelecer uma sessão PowerShell remota com Skype para Business Online e como usar o Skype para módulo Business Connector Online, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e705d-120">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="configure-server-to-server-authentication-if-required"></a><span data-ttu-id="e705d-121">Configurar a autenticação de servidor-para-servidor, se necessário</span><span class="sxs-lookup"><span data-stu-id="e705d-121">Configure server-to-server authentication if required</span></span>

<span data-ttu-id="e705d-122">Dependendo do tipo de ambiente híbrido que você está configurando, você precisará configurar a autenticação de servidor-para-servidor.</span><span class="sxs-lookup"><span data-stu-id="e705d-122">Depending on the type of hybrid environment you are configuring, you may need to configure server-to-server authentication.</span></span>  <span data-ttu-id="e705d-123">Para obter mais informações, consulte [Gerenciar a autenticação de servidor-para-servidor no Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span><span class="sxs-lookup"><span data-stu-id="e705d-123">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span></span>


## <a name="see-also"></a><span data-ttu-id="e705d-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e705d-124">See also</span></span>

[<span data-ttu-id="e705d-125">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="e705d-125">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

