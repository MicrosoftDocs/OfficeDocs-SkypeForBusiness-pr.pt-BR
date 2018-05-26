---
title: Adicionar Repositório de Servidor SQL de Backup de Conformidade de Chat Persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configurar o Backup repositórios de conformidade do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou repositórios do SQL Server de conformidade do servidor de Chat persistente.
ms.openlocfilehash: 7143ecdc51caf941196f1499e9cc1dc35764b0d3
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Adicionar Repositório de Servidor SQL de Backup de Conformidade de Chat Persistente
 
Configurar o Backup repositórios de conformidade do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou repositórios do SQL Server de conformidade do servidor de Chat persistente.
  
 **O SQL Server store**: selecione um SQL Server existente e, opcionalmente, uma instância para o Chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de backup de conformidade de Chat persistente.
  
Marque a caixa de seleção **Habilitar o SQL Server store espelhamento** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de backup de conformidade de Chat persistente.
  
Selecione na lista **espelhando o SQL Server store** um SQL Server e uma instância opcional para agir como o espelho do SQL Server para o Chat persistente backup de conformidade do SQL Server.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de Persistent Chat SQL Server.
  
Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover. O servidor testemunha faz não os dados de espelho ou host para os servidores de Chat persistente, mas garante que apenas um SQL Server em uma configuração espelhada esteja ativo SQL Server a qualquer momento.
  
Clique em **novo** para definir uma nova testemunha de SQL Server e, opcionalmente, uma instância para o Chat persistente backup de conformidade testemunha de espelhamento do SQL Server.
  
Clique em  **Voltar** para voltar à caixa de diálogo de definição de pool anterior.
  
Clique em **Avançar** depois de concluir a inserção das opções para configuração de repositório do SQL Server backup desse pool e para prosseguir com a definição do pool de servidor de Chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Consulte também

#### 

[Planejar o servidor de Chat persistente no Skype for Business Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos de servidor do Skype para Business Server 2015](../../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para o servidor de Chat persistente no Skype para Business Server 2015](../../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar o serviço de conformidade para o servidor de Chat persistente no Skype para Business Server 2015](../../../manage/persistent-chat/configure-compliance.md)
  
[Configurar alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

