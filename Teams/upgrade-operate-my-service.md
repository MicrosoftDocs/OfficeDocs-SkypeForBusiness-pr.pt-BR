---
title: Operações para Microsoft Teams| Gerenciamento de serviços | Qualidade
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Tarefas e atividades necessárias para Teams de serviço, incluindo monitoramento da saúde do serviço e avaliação e garantia de qualidade e uso da rede
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 994fa61664b136c2f76f962420435755ae2488cd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394413"
---
# <a name="operate-your-service"></a>Operar seu serviço

![Atualize o diagrama de jornada, enfatizando o estágio de Excelência Operacional.](media/upgrade-banner-op-excellence.png "Estágios da jornada de atualização, com ênfase no estágio de Excelência Operacional")

Este artigo faz parte do estágio de Excelência Operacional da sua jornada de atualização, que começa assim que você conclui a atualização do Skype for Business para o Teams.

Este artigo fornece uma visão geral dos requisitos para a operação Teams para sua organização após a atualização. Ao operar corretamente seus Teams serviços de Teams, você pode ter certeza de que está fornecendo uma experiência confiável e de alta qualidade para sua organização.

## <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações

O Guia de Operações fornece uma visão geral de todas as tarefas e atividades necessárias como parte da função de gerenciamento de serviço para Microsoft Teams.

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O Teams abrange Microsoft 365 ou Office 365 e os componentes de infraestrutura implantados no local (por exemplo, rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Você pode já ter implementado processos e tarefas associados aos serviços existentes. Dito isso, você provavelmente pode aumentar seus processos atuais ao planejar o gerenciamento de serviços hoje para dar suporte Teams no futuro.

O gerenciamento de serviços abrange todas as atividades e processos envolvidos no gerenciamento Teams de ponta a ponta. Como já foi dito anteriormente, alguns componentes do gerenciamento de serviços, a infraestrutura que o próprio serviço Microsoft 365 ou Office 365 compreende, são de responsabilidade da Microsoft, enquanto você, o cliente, é responsável pelos usuários para gerenciar os vários aspectos do Teams, da rede e dos pontos de extremidade que você fornece.

As tarefas e atividades neste guia são agrupadas em oito categorias, conforme descrito no diagrama a seguir. Cada uma dessas categorias será expandida nas seções a seguir.

![Um diagrama que representa uma lista de categorias de tarefas e atividades.](media/operate-my-service-image1.png "Um diagrama que representa uma lista de categorias de tarefas e atividades que o gerenciamento de serviços Teams inclui. O diagrama também mostra que o gerenciamento de serviços é em grande parte uma tarefa do cliente.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida como as operações serão implementadas para Teams.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Revise o Guia de Operações na íntegra.</li><li>Implemente uma estratégia de operações que se alinhe com as metas da sua organização para oferecer a qualidade e a confiabilidade de Teams cargas de trabalho.</li><li>Revise o guia Análise de Qualidade da Experiência.</li><li> Implemente uma estratégia de operações para executar regularmente avaliações de Qualidade da Experiência para garantir que sua implantação Teams está operando em seus recursos de pico.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>Mapeamento de funções operacionais

O planejamento que você realizou para operações durante a fase Envision é fundamental, pois as atividades de operações começam quando os primeiros usuários piloto estão habilitados. Este guia lista as atividades e tarefas que devem ser executadas diariamente, semanalmente, mensalmente ou conforme necessário para manter uma implantação de Teams de alta qualidade. Este guia fornece conhecimento e orientações sobre como executar essas atividades e tarefas críticas.

Um componente essencial de uma implantação bem-sucedida é garantir que o planejamento que você faça no início da fase Envision inclua determinar quem será responsável pela execução de atividades específicas. Depois que você descobrir quais tarefas e atividades se aplicam à sua implantação, elas precisam ser compreendidas e seguidas pelos grupos ou indivíduos que você atribui a eles.

Cada equipe identificada deve revisar e concordar com as tarefas e responsabilidades identificadas e iniciar a preparação. Isso pode incluir treinamento e preparação, fornecer atualizações para o plano de equipe ou garantir que os provedores externos estão prontos para entrega.

As atividades e funções definidas neste guia devem ser válidas na maioria dos cenários, mas cada implantação do Teams é exclusiva; portanto, você pode usar esse guia como ponto de partida para personalizar as atividades e funções padrão para atender às suas necessidades.

Certifique-se de que cada equipe responsável tenha uma boa compreensão das atividades necessárias para executar o serviço. É fundamental que cada equipe aceite e desacate sua responsabilidade em sua organização antes do primeiro piloto começar.

Depois que um contrato for realizado, as equipes correspondentes devem começar a operacionalizar suas funções.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td>
<td><ul><li>Use este documento para facilitar o exercício de mapeamento de função operacional.</li><li>Reunir-se com as respectivas equipes de suporte para atribuir nomes a cada item na lista de atividades necessárias.</li><li>Obtenha aceitação ou aprovação nas funções atribuídas.</li><li>Certifique-se de que as equipes correspondentes tenham o treinamento, preparação e recursos apropriados para concluir as atividades necessárias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams de serviço

Microsoft Teams reúne tecnologias entre Microsoft 365 e Office 365 para fornecer um hub para o trabalho em equipe. Exemplos incluem:

- Azure Active Directory (Azure AD) fornece serviços de autenticação e autorização para Teams.

- Exchange Online fornece recursos avançados, como ressalção legal e descoberta de e-discovery.

- SharePoint Online oferece a capacidade de compartilhar arquivos em canais e OneDrive for Business fornece um mecanismo para compartilhar arquivos em um chat privado.

As organizações também podem aproveitar os investimentos existentes na infraestrutura local. Por exemplo, contas do Active Directory locais existentes podem ser usadas para autenticação aproveitando o Azure AD Conexão. Determinadas versões Exchange Server podem ser usadas no lugar de Exchange Online.

Essas tecnologias se reúnem para fornecer um pacote de comunicações avançada, colaborativa e inteligente para os usuários. Essa integração rígida é um dos principais benefícios da Teams, mas também gera um requisito para o gerenciamento de serviços nessas tecnologias.

Este guia aborda as principais áreas de foco para gerenciar o Teams serviço. Provavelmente, você tem planos de gerenciamento de serviço para as tecnologias de suporte das Teams dependem. Caso não seja, você precisará estabelecer planos de gerenciamento de serviços adequados para esses componentes de tecnologia (no local e online) também. Isso ajudará a garantir que seus usuários desfrutem de uma experiência confiável e de alta qualidade com Teams.

#### <a name="references"></a>Referências

[Visão geral do Microsoft Teams](teams-overview.md)

[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md)

[Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Atividades do Guia de Operações

As seções a seguir dão uma visão geral das atividades necessárias para operar com êxito o Microsoft Teams serviço. Eles incluem referência a ferramentas, informações contextuais e conteúdo adicional para ajudá-lo a entender a atividade e a ajudar em iniciativas de preparação.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorar a saúde do serviço

É importante que você entenda a saúde geral do serviço Microsoft Teams para que você possa alertar proativamente outras pessoas em sua organização de qualquer evento que afete o serviço. Conforme descrito anteriormente, Teams depende de outros serviços Microsoft 365 e Office 365, como Azure Active Directory, Exchange Online, SharePoint Online e OneDrive for Business. Por isso, é igualmente importante que você monitore a saúde dos serviços dependentes.

Incorpore essa atividade ao seu processo de gerenciamento de incidentes para informar proativamente os usuários, o helpdesk e suas equipes de operações para se prepararem para lidar com escalonamentos de usuários.

As seções a seguir descrevem as ferramentas que você pode aproveitar para monitorar [incidentes de serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) que afetam o Teams serviço. Um resumo dos benefícios de cada ferramenta e quando você deve usar cada uma delas é incluído na tabela a seguir.

| Ferramenta de Monitoramento | Benefícios | Quando usar |
|---|---|---|
| Centro de administração do Microsoft 365 | Disponível em qualquer dispositivo com um navegador com suporte. | Use quando não precisar de notificações em tempo real. |
| Administração Microsoft 365 app | Fornece notificações por push para seu dispositivo móvel. | Use quando precisar ser notificado de incidentes de serviço enquanto estiver em uso. |
| Microsoft System Center | Integração com o Microsoft System Center. | Use quando precisar de recursos avançados de monitoramento e suporte de notificação. |
| Microsoft 365 API de Comunicações de Serviço | Acesso programático à Microsoft 365 ou Office 365 do serviço. | Use quando precisar de integração com uma ferramenta de monitoramento de terceiros ou quiser criar sua própria solução. |

> [!NOTE]
> Somente indivíduos que têm a função **de administrador global** ou administrador **de** serviço podem exibir a saúde do serviço.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoramento com o Centro de administração do Microsoft 365

O [Centro de administração do Microsoft 365](https://portal.office.com/) fornece um painel de [Saúde](https://portal.office.com/adminportal/home#/servicehealth) do Serviço onde você pode exibir a saúde atual do serviço Teams além dos serviços dependentes.

### <a name="monitoring-with-the-mobile-app"></a>Monitoramento com o aplicativo móvel

O Administração Microsoft 365 app está disponível no Apple iOS, Android e Windows (pc e celular). O aplicativo fornece aos administradores informações sobre a saúde do serviço e as próximas alterações. O aplicativo dá suporte a notificações por push que podem alertá-lo quase imediatamente após a postagem de um aviso. Isso ajuda você a se manter atualizado sobre o status, a saúde e quaisquer alterações futuras no serviço. O suporte à notificação a torna a ferramenta de monitoramento recomendada para administradores. Para obter mais informações, consulte:

[Administração Microsoft 365 Aplicativo Móvel](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Baixar o aplicativo Administração Microsoft 365 Mobile](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoramento com o Microsoft System Center

O Microsoft System Center é uma plataforma de gerenciamento integrada que ajuda você a gerenciar datacenter, dispositivos cliente e ambientes de TI de nuvem híbrida. Microsoft 365 ou Office 365 administradores que usam o System Center agora têm a opção de importar o Pacote de Gerenciamento, o que permite que eles extivem todas as comunicações de serviço no Operations Manager no System Center. Usar essa ferramenta oferece acesso ao status de seus serviços inscritos, incidentes de serviço ativos e resolvidos e suas comunicações da Central de Mensagens (alterações futuras). Para obter mais informações, consulte a seguinte [postagem de blog](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/).

Se você aproveitar System Center para monitorar Teams de serviço (e serviços dependentes), você poderá personalizar ainda mais o pacote de gerenciamento para alertar ou notificar grupos ou indivíduos específicos que foram identificados para reagir a incidentes.
Esses grupos podem incluir proprietários de serviços, auxiliares, grupos de suporte de segundo e terceiro nível e gerentes de incidentes em sua organização.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoramento de cenários avançados

Você pode monitorar a saúde do serviço e as alterações futuras aproveitando a API de Comunicações de Serviço para acessar a saúde do serviço e as alterações programaticamente. Use essa API para criar sua própria ferramenta de monitoramento ou conectar suas ferramentas de monitoramento existentes Microsoft 365 ou Office 365 comunicações de serviço, simplificando potencialmente a maneira como você monitora seu ambiente. Para obter mais informações, [consulte Microsoft 365 ou Office 365 para Enterprise desenvolvedores](/office/developer-program/microsoft-365-developer-program-faq).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Monitorar a saúde do serviço | Monitore proativamente Microsoft Teams a saúde do serviço (e os serviços dependentes) usando as ferramentas disponíveis. Os serviços dependentes incluem: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Em tempo real | |
| Notificação de incidentes | Notifique os participantes internos dos eventos que afetam o Teams serviço. Os participantes internos podem incluir usuários, auxiliares e gerentes de incidentes. | Conforme necessário | |

### <a name="references"></a>Referências

[Como verificar a Microsoft 365 ou Office 365 do serviço](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Continuidade e Saúde do Serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gerenciar alterações organizacionais

Microsoft Teams é um serviço baseado em nuvem. Com isso, vem a capacidade de fornecer novos recursos e funcionalidades em um ritmo rápido. A entrega da inovação contínua fornece um benefício óbvio para as organizações, mas essas alterações precisam ser gerenciadas adequadamente em sua organização para evitar a resistência do usuário ou as escalonamentos para o seu helpdesk.

As atualizações Teams são roladas automaticamente para seus usuários. Seus usuários sempre terão os recursos e clientes mais recentes disponíveis no serviço Teams. Não é possível gerenciar a adoção de atualizações Teams para seus usuários, portanto, é fundamental gerenciar as alterações por meio de programas eficazes de comunicação, treinamento e adoção. Se os usuários estão cientes da mudança,&mdash; instruídos sobre os benefícios e capacitados a aproveitar os novos recursos, eles poderão se adaptar mais rapidamente e receber a mudança.

### <a name="monitoring-for-change"></a>Monitoramento de alterações

A primeira etapa do gerenciamento de alterações é monitorar as alterações planejadas para Teams. A melhor fonte para monitorar essas alterações é o [roteiro](https://www.microsoft.com/microsoft-365/roadmap) Microsoft 365, que lista os recursos que estão em desenvolvimento no momento, que estão sendo lançados para os clientes ou que foram totalmente lançados. Você pode pesquisar Teams recursos específicos usando o filtro fornecido ou pode baixar o roteiro para um arquivo Excel para análise mais detalhada. Para cada recurso, o roteiro fornece uma breve descrição, juntamente com a data de lançamento antecipada.

No blog [Microsoft Teams,](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog) você pode aprender sobre práticas recomendadas, tendências e notícias sobre Teams de produtos. Espere encontrar as principais atualizações de recursos Teams ser anunciadas aqui. Você também pode se inscrever no blog por meio de um feed RSS. Em seguida, você pode [adicionar o RSS feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) diretamente em um canal Teams, portanto, todas as notícias importantes são entregues diretamente dentro do Teams.

Todos os recursos lançados estão documentados no [Release Notes for Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aqui você encontrará uma lista de recursos que foram lançados para desktop, web e dispositivos móveis. O mesmo conjunto de notas de versão também está disponível na guia **Novidades** na [Ajuda](get-help-in-microsoft-teams.md).

Familiarizar-se com os recursos disponíveis e garantir que você atribua proprietários aplicáveis para monitorar a alteração.

### <a name="planning-for-change"></a>Planejamento de alterações

Agora que você está ciente das próximas alterações no serviço Teams, a próxima etapa é preparar e planejar de acordo. Avalie cada alteração para determinar quais alterações exigem comunicação com os usuários, campanhas de conscientização, treinamento para equipes de suporte ou usuários ou campanhas de avaliação e adoção de recursos. Essa é a função principal de uma equipe de gerenciamento de alterações em sua organização. Abaixo está uma coleção de tabelas de exemplo que podem ajudá-lo a planejar as alterações.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Recurso: Gravação na Nuvem (Data de lançamento: janeiro de 2018)

**Faixa geral**

| Preparação para alterações | Status | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| Revisão jurídica | Concluído | Esse recurso é um pré-requisito para a integração da equipe de treinamento. | Project equipe |

**Gerenciamento de alterações técnicas**

| Preparação para alterações | Status | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| Alterações de IT necessárias | Sim | O administrador precisa habilitar a gravação somente para usuários identificados. | Equipe de suporte |
| Preparação técnica concluída | Sim | | Equipe de suporte |
| | | | |

**Gerenciamento de alterações do usuário**

| Preparação para alterações | Status | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| Impacto do usuário | Baixo | | |
| Preparação do usuário necessária | Sim | | |
| Comunicações prontas | Não | O email de comunicação foi redigido— revisão pendente. | Equipe de Comunicações |
| Treinamento pronto | Sim | O treinamento aproveitará o vídeo existente da Microsoft. | Equipe de Treinamento |

**Faixa de status**

| Preparação para alterações | Status | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| Status da versão | em andamento | Revisão pendente pelo patrocinador executivo. | Equipe de Gerenciamento de Alterações |
| Liberação de saída | | | |
| Data de lançamento | | | |

Para obter mais informações sobre como planejar o gerenciamento de alterações com Teams, consulte [Create a change management strategy for Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade| Descrição| Cadência| Equipe atribuída |
|---|---|---|---|
| Monitorar alterações| Monitore as alterações futuras no Microsoft Teams serviço.| Diário||
| Planejamento de alterações| Avalie e planeje novos recursos e recursos, incluindo planos de comunicação, campanhas de conscientização e treinamento.| Conforme necessário ||
| Preparação do usuário| Realize campanhas de comunicação, conscientização ou treinamento direcionadas para garantir que os usuários estão prontos para as próximas alterações.| Conforme necessário ||
| Dar suporte à preparação da equipe | Realize campanhas de comunicação, reconhecimento ou treinamento direcionadas para garantir que a equipe de suporte esteja pronta. As equipes de suporte podem incluir a equipe "white glove", helpdesks, suporte de Camada 2 ou Camada 3, parceiros externos e assim por diante. | Conforme necessário ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Avaliar Teams uso

Depois que o piloto inicial começar, é fundamental estabelecer uma cadência regular para medir o uso real Teams uso. Isso permite que sua organização obtenha informações sobre como o uso real se alinha com o uso previsto durante a fase Envision. Embora esta seção se concentre Teams uso, isso deve fazer parte de um esforço mais amplo para medir e avaliar Microsoft 365 ou Office 365 uso geral.

Analisar o uso com frequência no início da implantação oferece a você a oportunidade de:

- Valide se os usuários estão usando Teams.

- Identifique possíveis desafios de adoção antes de criar problemas críticos em toda a organização.

- Entenda se há discrepâncias entre os requisitos da fase Envision e o uso real.

Se o uso não for o que você espera, isso pode ser devido a um problema de implantação, ou o plano de adoção não está sendo executado corretamente ou algum outro problema. Dependendo do motivo real por trás do baixo uso, o administrador deve colaborar com as equipes relacionadas para ajudar a remover barreiras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medir o uso com o Centro de administração do Microsoft 365

Os dados de uso Teams estão disponíveis no painel Relatórios. Teams dados de uso podem ser encontrados em três relatórios diferentes. O primeiro relatório fornece uma exibição entre produtos sobre como os usuários se comunicam e colaboram usando os vários serviços em Microsoft 365 ou Office 365. Este relatório pode ser encontrado aqui: [Microsoft 365 relatórios no centro de administração - Usuários ativos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Os outros dois relatórios são Teams específicos e fornecem mais detalhes sobre Teams uso de uma perspectiva de usuário e dispositivo. Os dois relatórios podem ser encontrados aqui:

[Relatório de uso de dispositivos do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Relatório de atividades do usuário do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permissões necessárias

Os relatórios de uso no centro de administração podem ser acessados por pessoas que tenham sido atribuídas a uma função de administrador **global** ou uma função de administrador específica do produto (**administrador do Exchange**, **administrador Skype for Business**, administrador **SharePoint**).

Além disso, a **função** de leitor relatórios está disponível para usuários que exigem acesso aos relatórios, mas não executam tarefas que exigem permissões no nível do administrador. Você atribui essa função para fornecer relatórios de uso a qualquer pessoa que seja um stakeholder, para monitorar e impulsionar a adoção. Para obter mais informações sobre as diferentes funções disponíveis, consulte [About Microsoft 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Avaliando o uso

Depois de usar o painel Relatórios para medir o uso, é importante comparar o uso medido com os KSIs (indicadores de sucesso principais) que você definiu durante a fase de Envision do projeto. Você pode definir um KSI que pode ser definido como uso ativo ou um que esteja indiretamente vinculado ao uso ativo.

É importante identificar quaisquer variações entre o uso real e o planejado antes de retomar a aplicação para sites ou usuários adicionais. Você provavelmente identificará os aprendizados organizacionais como parte dessa atividade que você pode aproveitar para garantir que o próximo lote de sites ou usuários não tenha os mesmos problemas.

Primeiro, identifique se isso é uma adoção ou um problema técnico. Comece investigando os itens abaixo, para determinar onde o problema está.

1. Valide a qualidade executando uma [Análise de Qualidade da Experiência](upgrade-monitor-quality.md).

2. Trabalhe com a equipe de assistência técnica para verificar se não há problemas técnicos que impeçam os usuários de acessar ou usar o serviço. Se as tendências de problemas existirem[](#endpoint-troubleshooting), use a seção solução de problemas do ponto de extremidade posteriormente neste artigo para tentar resolver o problema antes de envolver o suporte.

3. Trabalhe com a equipe de treinamento e adoção para coletar comentários diretos dos usuários (consulte [Avaliar](#assess-user-sentiment) o sentimento do usuário posteriormente neste artigo) e verificar a eficácia das atividades de conscientização e adoção.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Medir o uso (fase de habilitação) | Mede e avalie Teams uso à medida que os sites continuam a ser integrados durante a fase de habilitação. Resolver problemas de uso conforme necessário. | Semanal | |
| Medir o uso | Mede e avalie Teams uso na fase Valor da Unidade (após a conclusão da implantação). Resolver problemas de uso conforme necessário. | Quinzenalmente | |
| (fase do valor da unidade) | | | |
| Atualizar plano de adoção | Atualize seu plano de adoção com base em como o uso medido se compara às suas metas de planejamento. | Conforme necessário | |

### <a name="references"></a>Referências

[Sobre o Centro de administração do Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Relatórios de atividades no Centro de administração do Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Avaliar o sentimento do usuário

Entender o sentimento do usuário pode atuar como um indicador-chave para a análise do sucesso da implantação Teams usuário. Os comentários do usuário podem impulsionar alterações em sua organização; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos seus usuários.

É importante receber comentários cedo e continuar avaliando o sentimento do usuário durante todo o ciclo de vida do projeto e além. Use as seguintes diretrizes para determinar o intervalo no qual sua organização procurará comentários:

- **Início do projeto**: ao avaliar o sentimento do usuário no início do projeto, você pode obter uma visão inicial sobre como seus usuários se sentem sobre sua experiência Teams pessoal.

- **Após etapas principais**: coletando comentários em todo o ciclo de vida do projeto, você pode medir o sentimento do usuário de forma contínua e fazer alterações conforme necessário. Isso é especialmente útil após etapas importantes.

- **Project** conclusão: Avaliar o sentimento do usuário no final de um projeto dirá o quanto você fez bem e onde o trabalho ainda precisa ser feito e permitirá que você compare os resultados com a pesquisa anterior.

- **Em andamento**: continue a medir o sentimento do usuário indefinidamente. Alterações no sentimento do usuário podem ser devido a alterações no ambiente da sua organização ou alterações no Teams serviço. Ao usar o sentimento do usuário em intervalos regulares, você pode entender o desempenho das equipes de gerenciamento de serviços e como sua organização está respondendo às alterações no serviço Teams serviço.

O sentimento do usuário pode ser avaliado por meio de vários métodos diferentes. Eles podem incluir pesquisas de email, entrevistas no estilo de telefone ou pessoalmente ou simplesmente criar um canal de comentários em Teams ou Yammer. Para obter mais informações, consulte [Práticas recomendadas para métodos de comentários](best-practices-feedback.md) do usuário Microsoft Teams.

Você também pode usar uma abordagem em todo o setor para avaliar o sentimento do usuário chamado NPS (net promotor score), que é descrito na seção a seguir.

### <a name="nps"></a>NPS

O NPS (Net promoter score) é uma métrica de fidelidade do cliente em todo o setor e uma boa abordagem a ser usada para avaliar o sentimento do usuário. O NPS pode ser calculado fazendo duas perguntas: "Qual é a probabilidade de você recomendar Teams para um colega?", seguido da pergunta de forma livre, "Por quê?"

NPS é um índice que varia de –100 a 100 que mede a disposição de um cliente para recomendar o produto ou serviço de uma empresa. O NPS baseia-se em uma pesquisa anônima que é entregue aos usuários por email ou outros meios eletrônicos. NPS mede a fidelidade entre um provedor e um consumidor. Ele consiste em apenas uma pergunta, que pede aos usuários para taxar sua experiência de 1 a 10, com a opção de fornecer comentários adicionais. Os usuários são classificados com base nas seguintes classificações:

- 9 ou 10 são Promoters: entusiastas idados que promoverão seu serviço e alimentarão outras pessoas.

- 7 ou 8 são Passivos: satisfeitos, mas não entusiastas, vulneráveis a outro serviço ou oferta.

- De 1 a 6 são Detratores: Clientes insatisfeitos que podem danificar seu serviço e impedir o crescimento.

![Um diagrama que demonstra a escala NPS.](media/operate-my-service-image2.png "Este diagrama demonstra a escala NPS. Ele mostra que as classificações de 0 a 6 são destrators, 7 a 8 são passivas e 9 a 10 são promotores.")

Embora o número NPS base seja útil, você obterá o maior valor analisando comentários do usuário. Eles ajudarão você a entender por que o usuário recomendaria (ou não) Teams outras pessoas. Esses comentários podem fornecer comentários valiosos para ajudar as equipes de gerenciamento do projeto ou do serviço a entender os ajustes necessários para fornecer um serviço de qualidade.

Para fornecer pesquisas NPS à sua organização, você pode aproveitar sua ferramenta de pesquisa online favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Avaliar o sentimento do usuário | Capture e avalie o sentimento do usuário usando pesquisas ou entrevistas ou por meio de um canal de comentários em Teams ou Yammer. | Conforme necessário | |
| Atualizar planos de adoção | Impulsionar a alteração em sua organização com base nos comentários do usuário; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos seus usuários. | Conforme necessário | |

### <a name="references"></a>Referências

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Usando Yammer para coletar comentários](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Práticas recomendadas para comentários do usuário](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gerenciar a qualidade da rede

Muitos elementos de planejamento principais vão para otimizar, remediar e remediar sua infraestrutura de rede para garantir um caminho eficiente e de alta qualidade para o serviço Microsoft Teams de rede. As tarefas de planejamento e os requisitos são abordados em nossas [diretrizes de preparação de](prepare-network.md) rede. As redes geralmente evoluem ao longo do tempo devido a atualizações, expansão ou outros requisitos de negócios. É importante que você seja responsável pelos seus requisitos para Teams em suas atividades de planejamento de rede.

Embora o planejamento de rede seja um aspecto crítico de uma implantação de Teams, é igualmente importante garantir que a rede permaneça saudável e permaneça atual, com base na alteração dos requisitos técnicos ou comerciais.

Para garantir a saúde da sua rede, várias atividades de operações precisam ser executadas em intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Monitorar Microsoft 365 ou Office 365 IPs e URLs | Monitore quaisquer alterações nos [intervalos Office 365 URLs e endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) usando o [feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fornecido e inicie uma solicitação de alteração para grupos de rede aplicáveis. | Diário | |
| Atualizar a rede com base em alterações em Microsoft 365 ou Office 365 IPs e URLs | Faça atualizações para os componentes de rede aplicáveis (firewalls, servidores proxy, VPNs, firewalls do lado do cliente e assim por diante) para refletir alterações nas [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). | Conforme necessário | |
| Fornecer dados de construção | Forneça informações atualizadas de sub-rede para o defensor da qualidade (ou partes interessadas relevantes) para garantir que as definições de construção no [CQD sejam mantidas](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) atualizadas. | Conforme necessário | |
| Implementar alterações | Implemente alterações na rede para dar suporte à alteração Teams requisitos técnicos e comerciais. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Redes com fio e Wi-Fi com fio</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul> | Conforme necessário | |
| Monitoramento e relatórios de rede | Monitore a rede de ponta a ponta para ver as tendências de disponibilidade, utilização e capacidade usando as ferramentas de gerenciamento de rede de terceiros existentes e os recursos de relatório disponíveis em seus provedores de rede. Use dados de tendência para planejamento de capacidade de rede. | Diário, semanal, mensal | |
| Planejamento de capacidade | Colabore com os Teams de serviço para entender as mudanças de requisitos técnicos e comerciais que podem impulsionar alterações adicionais de capacidade.  | Conforme necessário | |
| Solução de problemas e correção de rede | Ajude os Teams auxiliares, proprietários de serviços e principais participantes a solucionar problemas e solucionar problemas relacionados Teams conectividade, confiabilidade ou qualidade. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Redes com fio e Wi-Fi com fio</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul> | Conforme necessário | |
| Teste de alta disponibilidade e recuperação de desastres | Execute testes regulares de alta disponibilidade e recuperação de desastres na infraestrutura de rede para garantir que atenda aos objetivos de nível de serviço (SLOs) ou contratos de nível de serviço (SLAs) para o serviço Teams de serviço. | Mensal | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Criar esquema de dados](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Avaliar e garantir a qualidade

Todas as organizações precisam de um grupo ou indivíduo para serem responsáveis pela qualidade. Essa é a função mais importante do gerenciamento do serviço. A função Defensor da Qualidade é atribuída a uma pessoa ou grupo que é apaixonado pela experiência de seus usuários.
Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções. O melhor candidato para o posto de defensor da qualidade costuma ser o proprietário do serviço do cliente. Dependendo do tamanho e da complexidade da organização, pode ser qualquer pessoa ou grupo com uma paixão por garantir uma experiência de usuário de alta qualidade.

O defensor da qualidade aproveita ferramentas e processos documentados existentes, como o Painel de Qualidade de Chamada (CQD) e Melhorar e monitorar a qualidade de chamada para Teams, para monitorar [a](monitor-call-quality-qos.md) experiência do usuário, identificar tendências de qualidade e conduzir a correção quando necessário.
O defensor da qualidade deve trabalhar com as respectivas equipes para conduzir ações de correção e relatar a um comitê de direção sobre o progresso e quaisquer problemas abertos.

[Melhorar e monitorar a](monitor-call-quality-qos.md) qualidade das Teams inclui atividades que avaliam e fornecem orientações de correção em áreas-chave que têm o maior impacto na melhoria da experiência do usuário. As diretrizes fornecidas no Guia de Revisão da Experiência de Qualidade se concentram no uso do CQD Online como a principal ferramenta para relatar e investigar cada área, com foco no áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

Recomendamos que você nomee o campeão de qualidade no início. Depois de nomeados, eles devem começar a se familiarizar com o conteúdo em [Melhorar e monitorar](monitor-call-quality-qos.md) a qualidade de chamada para Teams e materiais de treinamento associados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade | Descrição | Cadência | Equipe Atribuída |
|---|---|---|---|
| Nominar e treinar defensores de qualidade | Nomear e treinar um campeão de qualidade. | Conforme necessário | |
| Executar Avaliações de Qualidade da Experiência (QERs) | Execute uma QER para identificar tendências de qualidade e confiabilidade, revisar em relação a destinos definidos e relatar aos principais participantes da organização. | Mensal (semanalmente durante implantações) | |
| Correção de unidade | Coordena os esforços de correção em toda a organização com base nas avaliações e descobertas de QER. | Conforme necessário | |
| Atualizar dados de criação no CQD | Atualizar ou adicionar novas definições de construção no CQD quando as alterações são feitas na rede ([consulte Upload Informações de construção](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Conforme necessário | |
| Preencher a função Defensor da Qualidade | Responsabilidade de ponta a ponta pela qualidade na organização. Isso inclui:<ul><li>Verifique se a QER está sendo conduzida regularmente.</li><li>Reporte aos principais participantes sobre o status de qualidade.</li><li>Verifique se as definições de dados de criação estão atualizadas.</li><li>Coordena os esforços de correção em toda a organização para garantir que os usuários tenham uma experiência de alta qualidade com Teams.</li></ul> | Diário | |

### <a name="references"></a>Referências

[Upload informações de criação](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Melhorar e monitorar a qualidade de chamada para Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gerenciar pontos de extremidade

Microsoft Teams pontos de extremidade podem ser definidos como qualquer computador, Mac, tablet ou dispositivo móvel (ou qualquer outro) que executa o Teams cliente. O *ponto de* extremidade do termo não abrange apenas o dispositivo em si, mas como um usuário se conecta ao dispositivo, por exemplo, usando o microfone ou alto-falante interno do dispositivo, fones de ouvido ou um fone de ouvido otimizado. Depois de implantados, os pontos de extremidade não devem ser esquecidos. Os Teams de extremidade exigem manutenção e cuidado contínuos. As seções a seguir descrevem áreas específicas em que se concentrar.

### <a name="endpoint-requirements"></a>Requisitos de ponto de extremidade

Um dos principais benefícios da Teams é que o cliente é mantido atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso. Os Teams móveis são mantidos atualizados por meio de seus respectivos armazenamentos de aplicativos.

O Teams cliente tem requisitos mínimos em termos da plataforma de software subjacente. Esses requisitos podem mudar ao longo do tempo e, portanto, é importante que você os monitore para alterações. Por exemplo, o Teams cliente tem uma versão mínima do iOS. Se o cliente usa um navegador da Internet, o navegador também precisa ser mantido atualizado. Uma lista de plataformas com suporte pode ser encontrada em [Obter clientes para Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Firewalls do lado do cliente podem afetar a qualidade da chamada e até mesmo impedir que uma chamada seja estabelecida. Depois que as exclusões apropriadas no firewall do cliente foram configuradas, elas precisam ser mantidas atualizadas com base nas informações Office 365 [URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). O fornecedor de terceiros terá orientações específicas sobre como atualizar as exclusões.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Wi-Fi drivers podem ser problemáticos. Como exemplo, um driver pode ter comportamentos de roaming muito agressivos entre os pontos de acesso que podem induzir a alternação desnecessária de ponto de acesso, levando a uma qualidade de chamada ruim. Um driver de Wi-Fi com desempenho ruim pode ser descoberto por meio de uma Análise de Qualidade da Experiência (consulte [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) for more detail). É essencial implementar um processo orientado pela qualidade que monitora os novos drivers Wi-Fi e garante que eles são testados antes de serem implantados para a população geral de usuários.

### <a name="endpoint-management"></a>Gerenciamento de ponto de extremidade

Um catálogo de pontos de extremidade e dispositivos de interface com suporte (como fones de ouvido) deve estar disponível e mantido. Este catálogo incluirá uma lista de dispositivos aprovados que foram selecionados e validados como parte das fases Envision e Onboard. Normalmente, dispositivos específicos são selecionados para cada tipo de persona em sua organização para atender às necessidades dos atributos dessa persona. Todos os pontos de extremidade têm um ciclo de vida e você precisa gerenciar os contratos de fornecedor, garantia, substituição, distribuição e políticas de reparo associadas a esses dispositivos.

### <a name="endpoint-troubleshooting"></a>Solução de problemas de ponto de extremidade

Mesmo que você tenha seguido as diretrizes anteriores, os usuários em sua organização ainda poderão ter problemas com Teams. Embora o problema possa não estar com o ponto de extremidade em si, os sintomas do problema normalmente são a superfície através do cliente para o usuário. As diretrizes a seguir destinam-se a fornecer etapas gerais que você pode tomar para resolver o problema; ele não deve ser um guia abrangente de solução de problemas. As etapas são fornecidas em uma ordem específica, mas não precisam ser seguidas explicitamente e podem não ser aplicáveis, dependendo da natureza do problema.

1. **Validar a saúde do serviço:** O problema que um usuário pode estar enfrentando pode estar relacionado a um evento que afeta negativamente o serviço Teams ou seus serviços dependentes. Como primeira etapa, recomendamos que você confirme que não há problemas de serviço ativos. Consulte [Como verificar a Microsoft 365 do serviço](/office365/enterprise/view-service-health). Lembre-se de verificar o status dos serviços dependentes (por exemplo, Exchange, SharePoint, OneDrive for Business). O monitoramento da saúde do serviço é discutido com mais detalhes na seção anterior, [Monitorar a saúde do serviço](#monitor-service-health).

2. **Validar a conectividade do cliente:** Problemas de conectividade causam problemas de funcionalidade ou de login Teams. Recomendamos (especialmente para novos sites ou locais) que você valide a conectividade com o serviço. Verifique se as seguintes [Office 365 URLs e intervalos de endereços IP são seguidas](/microsoft-365/enterprise/urls-and-ip-address-ranges) para cada site. Você pode aproveitar a [Ferramenta de](https://www.microsoft.com/download/details.aspx?id=53885) Avaliação de Rede da Microsoft para executar um teste de conectividade para validar se as portas de mídia foram abertas corretamente para Teams recursos. As etapas detalhadas sobre como executar os testes de conectividade são fornecidas nas diretrizes [de preparação da](prepare-network.md) rede.

3. **Verifique a lista de problemas conhecidos:** Consulte [Teams Solução de Problemas](/MicrosoftTeams/troubleshoot/teams) para determinar se o usuário foi afetado negativamente por um desses problemas. Siga a solução alternativa fornecida (se houver uma) para resolver o problema.

4. **Visite a Microsoft Teams: a comunidade** [Microsoft Teams oferece](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) espaços dedicados para Teams. A Teams comunidade fornece uma lista de discussão, postagens de blog e comunicados centralizados em torno Teams. Você pode postar uma pergunta ou pesquisar discussões anteriores em busca de soluções para seu problema.

5. **Entre em contato com o Suporte da Microsoft:** Você pode entrar em contato com o Suporte da Microsoft para problemas Teams online ou por telefone. Para obter informações, [consulte Contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products). Para clientes Premier, as solicitações de suporte podem ser iniciadas seguindo as diretrizes em [Contact support for Microsoft Teams (clientes Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Requisitos de ponto de extremidade | Verifique se o ponto de extremidade Teams continua a atender a todos os requisitos de software para Teams listados em [Obter clientes para Microsoft Teams](get-clients.md). | Mensal | |
| Firewalls de ponto de extremidade | Mantenha as exclusões apropriadas no firewall do ponto de extremidade com base [nas informações Office 365 URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). O fornecedor de terceiros terá orientações específicas sobre como manter as exclusões. Inscreva-se no [feed RSS para](https://support.office.com/o365ip/rss) ser notificado automaticamente das alterações. | Conforme necessário | |
| Drivers de Wi-Fi | Teste e atualize Wi-Fi drivers no computador. Valide os resultados usando o CQD ([Melhorar e monitorar a qualidade](monitor-call-quality-qos.md) das Teams). | Conforme necessário | |
| Gerenciamento de ponto de extremidade | Mantenha o catálogo de pontos de extremidade e dispositivos de interface com suporte (como fones de ouvido). Gerenciar contratos de fornecedor, garantia, distribuição, substituição e políticas de reparo. | Mensal | |
| Solução de problemas de ponto de extremidade | A solução de problemas de tarefas pode incluir verificar a conectividade, consultar a lista de problemas conhecidos, coleta de log, análise e escalonamento para o Suporte da Microsoft ou fornecedores de terceiros. | Conforme necessário | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Obter clientes para o Microsoft Teams](get-clients.md)

[Microsoft Teams comunidade](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Entre em contato com o suporte de produtos para empresas - Ajuda da Administração](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Entrar em contato com o suporte premier](https://support.microsoft.com/premier/contacts)

[Solução de Teams vídeo](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gerenciar o Teams

Depois que Microsoft Teams serviço de Microsoft Teams tiver sido implantado, você precisará executar várias atividades relacionadas à sua administração. As atividades variam de administrar o serviço e usuários individuais até o planejamento de capacidade e provisionamento de licenciamento e números de telefone. As seções a seguir abrangem algumas dessas tarefas comuns de administração.

### <a name="service-administration"></a>Administração de serviços

O Teams serviço tem várias configurações que podem ser configuradas em todo o locatário.
As alterações feitas nas configurações do locatário afetam todos os usuários que foram habilitados para Teams. Para uma lista detalhada dessas configurações, consulte [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).

### <a name="user-administration"></a>Administração do usuário

Para dar suporte aos usuários, uma organização pode exigir qualquer número de tarefas relacionadas, as tarefas específicas variam de uma organização para a próxima. Em última análise, essas tarefas precisam ser gerenciadas por uma equipe de suporte que tenha sido atribuída a essas tarefas operacionais. As tarefas a seguir são comumente necessárias para dar suporte aos usuários Teams.

#### <a name="general-tasks"></a>Tarefas gerais

[Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Criação de equipe (opcional)

Por padrão, todos os usuários com uma caixa de correio Exchange Online têm permissões para criar grupos Microsoft 365 e, portanto, uma equipe no Microsoft Teams. Se você quiser ter um controle mais rígido e restringir a criação de novas equipes [(e](assign-roles-permissions.md#permissions-to-create-teams), portanto, a criação de novos grupos de Microsoft 365), você pode delegar a criação de grupos e direitos de gerenciamento a um conjunto de administradores. Se sua organização quiser prosseguir com essa opção, consulte o processo descrito neste artigo para permitir que os usuários enviem solicitações processadas por uma equipe atribuída.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Administração de serviços | Administração de configurações de Teams locatários. | Conforme necessário | |
| Administração do usuário | Administração de configurações baseadas em usuário e licenciamento em Teams. | Conforme necessário | |
| Gerenciamento de licenças | Planeje as necessidades atuais e futuras para licenciamento baseado no usuário e no consumo (Planos de Chamada e Créditos de Comunicação) aproveitando o relatório de uso [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e o relatório de [pools de minutos PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Semanal | |
| Gerenciamento de números de telefone | Gerencie os números de telefone disponíveis para crescimento futuro e ajuste os níveis de inventário para atender às suas necessidades organizacionais. | Semanal | |
| Criação de equipe (opcional) | Revisar e processar solicitações para criação de equipe. | Conforme necessário | |

<!--ENDOFSECTION-->