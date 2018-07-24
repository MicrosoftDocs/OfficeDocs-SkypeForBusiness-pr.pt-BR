---
title: Implante o servidor de interoperabilidade de vídeo em Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Resumo: Implante a função de servidor VIS no Skype para Business Server.'
ms.openlocfilehash: 8bb21d667774b50fd7a7caddabfbd02e8125a4a2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967569"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="0de08-103">Implante o servidor de interoperabilidade de vídeo em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0de08-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="0de08-104">**Resumo:** Implante a função de servidor VIS no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0de08-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="0de08-105">Skype para Business Server agora pode integrar diretamente com sistemas de teleconferência Cisco (VTCs) como o Cisco C60 ou Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="0de08-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="0de08-106">Isso requer a introdução de uma nova função de servidor chamada o servidor de interoperabilidade de vídeo (VIS) e a configuração correta do VIS e o equipamento com que ele irá interoperar.</span><span class="sxs-lookup"><span data-stu-id="0de08-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="0de08-107">Um VTC registra com o Cisco Unified Communication Manager (CUCM) existente, e um tronco SIP de vídeo é usado entre o CUCM e o pool de VIS.</span><span class="sxs-lookup"><span data-stu-id="0de08-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0de08-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0de08-108">In this section</span></span>

<span data-ttu-id="0de08-109">A configuração da interoperabilidade entre um servidor ou pool VIS e sistemas VTC requer a realização dos cinco procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0de08-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="0de08-110">Criar um pool VIS no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0de08-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="0de08-111">Implantar a função de servidor VIS no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0de08-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="0de08-112">Configurar o servidor de interoperabilidade de vídeo no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0de08-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="0de08-113">Configurar CUCM para interoperação com Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0de08-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="0de08-114">Configurar um VTC para interoperação com Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0de08-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="0de08-115">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="0de08-115">Related sections</span></span>

[<span data-ttu-id="0de08-116">Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0de08-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

