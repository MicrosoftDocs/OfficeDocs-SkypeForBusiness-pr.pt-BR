---
title: Adicionar Repositório de Servidor SQL de Conformidade de Bate-papo Persistente
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
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Você configura os SQL Server de conformidade que fornecerão bancos de dados para o recurso de conformidade do Servidor de Chat Persistente ou do Servidor de Chat Persistente.
ms.openlocfilehash: c3a045e8a8489bce7c333ade7a133afbc80016a7db81239c5df5292854a76870
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309410"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Adicionar Conformidade de Chat Persistente do Repositório do SQL Server
 
Você configura os SQL Server de conformidade que fornecerão bancos de dados para o recurso de conformidade do Servidor de Chat Persistente ou do Servidor de Chat Persistente.
  
 **SQL Server:** selecione um SQL Server existente e, opcionalmente, uma instância para Chat Persistente.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para os dados de conformidade do Chat Persistente.
  
Marque a **caixa de seleção** Habilitar SQL Server de espelhamento de armazenamento para configurar um banco de dados SQL Server e uma instância opcional que fornecerá um banco de dados espelhado para os dados de conformidade do Chat Persistente.
  
Selecione na lista **Espelhamento** SQL Server armazenar uma instância SQL Server e opcional para atuar como o espelho SQL Server para o SQL Server.
  
Clique **em Novo** para definir um novo SQL Server e, opcionalmente, uma nova instância para o SQL Server de Chat Persistente.
  
Selecione na lista **Usar testemunha de espelhamento do SQL Server para habilitar o failover automático** um SQL Server que agirá como o servidor testemunha em cenários de failover. O servidor testemunha não espelha nem hospeda dados para os servidores de Chat Persistente, mas garante que apenas um SQL Server em uma configuração espelhada seja o servidor SQL Server a qualquer momento.
  
Clique **em Novo** para definir uma nova SQL Server, opcionalmente, uma instância para a testemunha de conformidade do Chat Persistente SQL Server espelhamento.
  
Clique em **Voltar** para voltar à caixa de diálogo de definição anterior.
  
Clique **em Avançar** depois de inserir as opções para a configuração de armazenamento de backup SQL Server do pool e continuar com a definição do pool do Servidor de Chat Persistente.
  
Clique em **Cancelar** para descartar todas as alterações e encerrar o assistente **Definir Novo Pool de Chat Persistente**.
  
Clique em **Ajuda** para acessar a ajuda sensível ao contexto, como esta página.
  
## <a name="see-also"></a>Confira também

[Planejar o Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos de servidor para Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware e software para o Servidor de Chat Persistente Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
