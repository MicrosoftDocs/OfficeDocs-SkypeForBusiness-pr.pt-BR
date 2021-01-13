---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do Skype for Business Server.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820671"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do Skype for Business Server.
  
É necessário incorporar o arquivamento à sua topologia antes de poder configurar sua implantação para suportar o arquivamento. As informações neste tópico explicam como usar o Construtor de Topologias para:
  
- Adicione um banco de dados de arquivamento à sua topologia.
    
- Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação do Skype for Business Server.
    
> [!NOTE]
> Se você quiser usar a integração com o Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores do Exchange para todos os usuários em sua implantação, não especifique o armazenamento do **SQL Server** de Arquivamento ou use as informações de espelhamento do SQL **Server Store.**
  
### <a name="add-an-archiving-database-to-your-topology"></a>Adicionar um banco de dados de arquivamento à sua topologia

1. Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
2. Inicie o Construtor de topologia.
    
3. Na árvore de console, navegue até o pool de Front-End no qual você deseja implantar o Arquivamento e clique no nome do pool de Front-End onde deseja implantar o arquivamento.
    
4. No menu **Ação**, clique em **Editar Propriedades**. 
    
5. Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Marque a caixa de seleção **Arquivamento**.
    
8. Em **Armazenamento de Arquivamento do SQL Server,** faça um dos seguintes:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar. Se todos os seus usuários estão instalados no Microsoft Exchange Server 2013 ou acima, você pode arquivar comunicações do Skype for Business para todos os seus usuários no Exchange. Nesse caso, você não precisa configurar o armazenamento de Arquivamento do SQL Server.
    
   - Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, na caixa de diálogo Definir Novo Armazenamento do **SQL Server,** faça o seguinte:
    
   - No **FQDN do SQL Server,** especifique o FQDN do servidor no qual você deseja criar o novo armazenamento do SQL Server.
    
   - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
   - Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.
    
9. Se você quiser usar o espelhamento do armazenamento do SQL Server, selecione Habilitar espelhamento do **SQL Server Store** e faça o seguinte:
    
   - Para usar um armazenamento existente do SQL **Server** para espelhamento, na caixa de listagem de espelho do armazenamento do SQL Server de arquivamento, clique no nome do armazenamento do SQL Server que você deseja usar para espelhamento.
    
   - Para especificar um novo armazenamento do SQL Server para espelhamento, clique em Novo e, em seguida, na caixa de diálogo Definir Novo Armazenamento do **SQL Server,** faça um dos seguintes:
    
     a. No **FQDN do SQL Server,** especifique o FQDN do SQL Server no qual você deseja criar o novo armazenamento do SQL Server.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
     c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.
    
   - Se você habilitar o espelhamento do SQL Server e quiser incluir uma testemunha de espelhamento do SQL Server (uma terceira instância separada do SQL Server que pode detectar a saúde do SQL Server primário e das instâncias espelho), selecione a caixa de seleção Usar espelhamento do SQL Server para habilitar a caixa de seleção de **failover** automático e, em seguida, faça um dos seguintes:
    
     a. No **FQDN do SQL Server,** especifique o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.
    
     b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
     c. Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.
    
10. Para salvar a configuração, clique em **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publicar a topologia atualizada para adicionar um banco de dados de arquivamento à sua implantação

1. Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessário para  adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o armazenamento de arquivos do Skype for Business Server (para que o Construtor de Topologias possa configurar a lista de controle de acesso discricionário (DACLs) necessária ou uma conta com direitos equivalentes.
  
2. Abra a topologia criada na seção anterior usando o Construtor de Topologias.
    
3. Na árvore do console, clique com o botão direito do mouse **no Skype for Business Server** e clique em Publicar **Topologia.**
    
4. Na página **Publicar topologia**, clique em **Avançar**.
    
5. Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**. 
    
    > [!NOTE]
    > Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados. > somente bancos de dados em SQL Servers dedicados podem ser instalados usando o Construtor de Topologias. Os bancos de dados em Servidores SQL que são colocados com outros componentes precisam ser instalados executando a configuração local nesse computador. 
  
6. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    > [!IMPORTANT]
    > Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado. Para obter detalhes, [consulte Configure archiving options for Skype for Business Server](configure-archiving-options.md) and Configure [archiving policies for Skype for Business Server](configure-archiving-policies.md). 
  

