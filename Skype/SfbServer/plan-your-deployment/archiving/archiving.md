---
title: Planejar o arquivamento em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumo: leia este tópico para saber como planejar o arquivamento no Skype for Business Server.'
ms.openlocfilehash: b763d2e771d054a1b7522e9af0eace4663f3ce0c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386429"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planejar o arquivamento em Skype for Business Server
 
**Resumo:** Leia este tópico para saber como planejar o arquivamento em Skype for Business Server.
  
Corporações e outras organizações estão sujeitas a um número cada vez maior de regulamentos setoriais e governamentais que exigem a retenção de tipos específicos de comunicações. Se sua organização tiver esses requisitos, você poderá usar o arquivamento no Skype for Business Server para arquivar mensagens instantâneas (IM) e comunicações de conferência (reunião) para ajudar a dar suporte a alguns dos seus requisitos de conformidade.
  
## <a name="archiving-components"></a>Componentes de arquivamento

Skype for Business Server usa os seguintes componentes de arquivamento:
  
- **Operadores de arquivamento**. Os agentes de arquivamento (também conhecidos como agentes unificados de coleta de dados) são instalados e ativados automaticamente em cada pool de Front-End Edição Enterprise e Edição Standard Server. Embora os agentes de arquivamento sejam ativados automaticamente, nenhuma mensagem será capturada até que o arquivamento seja habilitado e configurado adequadamente. Por padrão, o arquivamento está desabilitado.
    
- **Armazenamento de dados de arquivamento**. O armazenamento de dados para Skype for Business Server pode ser implementado como bancos de dados Skype for Business Server SQL Server, ou, se você tiver uma implantação Exchange, integrada ao Exchange armazenamento. 
    
O arquivamento também requer armazenamento de arquivos, mas o arquivamento usa o mesmo armazenamento de arquivo que os Servidores Front-End ou Edição Standard Server.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar os requisitos de suas organizações para arquivamento

Para implementar o arquivamento, você precisa decidir como atender aos requisitos de arquivamento da sua organização determinando o seguinte:
  
- **Qual opção de armazenamento usar**. Você pode implementar o armazenamento de duas maneiras ou usar uma combinação de ambas:
    
  - **Exchange armazenamento.** Se você tiver uma implantação Exchange, poderá integrar o arquivamento Skype for Business Server e Exchange para que seus dados arquivados do Skype for Business Server e Exchange sejam armazenados juntos Exchange. Se você habilitar Exchange opção de integração do Microsoft Exchange, as caixas de correio de usuário habilitadas no Exchange Server usam o armazenamento Exchange para dados arquivados, mas somente se as caixas de correio foram colocadas em In-Place Hold. Por padrão, a integração Exchange microsoft não está habilitada.
    
  - **Skype for Business Server armazenamento.** Se você tiver usuários que não estão em casa no Exchange ou que não tiveram suas caixas de correio colocadas no In-Place Hold, ou se você não quiser usar a integração do Microsoft Exchange para qualquer ou todos os usuários em sua implantação, poderá implantar bancos de dados de Arquivamento Skype for Business Server usando o SQL Server.
    
- **Quando implantar o arquivamento**. Você pode implantar o arquivamento como parte da implantação Skype for Business Server inicial ou adicioná-lo a uma implantação existente. Para usar Skype for Business Server de arquivamento (SQL Server bancos de dados), use o Construtor de Topologias para adicionar os bancos de dados à sua topologia e, em seguida, publique a topologia novamente. Se todos os seus usuários estão em casa no Exchange e suas caixas de correio são colocadas em In-Place espera, você não precisa atualizar sua topologia, mas só precisa habilitar a integração do Microsoft Exchange para armazenar dados arquivados no Exchange. 
    
- **Quais sites e usuários na organização exigem arquivamento**. Você pode configurar configurações de arquivamento para toda a sua organização e, opcionalmente, para sites, pools, usuários e grupos de usuários específicos.
    
- **Qual conteúdo deve ser arquivado**. Se você especificar o arquivamento no nível global ou para sites e usuários específicos, em cada um desses níveis, especifique se deve habilitar os seguintes tipos de conteúdo: 
    
  - Mensagens instantâneas de ponto a ponto
    
  - Conferências (reuniões), que são mensagens instantâneas com vários participantes
    
  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)
    
  - Os quadros de comunicações e votações compartilhados durante uma conferência
    
