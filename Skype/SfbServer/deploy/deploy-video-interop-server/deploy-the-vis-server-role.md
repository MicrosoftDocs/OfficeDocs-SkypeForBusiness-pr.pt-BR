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
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a>Implantar a função de servidor VIS no Skype for Business Server
 
**Resumo:** Implantar a função de Servidor de Interop de Vídeo (VIS) no Skype for Business Server.
  
Para configurar o serviço VIS no servidor que acabou de ser criado no Construtor de Topologias, inicie o assistente de implantação do Skype for Business Server, pressione **Install ou Update Skype for Business Server System** e siga estas etapas no assistente:
  
1.  Selecione **Instalar Armazenamento de Configuração Local.**
    
2. Selecione **Configurar ou Remover Componentes do Skype for Business Server.**
    
3. Selecione **Solicitar, Instalar ou Atribuir Certificados.**
    
4. Selecione **Iniciar serviços**.
    
O software para esse serviço agora está instalado e em execução. Você pode abrir a ferramenta mmc Serviços para ver se o serviço **Skype for Business Server Video Interop Server** está em execução juntamente com outros serviços do Skype for Business Server. Em seguida, você deve configurar o servidor ou pool do VIS.
## <a name="see-also"></a>Confira também

[Configurar o Servidor de Interop de Vídeo no Skype for Business Server](configure-the-vis.md)
