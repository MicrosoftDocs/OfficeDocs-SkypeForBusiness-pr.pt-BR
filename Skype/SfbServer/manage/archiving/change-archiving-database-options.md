---
title: Alterar opções de banco de dados de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumo: saiba como alterar as opções de banco de dados de arquivamento para Skype for Business Server.'
ms.openlocfilehash: 7a6d0c5168eded42a45996cb8154c4dd6f757a4c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399755"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Alterar opções de banco de dados de arquivamento no Skype for Business Server

**Resumo:** Saiba como alterar as opções de banco de dados de arquivamento para Skype for Business Server.
  
Se você implantar o arquivamento usando SQL Server armazenamento para arquivamento de armazenamento para qualquer um dos seus usuários, poderá fazer as seguintes alterações de armazenamento de banco de dados:
  
- Use um banco de SQL Server de dados diferente para arquivamento de armazenamento. Isso inclui o banco de dados de Arquivamento principal e qualquer banco de dados que você usa para SQL Server espelhamento.
    
- Alternar para a integração Exchange Microsoft para armazenar dados e arquivos de arquivamento em Exchange servidores. Se todos os seus usuários estão em seus servidores Exchange e você deseja usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, remova os bancos de dados de armazenamento SQL Server da sua topologia. 
    
Para fazer uma dessas alterações, você deve executar o Construtor de Topologias, fazer as alterações e publicar a topologia novamente. Não especifique **o arquivamento SQL Server ou** Habilitar  SQL Server informações de espelhamento do armazenamento, a menos que você tenha Skype for Business usuários que não estão em casa em servidores Exchange.
  
## <a name="change-archiving-database-options"></a>Modificar opções do banco de dados de arquivamento

1. Em um computador que está executando Skype for Business Server, ou no qual as ferramentas administrativas Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo Usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta membro do grupo Usuários local, mas para publicar uma topologia, que é necessária para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (ou seja,  ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o armazenamento de arquivos Skype for Business Server (ou seja, para que o Construtor de Topologias possa configurar as listas de controle de acesso discricionário necessárias (DACLs) ou uma conta com direitos equivalentes.
  
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
    
     - Para especificar um novo SQL Server, clique em **Novo** e, na caixa de diálogo Definir Novo SQL Server **Store**, faça o seguinte:
    
       - Em **SQL Server FQDN**, especifique o FQDN do servidor no qual você deseja criar o novo SQL Server store.
    
       - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       - Se SQL Server instância especificada estiver em uma relação de espelhamento, selecione **a** caixa de seleção Esta SQL está na caixa de seleção Relação de espelhamento e, em Número da porta **Espelho,** especifique o número da porta.
    
   - Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:
    
     - Para usar um armazenamento de SQL Server existente para espelhamento, **na** caixa de listagem de listagem de espelhamento de armazenamento de espelhos de arquivamento SQL Server, clique no nome do SQL Server store que você deseja usar para espelhamento.
    
     - Para especificar um novo SQL Server para espelhamento, clique em Novo e, em **seguida,** na caixa de diálogo Definir Novo SQL Server **Store**, faça um dos seguintes:
    
       a. Em **SQL Server FQDN**, especifique o FQDN do SQL Server no qual você deseja criar o novo SQL Server store.
    
       b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       c. Se SQL Server instância especificada estiver em uma relação de espelhamento, selecione **a** caixa de seleção Esta SQL está na caixa de seleção Relação de espelhamento e, em Número da porta **Espelho,** especifique o número da porta.
    
   - Se você habilitar SQL Server espelhamento e quiser adicionar ou alterar uma testemunha de espelhamento de SQL Server (uma terceira instância de SQL Server separada que pode detectar a saúde das instâncias de espelho e servidor do SQL Server principal), selecione a testemunha de espelhamento Use SQL Server para habilitar **o failover automático**  caixa de seleção e, em seguida, faça um dos seguintes:
    
      a. Em **SQL Server FQDN**, especifique o FQDN do servidor no qual você deseja criar a nova SQL Server de espelhamento.
    
      b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
      c. Se SQL Server instância especificada estiver em uma relação de espelhamento, selecione **a** caixa de seleção Esta SQL está na caixa de seleção Relação de espelhamento e, em Número da porta **Espelho,** especifique o número da porta.
    
   - Para alternar para Exchange microsoft para armazenar dados e arquivos de arquivamento em servidores Exchange (se todos os usuários em sua implantação estão em seus servidores Exchange), exclua todas as informações para bancos de dados de arquivamento.
    
     > [!IMPORTANT]
     > Se você tiver Skype for Business usuários que não estão em casa Exchange servidores, não exclua as informações SQL Server armazenamento. 
  
8. Para salvar a configuração, clique em **OK**.
    
    > [!IMPORTANT]
    > As alterações feitas no Construtor de Topologias não entrarão em vigor até publicar a nova topologia. Para obter detalhes, [consulte Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Altere o local do banco de dados de Arquivamento usando Windows PowerShell

Na maioria dos casos, você não precisará alterar o local do banco de dados de Arquivamento, que é especificado ao instalar o Servidor de Arquivamento. No entanto, se ocorrer uma falha de hardware ou outro problema, você poderá apontar o Servidor de Arquivamento para um novo banco de dados usando o cmdlet **Set-CsArchivingServer** .
  
O exemplo a seguir altera o local do banco de dados de Arquivamento para o Servidor de ArquivamentoServer:atl-cs-001.contoso.com Arquivamento. Neste exemplo, o novo banco de dados está localizado em ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


