---
title: Remover o banco de dados do Servidor SQL para um pool Front-End
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Após remover um pool de front-ends ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedam os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753403"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Remover o banco de dados do Servidor SQL para um pool Front-End

Após remover um pool de front-ends ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedam os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologia

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias e baixe a topologia existente. 
    
2. No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao pool de front-ends removido ou reconfigurado e clique em **excluir**.
    
3. Publique a topologia e verifique o status da replicação. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para remover os bancos de dados do usuário e do aplicativo do SQL Server

1. Para remover os bancos de dados no SQL Server, você deve ser membro do grupo sysadmins do SQL Server para o SQL Server em que você está removendo os arquivos de banco de dados. 
    
2. Abra o Shell de gerenciamento do Skype for Business Server.
    
3. Para remover o banco de dados do repositório de usuários do pool, digite:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde _\<FQDN\>_ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados e _\<instance\>_ é a instância de banco de dados nomeada (isto é, se houver uma definida). 
    
4. Para remover o banco de dados do repositório de aplicativos do pool, digite:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde _\<FQDN\>_ é o FQDN do servidor de banco de dados e _\<instance\>_ é a instância de banco de dados nomeada (isto é, se houver uma definida). 
    
5. Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione Y (ou Enter) para continuar, ou pressione N e, em seguida, Enter se você deseja interromper o cmdlet (se houver erros). 
    

