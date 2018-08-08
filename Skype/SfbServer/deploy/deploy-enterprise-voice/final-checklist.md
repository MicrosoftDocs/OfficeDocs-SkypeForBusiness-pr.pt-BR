---
title: Processo final de implantação de controle de admissão de chamada para Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
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
ms.openlocfilehash: e5791aa6f3b32e423f36021314bec930fa7f74e5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025671"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Implantação do controle de admissão de chamada: lista de verificação final do Skype para Business Server
 
Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype para Business Server Enterprise Voice. 
  
Consulte a lista de verificação para confirmar se você concluiu todas as tarefas de configuração necessárias para a implantação do serviço de Controle de Admissão de Chamadas (CAC).
  
- Se um ou mais servidores de borda estiverem implantados, cada endereço IP de interface externa deve ser adicionado à lista de sub-rede nas definições de configuração de rede, com uma máscara de bits de 32. Associe também essa sub-rede (endereço IP) ao ID do site da rede para o local geográfico onde o serviço de Borda A/V está implantado.
    
    > [!NOTE]
    > Servidores de borda não são necessárias para implementar o CAC. 
  
- Certifique-se de que CAC está habilitado, como especificado em [Habilitar o controle de admissão de chamada no Skype para Business Server](enable-call-admission-control.md).
    
- Certifique-se de que o CAC está habilitado em todos os sites centrais. Isso pode ser feito por meio do construtor de topologia. Se um aviso será gerado quando você publica, *não* ignorá-la.
    
- Certifique-se de que todas as subredes gerenciadas na rede corporativa estão definidas nas configurações de rede. Também é essencial que todas as sub-redes ser associadas a um site de rede, conforme explicado em [Deploy regiões de rede, sites e sub-redes em Skype para negócios](deploy-network.md).
    
- Certifique-se de que a subrede ou os endereços IP de todos os Servidores Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.
    

