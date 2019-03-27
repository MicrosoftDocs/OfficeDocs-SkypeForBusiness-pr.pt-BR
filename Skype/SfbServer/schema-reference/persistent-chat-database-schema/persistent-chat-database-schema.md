---
title: Esquema do banco de dados de Chat Persistente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Documenta o esquema do banco de dados de Chat persistente no Skype para Business Server.
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874043"
---
# <a name="persistent-chat-database-schema"></a>Esquema do banco de dados de Chat Persistente
 
Documenta o esquema do banco de dados de Chat persistente no Skype para Business Server.
  
O banco de dados de Chat persistente refere-se ao banco de dados correspondente para o Skype para funções de negócios Server servidor Back-End **PersistentChatStore** (correspondente ao banco de dados mgc) e **PersistentChatComplianceStore** (correspondente para o banco de dados mgccomp). O objetivo deste esquema de publicação é para habilitá-lo construir consultas e obter algumas ideias para criar relatórios úteis ao redor do uso de chat, salas ativas, cartazes superior e assim por diante.
  
> [!IMPORTANT]
> Reservamos o direito de evoluir este esquema. A Microsoft não faz nenhuma garantia para manter compatibilidade total com esse esquema publicada. 
  
Siga estas práticas recomendadas:
  
- Nenhum selecione\* / / é suportado, pois a lista de colunas pode crescer.
    
- Nenhuma modificação de esquema gerado pelo usuário é suportadas.
    
- Nenhuma operações de gravação são suportadas.
    
- Teste quaisquer consultas que você crie em bancos de dados de tamanho representativo para certificar-se de que as consultas podem ser executadas em um nível que atenda às suas necessidades.
    
## <a name="in-this-section"></a>Nesta seção

- [Tabelas de lista de Servidores de Chat Persistente](list-of-persistent-chat-server-tables.md)
    
- [Lista das tabelas de conformidade do servidor de Chat persistente no Skype para Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Detalhes da tabela do Servidor de Chat Persistente](persistent-chat-server-table-details.md)
    
- [Amostragem de consultas de banco de dados de Chat Persistente](sample-persistent-chat-database-queries.md)
    

