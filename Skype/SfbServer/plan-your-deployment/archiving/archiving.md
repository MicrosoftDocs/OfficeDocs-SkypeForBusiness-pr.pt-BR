---
title: Planejar o arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumo: Leia este tópico para saber como planejar o arquivamento no Skype for Business Server.'
ms.openlocfilehash: 9d24457d8345aa6b496489b68347a98c069abc69
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417871"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planejar o arquivamento no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como planejar o arquivamento no Skype for Business Server.
  
As corporações e outras organizações estão sujeitas à crescente quantidade de regulamentações do setor e governamentais que requerem a retenção de tipos específicos de comunicação. Se sua organização tiver tais requisitos, você poderá usar o arquivamento no Skype for Business Server para arquivar mensagens instantâneas (IM) e comunicações de conferência (reunião) para ajudar a dar suporte a alguns dos seus requisitos de conformidade.
  
## <a name="archiving-components"></a>Componentes de arquivamento

O Skype for Business Server usa os seguintes componentes de arquivamento:
  
- **Agentes de arquivamento**. Os agentes de arquivamento, também conhecido como agentes de coleta de dados unificados, são instalados e ativados automaticamente em todos os pools de front-ends e no servidor Standard Edition. Embora os operadores de arquivamento sejam ativados automaticamente, nenhuma mensagem será capturada até que o arquivamento seja habilitado e configurado adequadamente. Por padrão, o arquivamento está desabilitado.
    
- **Armazenamento de dados do arquivamento**. O armazenamento de dados do Skype for Business Server pode ser implementado como bancos de dados do SQL Server do Skype for Business Server ou, se você tiver uma implantação do Exchange integrada ao armazenamento do Exchange. 
    
O arquivamento também requer armazenamento de arquivos, mas usa o mesmo armazenamento de arquivos que os servidores front-end ou o servidor Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar os requisitos da sua organização para arquivamento

Para implementar o arquivamento, você precisa decidir como atender os requisitos da sua organização para arquivar, determinando o seguinte:
  
- **Qual opção de armazenamento usar**. Você pode implementar o armazenamento de uma desta duas formas ou combiná-las:
    
  - **Armazenamento do Exchange.** Se você tiver uma implantação do Exchange, poderá integrar o Skype for Business Server e o arquivamento do Exchange para que o Skype for Business Server e os dados do Exchange arquivados sejam armazenados juntos no Exchange. Se você habilitar a opção de integração do Microsoft Exchange, as caixas de correio do usuário hospedadas no Exchange Server usarão o armazenamento do Exchange para dados arquivados, mas somente se as caixas de correio tiverem sido colocadas no bloqueio in-loco. Por padrão, a integração do Microsoft Exchange não está habilitada.
    
  - **Armazenamento do Skype for Business Server.** Se você tiver usuários que não são hospedados no Exchange ou que não tiveram suas caixas de correio em bloqueio in-loco, ou se você não quiser usar a integração do Microsoft Exchange para qualquer um ou todos os usuários da sua implantação, poderá implantar bancos de dados do arquivamento do Skype for Business Server usando S Servidor QL.
    
- **Quando implantar**o arquivamento. Você pode implantar o arquivamento como parte da implantação inicial do Skype for Business Server, ou pode adicioná-lo a uma implantação existente. Para usar o armazenamento de arquivamento do Skype for Business Server (bancos de dados do SQL Server), você usa o construtor de topologias para adicionar os bancos de dados à sua topologia e, em seguida, publicar a topologia novamente. Se todos os seus usuários estiverem hospedados no Exchange e tiverem suas caixas de correio no bloqueio in-loco, você não precisará atualizar a topologia, mas só precisa habilitar a integração do Microsoft Exchange para armazenar dados armazenados no Exchange. 
    
- **Quais sites e usuários da organização requerem arquivamento**. Você pode definir as configurações de arquivamento para toda a sua organização e, opcionalmente, para sites, grupos, usuários e grupos de usuários específicos.
    
- **Qual conteúdo deve ser arquivado**. Se especificar o arquivamento global ou de sites e usuários específicos, você deverá especificar se é necessário habilitar estes tipos de conteúdo em cada um desses níveis: 
    
  - Mensagens instantâneas de ponto a ponto
    
  - Conferências (reuniões), que são mensagens instantâneas com vários participantes
    
  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)
    
  - Os quadros de comunicações e votações compartilhados durante uma conferência
    
