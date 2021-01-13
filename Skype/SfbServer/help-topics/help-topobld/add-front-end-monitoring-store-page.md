---
title: Adicionar Página de Repositório de Monitoramento de Front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Defina o armazenamento do SQL Server de monitoramento configurando as seguintes propriedades:'
ms.openlocfilehash: 5f8a3ccb22aea1efde0b214b9afa61c140e63014
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803541"
---
# <a name="add-front-end-monitoring-store-page"></a>Adicionar Página de Repositório de Monitoramento de Front-end
 
Defina **o armazenamento do SQL Server de monitoramento** configurando as seguintes propriedades:
  
- **Monitoramento do armazenamento do SQL Server:** selecione um nome de domínio totalmente qualificado do SQL Server (e, opcionalmente, uma instância) na lista.
    
    Clique **em** Novo para criar uma nova definição FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento do Monitoring Server.
    
- Marque a **caixa de seleção Habilitar** espelhamento do armazenamento do SQL Server se quiser adicionar espelhamento de banco de dados para o Monitoring Server.
    
    Selecione um espelho existente **do armazenamento do SQL Server de monitoramento** na lista.
    
    Clique **em Novo** para criar uma nova definição de FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento espelho.
    
- Se você selecionou Habilitar espelhamento do armazenamento do **SQL Server,** selecione Usar testemunha de espelhamento do SQL Server para habilitar o **failover** automático para selecionar um armazenamento testemunha de espelhamento do SQL Server na lista.
    
    Clique **em Novo** para criar uma nova definição FQDN do SQL Server e, opcionalmente, um nome de instância para o armazenamento de testemunha de espelhamento.
    
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de terminar de inserir as opções dessa caixa de diálogo para prosseguir com a configuração.
  
Clique **em Cancelar** para descartar todas as alterações e encerrar o assistente.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
