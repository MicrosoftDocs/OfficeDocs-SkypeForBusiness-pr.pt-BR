---
title: Configurando a integração do Lync Server no local com o Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60cfa8caa0aa2cb7dac704123f2a099bd305aed5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="dffc4-102">Configurando a integração do Lync Server 2013 local com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dffc4-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dffc4-103">_**Última modificação do tópico:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="dffc4-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="dffc4-104">Os clientes que usam implantações locais do Lync Server 2013 podem configurar a interoperabilidade com o Microsoft Outlook Web App no Microsoft Exchange Online em um modo de implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="dffc4-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="dffc4-105">Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="dffc4-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="dffc4-106">Para habilitar essa integração, você deve configurar o servidor de borda em sua implantação local do Lync Server, realizando as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="dffc4-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="dffc4-107">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="dffc4-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="dffc4-108">Configurar um provedor de hospedagem no servidor de borda</span><span class="sxs-lookup"><span data-stu-id="dffc4-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="dffc4-109">Verificar a replicação do repositório de gerenciamento central atualizado</span><span class="sxs-lookup"><span data-stu-id="dffc4-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="dffc4-110">Se o Lync Server 2013 estiver integrado ao Exchange Online, um usuário que está tentando entrar no IM do OWA será considerado um usuário remoto ou externo.</span><span class="sxs-lookup"><span data-stu-id="dffc4-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="dffc4-111">Neste cenário, esse usuário deve ter uma política de acesso externo atribuída que tenha a opção a seguir selecionada:</span><span class="sxs-lookup"><span data-stu-id="dffc4-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="dffc4-112">**Permitir comunicações com usuários remotos**</span><span class="sxs-lookup"><span data-stu-id="dffc4-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="dffc4-113">Habilite essa opção se quiser que os usuários em sua organização que estejam fora do firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server pela Internet.</span><span class="sxs-lookup"><span data-stu-id="dffc4-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="dffc4-114">Para obter mais informações, consulte [gerenciar política de acesso externo no Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="dffc4-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="dffc4-115">Configurar um espaço de endereçamento SIP compartilhado</span><span class="sxs-lookup"><span data-stu-id="dffc4-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="dffc4-116">Para integrar o Lync Server 2013 local com o Exchange Online, você deve configurar um espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="dffc4-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="dffc4-117">O mesmo espaço de endereço de domínio SIP é compatível com o Lync Server e o serviço do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dffc4-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="dffc4-118">Usando o Shell de gerenciamento do Lync Server, configure o servidor de borda para Federação executando o cmdlet **set-CSAccessEdgeConfiguration** , usando os parâmetros exibidos no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="dffc4-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="dffc4-119">**AllowFederatedUsers** especifica se os usuários internos têm permissão para se comunicar com usuários de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="dffc4-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="dffc4-120">Essa propriedade também determina se os usuários internos podem se comunicar com usuários em um cenário de espaço de endereçamento SIP compartilhado com o Lync Server e o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dffc4-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="dffc4-121">Para obter detalhes sobre como usar o Shell de gerenciamento do Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="dffc4-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="dffc4-122">Configurar um provedor de hospedagem no Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="dffc4-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="dffc4-123">Use o Shell de gerenciamento do Lync Server para configurar um provedor de hospedagem no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="dffc4-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="dffc4-124">Para fazer isso, execute o cmdlet **New-CsHostingProvider** usando os parâmetros no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="dffc4-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="dffc4-125">Se você estiver usando o Office 365 operado pela 21Vianet na China, substitua o valor para o parâmetro <STRONG>ProxyFqdn</STRONG> neste exemplo ("exap.um.Outlook.com") com o FQDN para o serviço operado pela 21vianet: "exap.um.Partner.Outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="dffc4-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="dffc4-126">**Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando (por exemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="dffc4-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="dffc4-127">Os valores que contêm espaços devem estar entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="dffc4-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="dffc4-128">**Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado.</span><span class="sxs-lookup"><span data-stu-id="dffc4-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="dffc4-129">Isso deve ser definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="dffc4-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="dffc4-130">**EnabledSharedAddressSpace**indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="dffc4-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="dffc4-131">Isso deve ser definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="dffc4-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="dffc4-132">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dffc4-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="dffc4-133">Isso deve ser definido como **false**.</span><span class="sxs-lookup"><span data-stu-id="dffc4-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="dffc4-134">**ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="dffc4-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="dffc4-135">Para o Exchange Online, o FQDN é exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="dffc4-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="dffc4-136">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dffc4-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="dffc4-137">Isso deve ser definido como **false**.</span><span class="sxs-lookup"><span data-stu-id="dffc4-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="dffc4-138">**VerificationLevel** indica o nível de verificação permitido para mensagens enviadas de e para o provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="dffc4-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="dffc4-139">Especifique **UseSourceVerification**.</span><span class="sxs-lookup"><span data-stu-id="dffc4-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="dffc4-140">Essa opção depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="dffc4-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="dffc4-141">Se esse nível não for especificado, a mensagem será rejeitada como não verificável.</span><span class="sxs-lookup"><span data-stu-id="dffc4-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="dffc4-142">Verificar a replicação do Repositório de Gerenciamento Central Atualizado</span><span class="sxs-lookup"><span data-stu-id="dffc4-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="dffc4-143">As alterações feitas usando os cmdlets nas seções anteriores são automaticamente aplicadas ao servidor de borda e geralmente levam menos de um minuto para serem replicadas.</span><span class="sxs-lookup"><span data-stu-id="dffc4-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="dffc4-144">Você pode verificar o status de replicação e se as alterações foram aplicadas ao servidor de borda usando os cmdlets a seguir.</span><span class="sxs-lookup"><span data-stu-id="dffc4-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="dffc4-145">Para verificar as atualizações de replicação em um servidor interno na sua implantação do Lync Server, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dffc4-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="dffc4-146">Para verificar se as alterações foram aplicadas, execute o seguinte cmdlet no servidor de borda:</span><span class="sxs-lookup"><span data-stu-id="dffc4-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dffc4-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="dffc4-147">See Also</span></span>


[<span data-ttu-id="dffc4-148">Fornecimento de mensagens de voz para usuários do Lync Server 2013 no Exchange UM hospedado</span><span class="sxs-lookup"><span data-stu-id="dffc4-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="dffc4-149">Integração de Unificação de mensagens do Exchange hospedada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dffc4-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
