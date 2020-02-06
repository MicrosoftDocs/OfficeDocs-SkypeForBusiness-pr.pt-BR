---
title: Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumo: Leia este tópico para saber como adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015.'
ms.openlocfilehash: 733d75e954c75cecfab38e0a2f1294c6e20984c1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794109"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como adicionar um servidor de chat persistente à sua topologia do Skype for Business Server 2015.
  
Depois de instalar o software de pré-requisito em cada servidor em que você planeja implantar o servidor de chat persistente, use o construtor de topologias para: 
  
- Atualizar sua topologia para incluir o Servidor de Chat Persistente
    
- Postar a topologia atualizada
    
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Atualizar sua topologia para incluir o Servidor de Chat Persistente

Execute as etapas a seguir para instalar um único pool de servidores de chat persistente sem uma configuração de recuperação de desastres. Para configurar um pool de servidor de chat persistente ampliado para alta disponibilidade e recuperação de desastre, consulte [Configurar alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Para implantar vários pools de servidores de chat persistentes, repita o mesmo processo para cada pool.
  
1. Em um computador que esteja executando o Skype for Business Server ou em que as ferramentas administrativas do Skype for Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia o que é necessário para instalar o Skype for Business Server, você deve usar uma conta que seja membro do grupo **Domain admins** e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (ler, gravar e modificar) no repositório de arquivos que você usará para o repositório de arquivos do servidor de chat persistente (para que o construtor de topologias possa configurar as DACLs necessárias) ou uma conta com direitos.
  
2. Iniciar o construtor de topologias.
    
3. Na árvore de console, navegue até o nó de **pools de chat persistente** e expanda-o para selecionar um pool do Skype for Business Server, ou clique com o botão direito do mouse no nó e selecione **novo pool de chat persistente**. Você deve definir o nome de domínio totalmente qualificado (FQDN) do pool e indicar se o pool será um pool de servidor único ou uma implantação de pool de vários servidores.
    
    Você pode escolher entre um **Pool de múltiplos computadores** ou um **Pool de computador único**. Escolha o primeiro se estiver planejando ter mais de um servidor front-end em seu pool de servidores de chat persistente. É possível escolher agora ou depois, já que após a criação do pool de computador único não é possível adicionar outros servidores. Se você escolher um pool de vários computadores, insira os nomes dos servidores front-end individuais que compõem o pool.
    
    > [!IMPORTANT]
    > Se a função de servidor de chat persistente estiver sendo instalada em um servidor Standard Edition, o FQDN precisará corresponder ao FQDN do servidor Standard Edition. 
  
4. Defina um **nome de exibição** simples para o pool do servidor de chat persistente. O nome de exibição pode ser usado por clientes personalizados, especialmente quando há vários pools de servidores de chat persistentes para diferenciar os quartos.
    
5. Defina a porta usada pelo servidor de chat persistente para se comunicar com os servidores front-end do Skype for Business Server. A porta padrão é 5041.
    
6. Se sua organização requerer suporte à conformidade, marque a caixa de seleção **Habilitar conformidade**. Se escolhido, o serviço de conformidade do servidor de chat persistente é instalado no mesmo computador que o servidor front-end persistente do servidor de chat. Você será solicitado a selecionar um servidor back-end do SQL Server para conformidade com o servidor de chat persistente mais tarde.
    
7. Atribua afinidade de site ao pool de servidores de chat persistente. Marque a caixa de seleção **usar este pool como \<padrão\> para o site SiteName** ou **Use este pool como padrão para todos os sites** para designar este pool de servidores de chat persistente como o pool padrão para o site atual ou todos os sites. Quando o cliente Skype for Business é usado para criar e gerenciar salas, o pool padrão associado ao site do usuário é usado pela criação e pela experiência de gerenciamento da sala para que possa direcionar as operações de criação e gerenciamento da sala para esse pool. Isso só se aplica quando você tem vários pools de servidores de chat persistentes implantados e deseja usar os recursos de criação e gerenciamento de salas do servidor de chat persistente.
    
    > [!IMPORTANT]
    > Você pode personalizar os recursos de criação e gerenciamento de sala usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente. 
  
8. Defina o **repositório SQL para o back-end persistente do servidor de chat (onde o conteúdo da sala de chat está armazenado)** seguindo um destes procedimentos:
    
   - Para usar um repositório existente do SQL Server, na lista suspensa, clique no nome da loja do SQL Server que você deseja usar.
    
   - Para especificar um novo banco de dados do SQL Server, clique em **novo**e, em **definir novo SQL Store**, execute o seguinte procedimento:
    
   - No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo banco de dados do SQL Server.
    
   - Selecione **Instância padrão** para usar a instância padrão ou **Instância nomeada** para especificar uma instância diferente e especifique a instância que deseja usar.
    
     > [!NOTE]
     > Para obter detalhes sobre como configurar bancos de dados de backup do SQL Server para recuperação de desastres, consulte [Configurar alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Defina a loja de conformidade do SQL Server se tiver habilitado a conformidade.
    
    > [!IMPORTANT]
    > Para obter detalhes sobre como configurar os espelhos do SQL Server para alta disponibilidade para o banco de dados persistente do servidor de chat e o banco de dados de conformidade do servidor de chat persistente, consulte [Configurar alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Defina o repositório de arquivos. Os repositórios de arquivos são pastas em que são armazenadas cópias de todos os arquivos enviados para o repositório de arquivos (por exemplo, para armazenar anexos de arquivos publicados em salas de chat). No caso de uma topologia de servidor de chat persistente de vários servidores, isso deve ser um caminho UNC (Convenção Universal de nomenclatura); e para uma topologia de servidor de chat persistente de servidor único, pode ser um caminho de arquivo local.
    
    Para usar um repositório de arquivos existente, execute as etapas a seguir:
    
    - No **FQDN do servidor de arquivos**, especifique o FQDN do computador no qual deseja criar um novo repositório de arquivos.
    
    - Em **Compartilhamento de arquivos**, especifique o repositório de arquivos que deseja usar.
    
      > [!IMPORTANT]
      > Você pode definir o repositório de arquivos no construtor de topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido que você define antes de publicar a topologia. Se o repositório de arquivos não existir, as tentativas de publicar a topologia irão falhar. 
  
11. Selecione o pool de servidores front-end a ser usado como um próximo nó para este pool de servidores de chat persistente. Este é o pool de servidores front-ends que poderá rotear solicitações persistentes do servidor de chat para esse pool.
    
12. Para salvar a configuração, clique em **Concluir**. O pool de servidores de chat persistente aparece no construtor de topologia acompanhado por suas configurações de pool específicas.
    
    Para publicar sua topologia atualizada à qual você adicionou o servidor de chat persistente, consulte publicar a topologia atualizada.
    
    > [!NOTE]
    > Com o construtor de topologias já aberto, você pode passar para a etapa 3 em publicar a topologia atualizada para começar a publicar sua topologia atualizada. 
  
## <a name="publish-the-updated-topology"></a>Postar a topologia atualizada
<a name="BKMK_PublishTopology"> </a>

Depois de atualizar sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central antes de poder configurar e usar o Skype for Business Server. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.
  
Antes de publicar sua topologia, instale os bancos de dados do servidor de chat persistente. Use o construtor de topologias para instalar bancos de dados selecionando **ação** e **instalar banco de dados**.
  
1. Em um computador que esteja executando o Skype for Business Server ou em que as ferramentas administrativas do Skype for Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo **Domain admins** e do grupo **RTCUniversalServerAdmins** , e que tenha permissões de controle total (ler, gravar e modificar) no repositório de arquivos a ser usado para o repositório de arquivos do servidor de chat persistente (de forma que o construtor de topologias possa configurar as DACLs (listas de controle de acesso discricional) necessárias ou uma conta com um usuário equivalente direitos.
    
2. Iniciar o construtor de topologias. Selecione **Abrir Topologia de um arquivo local**, se salvar localmente.
    
3. Na árvore de console, clique com o botão direito do mouse em **Skype for Business Server 2015**e, em seguida, clique em **publicar topologia**.
    
4. Na página **Publicar a topologia**, clique em **Avançar**.
    
5. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    

