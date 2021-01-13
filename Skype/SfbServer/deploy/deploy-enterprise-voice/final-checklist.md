---
title: Lista de verificação final da implantação do controle de admissão de chamadas para o Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de verificação final para implantar o CAC (Controle de Admissão de Chamadas) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830831"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implantação do controle de admissão de chamadas: lista de verificação final do Skype for Business Server
 
Lista de verificação final para implantar o CAC (Controle de Admissão de Chamadas) no Skype for Business Server Enterprise Voice. 
  
Use a lista de verificação a seguir para verificar se você concluiu todas as tarefas de configuração necessárias para implantar o Controle de Admissão de Chamada (CAC).
  
- Se um ou mais Servidores de Borda for implantado, cada endereço IP de interface externa precisa ser adicionado à lista de subredes nas configurações de rede, com uma bitmask de 32. Associe também essa sub-rede (endereço IP) ao ID do site de rede para o local geográfico onde o serviço Borda A/V está implantado.
    
    > [!NOTE]
    > Os Servidores de Borda não são necessários para implementar o CAC. 
  
- Certifique-se de que o CAC está habilitado, conforme especificado em [Habilitar](enable-call-admission-control.md)controle de admissão de chamadas no Skype for Business Server.
    
- Certifique-se de que o CAC está habilitado em todos os sites centrais. Isso pode ser feito por meio do Construtor de Topologias. Se um aviso for gerado quando você publicar,  *não o*  ignore.
    
- Certifique-se de que todas as subredes gerenciadas na rede empresarial estão definidas nas configurações de rede. Também é essencial que todas as sub-redes sejam associadas a um site de rede, conforme explicado em Implantar regiões de rede, sites e [sub-redes](deploy-network.md)no Skype for Business.
    
- Certifique-se de que a subrede ou os endereços IP de todos os Servidores de Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.
    

