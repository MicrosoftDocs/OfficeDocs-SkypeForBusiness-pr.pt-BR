---
title: Esquema do banco de dados de Chat Persistente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Isso documenta o esquema do banco de dados de Chat Persistente no Skype for Business Server.
---

# <a name="persistent-chat-database-schema"></a>Esquema do banco de dados de Chat Persistente
 
Isso documenta o esquema do banco de dados de Chat Persistente no Skype for Business Server.
  
O banco de dados de Chat Persistente refere-se ao banco de dados correspondente às funções de servidor back-end **Skype for Business Server PersistentChatStore** (correspondente ao banco de dados mgc) e **PersistentChatComplianceStore** (correspondente ao banco de dados mgccomp). O objetivo da publicação desse esquema é permitir que você crie consultas e obtenha algumas ideias sobre a criação de relatórios úteis sobre uso de chat, salas ativas, pôsteres principais e etc.
  
> [!IMPORTANT]
> Reservamo-nos o direito de desenvolver este esquema. A Microsoft não garante manter compatibilidade com versões anteriores completa para esse esquema publicado. 
  
Sigas estas práticas recomendadas:
  
- Nenhum SELECT\* // é suportado porque a lista de colunas pode crescer.
    
- Nenhuma modificação de esquema gerado pelo usuário é suportada.
    
- Nenhuma operações de gravação é suportada.
    
- Teste quaisquer consultas que você crie em bancos de dados de tamanho representativo para certificar-se de que as consultas podem ser executadas em um nível que atenda às suas necessidades.
    
## <a name="in-this-section"></a>Nesta seção

- [Tabelas de lista de Servidores de Chat Persistente](list-of-persistent-chat-server-tables.md)
    
- [Lista de tabelas de conformidade do Servidor de Chat Persistente Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Detalhes da tabela do Servidor de Chat Persistente](persistent-chat-server-table-details.md)
    
- [Amostragem de consultas de banco de dados de Chat Persistente](sample-persistent-chat-database-queries.md)
    

