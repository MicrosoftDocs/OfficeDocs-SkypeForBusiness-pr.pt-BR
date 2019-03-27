---
title: Remover o banco de dados do Servidor SQL de um servidor de Arquivamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
ms.openlocfilehash: acb402dd6cb28be5b607b8a358524dfc0c1fea69
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875437"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Remover o banco de dados do Servidor SQL de um servidor de Arquivamento

Depois de remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologia

1. No Skype para Business Server 2019 servidor Front-End, abra o construtor de topologias.
    
2. No construtor de topologias, navegue até **Componentes compartilhados** e depois **Repositórios do SQL Server**, com o botão direito do SQL Server instância associados a removido ou reconfigurado o servidor de arquivamento e clique em **Excluir**.
    
3. Publique a topologia e verifique o status de replicação. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para remover os arquivos de banco de dados do SQL Server

1. Para remover os bancos de dados no SQL Server, você deve ser membro do grupo de sysadmins do SQL Server para o qual você está removendo os arquivos de banco de dados do SQL Server. 
    
2. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
3. Na linha de comando, digite o seguinte:
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeado (isto é, se houver uma definida). 
    
4. Quando o cmdlet **Uninstall-CsDataBase** solicita a confirmação de ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e Enter se você deseja parar o cmdlet (se houver erros). 
    

