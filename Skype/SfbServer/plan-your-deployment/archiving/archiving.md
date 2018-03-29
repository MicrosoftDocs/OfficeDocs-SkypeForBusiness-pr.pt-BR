---
title: Planejar o arquivamento no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumo: Leia este tópico para saber como planejar para arquivamento no Skype para Business Server 2015.'
ms.openlocfilehash: 53895a404c2502a0d54553fda979add6031b09f6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-archiving-in-skype-for-business-server-2015"></a>Planejar o arquivamento no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como planejar para arquivamento no Skype para Business Server 2015.
  
As corporações e outras organizações estão sujeitas à crescente quantidade de regulamentações do setor e governamentais que requerem a retenção de tipos específicos de comunicação. Se sua organização tiver esses requisitos, você pode usar o arquivamento no Skype para Business Server 2015 para arquivar mensagens instantâneas (IM) e comunicações de webconferência (reunião) para ajudar a oferecer suporte a alguns dos seus requisitos de conformidade.
  
## <a name="archiving-components"></a>Componentes de arquivamento

Skype para Business Server usa os seguintes componentes de arquivamento:
  
- **Agentes de arquivamento**. Os agentes de arquivamento, também conhecido como agentes de coleta de dados unificados, são instalados e ativados automaticamente em todos os pools de front-ends e no servidor Standard Edition. Embora os operadores de arquivamento sejam ativados automaticamente, nenhuma mensagem será capturada até que o arquivamento seja habilitado e configurado adequadamente. Por padrão, o arquivamento está desabilitado.
    
- **Armazenamento de dados do arquivamento**. Armazenamento de dados para Skype para Business Server 2015 pode ser implementado como Skype para bancos de dados do SQL Server Business Server ou, se você tiver uma implantação do Exchange, integrado ao armazenamento do Exchange. 
    
O arquivamento também requer armazenamento de arquivos, mas usa o mesmo armazenamento de arquivos que os servidores front-end ou o servidor Standard Edition.
  
Para obter uma lista dos requisitos de hardware e software para arquivamento, consulte [requisitos de Hardware e software para arquivamento no Skype para Business Server 2015](hardware-and-software-requirements.md).
  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar os requisitos da sua organização para arquivamento

Para implementar o arquivamento, você precisará decidir como atender aos requisitos da sua organização para arquivamento, determinando o seguinte:
  
- **Qual opção de armazenamento usar**. Você pode implementar o armazenamento de uma desta duas formas ou combiná-las:
    
  - **Armazenamento do Exchange.** Se você tiver uma implantação do Exchange, você poderá integrar Skype Business Server e o arquivamento do Exchange para que seu Skype para Business Server e dados do Exchange arquivada são armazenados juntos no Exchange. Se você habilitar a opção de integração do Microsoft Exchange, caixas de correio de usuário hospedagem no uso do Exchange Server para dados arquivados, mas somente se as caixas de correio tenham sido colocadas em retenção In-loco de armazenamento do Exchange. Por padrão, a integração com o Microsoft Exchange não está habilitada.
    
  - **Skype para armazenamento de servidor de negócios.** Se você tiver usuários que não são hospedados no Exchange ou que não tiveram suas caixas de correio colocadas em retenção In-loco, ou se você não quiser usar a integração do Microsoft Exchange para um ou todos os usuários em sua implantação, você pode implantar o Skype para bancos de dados corporativos servidor de arquivamento usando S QL Server.
    
- **Quando implantar o arquivamento**. Você pode implantar o arquivamento como parte do seu Skype inicial para implantação de servidor de negócios, ou você pode adicioná-lo a uma implantação existente. Para usar o Skype para armazenamento de arquivamento Business Server (bancos de dados do SQL Server), use o construtor de topologias para adicionar os bancos de dados à sua topologia e publique a topologia novamente. Se todos os usuários hospedados no Exchange e tem colocado de suas caixas de correio em bloqueio In-loco, você não precisa atualizar sua topologia, mas só precisa habilitar a integração do Microsoft Exchange armazenar os dados arquivados no Exchange. 
    
