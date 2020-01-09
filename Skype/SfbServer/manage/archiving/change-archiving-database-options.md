---
title: Alterar opções de banco de dados de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumo: saiba como alterar as opções de banco de dados de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 3e7ae30e012464b6d1f72e323dd60ad397e7430d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992758"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Alterar opções de banco de dados de arquivamento no Skype for Business Server

**Resumo:** Saiba como alterar as opções de arquivamento de banco de dados para o Skype for Business Server.
  
Se você implantar o arquivamento usando o armazenamento do SQL Server para arquivar o armazenamento para qualquer um dos seus usuários, poderá fazer as seguintes alterações de armazenamento de banco de dados:
  
- Use um banco de dados do SQL Server diferente para arquivar o armazenamento. Isso inclui o banco de dados de arquivamento principal e qualquer banco de dados que você usa para o espelhamento do SQL Server.
    
- Alterne para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange. Se todos os usuários estiverem hospedados em seus servidores Exchange e você quiser usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, remova os bancos de dados da loja do SQL Server da sua topologia. 
    
Para fazer uma dessas alterações, você deve executar o construtor de topologias, fazer as alterações e, em seguida, publicar a topologia novamente. Não especifique o **arquivamento do SQL Server Store** ou habilite as informações de **espelhamento da loja do SQL Server** , a menos que você tenha usuários do Skype for Business que não são hospedados nos Exchange Servers.
  
## <a name="change-archiving-database-options"></a>Modificando opções do banco de dados de arquivamento

1. Em um computador que esteja executando o Skype for Business Server, ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo **Domain admins** e do grupo **RTCUniversalServerAdmins** , e que tenha permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Skype for Business Server (ou seja, para que o construtor de topologias possa configurar o controle de acesso discricional necessário listas (DACLs) ou uma conta com direitos equivalentes.
  
2. Iniciar o construtor de topologias.
    
3. Na árvore de console, navegue até o pool de front-ends no qual o arquivamento foi implantado e clique no nome do pool de front-ends no qual deseja alterar as opções de banco de dados.
    
4. No menu **Ação**, clique em **Editar propriedades**. 
    
5. Na caixa de diálogo **Editar propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Em **Arquivamento**, faça o seguinte:
    
   - Para alterar para um armazenamento existente diferente do SQL Server, em **Armazenamento de arquivamento do SQL Server**, na caixa de listagem suspensa, faça o seguinte:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
    
   - Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:
    
     - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
    
     - Para especificar uma nova loja do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo SQL Server Store** , faça o seguinte:
    
       - Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.
    
       - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       - Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação ao espelhamento** e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
   - Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:
    
     - Para usar uma loja existente do SQL Server para espelhamento, na caixa de listagem suspensa de **espelhamento do repositório do SQL Server** , clique no nome da loja do SQL Server que você deseja usar para espelhamento.
    
     - Para especificar uma nova loja do SQL Server para espelhamento, clique em **novo**e, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:
    
       a. No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.
    
       b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       c. Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação ao espelhamento** e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
   - Se você habilitar o espelhamento do SQL Server e quiser adicionar ou alterar uma testemunha de espelhamento do SQL Server (uma terceira instância do SQL Server separada que pode detectar a integridade do servidor SQL Server principal e as instâncias de espelhamento), marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** e siga um destes procedimentos:
    
      a. Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.
    
      b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
      c. Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação ao espelhamento** e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
   - Para alternar para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange (se todos os usuários na sua implantação estiverem hospedados em seus servidores Exchange), exclua todas as informações para arquivar bancos de dados.
    
     > [!IMPORTANT]
     > Se você tiver usuários do Skype for Business que não são hospedados nos Exchange Servers, não exclua as informações da loja do SQL Server. 
  
8. Para salvar a configuração, clique em **OK**.
    
    > [!IMPORTANT]
    > As alterações feitas no construtor de topologias não entram em vigor até que você publique a nova topologia. Para obter detalhes, consulte [Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Alterar a localização do banco de dados de arquivamento usando o Windows PowerShell

Na maioria dos casos, você não precisará mudar a localização do banco de dados de arquivamento, que é especificado ao instalar o servidor de arquivamento. Mas se ocorrer uma falha de hardware ou outro problema, você poderá apontar o servidor de arquivamento para um novo banco de dados usando o cmdlet **Set-CsArchivingServer**.
  
O exemplo a seguir altera a localização do banco de dados de arquivamento para o servidor de arquivamento ArchivingServer: ATL-cs-001.contoso.com. Neste exemplo, o novo banco de dados está localizado em ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


