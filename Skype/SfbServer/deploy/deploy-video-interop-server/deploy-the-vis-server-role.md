---
title: Implantar a função de servidor VIS no Skype for Business Server
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
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Resumo: Implantar a função de Servidor de Interop de Vídeo (VIS) no Skype for Business Server.'
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801961"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="03afc-103">Implantar a função de servidor VIS no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03afc-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="03afc-104">**Resumo:** Implantar a função de Servidor de Interop de Vídeo (VIS) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03afc-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="03afc-105">Para configurar o serviço VIS no servidor que acabou de ser criado no Construtor de Topologias, inicie o assistente de implantação do Skype for Business Server, pressione **Install ou Update Skype for Business Server System** e siga estas etapas no assistente:</span><span class="sxs-lookup"><span data-stu-id="03afc-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="03afc-106">Selecione **Instalar Armazenamento de Configuração Local.**</span><span class="sxs-lookup"><span data-stu-id="03afc-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="03afc-107">Selecione **Configurar ou Remover Componentes do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="03afc-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="03afc-108">Selecione **Solicitar, Instalar ou Atribuir Certificados.**</span><span class="sxs-lookup"><span data-stu-id="03afc-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="03afc-109">Selecione **Iniciar serviços**.</span><span class="sxs-lookup"><span data-stu-id="03afc-109">Select **Start services**.</span></span>
    
<span data-ttu-id="03afc-110">O software para esse serviço agora está instalado e em execução.</span><span class="sxs-lookup"><span data-stu-id="03afc-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="03afc-111">Você pode abrir a ferramenta mmc Serviços para ver se o serviço **Skype for Business Server Video Interop Server** está em execução juntamente com outros serviços do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03afc-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="03afc-112">Em seguida, você deve configurar o servidor ou pool do VIS.</span><span class="sxs-lookup"><span data-stu-id="03afc-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="03afc-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="03afc-113">See also</span></span>

[<span data-ttu-id="03afc-114">Configurar o Servidor de Interop de Vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03afc-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
