---
title: Remover o banco de dados do SQL Server para um pool de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um pool de Front-End ou reconfigure o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
ms.openlocfilehash: 65fd0367051e32aa081fa13859632504e1331669
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028604"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Remover o banco de dados do SQL Server para um pool de Front-End

Depois de remover um pool de Front-End ou reconfigure o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologia

1. Do Skype para Business Server 2019 servidor Front-End, abra o construtor de topologia e baixe a topologia existente. 
    
2. No construtor de topologias, navegue até **Componentes compartilhados** e depois **Repositórios do SQL Server**, clique com o botão a instância do SQL Server associada ao pool de Front-End removido ou reconfigurado e clique em **Excluir**.
    
3. Publique a topologia e verifique o status de replicação. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para remover os bancos de dados de aplicativo e de usuário do SQL server

1. Para remover os bancos de dados no SQL server, você deve ser membro do grupo de sysadmins do SQL Server para o qual você está removendo os arquivos de banco de dados do SQL server. 
    
2. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
3. Para remover o banco de dados para o repositório de usuário do pool, digite:
    
  ```
  Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeado (isto é, se houver uma definida). 
    
4. Para remover o banco de dados para o repositório de aplicativos do pool, digite:
    
  ```
  Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    Onde _ \<FQDN\> _ é o FQDN do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeado (isto é, se houver uma definida). 
    
5. Quando o cmdlet **Uninstall-CsDataBase** solicita a confirmação de ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e Enter se você deseja parar o cmdlet (se houver erros). 
    

