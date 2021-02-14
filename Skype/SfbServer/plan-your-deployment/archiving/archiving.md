---
title: Planejar arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumo: Leia este tópico para saber como planejar o arquivamento no Skype for Business Server.'
ms.openlocfilehash: b868555b0a79b1abdfd96e50cf88d6db9cdae2ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810141"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planejar arquivamento no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como planejar o arquivamento no Skype for Business Server.
  
Corporações e outras organizações estão sujeitas a um número cada vez maior de regulamentos setoriais e governamentais que exigem a retenção de tipos específicos de comunicações. Se sua organização tiver esses requisitos, você poderá usar o arquivamento no Skype for Business Server para arquivar comunicações de mensagens instantâneas (IM) e conferências (reuniões) para ajudar a dar suporte a alguns dos seus requisitos de conformidade.
  
## <a name="archiving-components"></a>Componentes de arquivamento

O Skype for Business Server usa os seguintes componentes de arquivamento:
  
- **Operadores de arquivamento**. Os agentes de arquivamento (também conhecidos como agentes de coleta de dados unificados) são instalados e ativados automaticamente em cada pool de front-end enterprise edition e servidor Standard Edition. Embora os agentes de arquivamento sejam ativados automaticamente, nenhuma mensagem será realmente capturada até que o arquivamento seja habilitado e configurado adequadamente. Por padrão, o arquivamento está desabilitado.
    
- **Armazenamento de dados de arquivamento**. O armazenamento de dados do Skype for Business Server pode ser implementado como bancos de dados do Skype for Business Server SQL Server ou, se você tiver uma implantação do Exchange, integrado ao armazenamento do Exchange. 
    
O arquivamento também requer armazenamento de arquivos, mas o arquivamento usa o mesmo armazenamento de arquivos que os Servidores front-end ou o servidor Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar os requisitos de suas organizações para arquivamento

Para implementar o arquivamento, você precisa decidir como atender aos requisitos da sua organização para arquivamento determinando o seguinte:
  
- **Qual opção de armazenamento usar.** Você pode implementar o armazenamento de duas maneiras ou usar uma combinação de ambas:
    
  - **Armazenamento do Exchange.** Se você tiver uma implantação do Exchange, poderá integrar o Skype for Business Server e o arquivamento do Exchange para que os dados arquivados do Skype for Business Server e do Exchange sejam armazenados juntos no Exchange. Se você habilitar a opção de integração do Microsoft Exchange, as caixas de correio do usuário que estão no Exchange Server usarão o armazenamento do Exchange para dados arquivados, mas somente se as caixas de correio foram colocadas em In-Place Espera. Por padrão, a integração com o Microsoft Exchange não está habilitada.
    
  - **Armazenamento do Skype for Business Server.** Se você tiver usuários que não estão no In-Place Exchange ou que não tiveram suas caixas de correio colocadas em espera, ou se não quiser usar a integração com o Microsoft Exchange para qualquer um ou todos os usuários em sua implantação, poderá implantar bancos de dados de Arquivamento do Skype for Business Server usando o SQL Server.
    
- **Quando implantar o arquivamento.** Você pode implantar o arquivamento como parte da implantação inicial do Skype for Business Server ou pode adicioná-lo a uma implantação existente. Para usar o armazenamento de arquivamento do Skype for Business Server (bancos de dados do SQL Server), use o Construtor de Topologias para adicionar os bancos de dados à sua topologia e publique a topologia novamente. Se todos os seus usuários estão no Exchange e têm suas caixas de correio colocadas em In-Place, você não precisa atualizar sua topologia, mas só precisa habilitar a integração com o Microsoft Exchange para armazenar dados arquivados no Exchange. 
    
- **Quais sites e usuários na organização exigem arquivamento.** Você pode definir configurações de arquivamento para toda a sua organização e, opcionalmente, para sites, pools, usuários e grupos de usuários específicos.
    
