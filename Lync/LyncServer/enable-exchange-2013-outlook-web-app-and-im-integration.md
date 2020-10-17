---
title: Habilitar o Exchange 2013 Outlook Web App e integração de IM
description: Habilitar o Exchange 2013 Outlook Web App e integração de IM.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551117"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="0ec9d-103">Habilitar o Exchange 2013 Outlook Web App e integração de IM</span><span class="sxs-lookup"><span data-stu-id="0ec9d-103">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ec9d-104">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0ec9d-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0ec9d-105">Para habilitar o Exchange 2013 Outlook Web Access (OWA) e a integração de mensagens instantâneas (IM) com o Lync Server 2013, você deve adicionar o servidor do Exchange 2013 servidor de acesso para cliente (CAS) à topologia 2013 do Lync Server como um servidor de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-105">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="0ec9d-106">Para criar um pool de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="0ec9d-106">To create a trusted application pool</span></span>

1.  <span data-ttu-id="0ec9d-107">Inicie o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-107">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="0ec9d-108">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0ec9d-108">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="0ec9d-109">Isso retorna siteID para o siteName no qual você está criando o pool.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-109">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="0ec9d-110">Para obter detalhes, consulte [Get-cssite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) na documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-110">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="0ec9d-111">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0ec9d-111">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="0ec9d-112">Para obter detalhes, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) na documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-112">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="0ec9d-113">O Exchange Server FQDN deve ser configurado como o certificado Exchange OWA do Nome da Entidade (SN) ou Nome Alternativo de Entidade (SAN).</span><span class="sxs-lookup"><span data-stu-id="0ec9d-113">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="0ec9d-114">No Exchange OWA, verifique se o pool do FQDN também é confiável.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-114">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0ec9d-115">Se o servidor CAS <EM>não</EM> estiver posicionado no mesmo servidor que está executando a Unificação de mensagens (um) do Exchange 2013, pule as etapas restantes deste procedimento e execute o procedimento "criar um aplicativo confiável para o servidor do Exchange 2013 CAS" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-115">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="0ec9d-116">Se o servidor CAS estiver posicionado no mesmo servidor que está executando a Unificação de mensagens (UM) do Exchange 2013, conclua as etapas deste procedimento e não execute o procedimento "criar um aplicativo confiável para o servidor do Exchange 2013 CAS" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-116">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="0ec9d-117">Execute **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-117">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="0ec9d-118">Abra o Construtor de Topologia e baixe a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-118">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="0ec9d-119">No painel à esquerda, expanda a árvore até chegar em **Servidores de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-119">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="0ec9d-120">Expanda o nó **Servidores de aplicativo confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-120">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="0ec9d-121">Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-121">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="0ec9d-122">Para criar um aplicativo confiável para o servidor CAS do Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="0ec9d-122">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="0ec9d-123">Inicie o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-123">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="0ec9d-124">Se o servidor CAS *não* estiver posicionado no mesmo servidor que está executando a Unificação de mensagens (um) do Exchange 2013, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0ec9d-124">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="0ec9d-125">Para obter detalhes, consulte o tópico [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) na documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-125">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="0ec9d-126">Execute **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-126">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="0ec9d-127">Do Construtor de Topologia, no painel à esquerda, expanda a árvore até chegar em **Servidores de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-127">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="0ec9d-128">Expanda o nó **Servidores de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-128">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="0ec9d-129">Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="0ec9d-129">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

