---
title: Remover o banco de dados do SQL Server de um servidor de Monitoramento
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
description: Depois de remover um Servidor de Monitoramento, você pode remover os bancos de dados SQL Server que hospedaram os dados do servidor. Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.
ms.openlocfilehash: cadb24e2dcbe88e643c234dd8559d07406e5566e3e7eea0e33eec796cd98cf52
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280386"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Remover o banco de dados do SQL Server de um servidor de Monitoramento

Depois de remover um Servidor de Monitoramento, você pode remover os bancos de dados SQL Server que hospedaram os dados do servidor. Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados SQL Server usando o Construtor de Topologias

1. No servidor front-end Skype for Business Server 2019, abra o Construtor de Topologias.
    
2. No Construtor de Topologias, navegue até **Componentes Compartilhados** e, em seguida, SQL Server Stores , clique com o botão direito do mouse na instância SQL Server associada ao Servidor de Monitoramento removido ou reconfigurado e clique em  **Excluir**.
    
3. Publique a topologia e verifique o status da replicação.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para remover os arquivos do banco de dados do SQL Server

1. Para remover os bancos de dados no servidor baseado em SQL Server, você deve ser membro do grupo SQL Server sysadmins para o servidor SQL Server onde você está removendo os arquivos de banco de dados.
    
2. Abra o Shell Skype for Business Server Gerenciamento.
    
3. Na linha de comando, digite o seguinte:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Onde está o FQDN (nome de domínio totalmente qualificado) do servidor de banco de dados e é a instância opcional nomeada do banco  _\<FQDN\>_ de  _\<instance\>_ dados. 
    
4. Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme as ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e digite se quiser interromper o cmdlet (se houver erros). 
    

