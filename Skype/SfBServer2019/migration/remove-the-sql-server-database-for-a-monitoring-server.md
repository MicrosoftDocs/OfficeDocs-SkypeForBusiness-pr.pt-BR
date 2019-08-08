---
title: Remover banco de dados do SQL Server de um servidor de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um servidor de monitoramento, você pode remover os bancos de dados do SQL Server que hospedam os dados do servidor. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
ms.openlocfilehash: 1034abac5b257200504c599fe8655a788d638aa0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241546"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Remover banco de dados do SQL Server de um servidor de Monitoramento

Depois de remover um servidor de monitoramento, você pode remover os bancos de dados do SQL Server que hospedam os dados do servidor. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologias

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.
    
2. No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, repositórios do **SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de monitoramento removido ou reconfigurado e clique em **excluir**.
    
3. Publique a topologia e, em seguida, verifique o status de replicação.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para remover os arquivos de banco de dados do SQL Server

1. Para remover os bancos de dados no servidor baseado no SQL Server, você deve ser membro do grupo Administradores do SQL Server para o servidor SQL Server no qual está removendo os arquivos de banco de dados.
    
2. Abra o Shell de gerenciamento do Skype for Business Server.
    
3. Na linha de comando, digite o seguinte:
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de _ \<dados\> _ e a instância é a instância do banco de dados nomeado opcional. 
    
4. Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme as ações, leia as informações e, em seguida, pressione Y (ou Enter) para continuar, ou pressione N e, em seguida, insira se você deseja parar o cmdlet (se houver erros). 
    

