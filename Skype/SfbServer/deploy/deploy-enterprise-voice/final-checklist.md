---
title: Lista de verificação final de implantação de controle de admissão de chamada para Skype for Business Server
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
description: Lista de verificação final para implantar o Cac (Controle de Admissão de Chamada) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 89893e846d37a2a10cbf33de53b8426a0b9d3d642846455e1415991903b0f3e3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338729"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implantação do controle de admissão de chamada: lista de verificação final para Skype for Business Server
 
Lista de verificação final para implantar o Cac (Controle de Admissão de Chamada) no Skype for Business Server Enterprise Voice. 
  
Use a lista de verificação a seguir para verificar se você concluiu todas as tarefas de configuração necessárias para implantar o Cac (Controle de Admissão de Chamada).
  
- Se um ou mais Servidores de Borda for implantado, cada endereço IP de interface externa precisa ser adicionado à lista de subredes nas configurações de rede, com uma bitmask de 32. Associe também essa sub-rede (endereço IP) ao ID do site de rede para o local geográfico onde o serviço Borda A/V está implantado.
    
    > [!NOTE]
    > Os Servidores de Borda não são necessários para implementar o CAC. 
  
- Certifique-se de que o CAC está habilitado, conforme especificado em [Habilitar controle de](enable-call-admission-control.md)admissão de chamada em Skype for Business Server .
    
- Certifique-se de que o CAC está habilitado em todos os sites centrais. Isso pode ser feito por meio do Construtor de Topologias. Se um aviso for gerado quando você publicar,  *não o*  ignore.
    
- Certifique-se de que todas as subredes gerenciadas na rede empresarial estão definidas nas configurações de rede. Também é essencial que todas as sub-redes sejam associadas a um site de rede, conforme explicado em Deploy network regions, sites and [subnets in Skype for Business](deploy-network.md).
    
- Certifique-se de que a subrede ou os endereços IP de todos os Servidores de Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.
    

