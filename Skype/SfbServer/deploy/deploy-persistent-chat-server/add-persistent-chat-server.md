---
title: Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumo: Leia este tópico para saber como adicionar o Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015.'
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825101"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Adicionar Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como adicionar o Servidor de Chat Persistente à sua topologia do Skype for Business Server 2015.
  
Depois de instalar o software de pré-requisito em cada servidor no qual você planeja implantar o Servidor de Chat Persistente, use o Construtor de Topologias para: 
  
- Atualizar sua topologia para incluir o Servidor de Chat Persistente
    
- Publicar a topologia atualizada
    
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Atualizar sua topologia para incluir o Servidor de Chat Persistente

Execute as etapas a seguir para instalar um único pool de Servidor de Chat Persistente sem uma configuração de recuperação de desastres. Para configurar um pool estendido de Servidor de Chat Persistente para alta disponibilidade e recuperação de desastre, consulte Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no [Skype for Business Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)
  
Para implantar vários pools de Servidor de Chat Persistente, repita o mesmo processo para cada pool.
  
1. Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo local Usuários, mas para publicar uma topologia, necessária para instalar  o Skype for Business Server, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (ler, gravar e modificar) no armazenamento de arquivos que você usará para o armazenamento de arquivos do Servidor de Chat Persistente (para que o Construtor de Topologias possa configurar os DACLs necessários) ou uma conta com direitos equivalentes.
  
2. Inicie o Construtor de topologia.
    
3. Na árvore de console, navegue até o nó **Pools** de Chat Persistente e expanda-o para selecionar um pool do Skype for Business Server ou clique com o botão direito do mouse no nó e selecione Novo Pool de **Chat Persistente.** Você deve definir o FQDN (nome de domínio totalmente qualificado) do pool e indicar se o pool será um pool de servidor único ou implantação de pool de vários servidores.
    
    Você pode escolher um **pool de vários computadores** ou **um pool de computador único.** Escolha o primeiro se estiver planejando ter mais de um Servidor front-end em seu pool de Servidor de Chat Persistente. Faça essa escolha agora ou em um momento posterior, porque depois de criar um único pool de computadores, você não poderá adicionar mais servidores a ele posteriormente. Se você escolher um pool de vários computadores, insira os nomes dos Servidores Front End individuais que compõem o pool.
    
    > [!IMPORTANT]
    > Se a função de Servidor de Chat Persistente estiver sendo instalada em um servidor Standard Edition, o FQDN precisará corresponder ao FQDN do servidor Standard Edition. 
  
4. Defina um Nome **de Exibição simples** para o pool de Servidor de Chat Persistente. O nome de exibição pode ser usado por clientes personalizados, especialmente quando há vários pools de Servidor de Chat Persistente para diferenciar salas.
    
5. Defina a porta usada pelo Servidor de Chat Persistente para se comunicar com os Servidores Front-End do Skype for Business Server. A porta padrão é 5041.
    
6. Se sua organização exigir suporte de conformidade, marque a caixa de seleção **Habilitar** conformidade. Se escolhido, o serviço de Conformidade do Servidor de Chat Persistente será instalado no mesmo computador que o Servidor Front-End do Servidor de Chat Persistente. Você será solicitado a selecionar um Servidor #A0 do SQL Server para Conformidade do Servidor de Chat Persistente posteriormente.
    
7. Atribuir afinidade de site para o pool de Servidor de Chat Persistente. Marque a caixa de seleção Usar este pool como padrão para **o site \<SiteName\>** ou Use este pool como padrão para todos os **sites** para designar esse pool de Servidor de Chat Persistente como o pool padrão para o site atual ou todos os sites. Quando o cliente Skype for Business é usado para criar e gerenciar salas, o pool padrão associado ao site do usuário é usado pela experiência de criação e gerenciamento da sala para que ele possa encaminhar operações de criação e gerenciamento de sala para esse pool. Isso só se aplica quando você tem vários pools de Servidor de Chat Persistente implantados e deseja usar os recursos de criação e gerenciamento de sala do Servidor de Chat Persistente.
    
    > [!IMPORTANT]
    > Você pode personalizar os recursos de criação e gerenciamento de salas usando o SDK (Kit de Desenvolvimento de Software) do Servidor de Chat Persistente. 
  