- **Quais sites e usuários da organização requerem arquivamento**. Você pode definir configurações de arquivamento para toda sua organização e, opcionalmente, para sites específicos, pools, os usuários e grupos de usuários.
    
- **Qual conteúdo deve ser arquivado**. Se especificar o arquivamento global ou de sites e usuários específicos, você deverá especificar se é necessário habilitar estes tipos de conteúdo em cada um desses níveis: 
    
  - Mensagens instantâneas de ponto a ponto
    
  - Conferências (reuniões), que são mensagens instantâneas com vários participantes
    
  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)
    
  - Os quadros de comunicações e votações compartilhados durante uma conferência
    
- **Qual conteúdo não deve ser arquivado**. Os tipos de conteúdo a seguir não podem ser arquivados: 
    
  - Transferências de arquivo de ponto a ponto
    
  - Áudio e vídeo de mensagens instantâneas e conferências de ponto a ponto
    
  - Compartilhamento de área de trabalho e aplicativos em mensagens instantâneas e conferências de ponto a ponto
    
    Skype para Business Server também não arquivar conversas de Chat persistente. Para arquivar conversas de Chat persistente, você deve habilitar e configurar o serviço de conformidade, que é um componente que pode ser implantado com o servidor de Chat persistente. Para obter detalhes, consulte [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).
    
- **Quanto tempo arquivados materiais devem ser retidos**. O banco de dados de arquivamento não se destina a retenção de longo prazo e Skype para Business Server não ofereça uma solução de descoberta eletrônica (pesquisa) para dados arquivados, portanto é necessário ser movido para outro armazenamento de dados. Skype para Business Server oferece uma ferramenta de exportação de sessão que você pode usar para exportar os dados arquivados e que cria transcrições pesquisáveis dos dados arquivados. 
    
     Para a política global e para cada política de site e de usuário que você criar, você pode especificar quando limpar os dados arquivados e exportados. Para obter mais informações sobre a limpeza de dados, consulte [Gerenciar a limpeza de dados arquivados no Skype para Business Server 2015](../../manage/archiving/purging-of-archived-data.md). Para obter mais informações sobre como usar a sessão ferramenta de exportação, consulte [exportar os dados arquivados no Skype para Business Server 2015](../../manage/archiving/export-archived-data.md).
    
- **Arquivar comunicações internas ou externas ou não**. É possível habilitar o arquivamento de comunicações internas (comunicações entre usuários internos), comunicações externas (comunicações que incluem pelo menos um usuário fora da sua rede interna) ou ambos. É possível especificar essas opções para toda a sua organização ou para sites ou pools específicos. Por padrão, nenhuma dessas opções está habilitada.
    
    > [!NOTE]
    > Controlar o arquivamento de comunicações internos ou externos só está disponível para Skype para a política de negócios. Para arquivamento do Exchange integrado, comunicações internas e externas são arquivadas ou não arquivadas. 
  
- **Implementar modo crítico ou não**. Se o arquivamento é um requisito para sua organização, configurando o modo crítico para bloquear sessões de mensagens Instantâneas e conferência em caso de um Skype para falha do servidor de negócios que impediria a arquivamento. Por exemplo: 
    
  - Um problema com o Skype para o serviço de armazenamento do servidor de negócios. Nesse caso, as mensagens instantâneas são bloqueadas para os usuários para os quais o arquivamento está habilitado.
    
  - Um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Nesse caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e não será possível ativar novas conferências.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após a correção das falhas.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Escolher opções de implantação e configuração de arquivamento

O arquivamento é instalado automaticamente em cada servidor front-end quando você implanta o servidor, mas não é habilitado até que você o configure. O modo de configuração está condicionado ao modo de implantação do arquivamento. Você pode implantar o arquivamento de uma destas formas:
  