- **Qual conteúdo deve ser arquivado.** Se você especificar o arquivamento no nível global ou para sites e usuários específicos, em cada um desses níveis, especifique se deve habilitar os seguintes tipos de conteúdo: 
    
  - Mensagens instantâneas de ponto a ponto
    
  - Conferências (reuniões), que são mensagens instantâneas com vários participantes
    
  - Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)
    
  - Os quadros de comunicações e votações compartilhados durante uma conferência
    
- **Qual conteúdo não pode ser arquivado.** Os seguintes tipos de conteúdo não podem ser arquivados: 
    
  - Transferências de arquivo ponto a ponto
    
  - Áudio/vídeo para mensagens instantâneas e conferências de ponto a ponto
    
  - O compartilhamento de área de trabalho e aplicativos para mensagens instantâneas e conferências de ponto a ponto
    
    O Skype for Business Server também não arquiva conversas de Chat Persistente. Para arquivar conversas de Chat Persistente, você deve habilitar e configurar o serviço de Conformidade, que é um componente que pode ser implantado com o Servidor de Chat Persistente. Para obter detalhes, [consulte Plan for Persistent Chat Server in Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)

    > [!NOTE] 
    > O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 
    
- **Quanto tempo os materiais arquivados devem ser retidos.** O banco de dados de Arquivamento não se destina à retenção de longo prazo, e o Skype for Business Server não fornece uma solução de descoberta de e-discovery (pesquisa) para dados arquivados, portanto, os dados precisam ser movidos para outro armazenamento. O Skype for Business Server fornece uma ferramenta de exportação de sessão que você pode usar para exportar dados arquivados e que cria transcrições pesquisáveis dos dados arquivados. 
    
     Para a política global e para cada política de site e usuário que você criar, você pode especificar quando limpar dados arquivados e exportados. Para obter mais informações sobre a purgação de dados, consulte Gerenciar a [purgação](../../manage/archiving/purging-of-archived-data.md)de dados arquivados no Skype for Business Server. Para obter mais informações sobre como usar a ferramenta de exportação de sessão, consulte Exportar dados [arquivados no Skype for Business Server.](../../manage/archiving/export-archived-data.md)
    
- **Arquivar comunicações internas ou externas ou não**. É possível habilitar o arquivamento para comunicações internas (comunicações entre usuários internos), comunicações externas (comunicações que incluem pelo menos um usuário fora da sua rede interna) ou ambos. É possível especificar estas opções para toda sua organização ou é possível especificá-lo para locais ou pools específicos. Por padrão, nenhuma opção é habilitada.
    
    > [!NOTE]
    > O controle do arquivamento para comunicações internas ou externas só está disponível para a Política do Skype for Business. Para arquivamento integrado ao Exchange, as comunicações internas e externas são arquivadas ou não arquivadas. 
  
- **Se implementar o modo crítico.** Se o arquivamento for um requisito para sua organização, a configuração do modo crítico bloqueará as sessões de IM e conferência em caso de falha do Skype for Business Server que impeça o arquivamento. Por exemplo: 
    
  - Um problema com o serviço de armazenamento do Skype for Business Server. Nesse caso, as IMs são bloqueadas para usuários habilitados para arquivamento.
    
  - Um compartilhamento de arquivos indisponível ou um problema com o serviço de armazenamento. Neste caso, todas as conferências ativas hospedadas no pool no momento da falha serão alternadas para o modo restrito e novas conferências não poderão ser ativadas.
    
    As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Escolher opções de configuração e implantação de arquivamento

O arquivamento é instalado automaticamente em cada Servidor Front-End quando você implanta o servidor, mas o arquivamento não é habilitado até que você o configure. A forma como você configura o arquivamento é determinada pela forma como você o implanta. Você pode implantar o arquivamento de uma das seguintes maneiras:
  
- Usar o armazenamento do Microsoft Exchange
    
- Usar o armazenamento do Skype for Business Server
    
