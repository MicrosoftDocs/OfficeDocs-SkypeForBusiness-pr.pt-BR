---
title: 'Lync Server 2013: configurar o suporte de Federação para um domínio do Lync Online'
description: 'Lync Server 2013: configurar o suporte de Federação para um domínio do Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553297"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="7fe32-103">Configurar o suporte de Federação para um domínio do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fe32-103">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe32-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7fe32-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7fe32-105">A Federação com um cliente do Microsoft Lync Online 2010 requer que você conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7fe32-105">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="7fe32-106">Configure o suporte para o domínio do cliente do Lync Online 2010 (por exemplo, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="7fe32-106">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="7fe32-107">Conforme especificado na seção [pré-requisitos para federação com um cliente do Lync Online no Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) desta documentação, você já deve ter habilitado a Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="7fe32-107">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="7fe32-108">A habilitação da federação exige a especificação do método a ser usado para controlar o acesso dos domínios federados.</span><span class="sxs-lookup"><span data-stu-id="7fe32-108">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="7fe32-109">Caso tenha configurado sua organização para usar a descoberta, a inclusão do domínio na sua lista de organizações permitidas é opcional.</span><span class="sxs-lookup"><span data-stu-id="7fe32-109">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="7fe32-110">Se você não habilitou a descoberta de domínios, deverá adicionar o nome de domínio do cliente do Lync Online à sua lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="7fe32-110">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="7fe32-111">Você pode adicionar um nome de domínio usando o painel de controle do Lync Server ou executando o cmdlet **New-CSAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="7fe32-111">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="7fe32-112">Para obter detalhes sobre como usar o painel de controle do Lync Server, incluindo a habilitação da descoberta de domínios, consulte [Manage SIP Federated Providers for Your Organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="7fe32-112">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="7fe32-113">Para obter detalhes sobre como usar o cmdlet **New-CSAllowedDomain** para adicionar um domínio, consulte [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="7fe32-113">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7fe32-114">Um cliente do Lync Online pode ter vários domínios.</span><span class="sxs-lookup"><span data-stu-id="7fe32-114">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="7fe32-115">Se quiser federar-se com mais de um dos domínios, você deve configurar o suporte para cada domínio individual com o qual você deseja dar suporte à Federação e o administrador do cliente do Lync Online deve habilitar a Federação para cada um dos domínios a serem federados.</span><span class="sxs-lookup"><span data-stu-id="7fe32-115">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="7fe32-116">Configure o suporte para o provedor de hospedagem do domínio do cliente do Lync Online 2010 com o qual você deseja federar.</span><span class="sxs-lookup"><span data-stu-id="7fe32-116">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="7fe32-117">Use os procedimentos desta seção para configurar o suporte ao provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="7fe32-117">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7fe32-118">Esta etapa é necessária somente para federação com um domínio de um cliente do Lync Online, não para federação com qualquer domínio implantado no local em um local de parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="7fe32-118">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="7fe32-119">Configurar o suporte para um provedor de hospedagem</span><span class="sxs-lookup"><span data-stu-id="7fe32-119">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="7fe32-120">Em um servidor front-end, inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7fe32-120">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7fe32-121">Execute o cmdlet **New-CsHostingProvider** para criar e configurar um provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="7fe32-121">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="7fe32-122">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="7fe32-122">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="7fe32-123">O exemplo anterior define os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="7fe32-123">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="7fe32-p105">**Identidade** especifica um identificador de valor exclusivo de cadeia de caracteres para o provedor de hospedagem que você está criando. Observe que o comando não funcionará casa haja um provedor existente já configurado com aquela Identity.</span><span class="sxs-lookup"><span data-stu-id="7fe32-p105">**Identity** specifies a unique string value identifier for the hosting provider that you are creating. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="7fe32-p106">**ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem. Este valor não pode ser modificado. Se o provedor de hospedagem alterar seu servidor proxy, será necessário que você exclua e recrie a entrada para aquele provedor.</span><span class="sxs-lookup"><span data-stu-id="7fe32-p106">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="7fe32-129">**VerificationLevel** especifica como (ou se) as mensagens enviadas de um provedor de hospedagem são verificados para garantir que sejam enviados a partir daquele provedor.</span><span class="sxs-lookup"><span data-stu-id="7fe32-129">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="7fe32-p107">**Enabled** indica se a conexão de rede entre o seu domínio e o provedor de hospedagem está ativada. As mensagens não podem ser trocadas entre as duas organizações até que este valor seja definido como **True**.</span><span class="sxs-lookup"><span data-stu-id="7fe32-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="7fe32-132">**EnabledSharedAddressSpace** indica se o provedor de hospedagem está sendo usado em um cenário de espaço de endereço SIP compartilhado (domínio dividido).</span><span class="sxs-lookup"><span data-stu-id="7fe32-132">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="7fe32-133">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar as contas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fe32-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="7fe32-134">Se estiver definido como **Falso**, o provedor hospedará outros tipos de conta, como contas do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="7fe32-134">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="7fe32-135">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fe32-135">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="7fe32-136">Para obter detalhes sobre como usar esse cmdlet, consulte [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="7fe32-136">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

