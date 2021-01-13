---
title: Implantar o Servidor de Interop de Vídeo no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Resumo: Implante a função de servidor VIS no Skype for Business Server.'
ms.openlocfilehash: 7b3ee96b1ff2e6c633efa9e1cc98aa14bb5babc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801951"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="ceb09-103">Implantar o Servidor de Interop de Vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ceb09-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="ceb09-104">**Resumo:** Implantar a função de servidor VIS no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ceb09-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="ceb09-105">O Skype for Business Server agora pode se integrar diretamente aos sistemas de teleconferência (VTCs) da Cisco, como o Cisco C60 ou o Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="ceb09-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="ceb09-106">Isso exige a introdução de uma nova função de servidor chamada Servidor de Interop de Vídeo (VIS) e a configuração correta do VIS e do equipamento com o que ele interoperará.</span><span class="sxs-lookup"><span data-stu-id="ceb09-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="ceb09-107">Um VTC se registra na infraestrutura da Cisco existente, como o Cisco Unified Communication Manager (CUCM), e um tronco SIP de vídeo é usado entre o CUCM e o pool do VIS.</span><span class="sxs-lookup"><span data-stu-id="ceb09-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ceb09-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ceb09-108">In this section</span></span>

<span data-ttu-id="ceb09-109">Configurar a interoperabilidade entre um servidor ou pool vis e sistemas VTC requer a execução dos cinco procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="ceb09-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="ceb09-110">Criar um pool de VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ceb09-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="ceb09-111">Implantar a função de servidor VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ceb09-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="ceb09-112">Configurar o Servidor de Interop de Vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ceb09-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="ceb09-113">Configurar o CUCM para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ceb09-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="ceb09-114">Configurar um VTC para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ceb09-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="ceb09-115">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="ceb09-115">Related sections</span></span>

[<span data-ttu-id="ceb09-116">Planejar o Servidor de Interop de Vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ceb09-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