> [!NOTE]
> Se você implementar os dois bancos de dados de Arquivamento do Skype for Business Server e habilitar a integração com o Microsoft Exchange, as políticas do Exchange substituirão as políticas de arquivamento do Skype for Business Server, mas somente para usuários que estão no Exchange e tiveram suas caixas de correio colocadas em In-Place Bloqueio. O arquivamento do Skype for Business depende da política de In-Place De espera do Microsoft Exchange. 
  
Se você implantar o arquivamento para um pool de front-end ou servidor Standard Edition, deverá habilita-lo para todos os outros pools de front-end e servidores Standard Edition em sua implantação. Se o arquivamento não estiver habilitado no pool em que uma conversa ou reunião está hospedada, todos os dados de conferência poderão não ser arquivados. O arquivamento ainda funcionará para mensagens de IM, mas o conteúdo e os eventos de conferência podem não ser arquivados.
  
> [!NOTE]
> Para habilitar a delegação de tarefas administrativas enquanto mantém os padrões de segurança da sua organização, o Skype for Business Server usa o RBAC (controle de acesso baseado em função). Com RBAC, o privilégio administrativo é concedido atribuindo usuários às funções administravas predefinidas. Para configurar as políticas e configurações de arquivamento do Skype for Business, o usuário deve ser atribuído à função CsArchivingAdministrator (a menos que a configuração seja feita diretamente no servidor onde o arquivamento é implantado, em vez de remotamente de outro computador). Para uma lista dos direitos, permissões e funções do usuário necessários para a implantação de arquivamento, consulte Implantar arquivamento para [o Skype for Business Server.](../../deploy/deploy-archiving/deploy-archiving.md) 
  
> [!NOTE]
> Se você usar a integração com o Microsoft Exchange, a configuração das políticas do Exchange exigirá direitos e permissões de administrador apropriados. Para obter detalhes, consulte a documentação do Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Armazenamento do Microsoft Exchange

 Se você escolher a integração com o Microsoft Exchange, usará políticas e configurações do Exchange para controlar o arquivamento do Skype for Business Server. Você pode configurar a opção de integração do Microsoft Exchange no nível global, no nível do site e no nível do pool. Se sua implantação incluir várias florestas, você deverá sincronizar as configurações entre o Skype for Business Server e o Exchange. Você precisará determinar:
  
- Arquivar IM, conferência ou ambos
    
- Se implementará o modo crítico, o que bloqueia mensagens im e sessões de conferência em caso de falha do Skype for Business Server 
    
- Seleção da opção de integração do Microsoft Exchange para usar o Exchange para armazenamento de dados arquivados
    
Para obter informações sobre como configurar as políticas e configurações de In-Place Exchange para dar suporte ao arquivamento, consulte a documentação do produto do Exchange.
  
### <a name="skype-for-business-server-storage"></a>Armazenamento do Skype for Business Server

Se você escolher o armazenamento do Skype for Business Server, usará configurações e políticas de arquivamento do Skype for Business Server para controlar como o arquivamento é habilitado e implementado. O armazenamento do Skype for Business Server usa bancos de dados do SQL Server, portanto, você precisará adicionar os bancos de dados do SQL Server apropriados à sua topologia e, em seguida, configurar suas políticas de arquivamento. 
  
### <a name="add-storage-databases-to-your-topology"></a>Adicionar bancos de dados de armazenamento à sua topologia

Ao adicionar bancos de dados de armazenamento do SQL Server à sua topologia, você pode optar por colocar os bancos de dados de Arquivamento com qualquer um dos seguintes:
  
- Banco de dados de monitoramento
    
- Banco de dados back-end de um pool de Front-Ends Enterprise Edition
    
