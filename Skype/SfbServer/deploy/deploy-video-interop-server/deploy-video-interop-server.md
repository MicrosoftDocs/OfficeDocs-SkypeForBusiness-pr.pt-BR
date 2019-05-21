---
title: Implantar o servidor de interoperabilidade de vídeo no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Resumo: implante a função de servidor VIS no Skype for Business Server.'
ms.openlocfilehash: c6ee0e52a4ac84622fee9ba281a64d1094c38c4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302732"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="629c8-103">Implantar o servidor de interoperabilidade de vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629c8-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="629c8-104">**Resumo:** Implante a função de servidor VIS no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="629c8-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="629c8-105">O Skype for Business Server agora pode se integrar diretamente a Cisco teleconferência Systems (VTCs), como o Cisco C60 ou o Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="629c8-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="629c8-106">Isso requer a introdução de uma nova função de servidor chamada servidor de interoperabilidade de vídeo (VIS) e a configuração correta do VIS e do equipamento com o qual ele interoperará.</span><span class="sxs-lookup"><span data-stu-id="629c8-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="629c8-107">Um VTC registra com o Cisco Unified Communication Manager (CUCM) existente, e um tronco SIP de vídeo é usado entre o CUCM e o pool de VIS.</span><span class="sxs-lookup"><span data-stu-id="629c8-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="629c8-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="629c8-108">In this section</span></span>

<span data-ttu-id="629c8-109">A configuração da interoperabilidade entre um servidor ou pool VIS e sistemas VTC requer a realização dos cinco procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="629c8-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="629c8-110">Criar um pool de VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629c8-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="629c8-111">Implantar a função de servidor VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629c8-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="629c8-112">Configurar o servidor de interoperabilidade de vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629c8-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="629c8-113">Configurar o CUCM para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629c8-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="629c8-114">Configurar um VTC para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629c8-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="629c8-115">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="629c8-115">Related sections</span></span>

[<span data-ttu-id="629c8-116">Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629c8-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

