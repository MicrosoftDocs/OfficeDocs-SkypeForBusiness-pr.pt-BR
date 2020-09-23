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
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Defina o monitoramento do SQL Server Store configurando as seguintes propriedades:'
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218872"
---
# <a name="add-front-end-monitoring-store-page"></a>Adicionar Página de Repositório de Monitoramento do Front End
 
**Defina o monitoramento do SQL Server Store** configurando as seguintes propriedades:
  
- **Monitoramento do SQL Server Store**: selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório do servidor de monitoramento.
    
- Marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** se quiser adicionar o espelhamento de banco de dados para o servidor de monitoramento.
    
    Selecione um **espelhamento de repositório do SQL Server de monitoramento** existente na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de espelho.
    
- Se você selecionou **habilitar espelhamento de repositório do SQL Server**, selecione, opcionalmente, **usar testemunha de espelhamento do SQL Server para habilitar o failover automático** para selecionar um repositório de testemunha de espelhamento do SQL Server na lista.
    
    Clique em **novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o repositório de testemunha de espelhamento.
    
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique em **Avançar** depois de concluir a inserção das opções para essa caixa de diálogo para prosseguir com a configuração.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Associar um repositório de monitoramento a um pool de front-ends no Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
