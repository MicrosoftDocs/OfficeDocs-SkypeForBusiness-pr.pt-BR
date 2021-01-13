---
title: Alterar opções de banco de dados de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumo: Saiba como alterar as opções de banco de dados de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817691"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Alterar opções de banco de dados de arquivamento no Skype for Business Server

**Resumo:** Saiba como alterar as opções de banco de dados de arquivamento para o Skype for Business Server.
  
Se você implantar o arquivamento usando o armazenamento do SQL Server para o armazenamento de arquivamento de qualquer um dos seus usuários, poderá fazer as seguintes alterações de armazenamento de banco de dados:
  
- Use um banco de dados do SQL Server diferente para o armazenamento de arquivamento. Isso inclui o banco de dados de Arquivamento primário e qualquer banco de dados usado para espelhamento do SQL Server.
    
- Alternar para a integração com o Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange. Se todos os seus usuários estão em seus servidores Exchange e você deseja usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, você deve remover os bancos de dados de armazenamento do SQL Server da sua topologia. 
    
Para fazer qualquer uma dessas alterações, execute o Construtor de Topologias, faça as alterações e publique a topologia novamente. Não especifique **o armazenamento do SQL Server** de arquivamento ou habilitar informações de espelhamento do armazenamento do SQL **Server,** a menos que você tenha usuários do Skype for Business que não estão instalados em servidores exchange.
  
## <a name="change-archiving-database-options"></a>Modificar opções do banco de dados de arquivamento

1. Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo **Admins.** do Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o armazenamento de arquivos do Skype for Business Server (ou seja, para que o Construtor de Topologias possa configurar as listas de controle de acesso discricionário (DACLs) necessárias ou uma conta com direitos equivalentes.
  
2. Inicie o Construtor de topologia.
    
3. Na árvore de console, navegue até o pool de front-ends no qual o arquivamento foi implantado e clique no nome do pool de front-ends no qual deseja alterar as opções de banco de dados.
    
4. No menu **Ação**, clique em **Editar Propriedades**. 
    
5. Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Em **Arquivamento**, faça o seguinte:
    
   - Para alterar para um armazenamento existente diferente do SQL Server, em **Armazenamento de arquivamento do SQL Server**, na caixa de listagem suspensa, faça o seguinte:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
    
   - Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir Novo Armazenamento do SQL Server**, faça o seguinte:
    
     - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
    
     - Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, na caixa de diálogo Definir Novo Armazenamento do **SQL Server,** faça o seguinte:
    
       - No **FQDN do SQL Server,** especifique o FQDN do servidor no qual você deseja criar o novo armazenamento do SQL Server.
    
       - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       - Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.
    
   - Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:
    
     - Para usar um armazenamento existente do SQL **Server** para espelhamento, na caixa de listagem de espelho do armazenamento do SQL Server de arquivamento, clique no nome do armazenamento do SQL Server que você deseja usar para espelhamento.
    
     - Para especificar um novo armazenamento do SQL Server para espelhamento, clique em Novo e, em seguida, na caixa de diálogo Definir Novo Armazenamento do **SQL Server,** faça um dos seguintes:
    
       a. No **FQDN do SQL Server,** especifique o FQDN do SQL Server no qual você deseja criar o novo armazenamento do SQL Server.
    
       b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.
    
   - Se você habilitar o espelhamento do SQL Server e quiser adicionar ou alterar uma testemunha de espelhamento do SQL Server (uma terceira instância separada do SQL Server que pode detectar a saúde do servidor SQL Server primário e das instâncias de espelho), selecione a caixa de seleção Usar espelhamento do SQL Server para habilitar a caixa de seleção de **failover** automático e, em seguida, faça um dos seguintes:
    
      a. No **FQDN do SQL Server,** especifique o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.
    
      b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
      c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.
    
   - Para alternar para a integração com o Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange (se todos os usuários em sua implantação estão armazenados em seus servidores Exchange), exclua todas as informações dos bancos de dados de Arquivamento.
    
     > [!IMPORTANT]
     > Se você tiver usuários do Skype for Business que não estão instalados em servidores Exchange, não exclua as informações do armazenamento do SQL Server. 
  
8. Para salvar a configuração, clique em **OK**.
    
    > [!IMPORTANT]
    > As alterações feitas no Construtor de Topologias não entrarão em vigor até que você publique a nova topologia. Para obter detalhes, [consulte Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server.](../../deploy/deploy-archiving/add-archiving-databases.md) 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Alterar o local do banco de dados de Arquivamento usando o Windows PowerShell

Na maioria dos casos, não será necessário alterar o local do banco de dados de Arquivamento, que é especificado quando você instala o Servidor de Arquivamento. No entanto, se ocorrer uma falha de hardware ou outro problema, você poderá apontar o Servidor de Arquivamento para um novo banco de dados usando o cmdlet **Set-CsArchivingServer.**
  
O exemplo a seguir altera o local do banco de dados de Arquivamento para o Servidor de Arquivamento ArchivingServer:atl-cs-001.contoso.com. Neste exemplo, o novo banco de dados está localizado em ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


