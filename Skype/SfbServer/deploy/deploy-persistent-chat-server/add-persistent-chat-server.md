---
title: Adicionar Servidor de Chat Persistente à topologia Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Resumo: leia este tópico para saber como adicionar o Servidor de Chat Persistente à sua topologia Skype for Business Server 2015.'
ms.openlocfilehash: 4b4148989430987c2a1435ce08315908e27e7e13
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857008"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Adicionar Servidor de Chat Persistente à topologia Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como adicionar o Servidor de Chat Persistente à sua topologia Skype for Business Server 2015.
  
Depois de instalar o software de pré-requisito em cada servidor no qual planeja implantar o Servidor de Chat Persistente, use o Construtor de Topologias para: 
  
- Atualize sua topologia para incluir o Servidor de Chat Persistente
    
- Publicar a topologia atualizada
    
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Atualize sua topologia para incluir o Servidor de Chat Persistente

Execute as etapas a seguir para instalar um único pool de Servidor de Chat Persistente sem uma configuração de recuperação de desastres. Para configurar um pool de Servidor de Chat Persistente estendido para alta disponibilidade e recuperação de desastres, consulte Configure high availability and [disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Para implantar vários pools de Servidor de Chat Persistente, repita o mesmo processo para cada pool.
  
1. Em um computador que está executando Skype for Business Server ou no qual as ferramentas administrativas Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários locais (ou uma conta com direitos de usuário equivalentes).
    
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta membro do grupo Usuários local, mas para publicar uma topologia, que é necessária para instalar  o Skype for Business Server, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (leia,  gravar e modificar) no armazenamento de arquivos que você vai usar para o armazenamento de arquivos do Servidor de Chat Persistente (para que o Construtor de Topologias possa configurar as DACLs necessárias) ou uma conta com direitos equivalentes.
  
2. Inicie o Construtor de topologia.
    
3. Na árvore de console, navegue até o nó **Pools** de Chat Persistente e expanda-o para selecionar um pool de Skype for Business Server, ou clique com o botão direito do mouse no nó e selecione Novo Pool de **Chat Persistente**. Você deve definir o FQDN (nome de domínio totalmente qualificado) do pool e indicar se o pool será um pool de servidores único ou uma implantação de pool de vários servidores.
    
    Você pode escolher um **Pool de Vários Computadores** ou **um Único Pool de Computadores.** Escolha o primeiro se você estiver planejando ter mais de um Servidor Front-End no pool do Servidor de Chat Persistente. Faça essa escolha agora ou em um ponto posterior, porque depois de criar um único pool de computadores, você não poderá adicionar servidores adicionais a ele posteriormente. Se você escolher um pool de vários computadores, insira os nomes dos Servidores Front-End individuais que compõem o pool.
    
    > [!IMPORTANT]
    > Se a função de Servidor de Chat Persistente estiver sendo instalada em um servidor Edição Standard, o FQDN precisará corresponder ao FQDN do servidor Edição Standard. 
  
4. Defina um nome **de exibição simples** para o pool do Servidor de Chat Persistente. O nome de exibição pode ser usado por clientes personalizados, especialmente quando há vários pools do Servidor de Chat Persistente para diferenciar salas.
    
5. Defina a porta usada pelo Servidor de Chat Persistente para se comunicar com Skype for Business Server Servidores Front-End. A porta padrão é 5041.
    
6. Se sua organização exigir suporte à conformidade, marque a caixa de seleção **Habilitar** conformidade. Se escolhido, o serviço de Conformidade do Servidor de Chat Persistente será instalado no mesmo computador que o Servidor Front-End do Servidor de Chat Persistente. Você será solicitado a selecionar um servidor SQL Server Back-End para Conformidade do Servidor de Chat Persistente posteriormente.
    
7. Atribua afinidade de site para o pool do Servidor de Chat Persistente. Selecione a caixa de seleção Usar **esse pool \<SiteName\>** como padrão para site ou Use esse pool como padrão para todos os **sites** para designar esse pool de Servidor de Chat Persistente como o pool padrão para o site atual ou todos os sites. Quando o cliente Skype for Business é usado para criar e gerenciar salas, o pool padrão associado ao site do usuário é usado pela experiência de criação e gerenciamento de sala para que ele possa rotear as operações de criação e gerenciamento de salas para esse pool. Isso só se aplica quando você tem vários pools de Servidor de Chat Persistente implantados e deseja usar os recursos de criação e gerenciamento de sala do Servidor de Chat Persistente.
    
    > [!IMPORTANT]
    > Você pode personalizar os recursos de criação e gerenciamento de sala usando o SDK (Kit de Desenvolvimento de Software do Servidor de Chat Persistente). 
  
8. Defina o SQL para o **Back-End** do Servidor de Chat Persistente (onde o conteúdo da sala de chat está armazenado) fazendo um dos seguintes:
    
   - Para usar um SQL Server existente, na listada, clique no nome do SQL Server que você deseja usar.
    
   - Para especificar um novo banco de SQL Server, clique em **Novo** e, em Definir Novo SQL **Store,** execute o seguinte:
    
   - Em **SQL Server FQDN,** especifique o FQDN do SQL Server no qual você deseja criar o novo banco de dados SQL Server.
    
   - Selecione **Instância Padrão para** usar a instância padrão ou, para especificar uma instância diferente, selecione **Instância** Nomeada e especifique a instância que você deseja usar.
    
     > [!NOTE]
     > Para obter detalhes sobre como configurar SQL Server de backup para recuperação de desastres, consulte Configure high availability and [disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Defina o SQL Server de conformidade se você habilitar a Conformidade.
    
    > [!IMPORTANT]
    > Para obter detalhes sobre como configurar SQL Server espelhos para alta disponibilidade para o banco de dados do Servidor de Chat Persistente e o banco de dados de conformidade do Servidor de Chat Persistente, consulte Configure high availability and [disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Defina o armazenamento de arquivos. Um repositório de arquivos é uma pasta onde uma cópia de qualquer arquivo carregado no repositório de arquivos é armazenada (por exemplo, armazenando anexos de arquivo postados em uma sala de chat). No caso de uma topologia do Servidor de Chat Persistente de vários servidores, esse deve ser um caminho UNC (Convenção de Nomenização Universal). e para uma topologia do Servidor de Chat Persistente de um único servidor, pode ser um caminho de arquivo local.
    
    Para usar um armazenamento de arquivos existente, execute as seguintes etapas:
    
    - No **FQDN do Servidor de** Arquivos, especifique o FQDN do computador no qual você deseja criar o novo armazenamento de arquivos.
    
    - Em **Compartilhamento de** Arquivos, especifique o armazenamento de arquivos que você deseja usar.
    
      > [!IMPORTANT]
      > Você pode definir o armazenamento de arquivos no Construtor de Topologias antes de criar o armazenamento de arquivos, mas deve criar o armazenamento de arquivos no local definido definido antes de publicar a topologia. Se o armazenamento de arquivos ainda não existir, as tentativas de publicar a topologia falharão. 
  
11. Selecione o pool do Servidor front-end a ser usado como próximo salto para este pool de Servidor de Chat Persistente. Esse é o pool do Servidor de Front-End que será capaz de rotear solicitações do Servidor de Chat Persistente para esse pool.
    
12. Para salvar a configuração, clique em **Concluir**. O pool do Servidor de Chat Persistente aparece no Construtor de Topologias acompanhado de suas configurações específicas de pool.
    
    Para publicar sua topologia atualizada à qual você adicionou o Servidor de Chat Persistente, consulte Publicar a topologia atualizada.
    
    > [!NOTE]
    > Com o Construtor de Topologias já aberto, você pode prosseguir para a etapa 3 em Publicar a topologia atualizada para começar a publicar sua topologia atualizada. 
  
## <a name="publish-the-updated-topology"></a>Publicar a topologia atualizada
<a name="BKMK_PublishTopology"> </a>

Depois de atualizar sua topologia no Construtor de Topologias, você deve publicar a topologia no armazenamento de Gerenciamento Central antes de configurar e usar Skype for Business Server. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.
  
Antes de publicar sua topologia, instale os bancos de dados para o Servidor de Chat Persistente. Use o Construtor de Topologias para instalar bancos de dados selecionando **Ação** e **Instalar Banco de Dados**.
  
1. Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão  instaladas, faça logon usando uma conta que seja membro do grupo Administradores de Domínio e do **grupo RTCUniversalServerAdmins** e que tenha permissões de controle total (leitura, gravação e modificação) no armazenamento de arquivos a ser usado para o armazenamento de arquivos Armazenamento de arquivos do Servidor de Chat Persistente (para que o Construtor de Topologias possa configurar as listas de controle de acesso discricionário necessárias (DACLs) ou uma conta com direitos de usuário equivalentes.
    
2. Inicie o Construtor de topologia. Selecione **Abrir Topologia de um arquivo local** se você a salvou localmente.
    
3. Na árvore do console, clique com o botão **direito do mouse Skype for Business Server 2015** e clique em Publicar **Topologia**.
    
4. Na página **Publicar a topologia**, clique em **Avançar**.
    
5. Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    