- **Qual conteúdo não deve ser arquivado**. Os tipos de conteúdo a seguir não podem ser arquivados: 
    
  - Transferências de arquivo de ponto a ponto
    
  - Áudio e vídeo de mensagens instantâneas e conferências de ponto a ponto
    
  - Compartilhamento de área de trabalho e aplicativos em mensagens instantâneas e conferências de ponto a ponto
    
    O Skype for Business Server também não arquiva conversas persistentes de chat. Para arquivar conversas de chat persistentes, você deve habilitar e configurar o serviço de conformidade, que é um componente que pode ser implantado com o servidor de chat persistente. Para obter detalhes, consulte [plano para servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
    
- Por quanto **tempo os materiais arquivados devem ser mantidos**. O banco de dados de arquivamento não se destina à retenção de longo prazo, e o Skype for Business Server não fornece uma solução de descoberta eletrônica (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento. O Skype for Business Server oferece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados e que cria transcrições pesquisáveis dos dados arquivados. 
    
     Para a política global e para cada política de site e usuário que você criar, você pode especificar quando limpar dados arquivados e exportados. Para obter mais informações sobre como limpar dados, consulte [gerenciar a eliminação de dados arquivados no Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Para obter mais informações sobre como usar a ferramenta de exportação de sessão, consulte [exportar dados arquivados no Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
- **Arquivar comunicações internas ou externas ou não**. É possível habilitar o arquivamento de comunicações internas (comunicações entre usuários internos), comunicações externas (comunicações que incluem pelo menos um usuário fora da sua rede interna) ou ambos. É possível especificar essas opções para toda a sua organização ou para sites ou pools específicos. Por padrão, nenhuma dessas opções está habilitada.
    
    > [!NOTE]
    > O controle de arquivamento de comunicações internas ou externas só está disponível para a política do Skype for Business. Para o arquivamento integrado ao Exchange, as comunicações internas e externas são arquivadas ou não arquivadas. 
  
- **Implementar modo crítico ou não**. Se o arquivamento for um requisito para sua organização, a configuração do modo crítico bloqueará as sessões de mensagens instantâneas e de conferência no caso de uma falha do Skype for Business Server que impediria o arquivamento. Por exemplo: 
    
  - Um problema com o serviço de armazenamento do Skype for Business Server. Nesse caso, as mensagens instantâneas são bloqueadas para os usuários para os quais o arquivamento está habilitado.
    
  - Um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Nesse caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e não será possível ativar novas conferências.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após a correção das falhas.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Escolher opções de implantação e configuração de arquivamento

O arquivamento é instalado automaticamente em cada servidor front-end quando você implanta o servidor, mas não é habilitado até que você o configure. O modo de configuração está condicionado ao modo de implantação do arquivamento. Você pode implantar o arquivamento de uma destas formas:
  
- Usar o armazenamento do Microsoft Exchange
    
- Usar o armazenamento do Skype for Business Server
    
> [!NOTE]
> Se você implementar os bancos de dados de arquivamento do Skype for Business Server e habilitar a integração do Microsoft Exchange, as políticas do Exchange substituirão as políticas de arquivamento do Skype for Business Server, mas somente para os usuários que estiverem hospedados no Exchange e tiveram suas caixas de correio colocadas em Bloqueio in-loco. O arquivamento do Skype for Business depende da política de bloqueio in-loco do Microsoft Exchange. 
  
Se você implantar o arquivamento para um pool de front-end ou um servidor Standard Edition, habilite-o para todos os outros pools de front-end e servidores Standard Edition na sua implantação. Se o arquivamento não estiver habilitado no pool que hospeda a conversa ou reunião, todos os dados das conferências poderão não ser arquivados. O arquivamento de mensagens instantâneas continua funcionando, mas o conteúdo das conferências e os eventos podem não ser arquivados.
  
> [!NOTE]
> Para habilitar a delegação de tarefas administrativas enquanto mantém os padrões de segurança da sua organização, o Skype for Business Server usa o controle de acesso baseado em função (RBAC). Com o RBAC, o privilégio administrativo é concedido com a atribuição de usuários às funções administravas predefinidas. Para configurar políticas e configurações de arquivamento do Skype for Business, o usuário deve ser atribuído à função CsArchivingAdministrator (a menos que a configuração seja feita diretamente no servidor em que o arquivamento é implantado, em vez de ser remotamente de outro computador ). Para obter uma lista de direitos de usuário, permissões e funções necessárias para o arquivamento de implantação, consulte [implantar o arquivamento para o Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Se você usa a integração do Microsoft Exchange, a configuração das políticas do Exchange exige direitos e permissões de administrador adequados. Para obter detalhes, consulte a documentação do Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Armazenamento do Microsoft Exchange

 Se você escolher a integração do Microsoft Exchange, use políticas e configurações do Exchange para controlar o arquivamento do Skype for Business Server. Você pode configurar a opção de integração do Microsoft Exchange no nível global, nível de site e nível de pool. Se sua implantação inclui várias florestas, você deve sincronizar as configurações entre o Skype for Business Server e o Exchange. Você precisará determinar:
  
- Se arquivará mensagens instantâneas, conferências ou ambas
    
- Se deve implementar o modo crítico, que bloqueia as sessões de chat e conferência em caso de falha no Skype for Business Server 
    
- Seleção da opção de integração do Microsoft Exchange para usar o Exchange para armazenamento de dados arquivados
    
Para obter informações sobre como configurar políticas e configurações de bloqueio do Exchange in-loco para dar suporte ao arquivamento, consulte a documentação do produto Exchange.
  
### <a name="skype-for-business-server-storage"></a>Armazenamento do Skype for Business Server

Se você escolher o armazenamento do Skype for Business Server, use as políticas e as configurações de arquivamento do Skype for Business Server para controlar como o arquivamento está habilitado e implementado. O armazenamento do Skype for Business Server usa bancos de dados do SQL Server, portanto, você precisará adicionar os bancos de dados do SQL Server apropriados à sua topologia e, em seguida, configurar suas políticas de arquivamento. 
  
### <a name="add-storage-databases-to-your-topology"></a>Adicionar bancos de dados de armazenamento à sua topologia

Ao adicionar bancos de dados de armazenamento do SQL Server à sua topologia, você pode optar por posicionar os bancos de dados de arquivamento com qualquer um dos seguintes:
  
- Banco de dados de monitoramento
    
- Banco de dados back-end de um pool de front-ends Enterprise Edition
    
> [!NOTE]
> O servidor que estiver hospedando o banco de dados de arquivamento pode hospedar outros bancos de dados. No entanto, ao considerar colocar o banco de dados de arquivamento com outros bancos de dados, saiba que se você estiver arquivando as mensagens de muitos usuários, o espaço em disco necessário para o banco de dados de arquivamento poderá aumentar bastante. Por essa razão, não recomendamos a colocação do banco de dados de arquivamento no banco de dados back-end. 
  
Se você colocar o banco de dados de arquivamento com o banco de dados de monitoramento, banco de dados back-end ou ambos, você pode usar uma única instância SQL para qualquer ou todos os bancos de dados ou pode usar uma instância SQL separada para cada banco de dados, com o seguinte limitação: cada instância SQL pode conter apenas um único banco de dados back-end, um único banco de dados de monitoramento e um único banco de dados de arquivamento.
  
Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [noções básicas de topologia para o Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Para obter detalhes sobre como atualizar sua topologia para incluir bancos de dados de armazenamento, consulte [criar e publicar nova topologia no Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar opções de arquivamento e políticas de usuários

Você precisará determinar:
  
- Se habilitará ou desabilitará o arquivamento de comunicações internas e externas
    
- Se arquivará mensagens instantâneas, conferências ou ambas
    
- Se deve implementar o modo crítico, que bloqueia as sessões de chat e conferência em caso de falha no Skype for Business Server 
    
- Se habilitará políticas para usuários e grupos específicos
    
As opções de arquivamento do Skype for Business Server podem ser especificadas nos seguintes níveis. 
  
- **Opção de nível global**. Essa é uma configuração de arquivamento padrão e se aplica a toda a sua implantação. Ele é criado quando você implanta o Skype for Business Server e, por padrão, desabilita o arquivamento para comunicações internas e externas. Não é possível excluir essa opção. Se você escolher a opção excluir, a política global será redefinida para as configurações-padrão.
    
- **Opções de nível de site**. Você pode habilitar ou desabilitar o arquivamento de um ou mais sites específicos com a criação e configuração de uma opção de arquivamento de nível de site. Você pode excluir qualquer opção de arquivamento que criar nesse nível. As opções de arquivamento em nível de site substitui a opção global, mas apenas para o site especificado na opção. 
    
    Por exemplo, se você habilitar o arquivamento de comunicações internas e externas em sua configuração global e criar uma configuração de site na qual desabilita o arquivamento das comunicações externas, somente as comunicações internas do site em questão continuarão sendo arquivadas. Se você habilitar somente o arquivamento de mensagens instantâneas em sua configuração global e criar uma configuração de site na qual habilita o arquivamento de mensagens instantâneas e conferências, somente as conferências do site passam a ser arquivadas; as conferências do restante da organização não serão arquivadas.
    
- **Opções de nível de pool**. Você pode especificar as configurações de arquivamento de um ou mais pools específicos com a criação e configuração de uma configuração de nível de pool para o pool em questão. As configurações de arquivamento de nível de pool precisam ser criadas. Você pode modificar e excluir qualquer configuração desse tipo. Além disso, essas configurações substituem a configuração global e a configuração de arquivamento de qualquer site que você tenha criado. 
    
    Por exemplo, digamos que você habilite somente o arquivamento de mensagens instantâneas na sua configuração global, crie uma configuração de nível de site na qual você habilite o arquivamento de mensagens instantâneas e conferências e crie uma configuração de nível de pool na qual você habilite somente o arquivamento de mensagens instantâneas. Nesse caso, as comunicações de mensagens instantâneas e conferências de todos os usuários do site devem ser arquivadas, exceto dos usuários hospedados no pool especificado na configuração de nível de pool. Para todos os demais usuários da organização, somente o arquivamento de mensagens instantâneas está habilitado.
    
- **Políticas de arquivamento para usuários**. Você pode habilitar ou desabilitar o arquivamento de um ou mais usuários e grupos de usuários específicos, com a criação, configuração e aplicação de uma política de arquivamento de nível de usuário para os usuários e grupos de usuários especificados. Você pode excluir todas as políticas de arquivamento de nível de usuário que criar, além de poder alterar os usuários e grupos de usuários aos quais a política de arquivamento se aplica. As políticas de arquivamento de nível de usuário substitui a política global e todas as políticas de site, mas somente para os usuários e grupos de usuários aos quais a política se aplica. 
    
    Por exemplo, suponha que você desabilite o arquivamento para comunicações internas e externas em sua configuração global, crie uma política no nível do site na qual você habilitou o arquivamento para comunicações internas e externas e, em seguida, crie uma política de nível de usuário na qual você Desabilite o arquivamento para comunicações externas. As comunicações serão arquivadas para comunicações internas e externas para todos os usuários do site, exceto para os usuários aos quais você aplicar a política de nível de usuário--para esses usuários, somente as comunicações internas serão arquivadas.
    
Para obter detalhes sobre como definir as configurações de arquivamento iniciais ao implantar o arquivamento, consulte [implantar o arquivamento para o Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Para obter detalhes sobre o gerenciamento do arquivamento após a implantação, consulte [gerenciar o arquivamento no Skype for Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Ferramentas de configuração de arquivamento

 Você controla a maioria das opções de arquivamento usando o painel de controle do Skype for Business Server. No entanto, há algumas opções disponíveis somente ao usar o Shell de gerenciamento do Skype for Business Server. Essas opções incluem o arquivamento de mensagens duplicadas e dados arquivados de exportações. Para obter mais informações sobre como usar o painel de controle do Skype for Business Server e o Shell de gerenciamento do Skype for Business Server para gerenciar as políticas de arquivamento, consulte [gerenciar o arquivamento no Skype for Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Acessar dados arquivados

O acesso aos dados arquivados depende de onde eles estão armazenados: 
  
- **Armazenamento do Microsoft Exchange**. Se você escolher a opção de integração do Exchange, o Skype for Business Server depositará o conteúdo de arquivamento no repositório do Exchange para todos os usuários que estiverem hospedados no Exchange e quem tiver tido suas caixas de correio no bloqueio in-loco. Os dados arquivados são armazenados na pasta de itens recuperáveis da caixa de correio do usuário, o que geralmente é invisível para os usuários e só pode ser pesquisado por usuários com uma função de **Gerenciamento de descoberta** do Exchange. O Exchange permite pesquisa e descoberta federada, juntamente com o SharePoint, se estiver implantado. Para obter mais detalhes sobre armazenamento, retenção e descoberta de dados armazenados no Exchange, consulte a documentação do Exchange e do SharePoint.
    
- **Armazenamento de arquivamento do Skype for Business Server**. Se você configurar bancos de dados de arquivamento do Skype for Business Server, o Skype for Business Server depositará o conteúdo do arquivamento de conteúdo nos bancos de dados de arquivamento do Skype for Business Server para qualquer usuário que não seja hospedado no Exchange e que não tenham suas caixas de correio em bloqueio in-loco. This data is not searchable, but it can be exported to formats that are searchable using other tools. Para obter detalhes sobre como exportar dados armazenados em bancos de dados de arquivamento, consulte [exportar dados arquivados no Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre arquivamento, consulte os tópicos a seguir:
  
- [Implantar o arquivamento para o Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gerenciar o arquivamento no Skype for Business Server](../../manage/archiving/archiving.md)
    
Para obter mais detalhes sobre como o Skype for Business Server e o Exchange trabalham juntos, consulte [planejar a integração do Skype for Business e do Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

