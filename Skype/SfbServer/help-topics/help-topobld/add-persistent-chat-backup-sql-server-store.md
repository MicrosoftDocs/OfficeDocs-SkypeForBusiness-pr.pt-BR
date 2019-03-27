---
title: Adicionar Repositório de SQL Server de Backup de Chat Persistente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure os repositórios de Backup do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou o pool de servidor de Chat persistente.
ms.openlocfilehash: ed507b14cf0b03da86eda4b3fbc8491997c801d9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880578"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>Adicionar Repositório de SQL Server de Backup de Chat Persistente
 
Configure os repositórios de Backup do SQL Server que fornecerão bancos de dados de backup para o servidor de Chat persistente ou o pool de servidor de Chat persistente.
  
 **O SQL Server store**: selecione um SQL Server existente e, opcionalmente, uma instância para o Chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de backup de Chat persistente.
  
Marque a caixa de seleção de **espelhamento do repositório de habilitar o SQL Server** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de backup de Chat persistente.
  
Selecione na lista **espelhando o SQL Server store** um SQL Server e uma instância opcional para agir como o espelho do SQL Server para o SQL Server de backup Chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento de Persistent Chat SQL Server.
  
Na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático**, selecione um SQL Server que atuará como o servidor testemunha em cenários de failover. O servidor testemunha faz não os dados de espelho ou host para os servidores de Chat persistente, mas garante que apenas um SQL Server em uma configuração espelhada esteja ativo SQL Server a qualquer momento.
  
Clique em **novo** para definir uma nova testemunha de SQL Server e, opcionalmente, uma instância do Chat persistente backup SQL Server testemunha de espelhamento.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique em **Avançar** depois de concluir a inserção das opções para configuração de repositório do SQL Server backup desse pool e para prosseguir com a definição do pool de servidor de Chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda contextual, como esta página.
  
## <a name="see-also"></a>Consulte Também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
