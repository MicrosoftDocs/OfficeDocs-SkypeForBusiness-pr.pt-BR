---
title: Adicionar Backup do Chat Persistente do Repositório do SQL Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure os armazenamentos de SQL Server backup que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou pool de Servidores de Chat Persistente.
ms.openlocfilehash: 038e8aff6c905ae60c7f5ed8a1e704cf7961d5dc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863898"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>Adicionar Backup do Chat Persistente do Repositório do SQL Server
 
Configure os armazenamentos de SQL Server backup que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou pool de Servidores de Chat Persistente.
  
 **SQL Server:** selecione um SQL Server existente e, opcionalmente, uma instância para Chat Persistente.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de backup de Chat Persistente.
  
Marque a **caixa de seleção** Habilitar SQL Server armazenamento de espelhamento para configurar um banco de dados SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de backup de Chat Persistente.
  
Selecione na lista **Espelhamento SQL Server armazenar** uma instância SQL Server e opcional para atuar como o espelho SQL Server para o backup de chat persistente SQL Server.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o SQL Server de Chat Persistente.
  
Selecione na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** um SQL Server que agirá como o servidor testemunha em cenários de failover. O servidor testemunha não espelha nem hospeda dados para os servidores de Chat Persistente, mas garante que apenas um SQL Server em uma configuração espelhada seja o servidor SQL Server a qualquer momento.
  
Clique **em Novo** para definir uma nova SQL Server testemunha opcionalmente uma instância para o backup de Chat Persistente SQL Server testemunha de espelhamento.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de inserir as opções para a configuração de armazenamento de backup SQL Server do pool e continuar com a definição do pool do Servidor de Chat Persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para o Servidor de Chat Persistente Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