- **Qual conteúdo não pode ser arquivado**. Os seguintes tipos de conteúdo não podem ser arquivados: 
    
  - Transferências de arquivo ponto a ponto
    
  - Áudio/vídeo para mensagens instantâneas e conferências de ponto a ponto
    
  - O compartilhamento de área de trabalho e aplicativos para mensagens instantâneas e conferências de ponto a ponto
    
    Skype for Business Server também não arquiva conversas de Chat Persistente. Para arquivar conversas de Chat Persistente, você deve habilitar e configurar o serviço de Conformidade, que é um componente que pode ser implantado com o Servidor de Chat Persistente. Para obter detalhes, [consulte Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 
    
- **Por quanto tempo os materiais arquivados devem ser mantidos**. O banco de dados de arquivamento não se destina à retenção a longo prazo, e o Skype for Business Server não fornece uma solução de descoberta por e-discovery (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento. Skype for Business Server fornece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados e que cria transcrições pesquisáveis dos dados arquivados. 
    
     Para a política global e para cada site e política de usuário que você criar, você pode especificar quando limpar dados arquivados e exportados. Para obter mais informações sobre como excluir dados, consulte [Manage purging of archived data in Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Para obter mais informações sobre como usar a ferramenta de exportação de sessão, consulte [Exportar dados arquivados em Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
- **Arquivar comunicações internas ou externas ou não**. É possível habilitar o arquivamento para comunicações internas (comunicações entre usuários internos), comunicações externas (comunicações que incluem pelo menos um usuário fora da sua rede interna) ou ambos. É possível especificar estas opções para toda sua organização ou é possível especificá-lo para locais ou pools específicos. Por padrão, nenhuma opção é habilitada.
    
    > [!NOTE]
    > O controle do arquivamento para comunicações internas ou externas está disponível apenas para Skype for Business Política. Para Exchange arquivamento integrado, as comunicações internas e externas são arquivadas ou não arquivadas. 
  
- **Se deve implementar o modo crítico**. Se o arquivamento for um requisito para sua organização, a configuração do modo crítico bloqueará sessões de IM e conferência no caso de uma falha Skype for Business Server que impediria o arquivamento. Por exemplo: 
    
  - Um problema com o serviço de Skype for Business Server de armazenamento. Nesse caso, o IM é bloqueado para usuários habilitados para arquivamento.
    
  - Um compartilhamento de arquivo indisponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Escolha opções de implantação e configuração de arquivamento

O arquivamento é instalado automaticamente em cada Servidor Front-End quando você implanta o servidor, mas o arquivamento não é habilitado até que você o configure. A forma como você configura o arquivamento é determinado pela forma como você o implanta. Você pode implantar o arquivamento de uma das seguintes maneiras:
  
- Usar o armazenamento Exchange Microsoft
    
- Usar Skype for Business Server armazenamento
    
> [!NOTE]
> Se você implementar os dois bancos de dados de arquivamento Skype for Business Server e habilitar Exchange integração do Microsoft Exchange, as políticas de Exchange substituem as políticas de arquivamento Skype for Business Server, mas somente para usuários que estão no Exchange  e tiveram suas caixas de correio colocadas em In-Place Hold. Skype for Business arquivamento depende da política de Exchange In-Place de espera da Microsoft. 
  
Se você implantar o arquivamento para um pool de Front-End ou Edição Standard Server, deverá habilita-lo para todos os outros pools de Front-End e servidores Edição Standard em sua implantação. Se o arquivamento não estiver habilitado no pool onde uma conversa ou reunião está hospedada, todos os dados de conferência podem não ser arquivados. O arquivamento ainda funcionará para mensagens de mensagens de mensagens IM, mas o conteúdo e os eventos de conferência podem não ser arquivados.
  
> [!NOTE]
> Para habilitar a delegação de tarefas administrativas enquanto mantém os padrões de segurança da sua organização, Skype for Business Server usa o controle de acesso baseado em função (RBAC). Com RBAC, o privilégio administrativo é concedido atribuindo usuários às funções administravas predefinidas. Para configurar Skype for Business configurações e políticas de arquivamento, o usuário deve ser atribuído à função CsArchivingAdministrator (a menos que a configuração seja feita diretamente no servidor onde o arquivamento é implantado, em vez de remotamente de outro computador). Para uma lista dos direitos, permissões e funções do usuário necessários para a implantação de arquivamento, consulte [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Se você usar a integração do Microsoft Exchange, a configuração de políticas Exchange requer direitos e permissões de administrador apropriados. Para obter detalhes, consulte a documentação Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange armazenamento

 Se você escolher a integração do Microsoft Exchange, use Exchange políticas e configurações para controlar o arquivamento de Skype for Business Server. Você pode configurar a opção Exchange de integração do Microsoft no nível global, no nível do site e no nível do pool. Se sua implantação incluir várias florestas, você deverá sincronizar as configurações entre Skype for Business Server e Exchange. Você precisará determinar:
  
- Se deve arquivar mensagens de IM, conferência ou ambos
    
- Se deve implementar o modo crítico, que bloqueia sessões de IM e conferência em caso de Skype for Business Server falha 
    
- Seleção da opção de integração Exchange microsoft para usar Exchange armazenamento de dados arquivados
    
Para obter informações sobre como configurar Exchange In-Place e configurações de espera para dar suporte ao arquivamento, consulte a documentação Exchange do produto.
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server armazenamento

Se você escolher Skype for Business Server armazenamento, use Skype for Business Server e configurações de arquivamento para controlar como o arquivamento é habilitado e implementado. Skype for Business Server armazenamento usa SQL Server bancos de dados, portanto, você precisará adicionar os bancos de dados de SQL Server apropriados à sua topologia e, em seguida, configurar suas políticas de arquivamento. 
  
### <a name="add-storage-databases-to-your-topology"></a>Adicionar bancos de dados de armazenamento à sua topologia

Ao adicionar SQL Server de armazenamento à sua topologia, você pode optar por colocar os bancos de dados de arquivamento com qualquer um dos seguintes:
  
- Banco de dados de monitoramento
    
- Banco de dados back-end de um pool de Front-Ends Enterprise Edition
    
> [!NOTE]
> O servidor que estiver hospedando o banco de dados de arquivamento pode hospedar outros bancos de dados. No entanto, ao considerar colocar o banco de dados de arquivamento com outros bancos de dados, saiba que se você estiver arquivando as mensagens de muitos usuários, o espaço em disco necessário para o banco de dados de arquivamento poderá aumentar bastante. Por essa razão, não recomendamos a colocação do banco de dados de arquivamento no banco de dados back-end. 
  
Se você contiver o banco de dados de Arquivamento com o banco de dados de Monitoramento, o banco de dados back-end ou ambos esses bancos de dados, poderá usar uma única instância de SQL para qualquer ou todos os bancos de dados ou pode usar uma instância de SQL separada para cada banco de dados, com a seguinte limitação: Cada instância do SQL pode conter apenas um único banco de dados back-end, um único banco de dados de Monitoramento,  e banco de dados de arquivamento único.
  
Para obter detalhes sobre a localização de todas as funções de servidor e bancos de dados, consulte [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Para obter detalhes sobre como atualizar sua topologia para incluir bancos de dados de armazenamento, consulte [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar opções de arquivamento e políticas de usuário

Você precisará determinar:
  
- Se deve habilitar ou desabilitar o arquivamento para comunicações internas e externas
    
- Se deve arquivar mensagens de IM, conferência ou ambos
    
- Se deve implementar o modo crítico, que bloqueia sessões de IM e conferência em caso de Skype for Business Server falha 
    
- Se é possível habilitar políticas para usuários e grupos específicos
    
Skype for Business Server opções de Arquivamento podem ser especificadas nos níveis a seguir. 
  
- **Opção de nível global**. Essa é a configuração padrão de arquivamento e se aplica a toda a implantação. Ele é criado quando você implanta Skype for Business Server e, por padrão, desabilita o arquivamento para comunicações internas e externas. Não é possível excluir essa opção. Se você escolher a opção excluir, a opção global será redefinida para as configurações padrão.
    
- **Opções de nível de site**. Você pode habilitar ou desabilitar o arquivamento de um ou mais sites específicos criando e configurando uma opção de arquivamento no nível do site para o site. Você pode excluir qualquer opção de arquivamento no nível do site que você criar. Uma opção de arquivamento no nível do site substitui a opção global, mas somente para o site especificado na opção. 
    
    Por exemplo, se você habilitar o arquivamento para comunicações internas e externas em sua configuração global e criar uma configuração de site na qual desabilite o arquivamento para comunicações externas, somente as comunicações internas serão arquivadas para esse site. Para outro exemplo, se você habilitar o arquivamento apenas para IM em sua configuração global e criar uma configuração de site na qual você habilita o arquivamento para IM e conferência, a conferência só será arquivada para o site, não para o restante da sua organização.
    
- **Opções de nível de pool**. Você pode especificar configurações de arquivamento para um ou mais pools específicos criando e configurando uma configuração no nível do pool para o pool individual. Uma configuração de arquivamento no nível do pool só existe se você a criar. Você pode modificar e excluir qualquer configuração de arquivamento no nível do pool. Uma configuração de arquivamento no nível do pool substitui a configuração global e qualquer configuração de arquivamento de site que você possa ter criado. 
    
    Por exemplo, suponha que você habilita o arquivamento para IM somente em sua configuração global, crie uma configuração no nível do site na qual você habilita o arquivamento para IM e conferência e, em seguida, crie uma configuração no nível do pool na qual você habilita o arquivamento somente para IM. As comunicações seriam arquivadas para IM e conferência para todos os usuários do site, exceto os usuários que estavam no pool especificado na configuração no nível do pool. Para todos os outros usuários da sua organização, o arquivamento seria habilitado apenas para IM.
    
- **Políticas de arquivamento do usuário**. Você pode habilitar ou desabilitar o arquivamento para um ou mais usuários e grupos específicos de usuários criando, configurando e aplicando uma política de arquivamento no nível do usuário para os usuários e grupos de usuários especificados. Você pode excluir qualquer política de arquivamento no nível do usuário que você criar e pode alterar a qual usuários e grupo de usuários a política de arquivamento se aplica. Uma política de arquivamento no nível do usuário substitui a política global e todas as políticas de site, mas somente para usuários e grupos de usuários aos quais a política é aplicada. 
    
    Por exemplo, suponha que você desabilite o arquivamento para comunicações internas e externas em sua configuração global, crie uma política no nível do site na qual você habilita o arquivamento para comunicações internas e externas e crie uma política no nível do usuário na qual desabilite o arquivamento para comunicações externas. As comunicações seriam arquivadas para comunicações externas e internas para todos os usuários do site, exceto para os usuários aos quais você aplica a política no nível do usuário, pois esses usuários apenas as comunicações internas seriam arquivadas.
    
Para obter detalhes sobre como configurar as configurações iniciais de arquivamento ao implantar o arquivamento, consulte [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Para obter detalhes sobre como gerenciar o arquivamento após a implantação, consulte [Manage archiving in Skype for Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Ferramentas de configuração de arquivamento

 Você controla a maioria das opções de arquivamento usando o painel Skype for Business Server controle. No entanto, há algumas opções disponíveis apenas usando o Shell Skype for Business Server Gerenciamento. Essas opções incluem arquivamento de mensagens duplicadas e exportação de dados arquivados. Para obter mais informações sobre como usar o Painel de Controle Skype for Business Server e o Shell de Gerenciamento Skype for Business Server para gerenciar políticas de arquivamento, consulte [Manage archiving in Skype for Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Acessar dados arquivados

O acesso aos dados arquivados depende de onde os dados estão armazenados: 
  
- **Armazenamento Exchange Microsoft**. Se você escolher Exchange opção de integração do Skype for Business Server, o Skype for Business Server deposita o conteúdo de arquivamento no armazenamento do Exchange para todos os usuários que estão no Exchange e que tiveram suas caixas de correio colocadas em In-Place Hold. Os dados arquivados são armazenados na pasta itens recuperáveis de caixas de correio do usuário, que geralmente são invisíveis para os usuários e só podem ser pesquisados por usuários com uma função de Gerenciamento de Descoberta **Exchange.** Exchange habilita a pesquisa e a descoberta federadas, juntamente com SharePoint, se ela for implantada. Para obter mais detalhes sobre armazenamento, retenção e descoberta de dados armazenados no Exchange, consulte a documentação Exchange e SharePoint.
    
- **Skype for Business Server de arquivamento**. Se você configurar Skype for Business Server bancos de dados de Arquivamento, o Skype for Business Server deposita conteúdo de arquivamento nos bancos de dados de arquivamento do Skype for Business Server para quaisquer usuários que não tenham sido Exchange e que não tenham suas caixas de correio colocadas In-Place Espera. Esses dados não podem ser pesquisados, mas eles podem ser exportados para formatos que podem ser pesquisados utilizando outras ferramentas. Para obter detalhes sobre como exportar dados armazenados em bancos de dados de arquivamento, consulte [Exportar dados arquivados em Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre arquivamento, consulte os seguintes tópicos:
  
- [Implantar arquivamento para Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gerenciar arquivamento em Skype for Business Server](../../manage/archiving/archiving.md)
    
Para obter mais detalhes sobre como Skype for Business Server e Exchange trabalhar juntos, consulte [Plan to integrate Skype for Business and Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

