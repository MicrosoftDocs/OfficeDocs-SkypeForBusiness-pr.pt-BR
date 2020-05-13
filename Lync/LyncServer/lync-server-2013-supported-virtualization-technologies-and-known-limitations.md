---
title: 'Lync Server 2013: tecnologias de virtualização suportadas e limitações conhecidas'
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
ms.openlocfilehash: 0968f79b8c9aedc3dc2d2318a2e8abf5c51531d7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="216c5-102">Tecnologias de virtualização suportadas e limitações conhecidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="216c5-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="216c5-103">_**Última modificação do tópico:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="216c5-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="216c5-104">O plug-in de VDI do Lync permite chamadas de áudio e vídeo para tecnologias de virtualização suportadas.</span><span class="sxs-lookup"><span data-stu-id="216c5-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="216c5-105">Isso estende a funcionalidade descrita para o Microsoft Lync Server 2010 no White paper sobre [virtualização do cliente no Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="216c5-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="216c5-106">Em conformidade com as regulamentações de telefone padrão, o suporte para o E911 também está incluído.</span><span class="sxs-lookup"><span data-stu-id="216c5-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="216c5-107">As seções a seguir descrevem as tecnologias de virtualização compatíveis com o plug-in VDI do Lync e as limitações de recursos conhecidas.</span><span class="sxs-lookup"><span data-stu-id="216c5-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="216c5-108">Suporte para tecnologias de virtualização</span><span class="sxs-lookup"><span data-stu-id="216c5-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="216c5-109">O plug-in de VDI do Lync suporta o Remoting completo de área de trabalho no cenário de área de trabalho virtual pessoal, mas não no cenário de sessão de área de trabalho remota.</span><span class="sxs-lookup"><span data-stu-id="216c5-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="216c5-110">Esses cenários podem ser descritos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="216c5-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="216c5-111">**Com suporte: áreas de trabalho virtuais personalizadas ou VDI (Virtual Desktop Infrastructure).**     Neste cenário, cada usuário faz logon em uma área de trabalho virtual personalizável e pode salvar arquivos na área de trabalho que persistem entre as sessões.</span><span class="sxs-lookup"><span data-stu-id="216c5-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="216c5-112">Os serviços de área de trabalho remota da Microsoft, o modo de exibição de horizonte VMware e o Citrix XenDesktop são implementações que foram testadas para uso com o Lync.</span><span class="sxs-lookup"><span data-stu-id="216c5-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="216c5-113">Para obter informações sobre ambientes VDI específicos do fornecedor e hardware de cliente que foram testados pela Microsoft, consulte [infraestrutura qualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="216c5-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="216c5-114">**Sem suporte: sessões da área de trabalho remota.**     Neste cenário, cada usuário faz logon em uma sessão de área de trabalho virtual genérica que não pode ser personalizada.</span><span class="sxs-lookup"><span data-stu-id="216c5-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="216c5-115">As implementações de exemplo incluem sessões de área de trabalho remota da Microsoft (RDSH) e Citrix XenApp combinados com o receptor Citrix.</span><span class="sxs-lookup"><span data-stu-id="216c5-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="216c5-116">O plug-in do Lync VDI não oferece suporte a outras tecnologias de virtualização, como a virtualização de aplicativo, que permite o uso de um aplicativo sem exigir a instalação do aplicativo completo localmente.</span><span class="sxs-lookup"><span data-stu-id="216c5-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="216c5-117">As implementações de exemplo incluem o Citrix XenApp e o Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="216c5-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="216c5-118">Não há suporte para o fluxo de aplicativos, comunicação remota de aplicativos e modos de virtualização mista (por exemplo, aplicativos remotos de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="216c5-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="216c5-119">Para permitir a extensibilidade, o plug-in do Lync VDI foi projetado para usar APIs independentes de plataforma chamadas DVCs (canais virtuais dinâmicos).</span><span class="sxs-lookup"><span data-stu-id="216c5-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="216c5-120">Para cenários que não são explicitamente suportados pelo Lync, consulte instruções de suporte do provedor de soluções VDI.</span><span class="sxs-lookup"><span data-stu-id="216c5-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="216c5-121">Limitações de recursos conhecidos</span><span class="sxs-lookup"><span data-stu-id="216c5-121">Known Feature Limitations</span></span>

<span data-ttu-id="216c5-122">Veja a seguir as limitações conhecidas quando você usa o Lync 2013 em um ambiente de VDI:</span><span class="sxs-lookup"><span data-stu-id="216c5-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="216c5-123">Há suporte limitado para recursos de delegação de chamada e de anonimato de agente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="216c5-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="216c5-124">Não há suporte aos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="216c5-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="216c5-125">Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo</span><span class="sxs-lookup"><span data-stu-id="216c5-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="216c5-126">Vídeo de várias exibições.</span><span class="sxs-lookup"><span data-stu-id="216c5-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="216c5-127">Gravação de conversas.</span><span class="sxs-lookup"><span data-stu-id="216c5-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="216c5-128">Serviços de área de trabalho remota (RDS).</span><span class="sxs-lookup"><span data-stu-id="216c5-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="216c5-129">Ingressar em reuniões anonimamente (ou seja, ingressar em reuniões do Lync hospedadas por uma organização que não se federa à sua organização).</span><span class="sxs-lookup"><span data-stu-id="216c5-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="216c5-130">Usando o plug-in do Lync VDI junto com um dispositivo do Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="216c5-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="216c5-131">Continuidade de chamadas em caso de indisponibilidade da rede.</span><span class="sxs-lookup"><span data-stu-id="216c5-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="216c5-132">Toques personalizados e recursos de música em espera.</span><span class="sxs-lookup"><span data-stu-id="216c5-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="216c5-133">O plug-in do Lync VDI não é suportado em um ambiente do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="216c5-133">The Lync VDI plug-in is not supported in a Microsoft 365 or Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

