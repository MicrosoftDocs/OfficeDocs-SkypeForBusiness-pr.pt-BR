---
title: Adicionar Backup do Chat Persistente do Repositório do SQL Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure os armazenamentos do SQL Server de backup que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente.
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818731"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>Adicionar Backup do Chat Persistente do Repositório do SQL Server
 
Configure os armazenamentos do SQL Server de backup que fornecerão bancos de dados de backup para o Servidor de Chat Persistente ou pool de Servidor de Chat Persistente.
  
 **Sql Server store:** selecione um SQL Server existente e, opcionalmente, uma instância para Chat Persistente.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de backup de Chat Persistente.
  
Marque a **caixa de** seleção Habilitar espelhamento do sql Server para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de backup de Chat Persistente.
  
Selecione na lista **Espelhando o SQL Server,** armazene um SQL Server e uma instância opcional para atuar como o espelho do SQL Server para o SQL Server de backup de Chat Persistente.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento do SQL Server de Chat Persistente.
  
Selecione na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** um SQL Server que agirá como o servidor testemunha em cenários de failover. O servidor testemunha não espelha ou hospeda dados para os servidores de Chat Persistente, mas garante que apenas um SQL Server em uma configuração espelhada seja o SQL Server ativo a qualquer momento.
  
Clique **em Novo** para definir uma nova testemunha do SQL Server, opcionalmente, uma instância para a testemunha de espelhamento do SQL Server de backup de Chat Persistente.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de terminar de inserir as opções para a configuração do sql Server store de backup desse pool e para prosseguir com a definição do pool do Servidor de Chat Persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Plano para Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
