---
title: 'Lync Server 2013: Tecnologias de virtualização suportadas e limitações conhecidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf513e9dee4e6a27708c8882519099c825f903f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="31c95-102">Tecnologias de virtualização suportadas e limitações conhecidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31c95-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31c95-103">_**Tópico da última modificação:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="31c95-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="31c95-104">O plug-in VDI do Lync permite chamadas de áudio e vídeo para tecnologias de virtualização compatíveis.</span><span class="sxs-lookup"><span data-stu-id="31c95-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="31c95-105">Isso estende a funcionalidade descrita para o Microsoft Lync Server 2010 no White Paper [virtualização do cliente no Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="31c95-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="31c95-106">Em conformidade com os regulamentos de telefonia padrão, o suporte para o E911 também está incluído.</span><span class="sxs-lookup"><span data-stu-id="31c95-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="31c95-107">As seções a seguir descrevem as tecnologias de virtualização que são compatíveis com o plug-in VDI do Lync e as limitações de recursos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="31c95-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="31c95-108">Suporte para Tecnologias de Virtualização</span><span class="sxs-lookup"><span data-stu-id="31c95-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="31c95-109">O plug-in VDI do Lync é compatível com o Remoting da área de trabalho virtual no cenário de área de trabalho virtual pessoal, mas não no cenário da sessão da área de trabalho remota.</span><span class="sxs-lookup"><span data-stu-id="31c95-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="31c95-110">Esses cenários podem ser descritos como segue:</span><span class="sxs-lookup"><span data-stu-id="31c95-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="31c95-111">**Com suporte: desktops virtuais ou VDI (Virtual Desktop Infrastructure) personalizados.**    Nesse cenário, cada usuário faz logon em uma área de trabalho virtual personalizável e pode salvar arquivos na área de trabalho que persistem em sessões.</span><span class="sxs-lookup"><span data-stu-id="31c95-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="31c95-112">Os serviços de área de trabalho remota da Microsoft, o modo de exibição horizonte do VMware e o Citrix XenDesktop são implementações que foram testadas para uso com o Lync.</span><span class="sxs-lookup"><span data-stu-id="31c95-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="31c95-113">Para obter informações sobre ambientes VDI específicos do fornecedor e hardware cliente que foram testados pela Microsoft, consulte [infraestrutura qualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="31c95-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="31c95-114">**Sem suporte: sessões da área de trabalho remota.**    Nesse cenário, cada usuário se conecta a uma sessão genérica da área de trabalho virtual que não pode ser personalizada.</span><span class="sxs-lookup"><span data-stu-id="31c95-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="31c95-115">Exemplos de implantações incluem Sessões de Área de Trabalho Remota da Microsoft (RDSH) e Citrix XenApp juntamente com o Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="31c95-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="31c95-116">O plug-in VDI do Lync não oferece suporte a outras tecnologias de virtualização, como a virtualização de aplicativos, que permite o uso de um aplicativo sem a necessidade de instalação do aplicativo completo localmente.</span><span class="sxs-lookup"><span data-stu-id="31c95-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="31c95-117">Exemplos de implementações incluem o Citrix XenApp e a Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="31c95-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="31c95-118">Aplicação de streaming, comunicação remota de aplicativos e modelos de virtualização mistos (por exemplo, comunicação remota de aplicativos em toda a área de trabalho remota) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="31c95-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="31c95-119">Para permitir a extensibilidade, o plug-in VDI do Lync foi projetado para usar APIs independentes de plataforma chamadas DVCs (canais virtuais dinâmicos).</span><span class="sxs-lookup"><span data-stu-id="31c95-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="31c95-120">Para cenários que não são explicitamente suportados pelo Lync, consulte declarações de suporte do provedor de soluções VDI.</span><span class="sxs-lookup"><span data-stu-id="31c95-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="31c95-121">Limitações conhecidas dos recursos</span><span class="sxs-lookup"><span data-stu-id="31c95-121">Known Feature Limitations</span></span>

<span data-ttu-id="31c95-122">Veja a seguir as limitações conhecidas quando você usa o Lync 2013 em um ambiente VDI:</span><span class="sxs-lookup"><span data-stu-id="31c95-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="31c95-123">Há suporte limitado para recursos de delegação de chamada e de anonimato do agente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="31c95-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="31c95-124">Não há suporte aos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="31c95-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="31c95-125">Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo</span><span class="sxs-lookup"><span data-stu-id="31c95-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="31c95-126">Vídeo com modo de exibição múltipla.</span><span class="sxs-lookup"><span data-stu-id="31c95-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="31c95-127">Gravação de conversas.</span><span class="sxs-lookup"><span data-stu-id="31c95-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="31c95-128">Serviços de área de trabalho remota (RDS).</span><span class="sxs-lookup"><span data-stu-id="31c95-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="31c95-129">Ingressar em reuniões anonimamente (isto é, ingressando em reuniões do Lync hospedadas por uma organização que não se federa à sua organização).</span><span class="sxs-lookup"><span data-stu-id="31c95-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="31c95-130">Usar o plug-in VDI do Lync juntamente com um dispositivo Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="31c95-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="31c95-131">Continuidade de chamadas em caso de indisponibilidade da rede.</span><span class="sxs-lookup"><span data-stu-id="31c95-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="31c95-132">Toques personalizados e recursos de música em espera.</span><span class="sxs-lookup"><span data-stu-id="31c95-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="31c95-133">O plug-in VDI do Lync não é compatível com um ambiente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="31c95-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

