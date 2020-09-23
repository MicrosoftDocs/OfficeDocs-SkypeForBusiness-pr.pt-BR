---
title: Adicionar Repositório de Servidor SQL de Backup de Conformidade de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configure os repositórios do SQL Server de conformidade de backup que fornecerão bancos de dados de backup para o servidor de chat persistente ou para os repositórios do SQL Server de conformidade do servidor de chat persistente.
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218692"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Adicionar Repositório de Servidor SQL de Backup de Conformidade de Bate-papo Persistente
 
Configure os repositórios do SQL Server de conformidade de backup que fornecerão bancos de dados de backup para o servidor de chat persistente ou para os repositórios do SQL Server de conformidade do servidor de chat persistente.
  
 **Repositório do SQL Server**: selecione um SQL Server existente e, opcionalmente, uma instância para o chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de conformidade do backup de chat persistente.
  
Marque a caixa de seleção **habilitar espelhamento do SQL Server Store** para configurar um banco de dados do SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de conformidade do backup de chat persistente.
  
Selecione na lista **espelhando o SQL Server Store** um SQL Server e uma instância opcional para atuar como o espelho do SQL Server para o SQL Server de conformidade de backup de chat persistente.
  
Clique em **novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o espelhamento do SQL Server do chat persistente.
  
Selecione na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** um SQL Server que agirá como o servidor testemunha em cenários de failover. O servidor testemunha não espelha ou hospeda dados para os servidores de chat persistente, mas garante que apenas um SQL Server em uma configuração espelhada seja o SQL Server ativo a qualquer momento.
  
Clique em **novo** para definir uma nova testemunha do SQL Server, opcionalmente, uma instância para a testemunha de espelhamento do SQL Server de conformidade de backup de chat persistente.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique em **Avançar** depois de inserir as opções para a configuração do SQL Server Store de backup desse pool e para prosseguir com a definição do pool do servidor de chat persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar o servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos de servidor para o Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para o servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar o serviço de conformidade para o servidor de chat persistente no Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurar alta disponibilidade e recuperação de desastre para servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
