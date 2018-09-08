---
title: Configurar federação com o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Resumo: Saiba como configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.'
ms.openlocfilehash: 7367a1fa7bf7eb305a8b72582e488cfd6ba6fa1c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884117"
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="fff8e-103">Configurar federação com o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fff8e-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="fff8e-104">**Resumo:** Saiba como configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="fff8e-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="fff8e-105">Siga as etapas nesta seção para configurar a interoperabilidade entre sua implantação no local e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="fff8e-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="fff8e-106">Configurar seu serviço de borda de local para federação com Skype para Business Online</span><span class="sxs-lookup"><span data-stu-id="fff8e-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="fff8e-107">Federação permite que os usuários em sua implantação no local para se comunicar com usuários do Office 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fff8e-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="fff8e-108">Para configurar a federação, execute os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="fff8e-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="fff8e-109">Configurar seu Skype para locatário Business Online para um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="fff8e-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="fff8e-110">Um endereço de protocolo SIP (Session Initiation Protocol) é um identificador único para cada usuário em uma rede, semelhante a um número de telefone ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="fff8e-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="fff8e-111">Antes de tentar mover os usuários no local para Skype para Business Online, você precisará configurar seu locatário do Office 365 para compartilhar o espaço de endereço de protocolo de iniciação de sessão (SIP) compartilhados com sua implantação no local.</span><span class="sxs-lookup"><span data-stu-id="fff8e-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="fff8e-112">Se ele não estiver configurado, talvez você veja a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="fff8e-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="fff8e-113">Move-CsUser: Falha de HostedMigration: Error=(510), descrição = (inquilino desse usuário não está habilitado para o espaço de endereçamento sip compartilhado.)</span><span class="sxs-lookup"><span data-stu-id="fff8e-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="fff8e-114">Para configurar um espaço de endereçamento SIP compartilhado, estabeleça uma sessão PowerShell remota com Skype para Business Online e, em seguida, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fff8e-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="fff8e-115">O atributo SharedSipAddressSpace deve permanecer "True" até a mudança para online ser final e não restar usuários locais.</span><span class="sxs-lookup"><span data-stu-id="fff8e-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="fff8e-116">Para estabelecer uma sessão PowerShell remota com Skype para Business Online, você precisará primeiro instalar o Skype para Business Online do módulo do conector para o Windows PowerShell, que você pode obter aqui: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="fff8e-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="fff8e-117">Depois de instalar o módulo, você pode estabelecer uma sessão remota com os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fff8e-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
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

<span data-ttu-id="fff8e-118">Para obter mais informações sobre como usar o PowerShell com Skype para Business Online, consulte [Configurar o computador para o Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fff8e-118">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="fff8e-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fff8e-119">See also</span></span>

[<span data-ttu-id="fff8e-120">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="fff8e-120">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)