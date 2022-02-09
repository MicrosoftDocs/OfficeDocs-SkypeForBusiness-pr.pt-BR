---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: leia este tópico para saber como adicionar bancos de dados de arquivamento à sua Skype for Business Server implantação.'
ms.openlocfilehash: 3bc4e14998e45803518436bb180906e9c79e14f4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401575"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua Skype for Business Server implantação.
  
É necessário incorporar o arquivamento à sua topologia antes de poder configurar sua implantação para suportar o arquivamento. As informações neste tópico explicam como usar o Construtor de Topologias para:
  
- Adicione um banco de dados de arquivamento à sua topologia.
    
- Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua Skype for Business Server implantação.
    
> [!NOTE]
> Se você quiser usar Exchange integração do Microsoft Exchange para armazenar dados e arquivos de arquivamento em servidores Exchange para todos os usuários em sua implantação, não especifique o armazenamento de **arquivamento** SQL Server ou use informações de espelhamento da **SQL Server Store**.
  
### <a name="add-an-archiving-database-to-your-topology"></a>Adicionar um banco de dados de arquivamento à sua topologia

1. Em um computador que está executando Skype for Business Server, ou no qual as ferramentas administrativas Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo Usuários local (ou uma conta com direitos de usuário equivalentes).
    
2. Inicie o Construtor de topologia.
    
3. Na árvore do console, navegue até o pool de Front-End no qual você deseja implantar o Arquivamento e clique no nome do pool de Front-End onde você deseja implantar o arquivamento.
    
4. No menu **Ação**, clique em **Editar Propriedades**. 
    
5. Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Marque a caixa de seleção **Arquivamento**.
    
8. Em **Arquivamento SQL Server store,** faça um dos seguintes:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar. Se todos os seus usuários estão em casa no Microsoft Exchange Server 2013 ou acima, você pode arquivar Skype for Business comunicações para todos os seus usuários no Exchange. Nesse caso, você não precisa configurar o SQL Server arquivamento.
    
   - Para especificar um novo SQL Server, clique em **Novo** e, na caixa de diálogo Definir Novo SQL Server **Store**, faça o seguinte:
    
   - Em **SQL Server FQDN**, especifique o FQDN do servidor no qual você deseja criar o novo SQL Server store.
    
   - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
   - Se SQL Server instância especificada estiver em uma relação de espelhamento, selecione **a** caixa de seleção Esta SQL está na caixa de seleção Relação de espelhamento e, em Número da porta **Espelho,** especifique o número da porta.
    
9. Se você quiser usar o SQL Server de armazenamento, selecione Habilitar SQL Server **espelhamento da Loja** e faça o seguinte:
    
   - Para usar um armazenamento de SQL Server existente para espelhamento, **na** caixa de listagem de listagem de espelhamento de armazenamento de espelhos de arquivamento SQL Server, clique no nome do SQL Server store que você deseja usar para espelhamento.
    
   - Para especificar um novo SQL Server para espelhamento, clique em Novo e, em **seguida,** na caixa de diálogo Definir Novo SQL Server **Store**, faça um dos seguintes:
    
     a. Em **SQL Server FQDN**, especifique o FQDN do SQL Server no qual você deseja criar o novo SQL Server store.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
     c. Se SQL Server instância especificada estiver em uma relação de espelhamento, selecione **a** caixa de seleção Esta SQL está na caixa de seleção Relação de espelhamento e, em Número da porta **Espelho,** especifique o número da porta.
    
   - Se você habilitar SQL Server espelhamento de SQL Server e quiser incluir uma testemunha de espelhamento de SQL Server (uma terceira instância de SQL Server separada que pode detectar a saúde das instâncias de espelho e SQL Server principal), selecione a testemunha de espelhamento Use SQL Server para habilitar **o failover automático**  caixa de seleção e, em seguida, faça um dos seguintes:
    
     a. Em **SQL Server FQDN**, especifique o FQDN do servidor no qual você deseja criar a nova SQL Server de espelhamento.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
     c. Se SQL Server instância especificada estiver em uma relação de espelhamento, selecione **a** caixa de seleção Esta SQL está na caixa de seleção Relação de espelhamento e, em Número da porta **Espelho,** especifique o número da porta.
    
10. Para salvar a configuração, clique em **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publicar a topologia atualizada para adicionar um banco de dados de arquivamento à sua implantação

1. Em um computador que está executando Skype for Business Server ou no qual as ferramentas administrativas Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários locais (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta membro do grupo Usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (leitura,  gravar e modificar) no compartilhamento de arquivos que você está usando para o armazenamento de arquivos Skype for Business Server (para que o Construtor de Topologias possa configurar a lista de controles de acesso discricionário necessário (DACLs) ou uma conta com direitos equivalentes.
  
2. Abra a topologia criada na seção anterior usando o Construtor de Topologias.
    
3. Na árvore do console, clique com o botão direito **Skype for Business Server** e clique em **Publicar Topologia**.
    
4. Na página **Publicar topologia**, clique em **Avançar**.
    
5. Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**. 
    
    > [!NOTE]
    > Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados. > somente bancos de dados em servidores SQL dedicados podem ser instalados usando o Construtor de Topologias. Os bancos de dados em Servidores SQL que são colocados com outros componentes precisam ser instalados executando a configuração local nesse computador. 
  
6. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    > [!IMPORTANT]
    > Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado. Para obter detalhes, [consulte Configure archiving options for Skype for Business Server](configure-archiving-options.md) [and Configure archiving policies for Skype for Business Server](configure-archiving-policies.md). 
  

