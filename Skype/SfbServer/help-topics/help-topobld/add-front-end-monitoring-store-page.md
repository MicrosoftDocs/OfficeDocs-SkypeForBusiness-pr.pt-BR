---
title: Adicionar Página de Repositório de Monitoramento do Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Defina o monitoramento do SQL Server Store configurando as seguintes propriedades:'
ms.openlocfilehash: 789083ad0743ed7baf94630c86e4647e218c336c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820853"
---
# <a name="add-front-end-monitoring-store-page"></a>Adicionar Página de Repositório de Monitoramento do Front End
 
**Defina o monitoramento do SQL Server Store** configurando as seguintes propriedades:
  
- **Monitorando a loja do SQL Server**: selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para a loja do servidor de monitoramento.
    
- Marque a caixa de seleção **habilitar o espelhamento da loja do SQL Server** se desejar adicionar o espelhamento de banco de dados para o servidor de monitoramento.
    
    Selecione um espelho existente do **SQL Server Store de monitoramento** na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento de espelho.
    
- Se você selecionou **habilitar o espelhamento da loja do SQL Server**, selecione **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar um repositório de testemunha de espelhamento do SQL Server na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento de testemunha de espelhamento.
    
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique em **Avançar** depois de concluir a inserção das opções para esta caixa de diálogo para continuar com a configuração.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Confira também

[Associar um repositório de monitoramento com um Pool de Front-Ends no Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
