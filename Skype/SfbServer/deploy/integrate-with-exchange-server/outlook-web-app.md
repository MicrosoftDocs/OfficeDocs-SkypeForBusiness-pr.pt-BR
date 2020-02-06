---
title: Configurar a integração entre o Skype for Business Server local e o Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumo: integre o Skype for Business Server e o Outlook Web App.'
ms.openlocfilehash: 2496cc7c2f357c4e1afa73dea18f304c6a7f9607
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797032"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="c70c8-103">Configurar a integração entre o Skype for Business Server local e o Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="c70c8-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="c70c8-104">**Resumo:** Integre o Skype for Business Server e o Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="c70c8-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="c70c8-105">Os clientes que usam implantações locais do Skype for Business Server podem configurar a interoperabilidade com o Microsoft Outlook Web App no Microsoft Exchange Online em um modo de implantação híbrido.</span><span class="sxs-lookup"><span data-stu-id="c70c8-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="c70c8-106">Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="c70c8-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="c70c8-107">Para habilitar essa integração, você deve configurar o servidor de borda na implantação do Skype for Business Server no local completando as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="c70c8-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="c70c8-108">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="c70c8-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="c70c8-109">Configurar um provedor de hospedagem no servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c70c8-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="c70c8-110">Verificar a replicação do repositório de gerenciamento central atualizado</span><span class="sxs-lookup"><span data-stu-id="c70c8-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="c70c8-111">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="c70c8-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="c70c8-112">Para integrar o Skype for Business Server local com o Exchange Online, você deve configurar um espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c70c8-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="c70c8-113">O mesmo espaço de endereço de domínio SIP é compatível com o Skype for Business Server e com o serviço do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c70c8-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="c70c8-114">Usando o Shell de gerenciamento do Skype for Business Server, configure o servidor de borda para Federação executando o cmdlet **set-CSAccessEdgeConfiguration** usando os parâmetros exibidos no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="c70c8-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="c70c8-115">O parâmetro **AllowFederatedUsers** especifica se usuários internos têm permissão para se comunicar com usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="c70c8-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="c70c8-116">Essa propriedade também determina se os usuários internos podem se comunicar com usuários em um cenário de espaço de endereço SIP compartilhado com o Skype for Business Server e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c70c8-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="c70c8-117">Para obter detalhes sobre como usar o Shell de gerenciamento do Skype for Business Server, consulte [Shell de gerenciamento do Skype for Business Server](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="c70c8-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="c70c8-118">Configurar um provedor de hospedagem no Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="c70c8-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="c70c8-119">Usando o Shell de gerenciamento do Skype for Business Server, configure um provedor de hospedagem no servidor de borda executando o cmdlet **New-CsHostingProvider** usando os parâmetros no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c70c8-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="c70c8-120">Se você estiver usando o Office 365 operado pela 21Vianet na China, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN do serviço operado pela 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="c70c8-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="c70c8-121">Se você estiver usando o Office 365 GCC High, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para GCC High: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="c70c8-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="c70c8-122">**Identity** especifica um identificador de valor de cadeia de caracteres único para o provedor de hospedagem que está sendo criado (por exemplo "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="c70c8-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="c70c8-123">Valores que contêm espaços devem estar entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="c70c8-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="c70c8-124">\*\*Habilitado \*\* indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c70c8-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="c70c8-125">Deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="c70c8-125">This must be set to True.</span></span>

- <span data-ttu-id="c70c8-126">**EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c70c8-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="c70c8-127">Deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="c70c8-127">This must be set to True.</span></span>

- <span data-ttu-id="c70c8-128">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c70c8-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="c70c8-129">Deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="c70c8-129">This must be set to False.</span></span>

- <span data-ttu-id="c70c8-130">**ProxyFQDN** especifica o nome de domínio totalmente qualificado (FQDN) para o servidor de proxy usado pelo provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="c70c8-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="c70c8-131">Para o Exchange Online, o FQDN é exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c70c8-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="c70c8-132">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido na topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c70c8-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="c70c8-133">Deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="c70c8-133">This must be set to False.</span></span>

- <span data-ttu-id="c70c8-134">**VerificationLevel** Indica o nível de verificação permitido para mensagens enviadas de e para o provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="c70c8-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="c70c8-135">Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="c70c8-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="c70c8-136">Se esse nível não for especificado, a mensagem será rejeitada como não verificável.</span><span class="sxs-lookup"><span data-stu-id="c70c8-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="c70c8-137">Verificar a replicação do Repositório de Gerenciamento Central Atualizado</span><span class="sxs-lookup"><span data-stu-id="c70c8-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="c70c8-138">As alterações feitas usando cmdlets nas seções anteriores são automaticamente aplicadas ao servidor de borda e geralmente levam menos de um minuto para serem duplicadas.</span><span class="sxs-lookup"><span data-stu-id="c70c8-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="c70c8-139">Você pode validar o status da replicação e, em seguida, confirmar que as alterações foram aplicadas ao seu servidor de borda usando os cmdlets a seguir.</span><span class="sxs-lookup"><span data-stu-id="c70c8-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="c70c8-140">Para verificar as atualizações de replicação, em um servidor interno na implantação do Skype for Business Server, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c70c8-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="c70c8-141">Verifique se o valor UpToDate está sendo exibido como verdadeiro para todas as réplicas.</span><span class="sxs-lookup"><span data-stu-id="c70c8-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="c70c8-142">Para confirmar se as alterações foram aplicadas, no servidor de borda, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c70c8-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="c70c8-143">Verifique se as informações mostradas correspondem às alterações confirmadas nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="c70c8-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="c70c8-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="c70c8-144">See also</span></span>

[<span data-ttu-id="c70c8-145">Fornecer aos usuários do Skype for Business Server o correio de voz no Exchange UM hospedado</span><span class="sxs-lookup"><span data-stu-id="c70c8-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="c70c8-146">Integração de Unificação de mensagens do Exchange hospedada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c70c8-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
