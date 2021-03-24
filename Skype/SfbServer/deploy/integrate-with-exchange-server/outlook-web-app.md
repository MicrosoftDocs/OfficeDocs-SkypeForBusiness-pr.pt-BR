---
title: Configurar a integração entre o Skype for Business Server local e o Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: Integrar o Skype for Business Server e o Outlook Web App.'
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109687"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="87575-103">Configurar a integração entre o Skype for Business Server local e o Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="87575-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="87575-104">**Resumo:** Integre o Skype for Business Server e o Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="87575-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="87575-105">Os clientes que estão usando implantações locais do Skype for Business Server podem configurar a interoperabilidade com o Microsoft Outlook Web App Microsoft Exchange Online em um modo de implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="87575-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="87575-106">Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="87575-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="87575-107">Para habilitar essa integração, você deve configurar o Servidor de Borda em sua implantação local do Skype for Business Server concluindo as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="87575-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="87575-108">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="87575-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="87575-109">Configurar um provedor de hospedagem no Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="87575-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="87575-110">Verificar a replicação do armazenamento de Gerenciamento Central atualizado</span><span class="sxs-lookup"><span data-stu-id="87575-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="87575-111">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="87575-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="87575-112">Para integrar o Skype for Business Server local com o Exchange Online, você deve configurar um espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="87575-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="87575-113">O mesmo espaço de endereço de domínio SIP é suportado pelo Skype for Business Server e pelo serviço Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="87575-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="87575-114">Usando o Shell de Gerenciamento do Skype for Business Server, configure o Servidor de Borda para federação executando o cmdlet **Set-CSAccessEdgeConfiguration,** usando os parâmetros exibidos no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="87575-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="87575-115">O parâmetro **AllowFederatedUsers** especifica se usuários internos têm permissão para se comunicar com usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="87575-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="87575-116">Essa propriedade também determina se os usuários internos podem se comunicar com os usuários em um cenário de espaço de endereço SIP compartilhado com o Skype for Business Server e o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="87575-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="87575-117">Para obter detalhes sobre como usar o Shell de Gerenciamento do Skype for Business Server, consulte [Skype for Business Server Management Shell](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="87575-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="87575-118">Configurar um provedor de hospedagem no Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="87575-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="87575-119">Usando o Shell de Gerenciamento do Skype for Business Server, configure um provedor de hospedagem no Servidor de Borda executando o cmdlet **New-CsHostingProvider,** usando os parâmetros no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="87575-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="87575-120">Se você estiver usando o Microsoft 365 ou o Office 365 operado pela 21Vianet na China, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para o serviço operado pela 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="87575-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="87575-121">Se você estiver usando o Microsoft 365 ou o Office 365 GCC High, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para GCC High: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="87575-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="87575-122">**Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando (por exemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="87575-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="87575-123">Valores que contêm espaços devem estar entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="87575-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="87575-124">**Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado.</span><span class="sxs-lookup"><span data-stu-id="87575-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="87575-125">Deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="87575-125">This must be set to True.</span></span>

- <span data-ttu-id="87575-126">**EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="87575-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="87575-127">Deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="87575-127">This must be set to True.</span></span>

- <span data-ttu-id="87575-128">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="87575-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="87575-129">Deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="87575-129">This must be set to False.</span></span>

- <span data-ttu-id="87575-130">**ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="87575-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="87575-131">Para o Exchange Online, o FQDN é exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="87575-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="87575-132">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido na topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="87575-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="87575-133">Deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="87575-133">This must be set to False.</span></span>

- <span data-ttu-id="87575-134">**VerificationLevel** Indica o nível de verificação permitido para mensagens enviadas de e para o provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="87575-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="87575-135">Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="87575-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="87575-136">Se esse nível não for especificado, a mensagem será rejeitada como não verificável.</span><span class="sxs-lookup"><span data-stu-id="87575-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="87575-137">Verificar a replicação do Repositório de Gerenciamento Central Atualizado</span><span class="sxs-lookup"><span data-stu-id="87575-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="87575-138">As alterações feitas usando os cmdlets nas seções anteriores são aplicadas automaticamente ao Servidor de Borda e geralmente levam menos de um minuto para replicar.</span><span class="sxs-lookup"><span data-stu-id="87575-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="87575-139">Você pode validar o status da replicação e confirmar se as alterações foram aplicadas ao Servidor de Borda usando os cmdlets a seguir.</span><span class="sxs-lookup"><span data-stu-id="87575-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="87575-140">Para verificar as atualizações de replicação, em um servidor interno em sua implantação do Skype for Business Server, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="87575-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="87575-141">Verifique se o valor UpToDate está mostrando TRUE para todas as réplicas.</span><span class="sxs-lookup"><span data-stu-id="87575-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="87575-142">Para confirmar se as alterações foram aplicadas, no Servidor de Borda, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="87575-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="87575-143">Verifique duas vezes se as informações mostradas coincidem com as alterações comprometidas nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="87575-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="87575-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="87575-144">See also</span></span>

[<span data-ttu-id="87575-145">Fornecendo caixa postal para usuários do Skype for Business Server na UM do Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="87575-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[<span data-ttu-id="87575-146">Integração de Unificação de Mensagens do Exchange hospedada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="87575-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)