---
title: Remover o banco de dados do SQL Server para um servidor de monitoramento
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um Monitoring Server, você pode remover os bancos de dados do SQL Server que hospedava os dados do servidor. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
ms.openlocfilehash: 85999f1bbb3fc443edcab9d1f1354f26187c6a75
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373354"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Remover o banco de dados do SQL Server para um servidor de monitoramento

Depois de remover um Monitoring Server, você pode remover os bancos de dados do SQL Server que hospedava os dados do servidor. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologia

1. No Skype para Business Server 2019 servidor Front-End, abra o construtor de topologias.
    
2. No construtor de topologias, navegue até **Componentes compartilhados** e depois **Repositórios do SQL Server**, com o botão direito do SQL Server instância associados a removido ou reconfigurado Monitoring Server e, em seguida, clique em **Excluir**.
    
3. Publique a topologia e verifique o status de replicação.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para remover os arquivos de banco de dados do SQL Server

1. Para remover os bancos de dados no servidor baseado em SQL Server, você deve ser membro do grupo de sysadmins do SQL Server para o SQL server onde você está removendo os arquivos de banco de dados.
    
2. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
3. Na linha de comando, digite o seguinte:
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeada opcional. 
    
4. Quando o cmdlet **Uninstall-CsDataBase** solicita a confirmação de ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e Enter se você deseja parar o cmdlet (se houver erros). 
    