8. Defina **o armazenamento SQL para o Back-End** do Servidor de Chat Persistente (onde o conteúdo da sala de chat está armazenado) fazendo um dos seguintes:
    
   - Para usar um armazenamento existente do SQL Server, na lista drop-down, clique no nome do armazenamento do SQL Server que você deseja usar.
    
   - Para especificar um novo banco de dados do SQL Server, clique em **Novo** e, em **Definir Novo Sql Store,** execute o seguinte:
    
   - No **FQDN do SQL Server,** especifique o FQDN do SQL Server no qual você deseja criar o novo banco de dados do SQL Server.
    
   - Selecione **Instância Padrão para** usar a instância padrão ou, para especificar uma instância diferente, selecione **Instância** Nomeada e especifique a instância que você deseja usar.
    
     > [!NOTE]
     > Para obter detalhes sobre como configurar bancos de dados de backup do SQL Server para recuperação de desastres, consulte [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
9. Defina o armazenamento de conformidade do SQL Server se você tiver habilitado a Conformidade.
    
    > [!IMPORTANT]
    > Para obter detalhes sobre como configurar espelhos do SQL Server para alta disponibilidade para o banco de dados do Servidor de Chat Persistente e o banco de dados de conformidade do Servidor de Chat Persistente, consulte Configurar alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente no [Skype for Business Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
10. Defina o armazenamento de arquivos. Um repositório de arquivos é uma pasta onde uma cópia de qualquer arquivo carregado no repositório de arquivos é armazenada (por exemplo, armazenar anexos de arquivo postados em uma sala de chat). No caso de uma topologia de Servidor de Chat Persistente com vários servidores, deve ser um caminho UNC; e para uma topologia de servidor único do Servidor de Chat Persistente, ela pode ser um caminho de arquivo local.
    
    Para usar um armazenamento de arquivos existente, execute as seguintes etapas:
    
    - No **FQDN do Servidor** de Arquivos, especifique o FQDN do computador no qual você deseja criar o novo armazenamento de arquivos.
    
    - Em **Compartilhamento de** Arquivos, especifique o armazenamento de arquivos que você deseja usar.
    
      > [!IMPORTANT]
      > Você pode definir o armazenamento de arquivos no Construtor de Topologias antes de criar o armazenamento de arquivos, mas deve criar o armazenamento de arquivos no local definido antes de publicar a topologia. Se o armazenamento de arquivos ainda não existir, as tentativas de publicar a topologia falharão. 
  
11. Selecione o pool do Servidor Front End a ser usado como próximo salto para esse pool de Servidor de Chat Persistente. Este é o pool do Servidor front-end que será capaz de encaminhar solicitações do Servidor de Chat Persistente para esse pool.
    
12. Para salvar a configuração, clique em **Concluir.** O pool de Servidor de Chat Persistente aparece no Construtor de Topologias acompanhado pelas configurações específicas do pool.
    
    Para publicar sua topologia atualizada à qual você adicionou o Servidor de Chat Persistente, consulte Publicar a topologia atualizada.
    
    > [!NOTE]
    > Com o Construtor de Topologias já aberto, você pode prosseguir para a etapa 3 em Publicar a topologia atualizada para começar a publicar sua topologia atualizada. 
  
## <a name="publish-the-updated-topology"></a>Publicar a topologia atualizada
<a name="BKMK_PublishTopology"> </a>

Depois de atualizar sua topologia no Construtor de Topologias, você deve publicar a topologia no armazenamento de Gerenciamento Central antes de configurar e usar o Skype for Business Server. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.
  
Antes de publicar sua topologia, instale os bancos de dados para o Servidor de Chat Persistente. Use o Construtor de Topologias para instalar bancos de dados selecionando **Ação** e **Instalar Banco de Dados.**
  
1. Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, Faça logon usando uma conta que seja membro do grupo **Admins.** do Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (ler, gravar e modificar) no armazenamento de arquivos a ser usado para o armazenamento de arquivos do Servidor de Chat Persistente (para que o Construtor de Topologias possa configurar as listas de controle de acesso discricionário (DACLs) necessárias) ou uma conta com direitos de usuário equivalentes.
    
2. Inicie o Construtor de topologia. Selecione **Abrir Topologia em um arquivo local se** você a tiver salvo localmente.
    
3. Na árvore do console, clique com o botão direito do mouse **no Skype for Business Server 2015** e clique em Publicar **Topologia.**
    
4. Na página **Publicar a topologia**, clique em **Avançar**.
    
5. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    

