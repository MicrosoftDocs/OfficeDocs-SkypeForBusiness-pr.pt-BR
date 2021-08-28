---
title: Remover o banco de dados do SQL Server para um pool Front-End
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Depois de remover um pool de Front-End ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados SQL Server que hospedaram os dados do pool. Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.
ms.openlocfilehash: 2a11057811035b0dc51810d3a6b7eb8220c7df1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580105"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Remover o banco de dados do SQL Server para um pool Front-End

Depois de remover um pool de Front-End ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados SQL Server que hospedaram os dados do pool. Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados SQL Server usando o Construtor de Topologias

1. Na página Skype for Business Server 2019, abra o Construtor de Topologias e baixe a topologia existente. 
    
2. No Construtor de Topologias, navegue até **Componentes Compartilhados** e, em seguida, SQL Server Stores , clique com o botão direito do mouse na instância SQL Server associada ao pool de Front-End removido ou reconfigurado e clique em  **Excluir**.
    
3. Publique a topologia e verifique o status da replicação. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para remover bancos de dados de usuários e aplicativos do SQL servidor

1. Para remover os bancos de dados no servidor SQL, você deve ser membro do grupo SQL Server sysadmins para o servidor SQL onde você está removendo os arquivos de banco de dados. 
    
2. Abra Skype for Business Server Shell de Gerenciamento.
    
3. Para remover o banco de dados do repositório de usuários do pool, digite:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde está o FQDN (nome de domínio totalmente qualificado) do servidor de banco de dados e é a instância nomeada do banco de dados  _\<FQDN\>_  _\<instance\>_ (ou seja, se uma foi definida). 
    
4. Para remover o banco de dados do repositório de aplicativos do pool, digite:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde está o FQDN do servidor de banco de dados e é a instância nomeada do banco de dados  _\<FQDN\>_  _\<instance\>_ (ou seja, se uma foi definida). 
    
5. Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme as ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e digite se quiser interromper o cmdlet (se houver erros). 
    

