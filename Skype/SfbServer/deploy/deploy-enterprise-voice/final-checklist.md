---
title: Processo final de implantação de controle de admissão de chamada para Skype para Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: beec5c03f47d8f06ec862c3e9a3609fba7b66f2c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a>Lista de verificação final da implantação do serviço de controle de admissão de chamadas do Skype for Business Server 2015
 
Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype para Business Server Enterprise Voice. 
  
Consulte a lista de verificação para confirmar se você concluiu todas as tarefas de configuração necessárias para a implantação do serviço de Controle de Admissão de Chamadas (CAC).
  
- Se um ou mais servidores de borda estiverem implantados, cada endereço IP de interface externa deve ser adicionado à lista de sub-rede nas definições de configuração de rede, com uma máscara de bits de 32. Associe também essa sub-rede (endereço IP) ao ID do site da rede para o local geográfico onde o serviço de Borda A/V está implantado.
    
    > [!NOTE]
    > Servidores de borda não são necessárias para implementar o CAC. 
  
- Certifique-se de que CAC está habilitado, como especificado em [Habilitar o controle de admissão de chamada no Skype para Business Server 2015](enable-call-admission-control.md).
    
- Certifique-se de que o CAC está habilitado em todos os sites centrais. Isso pode ser feito por meio do construtor de topologia. Se um aviso será gerado quando você publica, *não* ignorá-la.
    
- Certifique-se de que todas as subredes gerenciadas na rede corporativa estão definidas nas configurações de rede. Também é essencial que todas as sub-redes ser associadas a um site de rede, conforme explicado em [Deploy regiões de rede, sites e sub-redes em Skype para negócios 2015](deploy-network.md).
    
- Certifique-se de que a subrede ou os endereços IP de todos os Servidores Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.
    

