---
title: Lista de verificação final da implantação do controle de admissão de chamadas do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: fab6472d931d0475a3e3b0a0f413fce7775d7a15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281585"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implantação de controle de admissão de chamadas: lista de verificação final do Skype for Business Server
 
Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype for Business Server Enterprise Voice. 
  
Consulte a lista de verificação para confirmar se você concluiu todas as tarefas de configuração necessárias para a implantação do serviço de Controle de Admissão de Chamadas (CAC).
  
- Se um ou mais servidores Edge estiverem implantados, cada endereço IP de interface externa precisará ser adicionado à lista de sub-rede nas configurações de configuração de rede, com uma máscara de bits de 32. Associe também essa sub-rede (endereço IP) ao ID do site da rede para o local geográfico onde o serviço de Borda A/V está implantado.
    
    > [!NOTE]
    > Os servidores de borda não precisam implementar o CAC. 
  
- Verifique se o CAC está habilitado, conforme especificado em [habilitar controle de admissão de chamadas no Skype for Business Server](enable-call-admission-control.md).
    
- Certifique-se de que o CAC está habilitado em todos os sites centrais. Isso pode ser feito por meio do construtor de topologias. Se um aviso for gerado durante a publicação, *não* o ignore.
    
- Certifique-se de que todas as subredes gerenciadas na rede corporativa estão definidas nas configurações de rede. Também é essencial que cada sub-rede seja associada a um site de rede, conforme explicado em [implantar regiões de rede, sites e sub-redes no Skype for Business](deploy-network.md).
    
- Certifique-se de que a subrede ou os endereços IP de todos os Servidores Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.
    

