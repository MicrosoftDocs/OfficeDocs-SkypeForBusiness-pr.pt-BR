---
title: Adicionar página repositório de monitoramento do Front End
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Você definir o repositório de monitoramento do SQL Server, definindo as seguintes propriedades:'
ms.openlocfilehash: 14528aeb86d34f96d54d3cf4088ea8d2b08dfd88
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21065338"
---
# <a name="add-front-end-monitoring-store-page"></a>Adicionar página repositório de monitoramento do Front End
 
Você **definir o SQL Server store de monitoramento** Configurando as propriedades a seguintes:
  
- **Monitorando o SQL Server store**: selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório do Monitoring Server.
    
- Se você deseja adicionar o espelhamento de banco de dados para o Monitoring Server, marque a caixa de seleção **Habilitar o SQL Server store de espelhamento** .
    
    Selecione um **espelho de repositório de monitoramento do SQL Server** de existente na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de espelho.
    
- Se você selecionou o **espelhamento do repositório de habilitar o SQL Server**, selecione, opcionalmente, **Use o SQL Server espelhamento testemunha para habilitar o failover automático** para selecionar um repositório de testemunha da lista de espelhamento do SQL Server.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de testemunha de espelhamento.
    
Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.
  
Clique em **Avançar** depois de concluir a inserção das opções para essa caixa de diálogo prosseguir com a configuração.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Consulte também

[Associar um repositório de monitoramento um pool de Front-End no Skype para Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)