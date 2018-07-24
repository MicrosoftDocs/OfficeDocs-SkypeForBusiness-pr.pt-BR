---
title: Configurar a integração entre o local Skype para Business Server e o Outlook Web App
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumo: Integre Skype para Business Server e o Outlook Web App.'
ms.openlocfilehash: 206100ce74731b9ffa6b2987e4884b7589f6e2c8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995845"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="9be44-103">Configurar a integração entre o local Skype para Business Server e o Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="9be44-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>
 
<span data-ttu-id="9be44-104">**Resumo:** Integre Skype para Business Server e o Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="9be44-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>
  
<span data-ttu-id="9be44-105">Clientes que utilizam o local Skype para implantações de servidor de negócios podem configurar a interoperabilidade com o Microsoft Outlook Web App no Microsoft Exchange Online em um modo de implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="9be44-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="9be44-106">Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="9be44-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="9be44-107">Para habilitar essa integração, você deverá configurar o servidor de borda na sua Skype local para implantação de servidor de negócios concluindo as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9be44-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span> 
  
- <span data-ttu-id="9be44-108">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="9be44-108">Configure a shared SIP address space</span></span>
    
- <span data-ttu-id="9be44-109">Configurar um provedor de hospedagem no servidor de borda</span><span class="sxs-lookup"><span data-stu-id="9be44-109">Configure a hosting provider on the Edge Server</span></span>
    
- <span data-ttu-id="9be44-110">Verificar a replicação do repositório de gerenciamento Central atualizado</span><span class="sxs-lookup"><span data-stu-id="9be44-110">Verify replication of the updated Central Management store</span></span>
    
## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="9be44-111">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="9be44-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="9be44-112">Para integrar o local Skype para Business Server com o Exchange Online, você deve configurar um espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="9be44-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="9be44-113">O mesmo espaço de endereço de domínio SIP é compatível com Skype para Business Server e o serviço do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9be44-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>
  
<span data-ttu-id="9be44-114">Usando o Skype do Shell de gerenciamento do servidor de negócios, configure o servidor de borda para federação executando o cmdlet **Set-CSAccessEdgeConfiguration** , usando os parâmetros exibidos no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9be44-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="9be44-115">Parâmetro **AllowFederatedUsers** Especifica se os usuários internos poderão se comunicar com usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="9be44-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="9be44-116">Essa propriedade também determina se os usuários internos podem se comunicar com usuários em um cenário de espaço de endereço SIP compartilhado com Skype para Business Server e o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9be44-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>
    
<span data-ttu-id="9be44-117">Para obter detalhes sobre como usar o Skype do Shell de gerenciamento do servidor de negócios, consulte [Skype do Shell de gerenciamento do servidor de negócios](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="9be44-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="9be44-118">Configurar um provedor de hospedagem no Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="9be44-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="9be44-119">Usando o Skype do Shell de gerenciamento do servidor de negócios, configure um provedor de hospedagem no servidor de borda executando o cmdlet **New-CsHostingProvider** , com os parâmetros do exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9be44-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="9be44-120">Se você estiver usando o Office 365 operado pela 21Vianet na China, substitua o valor do parâmetro **ProxyFqdn** neste exemplo ("exap.um.outlook.com") pelo FQDN do serviço operado pela 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="9be44-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the **ProxyFqdn** parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>
  
- <span data-ttu-id="9be44-121">**Identidade** Especifica um identificador de valor de cadeia de caracteres exclusiva para o provedor de hospedagem que você está criando (por exemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="9be44-121">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="9be44-122">Valores que contêm espaços devem estar entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="9be44-122">Values that contain spaces must be in double quotes.</span></span>
    
- <span data-ttu-id="9be44-123">**Habilitado ** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado.</span><span class="sxs-lookup"><span data-stu-id="9be44-123">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="9be44-124">Deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="9be44-124">This must be set to True.</span></span>
    
- <span data-ttu-id="9be44-125">**EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="9be44-125">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="9be44-126">Deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="9be44-126">This must be set to True.</span></span>
    
- <span data-ttu-id="9be44-127">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="9be44-127">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="9be44-128">Deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="9be44-128">This must be set to False.</span></span>
    
- <span data-ttu-id="9be44-129">**ProxyFQDN** Especifica o nome de domínio totalmente qualificado (FQDN) para o servidor proxy usado pelo provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="9be44-129">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="9be44-130">Para o Exchange Online, o FQDN é exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9be44-130">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>
    
- <span data-ttu-id="9be44-131">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido dentro de sua Skype para a topologia de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="9be44-131">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="9be44-132">Deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="9be44-132">This must be set to False.</span></span>
    
- <span data-ttu-id="9be44-133">**VerificationLevel** Indica o nível de verificação permitido para mensagens que são enviadas de e para o provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="9be44-133">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="9be44-134">Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="9be44-134">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="9be44-135">Se este nível não for especificado, a mensagem será rejeitada como sendo não-verificáveis.</span><span class="sxs-lookup"><span data-stu-id="9be44-135">If this level is not specified, the message will be rejected as being unverifiable.</span></span>
    
## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="9be44-136">Verificar a replicação do Repositório de Gerenciamento Central Atualizado</span><span class="sxs-lookup"><span data-stu-id="9be44-136">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="9be44-137">As alterações feitas usando os cmdlets nas seções anteriores são aplicadas automaticamente ao servidor de borda e geralmente levam menos de um minuto para replicar.</span><span class="sxs-lookup"><span data-stu-id="9be44-137">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="9be44-138">Você pode validar o status da replicação e, em seguida, confirme que as alterações foram aplicadas ao seu servidor de borda usando os cmdlets a seguir.</span><span class="sxs-lookup"><span data-stu-id="9be44-138">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>
  
<span data-ttu-id="9be44-139">Para verificar as atualizações de replicação, em um servidor interno à sua Skype para implantação do Business Server, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9be44-139">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>
  
```
Get-CsManagementStoreReplicationStatus
```

<span data-ttu-id="9be44-140">Para confirmar que as alterações foram aplicadas, no servidor de borda, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9be44-140">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a><span data-ttu-id="9be44-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9be44-141">See also</span></span>

[<span data-ttu-id="9be44-142">Fornecendo Skype para Business Server caixa postal aos usuários em UM do Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="9be44-142">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[<span data-ttu-id="9be44-143">Hospedado integração Exchange Unified Messaging no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="9be44-143">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)