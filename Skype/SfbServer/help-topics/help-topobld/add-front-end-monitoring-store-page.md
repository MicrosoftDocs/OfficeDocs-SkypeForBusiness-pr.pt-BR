---
title: Adicionar página repositório de monitoramento do Front End
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Você definir o repositório de monitoramento do SQL Server, definindo as seguintes propriedades:'
ms.openlocfilehash: fe95cab603729736b0483774baa7111837a31c8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
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

#### 

[Associar um repositório de monitoramento um pool de Front-End no Skype para Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)

