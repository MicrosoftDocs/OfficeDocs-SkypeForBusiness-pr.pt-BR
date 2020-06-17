---
title: Remover o banco de dados do Servidor SQL de um servidor de Arquivamento
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
description: Após remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedaram os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753303"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Remover o banco de dados do Servidor SQL de um servidor de Arquivamento

Após remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedaram os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologia

1. No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.
    
2. No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de arquivamento removido ou reconfigurado e clique em **excluir**.
    
3. Publique a topologia e verifique o status da replicação. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para remover os arquivos do banco de dados do SQL Server

1. Para remover os bancos de dados no SQL Server, você deve ser um membro do grupo sysadmins do SQL Server de onde você está removendo os arquivos de banco de dados. 
    
2. Abra o Shell de gerenciamento do Skype for Business Server.
    
3. Na linha de comando, digite o seguinte:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde _\<FQDN\>_ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados e _\<instance\>_ é a instância de banco de dados nomeada (isto é, se houver uma definida). 
    
4. Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione Y (ou Enter) para continuar, ou pressione N e, em seguida, Enter se você deseja interromper o cmdlet (se houver erros). 
    

