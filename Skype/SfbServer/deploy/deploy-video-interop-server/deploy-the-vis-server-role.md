---
title: Implantar a função de servidor VIS no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Resumo: Implante a função de servidor de interoperabilidade de vídeo (VIS) no Skype para Business Server.'
ms.openlocfilehash: 109992482490a300125cad7177cc3e6070f2d02a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894581"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="d7d30-103">Implantar a função de servidor VIS no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d7d30-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="d7d30-104">**Resumo:** Implante a função de servidor de interoperabilidade de vídeo (VIS) no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7d30-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="d7d30-105">Para configurar o serviço VIS no servidor recém-criado no construtor de topologia, inicie o Skype para o Assistente de implantação de servidor de negócios, pressione **instalar ou Skype de atualização para o sistema de servidor de negócios** e siga estas etapas no Assistente para:</span><span class="sxs-lookup"><span data-stu-id="d7d30-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="d7d30-106">Selecione **Instalar Repositório de Configuração Local**.</span><span class="sxs-lookup"><span data-stu-id="d7d30-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="d7d30-107">Selecione **instalar ou remover Skype para componentes de servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="d7d30-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="d7d30-108">Selecione **Solicitar, Instalar ou Atribuir Certificados**.</span><span class="sxs-lookup"><span data-stu-id="d7d30-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="d7d30-109">Selecione **Iniciar serviços**.</span><span class="sxs-lookup"><span data-stu-id="d7d30-109">Select **Start services**.</span></span>
    
<span data-ttu-id="d7d30-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="d7d30-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="d7d30-111">Você pode abrir a ferramenta mmc de serviços para ver se o serviço de **Skype para interoperabilidade de vídeo Business Server Server** é executado, juntamente com outro Skype para serviços de Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7d30-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="d7d30-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="d7d30-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="d7d30-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="d7d30-113">See also</span></span>

[<span data-ttu-id="d7d30-114">Configurar o servidor de interoperabilidade de vídeo no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d7d30-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