> [!NOTE]
> O servidor que estiver hospedando o banco de dados de arquivamento pode hospedar outros bancos de dados. No entanto, ao considerar colocar o banco de dados de arquivamento com outros bancos de dados, saiba que se você estiver arquivando as mensagens de muitos usuários, o espaço em disco necessário para o banco de dados de arquivamento poderá aumentar bastante. Por essa razão, não recomendamos a colocação do banco de dados de arquivamento no banco de dados back-end. 
  
Se você sobressalto o banco de dados de Arquivamento com o banco de dados de Monitoramento, o banco de dados back-end ou ambos, você pode usar uma única instância SQL para qualquer um ou todos os bancos de dados ou pode usar uma instância SQL separada para cada banco de dados, com a seguinte limitação: cada instância SQL pode conter apenas um único banco de dados back-end, um único banco de dados de Monitoramento e um único banco de dados de Arquivamento.
  
Para obter detalhes sobre a localização de todas as funções de servidor e bancos de dados, consulte [Noções básicas de topologia do Skype for Business Server.](../../plan-your-deployment/topology-basics/topology-basics.md) Para obter detalhes sobre como atualizar sua topologia para incluir bancos de dados de armazenamento, consulte Criar e publicar uma [nova topologia no Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md)
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar opções de arquivamento e políticas de usuário

Você precisará determinar:
  
- Se é para habilitar ou desabilitar o arquivamento para comunicações internas e externas
    
- Arquivar IM, conferência ou ambos
    
- Se implementará o modo crítico, o que bloqueia mensagens im e sessões de conferência em caso de falha do Skype for Business Server 
    
- Se é para habilitar políticas para usuários e grupos específicos
    
As opções de Arquivamento do Skype for Business Server podem ser especificadas nos níveis a seguir. 
  
- **Opção de nível global.** Essa é a configuração de arquivamento padrão e se aplica a toda a sua implantação. Ele é criado quando você implanta o Skype for Business Server e, por padrão, desabilita o arquivamento para comunicações internas e externas. Não é possível excluir essa opção. Se você escolher a opção de exclusão, a opção global será redefinida para as configurações padrão.
    
- **Opções de nível de site.** Você pode habilitar ou desabilitar o arquivamento para um ou mais sites específicos criando e configurando uma opção de arquivamento no nível do site para o site. Você pode excluir qualquer opção de arquivamento no nível do site que criar. Uma opção de arquivamento no nível do site substitui a opção global, mas somente para o site especificado na opção. 
    
    Por exemplo, se você habilitar o arquivamento de comunicações internas e externas em sua configuração global e criar uma configuração de site na qual desabilite o arquivamento para comunicações externas, somente as comunicações internas serão arquivadas para esse site. Em outro exemplo, se você habilitar o arquivamento apenas para mensagens automáticas em sua configuração global e criar uma configuração de site na qual você habilita o arquivamento para IM e conferência, a conferência só será arquivada para o site, não para o restante da sua organização.
    
- **Opções de nível de pool.** Você pode especificar configurações de arquivamento para um ou mais pools específicos criando e definindo uma configuração de nível de pool para o pool individual. Uma configuração de arquivamento em nível de pool existe somente se você a criar. Você pode modificar e excluir qualquer configuração de arquivamento no nível do pool. Uma configuração de arquivamento em nível de pool substitui a configuração global e qualquer configuração de arquivamento de site que você possa ter criado. 
    
    Por exemplo, suponha que você habilita o arquivamento de IM apenas em sua configuração global, cria uma configuração de nível de site na qual habilita o arquivamento para IM e conferência e, em seguida, cria uma configuração de nível de pool na qual habilita o arquivamento apenas para IM. As comunicações seriam arquivadas para IM e conferências para todos os usuários do site, exceto os usuários que estavam no pool especificado na configuração no nível do pool. Para todos os outros usuários em sua organização, o arquivamento seria habilitado somente para IM.
    
