---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: Leia este tópico para aprender a adicionar bancos de dados de arquivamento à sua implantação do Skype for Business Server.'
ms.openlocfilehash: 2110a6c82aed473fdc07e5796075aabdb50c7086
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278994"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server
 
**Resumo:** Leia este tópico para aprender a adicionar bancos de dados de arquivamento à sua implantação do Skype for Business Server.
  
É necessário incorporar o arquivamento à sua topologia antes de configurar sua implantação para suportar o arquivamento. As informações neste tópico explicam como usar o construtor de topologias para:
  
- Adicionar um banco de dados de arquivamento à sua topologia.
    
- Publique a topologia atualizada para adicionar o banco de dados de arquivamento à implantação do Skype for Business Server.
    
> [!NOTE]
> Se você quiser usar a integração do Microsoft Exchange para armazenar arquivos e dados do arquivamento em servidores Exchange para todos os usuários em sua implantação, não especifique a **loja do SQL Server** do SQL Server ou use as informações de espelhamento da **loja do SQL Server** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Adicionar um banco de dados de arquivamento à sua topologia

1. Em um computador que esteja executando o Skype for Business Server, ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
2. Iniciar o construtor de topologias.
    
3. Na árvore do console, navegue até o pool de Front-Ends no qual você deseja implantar o arquivamento e clique no nome do pool.
    
4. No menu **Ação**, clique em **Editar Propriedades**. 
    
5. Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Marque a caixa de seleção **Arquivamento**.
    
8. Em **arquivar repositório do SQL Server,** siga um destes procedimentos:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar. Se todos os seus usuários estiverem hospedados no Microsoft Exchange Server 2013 ou superior, você poderá arquivar as comunicações do Skype for Business para todos os usuários no Exchange. Nesse caso, você não precisa configurar o repositório de arquivamento do SQL Server.
    
   - Para especificar uma nova loja do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo SQL Server Store** , faça o seguinte:
    
   - Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.
    
   - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
   - Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
9. Se você quiser usar o espelhamento da loja do SQL Server, selecione Habilitar o espelhamento da **loja do SQL Server**e, em seguida, faça o seguinte:
    
   - Para usar uma loja existente do SQL Server para espelhamento, na caixa de listagem suspensa de espelhamento do **repositório do SQL Server** , clique no nome da loja do SQL Server que você deseja usar para espelhamento.
    
   - Para especificar uma nova loja do SQL Server para espelhamento, clique em **novo**e, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:
    
     a. No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
     c. Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
   - Se você habilitar o espelhamento do SQL Server e quiser incluir uma testemunha de espelhamento do SQL Server (uma terceira instância separada do SQL Server que pode detectar a integridade das instâncias primárias do SQL Server e do espelho), selecione o **recurso usar a testemunha de espelhamento do SQL Server para habilitar a configuração automática falha** na caixa de seleção e siga um destes procedimentos:
    
     a. Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
     c. Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.
    
10. Para salvar a configuração, clique em **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação

1. Em um computador que esteja executando o Skype for Business Server, ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo **Domain admins** e o **RTCUniversalServer Grupo Administradores** , e que tem permissões de controle total (ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Skype for Business Server (para que o construtor de topologias possa configurar a lista de controle de acesso discricional necessária) ou um conta com direitos equivalentes.
  
2. Abra a topologia que você criou na seção anterior usando o construtor de topologias.
    
3. Na árvore do console, clique com o botão direito do mouse em **Skype for Business Server**e, em seguida, clique em **publicar topologia**.
    
4. Na página **Publicar a topologia**, clique em **Avançar**.
    
5. Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**. 
    
    > [!NOTE]
    > Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados. os bancos de dados > somente em servidores SQL dedicados podem ser instalados usando-se o construtor de topologias. Bancos de dados em SQL Servers que são colocados com outros componentes de servidor devem ser instalados executando a instalação local em tal computador. 
  
6. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    > [!IMPORTANT]
    > Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado. Para obter detalhes, consulte [Configurar opções de arquivamento para o Skype for Business Server](configure-archiving-options.md) e [configurar as políticas de arquivamento para o Skype for Business Server](configure-archiving-policies.md). 
  

