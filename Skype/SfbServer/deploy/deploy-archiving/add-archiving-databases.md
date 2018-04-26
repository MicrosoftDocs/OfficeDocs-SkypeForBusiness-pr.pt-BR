---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do .'
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a>Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server 2015
 
Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do .
  
É necessário incorporar o arquivamento à sua topologia antes de configurar sua implantação para suportar o arquivamento. As informações neste tópico explicam como usar o  para:
  
- Adicionar um banco de dados de arquivamento à sua topologia.
    
- Publicar a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação do .
    
> [!NOTE]
> Se você quiser usar a integração do  para armazenar dados de arquivamento e arquivos nos servidores do  para todos seus usuários em sua implantação, não especifique informações do  ou .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Adicionar um banco de dados de arquivamento à sua topologia

1. Em um computador que está executando o  ou no qual as ferramentas administrativas do  estejam instaladas, faça logon usando uma conta que seja membro do grupo de usuários local (ou uma conta com direitos de usuário equivalentes).
    
2. Start Topology Builder.
    
3. Na árvore do console, navegue até o pool de Front-Ends no qual você deseja implantar o arquivamento e clique no nome do pool.
    
4. No menu **Ação**, clique em **Editar Propriedades**. 
    
5. Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.
    
6. Role a tela para baixo até **Arquivamento**.
    
7. Marque a caixa de seleção **Arquivamento**.
    
8. Under **Archiving SQL Server store,** do one of the following:
    
   - Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar. Se todos os seus usuários estiverem hospedados no  ou acima, você poderá arquivar as comunicações do  para todos os seus usuários no . Nesse caso, não é necessário configurar o repositório de Arquivamento do .
    
   - Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:
    
   - Em FQDN do SQL Server, especifique o FQDN do servidor no qual deseja criar o armazenamento do .
    
   - Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
   - Na instância do  especificada em uma relação de espelhamento, marque a caixa de seleção Esta instância do SQL está em relação de espelhamento e, então, em Número da porta espelho, especifique o número da porta.
    
9. If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:
    
   - Para usar um armazenamento existente do  para espelhamento, na caixa de listagem suspensa Espelho do armazenamento do SQL Server de arquivamento, clique no nome do armazenamento do  que deseja usar para espelhamento.
    
   - Para especificar um novo armazenamento do  para espelhamento, clique em Novo e, então, na caixa de diálogo Definir novo armazenamento do SQL Server, realize uma das seguintes ações:
    
    a. Em FQDN do SQL Server, especifique o FQDN do SQL Server no qual deseja criar o novo armazenamento do .
    
    b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.
    
    c. Na instância do  especificada em uma relação de espelhamento, marque a caixa de seleção Esta instância do SQL está em relação de espelhamento e, então, em Número da porta espelho, especifique o número da porta.
    
   - Se você habilitar o espelhamento do  e quiser adicionar ou alterar uma testemunha de espelhamento do  (uma terceira instância do  separada, que possa detectar a integridade do servidor primário do  e as instâncias de espelho), marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar failover automático e, em seguida, realize uma destas ações:
    
    a. Em FQDN do SQL Server, especifique o FQDN do servidor no qual deseja criar a nova testemunha de espelhamento do .
    
    b. Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.
    
    c. Na instância do  especificada em uma relação de espelhamento, marque a caixa de seleção Esta instância do SQL está em relação de espelhamento e, então, em Número da porta espelho, especifique o número da porta.
    
10. Para salvar a configuração, clique em **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação

1. Em um computador com o  em execução ou em que as ferramentas administrativas  estejam instaladas, faça logon usando uma conta que faça parte do grupo de usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia utilizando uma conta que seja membro do grupo Usuários local, mas para publicar uma topologia (que é necessário para adicionar um servidor à topologia), você deve utilizar uma conta que seja membro do grupo Administradores de domínio e o grupo RTCUniversalServerAdmins e que possui permissões de controle total (ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivo  (de forma que  possa configurar a lista de controle de acesso condicional (DACLs) ou uma conta com direitos equivalentes.
  
2. Abra a topologia que você criou na seção anterior utilizando o .
    
3. Na árvore do console, clique com o botão direito do mouse em **** e depois em **Publicar Topologia**.
    
4. Na página **Publicar a topologia**, clique em **Avançar**.
    
5. Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**. 
    
    > [!NOTE]
    > Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados. Apenas bancos de dados em SQL Servers dedicados podem ser instalados utilizando o . Bancos de dados em SQL Servers que são colocados com outros componentes de servidor devem ser instalados executando a instalação local em tal computador. 
  
6. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    > [!IMPORTANT]
    > Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado. For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md). 
  