- **Políticas de arquivamento do usuário.** Você pode habilitar ou desabilitar o arquivamento para um ou mais usuários e grupos de usuários específicos criando, configurando e aplicando uma política de arquivamento no nível do usuário para os usuários e grupos de usuários especificados. Você pode excluir qualquer política de arquivamento no nível do usuário que criar e pode alterar a quais usuários e grupos de usuários a política de arquivamento se aplica. Uma política de arquivamento no nível do usuário substitui a política global e quaisquer políticas de site, mas somente para usuários e grupos de usuários aos quais a política é aplicada. 
    
    Por exemplo, suponha que você desabilite o arquivamento para comunicações internas e externas em sua configuração global, crie uma política de nível de site na qual você habilita o arquivamento para comunicações internas e externas e, em seguida, crie uma política de nível de usuário na qual desabilite o arquivamento para comunicações externas. As comunicações seriam arquivadas para comunicações externas e internas para todos os usuários do site, exceto para os usuários aos quais você aplica a política de nível de usuário. Para esses usuários, apenas as comunicações internas seriam arquivadas.
    
Para obter detalhes sobre como definir as configurações iniciais de arquivamento ao implantar o arquivamento, consulte [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Para obter detalhes sobre como gerenciar o arquivamento após a implantação, consulte Gerenciar arquivamento [no Skype for Business Server.](../../manage/archiving/archiving.md) 
  
## <a name="archiving-configuration-tools"></a>Ferramentas de configuração de arquivamento

 Você controla a maioria das opções de arquivamento usando o Painel de Controle do Skype for Business Server. No entanto, há algumas opções disponíveis apenas usando o Shell de Gerenciamento do Skype for Business Server. Essas opções incluem o arquivamento de mensagens duplicadas e a exportação de dados arquivados. Para obter mais informações sobre como usar o Painel de Controle do Skype for Business Server e o Shell de Gerenciamento do Skype for Business Server para gerenciar políticas de arquivamento, consulte Gerenciar arquivamento no [Skype for Business Server.](../../manage/archiving/archiving.md)
  
## <a name="access-archived-data"></a>Acessar dados arquivados

O acesso aos dados arquivados depende de onde os dados estão armazenados: 
  
- **Armazenamento do Microsoft Exchange.** Se você escolher a opção de integração do Exchange, o Skype for Business Server deposita o conteúdo de arquivamento no armazenamento do Exchange para todos os usuários que estão no Exchange e que tiveram suas caixas de correio colocadas em In-Place Espera. Os dados arquivados são armazenados na pasta itens recuperáveis de caixas de correio do usuário, que geralmente é invisível para os usuários e só pode ser pesquisada por usuários com uma função de Gerenciamento de Descoberta do **Exchange.** O Exchange habilita a pesquisa e a descoberta federadas, juntamente com o SharePoint, se estiver implantado. Para obter mais detalhes sobre armazenamento, retenção e descoberta de dados armazenados no Exchange, consulte a documentação do Exchange e do SharePoint.
    
- Armazenamento de arquivamento do **Skype for Business Server.** Se você configurar os bancos de dados de Arquivamento do Skype for Business Server, o Skype for Business Server deposita conteúdo de arquivamento nos bancos de dados de Arquivamento do Skype for Business Server para todos os usuários que não estão no Exchange e que não tiveram suas caixas de correio colocadas em In-Place Espera. Esses dados não podem ser pesquisados, mas eles podem ser exportados para formatos que podem ser pesquisados utilizando outras ferramentas. Para obter detalhes sobre como exportar dados armazenados em bancos de dados de Arquivamento, consulte Exportar dados [arquivados no Skype for Business Server.](../../manage/archiving/export-archived-data.md)
    
## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre arquivamento, consulte os seguintes tópicos:
  
- [Implantar arquivamento para o Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gerenciar arquivamento no Skype for Business Server](../../manage/archiving/archiving.md)
    
Para obter mais detalhes sobre como o Skype for Business Server e o Exchange funcionam juntos, consulte Plano para integrar [o Skype for Business e o Exchange.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
  

