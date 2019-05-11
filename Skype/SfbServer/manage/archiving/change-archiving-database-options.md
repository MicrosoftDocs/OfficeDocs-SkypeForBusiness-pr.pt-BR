---
title: Alterar as opções de banco de dados de arquivamento no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumo: Saiba como alterar as opções de banco de dados arquivamento para Skype para Business Server.'
ms.openlocfilehash: b2ffa1cfd9686be941cca2a1ffdc2684006dde50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884962"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Alterar as opções de banco de dados de arquivamento no Skype para Business Server

**Resumo:** Saiba como alterar as opções de banco de dados arquivamento para Skype para Business Server.
  
Se você implantar o arquivamento usando o armazenamento do SQL Server para armazenamento de arquivamento para qualquer um dos seus usuários, você pode fazer o seguinte banco de dados alterações de armazenamento:
  
- Use outro banco de dados do SQL Server para armazenamento de arquivamento. Isso inclui o banco de dados de arquivamento primário e de qualquer banco de dados que você pode usar para espelhamento do SQL Server.
    
- Alterne para a integração do Microsoft Exchange para armazenar arquivos nos servidores do Exchange e dados de arquivamento. Se todos os usuários estão hospedados em seus servidores Exchange e você deseja usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, você deve remover os bancos de dados de repositório do SQL Server da sua topologia. 
    
Para tornar qualquer uma dessas alterações, você deve executar o construtor de topologias, faça as alterações e publique a topologia novamente. Não especifica informações do **repositório de arquivamento do SQL Server** ou **espelhamento do repositório de habilitar o SQL Server** , a menos que tenha Skype para usuários corporativos que não esteja hospedados em servidores do Exchange.
  
## <a name="change-archiving-database-options"></a>Modificando opções do banco de dados de arquivamento

1. Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo local de usuários (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo de usuários local, mas para publicar uma topologia, o que é necessário para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo **Administradores** de domínio e o **RTCUniversalSer verAdmins** grupo e que tem permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o Skype para repositório de arquivos do servidor de negócios (ou seja, de modo que o construtor de topologia pode configurar o controle de acesso discricionário necessários listas (DACLs) ou uma conta com direitos equivalentes.
  
2. Inicie o construtor de topologias.
    
3. Na árvore de console, navegue até o pool de front-ends no qual o arquivamento foi implantado e clique no nome do pool de front-ends no qual deseja alterar as opções de banco de dados.
    
4. No menu **Ação**, clique em **Editar propriedades**. 
    
5. Na caixa de diálogo **Editar propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Em **Arquivamento**, faça o seguinte:
    
   - Para alterar para um armazenamento existente diferente do SQL Server, em **Armazenamento de arquivamento do SQL Server**, na caixa de listagem suspensa, faça o seguinte:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
    
   - Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:
    
     - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.
    
     - Para especificar um novo repositório do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , faça o seguinte:
    
       - Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.
    
       - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       - Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.
    
   - Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:
    
     - Para usar um armazenamento existente do SQL Server para espelhamento, na caixa de listagem suspensa **espelho do repositório de arquivamento do SQL Server** , clique no nome do repositório do SQL Server que você deseja usar para espelhamento.
    
     - Para especificar um novo repositório do SQL Server para espelhamento, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , siga um destes procedimentos:
    
       a. Em **FQDN do SQL Server**, especifique o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.
    
       b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
       c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.
    
   - Se você habilitar o espelhamento do SQL Server e deseja adicionar ou alterar um (uma terceira, separada instância do SQL Server que pode detectar a integridade das instâncias principais do SQL Server server e espelho) de testemunha de espelhamento do SQL Server, selecione a testemunha de espelhamento do SQL Server do uso de **para Habilitar o failover automático** caixa de seleção e, em seguida, execute um dos seguintes:
    
      a. Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo SQL Server testemunha de espelhamento.
    
      b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
      c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.
    
   - Para alternar para a integração do Microsoft Exchange para armazenar dados de arquivamento e arquivos nos servidores do Exchange (se todos os usuários em sua implantação são hospedados em seus servidores do Exchange), exclua todas as informações de bancos de dados de arquivamento.
    
     > [!IMPORTANT]
     > Se você tiver quaisquer Skype para usuários corporativos que não esteja hospedado em servidores do Exchange, não exclua as informações de repositório do SQL Server. 
  
8. Para salvar a configuração, clique em **OK**.
    
    > [!IMPORTANT]
    > As alterações feitas no construtor de topologia não entrarão em vigor até que você publica a nova topologia. Para obter detalhes, consulte [bancos de dados de arquivamento de adicionar a uma implantação existente no Skype para Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Alterar a localização do banco de dados de arquivamento usando o Windows PowerShell

Na maioria dos casos, você não precisará mudar a localização do banco de dados de arquivamento, que é especificado ao instalar o servidor de arquivamento. Mas se ocorrer uma falha de hardware ou outro problema, você poderá apontar o servidor de arquivamento para um novo banco de dados usando o cmdlet **Set-CsArchivingServer**.
  
O exemplo a seguir altera o local do banco de dados de arquivamento para o archivingserver: ATL-cs-001.contoso.com o servidor de arquivamento. Neste exemplo, o novo banco de dados está localizado em ArchivingDatabase:atl-sql-001.contoso.com:
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