- Usar o armazenamento do Microsoft Exchange
    
- Usar Skype para armazenamento de servidor de negócios
    
> [!NOTE]
> Se você implementa a ambos os Skype para bancos de dados de arquivamento do servidor de negócios e habilitar a integração do Microsoft Exchange, as políticas do Exchange substituem Skype para Business Server políticas de arquivamento, mas somente para usuários que estão hospedados no serviço do Exchange e que tenham tido suas caixas de correio colocadas em Bloqueio in-loco. Skype para arquivamento de negócios depende a política de retenção de In-loco do Microsoft Exchange. 
  
Se você implantar o arquivamento para um pool de Front-End ou servidor Standard Edition, você deve habilitá-lo para todos os outros pools de Front-End e servidores Standard Edition em sua implantação. Se o arquivamento não estiver habilitado no pool que hospeda a conversa ou reunião, todos os dados das conferências poderão não ser arquivados. O arquivamento de mensagens instantâneas continua funcionando, mas o conteúdo das conferências e os eventos podem não ser arquivados.
  
> [!NOTE]
> Para habilitar a delegação de tarefas administrativas enquanto mantém os padrões de segurança da sua organização, Skype para Business Server usa o controle de acesso baseado em função (RBAC). Com o RBAC, o privilégio administrativo é concedido com a atribuição de usuários às funções administravas predefinidas. Para configurar o Skype para configurações e políticas de arquivamento de negócios, o usuário deve ser atribuído à função CsArchivingAdministrator (a menos que a configuração é feita diretamente no servidor onde arquivamento tiver sido implantado, em vez de remotamente de outro computador ). Para obter uma lista dos direitos de usuário, permissões e funções exigidas para arquivamento de implantação, consulte [Deploy arquivamento para Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Se você usar a integração do Microsoft Exchange, a configuração de políticas do Exchange requer permissões e direitos de administrador apropriadas. Para obter detalhes, consulte a documentação do Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Armazenamento do Microsoft Exchange

 Se você escolher a integração com o Microsoft Exchange, use Exchange políticas e configurações para controlar o arquivamento de Skype para Business Server. Você pode configurar a opção de integração do Microsoft Exchange no nível global, nível de site e nível de pool. Se sua implantação incluir várias florestas, você deve sincronizar as configurações entre Skype para Business Server e o Exchange. Você precisará determinar:
  
- Se arquivará mensagens instantâneas, conferências ou ambas
    
- Se implementará o modo crítico, que bloqueia a sessões de mensagens Instantâneas e conferência em caso de um Skype para falha do servidor de negócios 
    
- Seleção da opção de integração do Microsoft Exchange para usar o Exchange para o armazenamento de dados arquivados
    
Para obter informações sobre como definir configurações para dar suporte ao arquivamento e as políticas de retenção de In-loco do Exchange, consulte a documentação de produto do Exchange.
  
### <a name="skype-for-business-server-storage"></a>Armazenamento do Skype for Business Server

Se você escolher Skype para armazenamento Business Server, você use Skype para configurações e políticas de arquivamento Business Server para controlar como o arquivamento é habilitado e implementado. Skype para armazenamento Business Server usa bancos de dados do SQL Server, então você precisará adicionar os bancos de dados do SQL Server apropriados à sua topologia e, em seguida, configurar suas políticas de arquivamento. 
  
### <a name="add-storage-databases-to-your-topology"></a>Adicionar bancos de dados de armazenamento à sua topologia

Ao adicionar bancos de dados de armazenamento do SQL Server à sua topologia, você pode optar por colocar os bancos de dados de arquivamento com qualquer um dos seguintes procedimentos:
  
- Banco de dados de monitoramento
    
- Banco de dados back-end de um pool de front-ends Enterprise Edition
    
> [!NOTE]
> O servidor que estiver hospedando o banco de dados de arquivamento pode hospedar outros bancos de dados. No entanto, ao considerar colocar o banco de dados de arquivamento com outros bancos de dados, saiba que se você estiver arquivando as mensagens de muitos usuários, o espaço em disco necessário para o banco de dados de arquivamento poderá aumentar bastante. Por essa razão, não recomendamos a colocação do banco de dados de arquivamento no banco de dados back-end. 
  
Se você colocar o banco de dados de arquivamento com o banco de dados de monitoramento, banco de dados de back-end ou ambos desses bancos de dados, você pode usar uma única instância do SQL para um ou todos os bancos de dados, ou você pode usar uma instância SQL separada para cada banco de dados, com os seguintes itens limitação: instância SQL Each pode conter somente um único banco de dados de back-end, o único banco de dados de monitoramento e único banco de dados de arquivamento.
  
Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [Noções básicas de topologia para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md). Para obter detalhes sobre como atualizar sua topologia para incluir bancos de dados de armazenamento, consulte [criar e publicar a nova topologia no Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar opções de arquivamento e políticas de usuários

Você precisará determinar:
  
- Se habilitará ou desabilitará o arquivamento de comunicações internas e externas
    
- Se arquivará mensagens instantâneas, conferências ou ambas
    
- Se implementará o modo crítico, que bloqueia a sessões de mensagens Instantâneas e conferência em caso de um Skype para falha do servidor de negócios 
    
- Se habilitará políticas para usuários e grupos específicos
    
Skype para opções de arquivamento do servidor de negócios pode ser especificada nos seguintes níveis. 
  
- **Opção de nível global**. Essa é uma configuração de arquivamento padrão e se aplica a toda a sua implantação. Ela é criada quando você implanta o Skype para Business Server e, por padrão, desabilita o arquivamento de comunicações internas e externas. Não é possível excluir essa opção. Se você escolher a opção excluir, a política global será redefinida para as configurações-padrão.
    
- **Opções de nível de site**. Você pode habilitar ou desabilitar o arquivamento de um ou mais sites específicos com a criação e configuração de uma opção de arquivamento de nível de site. Você pode excluir qualquer opção de arquivamento que criar nesse nível. As opções de arquivamento em nível de site substitui a opção global, mas apenas para o site especificado na opção. 
    
    Por exemplo, se você habilitar o arquivamento de comunicações internas e externas em sua configuração global e criar uma configuração de site na qual desabilita o arquivamento das comunicações externas, somente as comunicações internas do site em questão continuarão sendo arquivadas. Se você habilitar somente o arquivamento de mensagens instantâneas em sua configuração global e criar uma configuração de site na qual habilita o arquivamento de mensagens instantâneas e conferências, somente as conferências do site passam a ser arquivadas; as conferências do restante da organização não serão arquivadas.
    
- **Opções de nível de pool**. Você pode especificar as configurações de arquivamento de um ou mais pools específicos com a criação e configuração de uma configuração de nível de pool para o pool em questão. As configurações de arquivamento de nível de pool precisam ser criadas. Você pode modificar e excluir qualquer configuração desse tipo. Além disso, essas configurações substituem a configuração global e a configuração de arquivamento de qualquer site que você tenha criado. 
    
    Por exemplo, digamos que você habilite somente o arquivamento de mensagens instantâneas na sua configuração global, crie uma configuração de nível de site na qual você habilite o arquivamento de mensagens instantâneas e conferências e crie uma configuração de nível de pool na qual você habilite somente o arquivamento de mensagens instantâneas. Nesse caso, as comunicações de mensagens instantâneas e conferências de todos os usuários do site devem ser arquivadas, exceto dos usuários hospedados no pool especificado na configuração de nível de pool. Para todos os demais usuários da organização, somente o arquivamento de mensagens instantâneas está habilitado.
    
- **Políticas de arquivamento para usuários**. Você pode habilitar ou desabilitar o arquivamento de um ou mais usuários e grupos de usuários específicos, com a criação, configuração e aplicação de uma política de arquivamento de nível de usuário para os usuários e grupos de usuários especificados. Você pode excluir todas as políticas de arquivamento de nível de usuário que criar, além de poder alterar os usuários e grupos de usuários aos quais a política de arquivamento se aplica. As políticas de arquivamento de nível de usuário substitui a política global e todas as políticas de site, mas somente para os usuários e grupos de usuários aos quais a política se aplica. 
    
    Por exemplo, suponha que você desabilitar o arquivamento de comunicações internas e externas em sua configuração global, criar uma política de nível do site no qual você habilita o arquivamento de comunicações internas e externas e, em seguida, criar uma política de nível de usuário na qual você Desabilite o arquivamento de comunicações externas. Comunicações fosse arquivadas para comunicação interna e externa para todos os usuários do site, exceto os usuários aos quais você aplica a política de nível do usuário – desses usuários comunicações internas apenas seriam ser arquivadas.
    
Para obter detalhes sobre como configurar as configurações de arquivamento iniciais quando você implanta o arquivamento, consulte [implantar o arquivamento para Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md). Para obter detalhes sobre como gerenciar o arquivamento após a implantação, consulte [Gerenciar o arquivamento no Skype para Business Server 2015](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Ferramentas de configuração de arquivamento

 Você pode controlar a maioria das opções de arquivamento usando o Skype para painel de controle do servidor de negócios. No entanto, há algumas opções disponíveis somente por meio do Skype do Shell de gerenciamento do servidor de negócios. Essas opções incluem o arquivamento de mensagens duplicadas e dados arquivados de exportações. Para obter mais informações sobre como usar o Skype para painel de controle do Business Server e do Skype do Shell de gerenciamento do servidor de negócios para gerenciar políticas de arquivamento, consulte [Gerenciar o arquivamento no Skype para Business Server 2015](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Acessar dados arquivados

O acesso aos dados arquivados depende de onde eles estão armazenados: 
  
- **Armazenamento do Microsoft Exchange**. Se você escolher a opção de integração do Exchange, Skype para Business Server deposita o arquivamento de conteúdo no repositório do Exchange para todos os usuários hospedados no Exchange, e que tenha tido suas caixas de correio colocadas em retenção In-loco. Os dados arquivados são armazenados na pasta de itens recuperáveis usuário caixas de correio, que é geralmente invisível para usuários e só poderá ser pesquisada por usuários com uma função de **Gerenciamento de descoberta** do Exchange. Exchange habilita a pesquisa federada e descoberta, juntamente com o SharePoint, se ele for implantado. Para obter mais detalhes sobre o armazenamento, retenção e descoberta de dados armazenados no Exchange, consulte a documentação do Exchange e SharePoint.
    
- **Skype para armazenamento de arquivamento Business Server**. Se você configurar Skype para bancos de dados de arquivamento do servidor de negócios, Skype para depósitos Business Server arquivamento de conteúdo no Skype para bancos de dados de arquivamento do servidor de negócios para todos os usuários não hospedados no Exchange e que não tiveram suas caixas de correio colocadas em retenção In-loco. Esses dados não podem ser pesquisados, mas é possível exportá-los para formatos que podem ser pesquisados com o uso de outras ferramentas. Para obter detalhes sobre como exportar dados armazenados nos bancos de dados de arquivamento, consulte [exportar os dados arquivados no Skype para Business Server 2015](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre arquivamento, consulte os tópicos a seguir:
  
- [Implantar o arquivamento para Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gerenciar o arquivamento no Skype para Business Server 2015](../../manage/archiving/archiving.md)
    
Para obter mais detalhes sobre como Skype para Business Server e do Exchange funcionam juntas, consulte [Planejar a integração do Skype para Exchange e de negócios](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

