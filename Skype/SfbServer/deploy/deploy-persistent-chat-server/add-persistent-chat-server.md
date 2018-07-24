---
title: Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumo: Leia este tópico para saber como adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015.'
ms.openlocfilehash: 9d6845b7239056ec18be780060ba6ef96756f743
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973007"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015
 
**Resumo:** Leia este tópico para saber como adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015.
  
Depois de instalar o software de pré-requisito em cada servidor no qual você planeja implantar o servidor de Chat persistente, você pode usar o construtor de topologias para: 
  
- Atualizar sua topologia para incluir o Servidor de Chat Persistente
    
- Postar a topologia atualizada
    
> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Atualizar sua topologia para incluir o Servidor de Chat Persistente

Execute as seguintes etapas para instalar um único pool de servidor de Chat persistente sem uma configuração de recuperação de desastres. Para configurar um pool de servidor de Chat persistente ampliado para alta disponibilidade e recuperação de desastres, consulte [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Para implantar vários pools de servidor de Chat persistente, repita o processo para cada pool.
  
1. Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo local de usuários (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo de usuários local, mas para publicar uma topologia, o que é necessário para instalar o Skype para Business Server, você deve usar uma conta que seja membro do grupo **Administradores** de domínio e o ** RTCUniversalServerAdmins** grupo e que tem permissões de controle total (leitura, gravação e modificar) no armazenamento de arquivo que você pretende usar para o repositório de arquivos do servidor de Chat persistente (de modo que esse construtor de topologia pode configurar as DACLs necessárias), ou uma conta com direitos equivalentes.
  
2. Inicie o construtor de topologias.
    
3. Na árvore de console, navegue até o nó **Pools de Chat persistente** e expandi-lo e selecione um Skype para o pool de servidores corporativos, ou com o botão direito no nó e selecione **Novo Pool de Chat persistente**. Você deve definir o nome de domínio totalmente qualificado do pool (FQDN) e indique se o pool será um pool de servidor único ou a implantação do pool de vários servidores.
    
    Você pode escolher entre um **Pool de múltiplos computadores** ou um **Pool de computador único**. Escolha o primeiro se você estiver planejando ter mais de um servidor Front-End em seu pool do servidor de Chat persistente. É possível escolher agora ou depois, já que após a criação do pool de computador único não é possível adicionar outros servidores. Se você escolher um pool de vários computadores, insira os nomes dos individuais servidores Front-End que compõem o pool.
    
    > [!IMPORTANT]
    > Se a função de servidor de Chat persistente está sendo instalada em um servidor Standard Edition, o FQDN deve corresponder ao FQDN do servidor do Standard Edition. 
  
4. Defina um **Nome para exibição** simples para o pool do servidor de Chat persistente. O nome para exibição pode ser usado pelos clientes personalizados, especialmente quando há vários pools de servidor de Chat persistente para diferenciar salas.
    
5. Defina a porta usada pelo servidor de Chat persistente para se comunicar com Skype para Business Server servidores Front-End. A porta padrão é 5041.
    
6. Se sua organização requerer suporte à conformidade, marque a caixa de seleção **Habilitar conformidade**. Se escolhido, o serviço de conformidade de servidor de Chat persistente está instalado no mesmo computador como Persistent Chat Server servidor Front-End. Você precisará selecionar um servidor do SQL Server Back End para conformidade de servidor de Chat persistente mais tarde.
    
7. Atribua a afinidade de site para o pool do servidor de Chat persistente. Selecione o **usar este pool como padrão para o site \<SiteName\> ** caixa de seleção ou **usar este pool como padrão para todos os sites** para designar este pool de servidor de Chat persistente como o pool de padrão para o site atual ou todos os sites. Quando o Skype para o cliente de negócios é usado para criar e gerenciar salas, pool padrão associado com o site do usuário é usado pela experiência de criação e gerenciamento de sala para que ele pode rotear as operações de criação e gerenciamento de sala a esse pool. Isso se aplica apenas quando você tiver vários pools de servidor de Chat persistente implantados e quiser usar os recursos de criação e gerenciamento de sala do servidor de Chat persistente.
    
    > [!IMPORTANT]
    > Você pode personalizar os recursos de criação e gerenciamento de sala usando o Persistent Chat Server Software Development Kit (SDK). 
  
8. Defina o **repositório de SQL para a Persistent Chat Server Back-End (onde conteúdo da sala de bate-papo é armazenado)** seguindo um destes procedimentos:
    
   - Para usar um armazenamento existente do SQL Server, na lista suspensa, clique no nome do repositório do SQL Server que você deseja usar.
    
   - Para especificar um novo banco de dados do SQL Server, clique em **novo**e em **Definir novo repositório SQL**, execute o seguinte procedimento:
    
   - Em **FQDN do SQL Server**, especifique o FQDN do SQL Server no qual você deseja criar o novo banco de dados do SQL Server.
    
   - Selecione **Instância padrão** para usar a instância padrão ou **Instância nomeada** para especificar uma instância diferente e especifique a instância que deseja usar.
    
    > [!NOTE]
    > Para obter detalhes sobre como configurar o backup bancos de dados do SQL Server para recuperação de desastres, consulte [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Defina o SQL Server store de conformidade, se você habilitou a conformidade.
    
    > [!IMPORTANT]
    > Para obter detalhes sobre como configurar espelhos do SQL Server para alta disponibilidade para o banco de dados do servidor de Chat persistente e o banco de dados de conformidade do servidor de Chat persistente, consulte Configure [alta disponibilidade e recuperação de desastres for Persistent Chat Server in Skype para o Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Defina o repositório de arquivos. Os repositórios de arquivos são pastas em que são armazenadas cópias de todos os arquivos enviados para o repositório de arquivos (por exemplo, para armazenar anexos de arquivos publicados em salas de chat). No caso de uma topologia de servidor de Chat persistente de vários servidores, isso deve ser um caminho de convenção de nomenclatura Universal (UNC); e, para uma topologia de servidor de Chat persistente de servidor único, ele pode ser um caminho de arquivo local.
    
    Para usar um repositório de arquivos existente, execute as etapas a seguir:
    
    - No **FQDN do servidor de arquivos**, especifique o FQDN do computador no qual deseja criar um novo repositório de arquivos.
    
    - Em **Compartilhamento de arquivos**, especifique o repositório de arquivos que deseja usar.
    
     > [!IMPORTANT]
     > Você pode definir o repositório de arquivos no construtor de topologia antes de você criar o repositório de arquivos, mas você deve criar o repositório de arquivos no local definido definido por você antes de publicar a topologia. Se o repositório de arquivos não existir, as tentativas de publicar a topologia irão falhar. 
  
11. Selecione o pool de servidor Front-End a ser usado como próximo salto para este pool de servidor de Chat persistente. Este é o pool de servidor Front-End que serão capaz de rotear as solicitações de servidor de Chat persistente para esse pool.
    
12. Para salvar a configuração, clique em **Concluir**. O pool do servidor de Chat persistente aparece no construtor de topologia acompanhados por suas configurações de pool específico.
    
    Para publicar a topologia atualizada para o qual você tenha adicionado Persistent Chat Server, consulte Publish a topologia atualizada.
    
    > [!NOTE]
    > Com o construtor de topologias já aberto, você poderá prosseguir para a etapa 3 em Publish a topologia atualizada para começar a topologia atualizada de publicação. 
  
## <a name="publish-the-updated-topology"></a>Postar a topologia atualizada
<a name="BKMK_PublishTopology"> </a>

Depois de atualizar sua topologia no construtor de topologia, você deve publicar a topologia no repositório de gerenciamento Central antes de configurar e usar Skype para servidor de Business. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.
  
Antes de publicar sua topologia, instale os bancos de dados para o servidor de Chat persistente. Use o construtor de topologias para instalar bancos de dados, selecionando a **ação** e **Instalar o banco de dados**.
  
1. Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo **Administradores** de domínio e o grupo **RTCUniversalServerAdmins** , e que tem permissões de controle total (leitura, gravação e modificar) no repositório de arquivo a ser usado para o repositório de arquivos do servidor de Chat persistente (de modo que esse construtor de topologia pode configurar as listas de controle de acesso discricionário necessária (DACLs)), ou uma conta de usuário equivalentes direitos.
    
2. Inicie o construtor de topologias. Selecione **Abrir Topologia de um arquivo local**, se salvar localmente.
    
3. Na árvore de console, clique com o botão **Skype para Business Server 2015**e, em seguida, clique em **Publicar topologia**.
    
4. Na página **Publicar a topologia**, clique em **Avançar**.
    
5. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    

