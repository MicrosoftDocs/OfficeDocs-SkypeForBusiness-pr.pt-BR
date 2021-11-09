---
title: Expansor de Configurações de Repositório SQL
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um banco de dados SQL Server, você deve alterar a instância SQL Server banco de dados. Não é possível usar a caixa de diálogo Editar Propriedades para executar tarefas como mover seu banco de dados do Servidor de Arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo Editar Propriedades para alterar a instância do SQL Server que hospeda o armazenamento de Gerenciamento Central.
ms.openlocfilehash: f77eeb2f397b02231b7d1b004c243f218967c040
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864098"
---
# <a name="sql-store-settings-expander"></a>Expansor de Configurações de Repositório SQL
 
Para editar as propriedades de um banco de dados SQL Server, você deve alterar a instância SQL Server banco de dados. Não é possível usar a caixa de diálogo **Editar Propriedades** para executar tarefas como mover seu banco de dados do Servidor de Arquivamento de um computador para outro. Além disso, você não pode usar a caixa de diálogo **Editar Propriedades** para alterar a instância do SQL Server que hospeda o armazenamento de Gerenciamento Central.
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>Editando as propriedades de um banco de SQL Server de dados

Para alterar a instância de SQL Server usada por qualquer banco de dados diferente do armazenamento de Gerenciamento Central, conclua o seguinte procedimento no Construtor de Topologias:
  
### <a name="to-modify-an-instance-of-sql-server"></a>Para modificar uma instância de SQL Server

1. Selecione o banco de dados apropriado no nó **Repositórios do SQL** e clique em **Editar Propriedades**.
    
2. Na caixa de diálogo **Editar Propriedades**, execute um destes procedimentos:
    
   - Para usar a instância SQL Server padrão, selecione **Instância** Padrão e clique em **OK**.
    
   - Para usar uma instância de banco de dados nomeada, selecione **Instância nomeada**, insira o nome da instância na caixa de texto e clique em **OK**. Você deve inserir apenas o nome da instância (por exemplo, ArchivingInstance) e não todo o caminho SQL Server.
    
Quando você estiver trabalhando na caixa de diálogo **Editar Propriedades,** o Construtor de Topologias não verificará se a instância do banco de dados inserida é uma instância válida. Por exemplo, se você digitar InadvertidamenteArchivingInstanec como o nome da instância e clicar em **OK**, Construtor de Topologia aceitará essa instância inválida. Antes de publicar essa topologia, você deve corrigir esse erro: se uma instância SQL Server não puder ser encontrada, o Construtor de Topologias não criará essa instância para você.
  

