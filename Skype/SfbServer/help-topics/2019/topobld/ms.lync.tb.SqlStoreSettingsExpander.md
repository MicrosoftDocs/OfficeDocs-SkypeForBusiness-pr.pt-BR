---
title: Expansor de Configurações de Repositório SQL
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância de banco de dados do SQL Server. Você não pode usar a caixa de diálogo Editar propriedades para executar tarefas como mover o banco de dados do servidor de arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo Editar propriedades para alterar a instância do SQL Server que hospeda o repositório de gerenciamento Central.
ms.openlocfilehash: d1b5287344095c062421a6afc56d620c81584fd3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235189"
---
# <a name="sql-store-settings-expander"></a>Expansor de Configurações de Repositório SQL
 
Para editar as propriedades de um banco de dados do SQL Server, você deve alterar a instância de banco de dados do SQL Server. Você não pode usar a caixa de diálogo **Editar propriedades** para executar tarefas como mover o banco de dados do servidor de arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo **Editar propriedades** para alterar a instância do SQL Server que hospeda o repositório de gerenciamento Central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Editando as propriedades de um banco de dados do SQL Server

Para alterar a instância do SQL Server que é usado por qualquer banco de dados que não seja o repositório de gerenciamento Central, complete o procedimento a seguir no construtor de topologia:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar uma instância do SQL Server

1. Selecione o banco de dados apropriado sob o nó **SQL armazena** e, em seguida, clique em **Editar propriedades**.
    
2. Na caixa de diálogo **Editar propriedades** , siga um destes procedimentos:
    
   - Para usar a instância do SQL Server padrão, selecione a **Instância padrão** e clique em **Okey**.
    
   - Para usar uma instância nomeada do banco de dados, selecione a **Instância nomeada**, insira o nome da instância na caixa de texto e, em seguida, clique em **Okey**. Você deve inserir apenas o nome da instância (por exemplo, ArchivingInstance) e não o caminho inteiro do SQL Server.
    
Quando você estiver trabalhando na caixa de diálogo **Editar propriedades** , construtor de topologia não verificará se a instância do banco de dados que você digitou é uma instância válida. Por exemplo, se você inadvertidamente typeArchivingInstanec como o nome da instância e, em seguida, clique em **Okey**, construtor de topologia aceitará essa instância inválida. Antes de publicar essa topologia, você deve corrigir este erro: se não for encontrada uma instância do SQL Server, construtor de topologia não criará essa instância para você.
  

