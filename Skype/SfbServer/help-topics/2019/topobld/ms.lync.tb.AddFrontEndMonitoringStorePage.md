---
title: Adicionar Página de Repositório de Monitoramento de Front-end
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Você define o armazenamento SQL Server monitoramento configurando as seguintes propriedades:'
ms.openlocfilehash: 9ba6a6d6481f36eb7a7a28ec91881b60429b3fcd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398144"
---
# <a name="add-front-end-monitoring-store-page"></a>Adicionar Página de Repositório de Monitoramento de Front-end
 
Você **define o armazenamento SQL Server monitoramento** configurando as seguintes propriedades:
  
- **Monitoring SQL Server store**: selecione um SQL Server nome de domínio totalmente qualificado (e, opcionalmente, uma instância) na lista.
    
    Clique **em Novo** para criar uma nova SQL Server FQDN e, opcionalmente, um nome de instância para o armazenamento do Servidor de Monitoramento.
    
- Marque a **caixa de seleção Habilitar SQL Server espelhamento** de armazenamento se quiser adicionar espelhamento de banco de dados para o Servidor de Monitoramento.
    
    Selecione um espelho **de armazenamento SQL Server monitoramento** existente na lista.
    
    Clique **em Novo** para criar uma nova SQL Server FQDN e, opcionalmente, um nome de instância para o armazenamento espelho.
    
- Se você selecionou **Habilitar SQL Server** espelhamento de armazenamento, selecione Usar SQL Server testemunha de espelhamento para habilitar o **failover** automático para selecionar um SQL Server de espelhamento de testemunha na lista.
    
    Clique **em Novo** para criar uma nova SQL Server FQDN e, opcionalmente, um nome de instância para o armazenamento de testemunha de espelhamento.
    
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de terminar de inserir as opções para que essa caixa de diálogo prossiga com a configuração.
  
Clique **em Cancelar** para descartar todas as alterações e encerrar o assistente.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
