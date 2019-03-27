---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua Skype para implantação de servidor de negócios.'
ms.openlocfilehash: 083b6329cdf27331ba861b96a74f94e2ae5aa912
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895311"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Adicionar bancos de dados de arquivamento a uma implantação existente no Skype para Business Server
 
**Resumo:** Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua Skype para implantação de servidor de negócios.
  
É necessário incorporar o arquivamento à sua topologia antes de configurar sua implantação para suportar o arquivamento. As informações neste tópico explicam como usar o construtor de topologias para:
  
- Adicionar um banco de dados de arquivamento à sua topologia.
    
- Publica a topologia atualizada para adicionar o banco de dados de arquivamento à sua Skype para implantação de servidor de negócios.
    
> [!NOTE]
> Se desejar usar a integração do Microsoft Exchange para armazenar arquivos nos servidores do Exchange para todos os seus usuários e dados de arquivamento em sua implantação, não especifique as informações de **repositório de arquivamento do SQL Server** ou **espelhamento do repositório de servidor SQL de uso** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Adicionar um banco de dados de arquivamento à sua topologia

1. Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo local de usuários (ou uma conta com direitos de usuário equivalentes).
    
2. Inicie o construtor de topologias.
    
3. Na árvore do console, navegue até o pool de Front-Ends no qual você deseja implantar o arquivamento e clique no nome do pool.
    
4. No menu **Ação**, clique em **Editar Propriedades**. 
    
5. Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Marque a caixa de seleção **Arquivamento**.
    
8. Em **repositório de arquivamento do SQL Server,** siga um destes procedimentos:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar. Se todos os usuários estão hospedados no Microsoft Exchange Server 2013 ou acima, você pode arquivar Skype para comunicações comerciais de todos os usuários do Exchange. Nesse caso, você não precisará configurar o repositório de arquivamento do SQL Server.
    
   - Para especificar um novo repositório do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , faça o seguinte:
    
   - Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.
    
   - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
   - Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.
    
9. Se você quiser usar o espelhamento do repositório do SQL Server, selecione **Habilitar SQL Server Store espelhamento**e, em seguida, faça o seguinte:
    
   - Para usar um armazenamento existente do SQL Server para espelhamento, na caixa de listagem suspensa **espelho do repositório de arquivamento do SQL Server** , clique no nome do repositório do SQL Server que você deseja usar para espelhamento.
    
   - Para especificar um novo repositório do SQL Server para espelhamento, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , siga um destes procedimentos:
    
     a. Em **FQDN do SQL Server**, especifique o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
     c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.
    
   - Se você habilitar o espelhamento do SQL Server e deseja incluir um (uma terceira, separada instância do SQL Server que pode detectar a integridade das instâncias do SQL Server e espelho primárias) de testemunha de espelhamento do SQL Server, selecione o **testemunha de espelhamento de usar do SQL Server para habilitar automática failover** caixa de seleção e, em seguida, execute um dos seguintes:
    
     a. Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo SQL Server testemunha de espelhamento.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
     c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.
    
10. Para salvar a configuração, clique em **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação

1. Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo local de usuários (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo de usuários local, mas para publicar uma topologia, o que é necessário para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo **Administradores** de domínio e o **RTCUniversalServer Os administradores** grupo e que tem permissões de controle total (leitura, gravação e modificar) no compartilhamento de arquivos que você está usando para o Skype para repositório de arquivos do servidor de negócios (para que o construtor de topologias possa configurar a lista de controle de acesso discricionário necessária (DACLs) ou uma conta com direitos equivalentes.
  
2. Abra a topologia que você criou na seção anterior utilizando o construtor de topologias.
    
3. Na árvore de console, clique com o botão **Skype para Business Server**e, em seguida, clique em **Publicar topologia**.
    
4. Na página **Publicar a topologia**, clique em **Avançar**.
    
5. Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**. 
    
    > [!NOTE]
    > Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados. bancos de dados somente em servidores dedicados do SQL gt _ podem ser instalados usando o construtor de topologia. Bancos de dados em SQL Servers que são colocados com outros componentes de servidor devem ser instalados executando a instalação local em tal computador. 
  
6. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    > [!IMPORTANT]
    > Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado. Para obter detalhes, consulte [Configurar opções de arquivamento para Skype para Business Server](configure-archiving-options.md) e [Configurar políticas para Skype para Business Server de arquivamento](configure-archiving-policies.md). 
  

