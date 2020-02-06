---
title: Esquema do banco de dados de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Isso documenta o esquema do banco de dados de chat persistente no Skype for Business Server.
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814739"
---
# <a name="persistent-chat-database-schema"></a>Esquema do banco de dados de Chat Persistente
 
Isso documenta o esquema do banco de dados de chat persistente no Skype for Business Server.
  
O banco de dados de chat persistente refere-se ao banco de dados correspondente às funções de servidor back-end do Skype for Business Server **PersistentChatStore** (correspondente ao banco de dados do MGC) e **PersistentChatComplianceStore** (correspondente ao banco de dados do mgccomp). O objetivo de publicar esse esquema é habilitá-lo para criar consultas e obter algumas ideias para criar relatórios úteis sobre uso de chat, salas ativas, principais pôsters e assim por diante.
  
> [!IMPORTANT]
> Reservamo-nos o direito de desenvolver este esquema. A Microsoft não faz nenhuma garantia para manter a compatibilidade com versões anteriores do esquema publicado. 
  
Siga estas práticas recomendadas:
  
- Não há\* suporte para Select//is porque a lista de colunas pode aumentar.
    
- Não há suporte para modificações de esquema geradas pelo usuário.
    
- Não há suporte para operações de gravação.
    
- Teste todas as consultas que você cria em bancos de dados de tamanho representativo para ter certeza de que as consultas podem ser executadas em um nível para atender às suas necessidades.
    
## <a name="in-this-section"></a>Nesta seção

- [Tabelas de lista de Servidores de Chat Persistente](list-of-persistent-chat-server-tables.md)
    
- [Lista de tabelas de conformidade do servidor de chat persistente no Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Detalhes da tabela do Servidor de Chat Persistente](persistent-chat-server-table-details.md)
    
- [Amostragem de consultas de banco de dados de Chat Persistente](sample-persistent-chat-database-queries.md)
    

