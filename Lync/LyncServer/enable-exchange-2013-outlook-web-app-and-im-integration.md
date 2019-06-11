---
title: Habilitar o Exchange 2013 o Outlook Web App e a integração de mensagens instantâneas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69df3f33f0671d3014e90859fd39cc2b85f9558b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="0385e-102">Habilitar o Exchange 2013 o Outlook Web App e a integração de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="0385e-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0385e-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0385e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0385e-104">Para habilitar o Exchange 2013 o Outlook Web Access (OWA) e a integração de mensagens instantâneas (IM) do Exchange com o Lync Server 2013, você deve adicionar o servidor Exchange 2013 cliente Access Server (CAS) à topologia do Lync Server 2013 como um servidor de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="0385e-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="0385e-105">Para criar um pool de aplicativos confiável</span><span class="sxs-lookup"><span data-stu-id="0385e-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="0385e-106">Inicie o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0385e-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="0385e-107">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0385e-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="0385e-108">Isso retorna o siteid para o siteName no qual você está criando o pool.</span><span class="sxs-lookup"><span data-stu-id="0385e-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="0385e-109">Para obter detalhes, consulte [Get-cssite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) na documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0385e-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="0385e-110">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0385e-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="0385e-111">Para obter detalhes, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) na documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0385e-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="0385e-112">O FQDN do servidor Exchange deve ser configurado como o nome do requerente do certificado do OWA do Exchange (SN) ou o nome alternativo do assunto (SAN).</span><span class="sxs-lookup"><span data-stu-id="0385e-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="0385e-113">Em Exchange OWA, verifique se o FQDN do pool também é confiável.</span><span class="sxs-lookup"><span data-stu-id="0385e-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0385e-114">Se o servidor CAS <EM>não</EM> estiver posicionado no mesmo servidor que está executando o Exchange 2013 Unified Messaging (um), pule as etapas restantes deste procedimento e execute o procedimento "criar um aplicativo confiável para o servidor Exchange 2013 CAS" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0385e-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="0385e-115">Se o servidor de CAS estiver posicionado no mesmo servidor que está executando o Exchange 2013 Unified Messaging (UM), conclua as etapas neste procedimento e não execute o procedimento "criar um aplicativo confiável para o servidor Exchange 2013 CAS" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0385e-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="0385e-116">Execute **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="0385e-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="0385e-117">Abra o construtor de topologias e baixe a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="0385e-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="0385e-118">No painel esquerdo, expanda a árvore até chegar a **servidores de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="0385e-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="0385e-119">Expanda o nó **servidores de aplicativos confiáveis** .</span><span class="sxs-lookup"><span data-stu-id="0385e-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="0385e-120">Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="0385e-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="0385e-121">Para criar um aplicativo confiável para o servidor CAS do Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="0385e-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="0385e-122">Inicie o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0385e-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="0385e-123">Se o servidor CAS *não* estiver posicionado no mesmo servidor que está executando o Exchange 2013 Unified Messaging (um), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0385e-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="0385e-124">Para obter detalhes, consulte o tópico [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) na documentação do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0385e-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="0385e-125">Execute **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="0385e-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="0385e-126">No construtor de topologias, no painel esquerdo, expanda a árvore até chegar a **servidores de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="0385e-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="0385e-127">Expanda o nó **servidores de aplicativos confiáveis** .</span><span class="sxs-lookup"><span data-stu-id="0385e-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="0385e-128">Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="0385e-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

