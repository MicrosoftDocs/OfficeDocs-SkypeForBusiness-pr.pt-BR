---
title: Expansor de Configurações de Repositório SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Para editar as propriedades de um banco de dados SQL Server, você deve alterar a instância do banco de dados do SQL Server. Não é possível usar a caixa de diálogo Editar propriedades para executar tarefas, como mover seu banco de dados do servidor de arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo Editar propriedades para alterar a instância do SQL Server que hospeda o repositório de gerenciamento central.
ms.openlocfilehash: 2d9f03f7aed8aecc591a3f7c9177b5286fb3772b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684344"
---
# <a name="sql-store-settings-expander"></a>Expansor de Configurações de Repositório SQL
 
Para editar as propriedades de um banco de dados SQL Server, você deve alterar a instância do banco de dados do SQL Server. Não é possível usar a caixa de diálogo **Editar propriedades** para executar tarefas, como mover seu banco de dados do servidor de arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo **Editar propriedades** para alterar a instância do SQL Server que hospeda o repositório de gerenciamento central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Editando as propriedades de um banco de dados SQL Server

Para alterar a instância do SQL Server que é usada por qualquer banco de dados diferente do repositório de gerenciamento central, conclua o seguinte procedimento no construtor de topologias:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar uma instância do SQL Server

1. Selecione o banco de dados apropriado no nó **repositórios SQL** e clique em **Editar propriedades**.
    
2. Na caixa de diálogo **Editar propriedades** , siga um destes procedimentos:
    
   - Para usar a instância padrão do SQL Server, selecione **instância padrão** e clique em **OK**.
    
   - Para usar uma instância de banco de dados nomeado, selecione **instância nomeada**, insira o nome da instância na caixa de texto e clique em **OK**. Você deve inserir apenas o nome da instância (por exemplo, ArchivingInstance), e não todo o caminho do SQL Server.
    
Quando você estiver trabalhando na caixa de diálogo **Editar propriedades** , o construtor de topologias não verificará se a instância do banco de dados que você inseriu é uma instância válida. Por exemplo, se você inadvertidamente typeArchivingInstanec como o nome da instância e, em seguida, clique em **OK**, o construtor de topologias aceitará essa instância inválida. Antes de poder publicar esta topologia, você deve corrigir esse erro: se uma instância do SQL Server não puder ser encontrada, o construtor de topologias não criará essa instância para você.
  

