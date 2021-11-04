---
title: Adicionar Página de Repositório de Monitoramento de Front-end
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 074d7aefa6e5b724d7266fbfb9d2b05dd558e4fc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766919"
---
# <a name="add-front-end-monitoring-store-page"></a>Adicionar Página de Repositório de Monitoramento de Front-end
 
Você **define o armazenamento SQL Server monitoramento** configurando as seguintes propriedades:
  
- **Monitoring SQL Server store**: SQL Server selecione um nome de domínio totalmente qualificado (e, opcionalmente, uma instância) na lista.
    
    Clique **em Novo** para criar uma nova SQL Server FQDN e, opcionalmente, um nome de instância para o armazenamento do Servidor de Monitoramento.
    
- Marque a **caixa de seleção Habilitar SQL Server espelhamento** de armazenamento se quiser adicionar espelhamento de banco de dados para o Servidor de Monitoramento.
    
    Selecione um espelho **de SQL Server de armazenamento** existente na lista.
    
    Clique **em Novo** para criar uma nova SQL Server FQDN e, opcionalmente, um nome de instância para o armazenamento espelho.
    
- Se você selecionou **Habilitar SQL Server** espelhamento de armazenamento, selecione Usar SQL Server testemunha de espelhamento para habilitar o **failover** automático para selecionar um SQL Server de espelhamento de testemunha na lista.
    
    Clique **em Novo** para criar uma nova SQL Server FQDN e, opcionalmente, um nome de instância para o armazenamento de testemunha de espelhamento.
    
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de terminar de inserir as opções para que essa caixa de diálogo prossiga com a configuração.
  
Clique **em Cancelar** para descartar todas as alterações e encerrar o assistente.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
