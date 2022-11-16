---
title: Operações do Microsoft Teams| | de Gerenciamento de Serviços Qualidade
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Tarefas e atividades necessárias para o gerenciamento de serviços do Teams, incluindo monitorar a integridade do serviço e avaliar e garantir a qualidade e o uso da rede
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
ms.openlocfilehash: 7da8db4b8ba281082d7f1565800a9f4d543dcb97
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019427"
---
# <a name="operate-your-service"></a>Operar seu serviço

![Diagrama de jornada de atualização, enfatizando o estágio de Excelência Operacional.](media/upgrade-banner-op-excellence.png "Estágios da jornada de atualização, com ênfase no estágio de Excelência Operacional")

Este artigo faz parte do estágio de Excelência Operacional de sua jornada de atualização, que começa assim que você concluir sua atualização de Skype for Business para o Teams.

Este artigo fornece uma visão geral dos requisitos para operar com êxito o Teams para sua organização após a atualização. Ao operar corretamente seus serviços do Teams, você pode ter certeza de que está fornecendo uma experiência confiável e de alta qualidade para sua organização.

## <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações

O Guia de Operações fornece uma visão geral de todas as tarefas e atividades necessárias como parte da função de gerenciamento de serviços do Microsoft Teams.

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O serviço do Teams abrange o Microsoft 365 ou Office 365 e os componentes de infraestrutura implantados localmente (por exemplo, rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Talvez você já tenha implementado processos e tarefas associadas aos serviços existentes. Dito isso, você provavelmente pode aumentar seus processos atuais ao planejar o gerenciamento de serviços hoje para dar suporte ao Teams no futuro.

O gerenciamento de serviço abrange todas as atividades e processos envolvidos no gerenciamento do Teams de ponta a ponta. Conforme observado anteriormente, alguns componentes do gerenciamento de serviços, a infraestrutura que o serviço microsoft 365 ou Office 365 em si compreende, são responsabilidade da Microsoft, enquanto você, o cliente, é responsável pelos usuários para gerenciar os vários aspectos do Teams, da rede e dos pontos de extremidade fornecidos por você.

As tarefas e atividades neste guia são agrupadas em oito categorias, conforme descrito no diagrama a seguir. Cada uma dessas categorias será expandida nas seções a seguir.

![Um diagrama que mostra uma lista de categorias de tarefas e atividades.](media/operate-my-service-image1.png "Um diagrama que mostra uma lista de categorias de tarefas e atividades que o gerenciamento de serviços do Teams inclui. O diagrama também mostra que o gerenciamento de serviços é em grande parte uma tarefa do cliente.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida como as operações serão implementadas para o Teams.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Examine o Guia de Operações na íntegra.</li><li>Implemente uma estratégia de operações alinhada com as metas da sua organização para fornecer a qualidade e a confiabilidade das cargas de trabalho do Teams.</li><li>Examine o guia Revisão de Qualidade da Experiência.</li><li> Implemente uma estratégia de operações para executar regularmente revisões de qualidade de experiência para garantir que a implantação do Teams esteja operando em seus recursos de pico.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>Mapeamento de funções operacionais

O planejamento que você realizou para operações durante a fase Envision é fundamental, pois as atividades de operações começam quando os primeiros usuários piloto estão habilitados. Este guia lista as atividades e tarefas que devem ser executadas diariamente, semanalmente, mensais ou conforme necessário para manter uma implantação do Teams de alta qualidade. Este guia fornece conhecimento e diretrizes sobre como executar essas atividades e tarefas críticas.

Um componente crucial de uma implantação bem-sucedida é garantir que o planejamento que você faz no início da fase Envision inclua determinar quem será responsável pela execução de atividades específicas. Depois de descobrir quais tarefas e atividades se aplicam à sua implantação, elas precisam ser compreendidas e seguidas pelos grupos ou indivíduos que você atribui a elas.

Cada equipe que você identificar deve examinar e concordar com as tarefas e responsabilidades identificadas e iniciar a preparação. Isso pode incluir treinamento e preparação, fornecer atualizações para o plano de pessoal ou garantir que os provedores externos estejam prontos para entregar.

As atividades e funções definidas neste guia devem ser válidas na maioria dos cenários, mas cada implantação do Teams é exclusiva; Portanto, você pode usar esse guia como ponto de partida para personalizar as atividades e as funções padrão para atender às suas necessidades.

Verifique se cada equipe responsável tem uma boa compreensão das atividades necessárias para executar o serviço. É fundamental que cada equipe aceite e assine sua responsabilidade em sua organização antes do início do primeiro piloto.

Depois que um contrato estiver em vigor, as equipes correspondentes devem começar a operacionalizar suas funções.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td>
<td><ul><li>Use este documento para facilitar o exercício de mapeamento de função operacional.</li><li>Encontre-se com as respectivas equipes de suporte para atribuir nomes a cada item na lista de atividades necessárias.</li><li>Obtenha aceitação ou aprovação nas funções atribuídas.</li><li>Verifique se as equipes correspondentes têm o treinamento, a preparação e os recursos apropriados para concluir as atividades necessárias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependências de serviço do Teams

O Microsoft Teams reúne tecnologias no Microsoft 365 e Office 365 para fornecer um hub para trabalho em equipe. Exemplos incluem:

- O Azure Active Directory (Azure AD) fornece serviços de autenticação e autorização para o Teams.

- Exchange Online fornece recursos avançados, como retenção legal e descoberta eletrônica.

- O SharePoint Online fornece a capacidade de compartilhar arquivos em canais e OneDrive for Business fornece um mecanismo para compartilhar arquivos em um chat privado.

As organizações também podem aproveitar os investimentos existentes em infraestrutura local. Por exemplo, contas Active Directory local existentes podem ser usadas para autenticação aproveitando Azure AD Connect. Determinadas versões de Exchange Server podem ser usadas no lugar de Exchange Online.

Essas tecnologias se reúnem para fornecer um pacote de comunicações avançado, colaborativo e inteligente para os usuários. Essa integração apertada é um benefício fundamental do Teams, mas também gera um requisito para o gerenciamento de serviços entre essas tecnologias.

Este guia aborda as principais áreas de foco para gerenciar o serviço do Teams. Provavelmente, você tem planos de gerenciamento de serviços em vigor para as tecnologias de suporte das quais o Teams depende. Caso contrário, você precisará estabelecer planos de gerenciamento de serviço adequados para esses componentes de tecnologia (locais e online) também. Isso ajudará a garantir que seus usuários desfrutem de uma experiência confiável e de alta qualidade com o Teams.

#### <a name="references"></a>Referências

[Visão geral do Microsoft Teams](teams-overview.md)

[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md)

[Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md)

[Coexistência e interoperabilidade do Microsoft Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Atividades do Guia de Operações

As seções a seguir fornecem uma visão geral das atividades necessárias para operar com êxito o serviço do Microsoft Teams. Elas incluem referência a ferramentas, informações contextuais e conteúdo adicional para ajudar você a entender a atividade e ajudar nas iniciativas de preparação.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorar a integridade do serviço

É importante que você entenda a integridade geral do serviço microsoft teams para que você possa alertar proativamente outras pessoas em sua organização de qualquer evento que afete o serviço. Conforme descrito anteriormente, o Teams depende de outros serviços do Microsoft 365 e Office 365, como Azure Active Directory, Exchange Online, SharePoint Online e OneDrive for Business. Por causa disso, é igualmente importante que você monitore a integridade dos serviços dependentes.

Incorpore essa atividade ao processo de gerenciamento de incidentes para informar proativamente os usuários, o helpdesk e suas equipes de operações para se preparar para lidar com escalonamentos de usuários.

As seções a seguir descrevem as ferramentas que você pode aproveitar para monitorar [incidentes de serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) que afetam o serviço do Teams. Um resumo dos benefícios de cada ferramenta e quando você deve usar cada uma delas, é incluído na tabela a seguir.

| Ferramenta de Monitoramento | Benefícios | Quando usar |
|---|---|---|
| Centro de administração do Microsoft 365 | Disponível em qualquer dispositivo com um navegador com suporte. | Use quando não precisar de notificações em tempo real. |
| Administração Microsoft 365 aplicativo | Fornece notificações por push para seu dispositivo móvel. | Use quando precisar ser notificado de incidentes de serviço enquanto estiver em movimento. |
| Microsoft System Center | Integração com o Microsoft System Center. | Use quando precisar de recursos avançados de monitoramento e suporte à notificação. |
| API de Comunicações de Serviço do Microsoft 365 | Acesso programático à integridade do serviço do Microsoft 365 ou Office 365. | Use quando precisar de integração com uma ferramenta de monitoramento de terceiros ou quiser criar sua própria solução. |

> [!NOTE]
> Somente indivíduos atribuídos à função **de administrador global** ou administrador de **serviços** podem exibir a integridade do serviço.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoramento com o Centro de administração do Microsoft 365

O [Centro de administração do Microsoft 365](https://portal.office.com/) fornece um [painel do Service Health](https://portal.office.com/adminportal/home#/servicehealth) em que você pode exibir a integridade atual do serviço teams, além dos serviços dependentes.

### <a name="monitoring-with-the-mobile-app"></a>Monitoramento com o aplicativo móvel

O aplicativo Administração Microsoft 365 está disponível no Apple iOS, Android e Windows (PC e dispositivos móveis). O aplicativo fornece aos administradores informações sobre a integridade do serviço e as alterações futuras. O aplicativo dá suporte a notificações por push que podem alertá-lo quase imediatamente após a publicação de um aviso. Isso ajuda você a se manter atualizado sobre o status, a integridade e quaisquer alterações futuras no serviço. O suporte à notificação faz dele a ferramenta de monitoramento recomendada para administradores. Para obter mais informações, confira:

[Administração Microsoft 365 Aplicativo Móvel](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Baixar o aplicativo móvel Administração Microsoft 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoramento com o Microsoft System Center

O Microsoft System Center é uma plataforma de gerenciamento integrada que ajuda você a gerenciar datacenter, dispositivos cliente e ambientes de TI de nuvem híbrida. Os administradores do Microsoft 365 ou Office 365 que usam o System Center agora têm a opção de importar o Pacote de Gerenciamento, o que permite exibir todas as comunicações de serviço no Operations Manager no System Center. O uso dessa ferramenta fornece acesso ao status de seus serviços inscritos, incidentes de serviço ativos e resolvidos e suas comunicações do Centro de Mensagens (alterações futuras). Para obter mais informações, consulte a [seguinte postagem no blog](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/).

Se você aproveitar o System Center para monitorar a integridade do serviço do Teams (e serviços dependentes), poderá personalizar ainda mais o pacote de gerenciamento para alertar ou notificar grupos ou indivíduos específicos que foram identificados para reagir a incidentes.
Esses grupos podem incluir proprietários de serviços, helpdesks, grupos de suporte de segundo e terceiro nível e gerentes de incidentes em sua organização.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoramento de cenários avançados

Você pode monitorar a integridade do serviço e as alterações futuras aproveitando a API de Comunicações de Serviço para acessar a integridade do serviço e as alterações programaticamente. Use essa API para criar sua própria ferramenta de monitoramento ou conectar suas ferramentas de monitoramento existentes ao Microsoft 365 ou Office 365 comunicações de serviço, potencialmente simplificando a forma como você monitora seu ambiente. Para obter mais informações, consulte [Microsoft 365 ou Office 365 para desenvolvedores enterprise](/office/developer-program/microsoft-365-developer-program-faq).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Monitorar a integridade do serviço | Monitore proativamente a integridade do serviço do Microsoft Teams , (e serviços dependentes) usando as ferramentas disponíveis. Os serviços dependentes incluem: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Em tempo real | |
| Notificação de incidente | Notifique os stakeholders internos de eventos que afetam o serviço do Teams. Os stakeholders internos podem incluir usuários, auxiliares e gerentes de incidentes. | Conforme necessário | |

### <a name="references"></a>Referências

[Como verificar a integridade do serviço do Microsoft 365 ou Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Integridade e continuidade do serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gerenciar alterações organizacionais

O Microsoft Teams é um serviço baseado em nuvem. Com isso vem a capacidade de fornecer novos recursos e funcionalidades em um ritmo rápido. Fornecer inovação contínua fornece um benefício óbvio para as organizações, mas essas alterações precisam ser gerenciadas adequadamente em sua organização para evitar resistência do usuário ou escalonamentos no seu helpdesk.

Atualizações para o Teams são distribuídas automaticamente para seus usuários. Seus usuários sempre terão o cliente e os recursos mais recentes disponíveis no serviço do Teams. Não é possível gerenciar a distribuição de atualizações do Teams para seus usuários, portanto, é extremamente importante gerenciar alterações por meio de programas eficazes de comunicação, treinamento e adoção. Se seus usuários estiverem cientes da alteração, educados sobre os benefícios e capacitados para aproveitar as novas funcionalidades&mdash;, eles poderão se adaptar mais rapidamente e saudar a mudança.

### <a name="monitoring-for-change"></a>Monitoramento para alteração

A primeira etapa no gerenciamento de alterações é monitorar as alterações planejadas para o Teams. A melhor fonte para monitorar essas alterações é o [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap), que lista recursos que estão em desenvolvimento no momento, sendo distribuídos aos clientes ou totalmente iniciados. Você pode pesquisar recursos específicos do Teams usando o filtro fornecido ou baixar o roteiro em um arquivo do Excel para análise posterior. Para cada recurso, o roteiro fornece uma breve descrição, juntamente com a data de lançamento prevista.

No [blog do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), você pode aprender sobre as melhores práticas, tendências e notícias sobre atualizações de produtos do Teams. Espere encontrar grandes atualizações de recursos para o Teams a serem anunciadas aqui. Você também pode assinar o blog por meio de um feed do RSS. Em seguida, você pode adicionar [o feed do RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) diretamente em um canal do Teams, para que todas as notícias importantes sejam entregues diretamente dentro do Teams.

Todos os recursos lançados estão documentados nas [Notas de Lançamento do Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aqui você encontrará uma lista de recursos que foram lançados para dispositivos de área de trabalho, Web e dispositivos móveis. O mesmo conjunto de notas de versão também está disponível na guia **Novidades** na [Ajuda](get-help-in-microsoft-teams.md).

Familiarize-se com os recursos disponíveis e certifique-se de atribuir proprietários aplicáveis para monitorar a alteração.

### <a name="planning-for-change"></a>Planejando a alteração

Agora que você está ciente das próximas alterações no serviço do Teams, a próxima etapa é preparar e planejar de acordo. Avalie cada alteração para determinar quais alterações exigem comunicação com usuários, campanhas de conscientização, treinamento para equipes de suporte ou usuários ou campanhas de avaliação e adoção de recursos. Essa é a função principal de uma equipe de gerenciamento de alterações em sua organização. Abaixo está uma coleção de tabelas de exemplo que pode ajudá-lo a planejar a alteração.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Recurso: Gravação na Nuvem (data de lançamento: janeiro de 2018)

**Faixa geral**

| Preparação para alterações | Status | Notas/próximas etapas | Proprietário |
|---|---|---|---|
| Revisão legal | Concluído | Esse recurso é um pré-requisito para integrar a equipe de treinamento. | Equipe do projeto |

**Gerenciamento de alterações técnicas**

| Preparação para alterações | Status | Notas/próximas etapas | Proprietário |
|---|---|---|---|
| Alterações de TI necessárias | Sim | Administração precisa habilitar a gravação somente para usuários identificados. | Equipe de suporte |
| Preparação técnica concluída | Sim | | Equipe de suporte |
| | | | |

**Gerenciamento de alterações de usuário**

| Preparação para alterações | Status | Notas/próximas etapas | Proprietário |
|---|---|---|---|
| Impacto do usuário | Baixo | | |
| Preparação do usuário necessária | Sim | | |
| Comunicações prontas | Não | O email de comunicação foi redigido — revisão pendente. | Equipe de Comunicações |
| Treinamento pronto | Sim | O treinamento aproveitará o vídeo existente da Microsoft. | Equipe de Treinamento |

**Faixa de status**

| Preparação para alterações | Status | Notas/próximas etapas | Proprietário |
|---|---|---|---|
| Status da versão | em andamento | Revisão pendente pelo patrocinador executivo. | Equipe de Gerenciamento de Alterações |
| Aprovação de versão | | | |
| Data de lançamento | | | |

Para obter mais informações sobre como planejar o gerenciamento de alterações com o Teams, consulte [Criar uma estratégia de gerenciamento de alterações para o Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade| Descrição| Cadência| Equipe atribuída |
|---|---|---|---|
| Monitorar a alteração| Monitore as próximas alterações no serviço do Microsoft Teams.| Diário||
| Planejando a alteração| Avalie e planeje novos recursos e recursos, incluindo planos de comunicação, campanhas de conscientização e treinamento.| Conforme necessário ||
| Preparação do usuário| Execute campanhas de comunicação, conscientização ou treinamento direcionadas para garantir que os usuários estejam prontos para a próxima alteração.| Conforme necessário ||
| Preparação da equipe de suporte | Execute campanhas de comunicação, conscientização ou treinamento direcionadas para garantir que a equipe de suporte esteja pronta. As equipes de suporte podem incluir a equipe "luva branca", helpdesks, suporte de Camada 2 ou Nível 3, parceiros externos e assim por diante. | Conforme necessário ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Avaliar o uso do Teams

Após o início do piloto inicial, é fundamental estabelecer uma cadência regular para medir o uso real do Teams. Isso permite que sua organização obtenha informações sobre como o uso real se alinha com o uso previsto durante a fase Envision. Embora esta seção se concentre no uso do Teams, isso deve fazer parte de um esforço mais amplo para medir e avaliar o uso do Microsoft 365 ou Office 365 geral.

Revisar o uso com frequência no início da implantação oferece a oportunidade de:

- Valide se os usuários estão usando o Teams.

- Identifique possíveis desafios de adoção antes de criar problemas críticos em toda a organização.

- Entenda se há discrepâncias entre os requisitos de fase do Envision e o uso real.

Se o uso não for o esperado, isso pode ser devido a um problema de implantação ou o plano de adoção não está sendo executado corretamente ou algum outro problema. Dependendo do motivo real por trás do baixo uso, o administrador deve colaborar com as equipes relacionadas para ajudar a remover barreiras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medindo o uso com o Centro de administração do Microsoft 365

Os dados de uso do Teams estão disponíveis no painel Reporting. Os dados de uso do Teams podem ser encontrados em três relatórios diferentes. O primeiro relatório fornece uma visão entre produtos de como os usuários se comunicam e colaboram usando os vários serviços no Microsoft 365 ou Office 365. Este relatório pode ser encontrado aqui: [Relatórios do Microsoft 365 no centro de administração – Usuários Ativos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Os outros dois relatórios são específicos do Teams e fornecem mais detalhes sobre o uso do Teams de uma perspectiva de usuário e dispositivo. Ambos os relatórios podem ser encontrados aqui:

[Relatório de uso de dispositivos do Microsoft Teams](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Relatório de atividades do usuário do Microsoft Teams](/microsoft-365/admin/activity-reports/microsoft-teams-user-activity-preview)

#### <a name="required-permissions"></a>Permissões necessárias

Os relatórios de uso no centro de administração podem ser acessados por pessoas que receberam uma **função Administrador global** ou uma função de administrador específica do produto (**administrador do Exchange**, **administrador Skype for Business**, **administrador do SharePoint**).

Além disso, a função **Leitor de relatórios** está disponível para usuários que exigem acesso aos relatórios, mas não executam nenhuma tarefa que exija permissões no nível do administrador. Você atribui essa função para fornecer relatórios de uso a qualquer pessoa que seja um stakeholder, para monitorar e impulsionar a adoção. Para obter mais informações sobre as diferentes funções disponíveis, consulte [Sobre as funções de administrador do Microsoft 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Avaliando o uso

Depois de usar o painel Reporting para medir o uso, é importante comparar o uso medido com os principais indicadores de sucesso (KSIs) que você definiu durante a fase De visualização do projeto. Você pode definir um KSI que pode ser definido como uso ativo ou um que esteja indiretamente vinculado ao uso ativo.

É importante identificar quaisquer variações entre o uso real e planejado antes de retomar a distribuição para sites ou usuários adicionais. Você provavelmente identificará os aprendizados organizacionais como parte dessa atividade que você pode aproveitar para garantir que o próximo lote de sites ou usuários não encontre os mesmos problemas.

Primeiro, identifique se isso é um problema técnico ou de adoção. Comece investigando os itens abaixo, a fim de determinar onde está o problema.

1. Valide a qualidade executando uma [Revisão de Qualidade de Experiência](upgrade-monitor-quality.md).

2. Trabalhe com a equipe de helpdesk para verificar se não há problemas técnicos de tendência que impeçam os usuários de acessar ou usar o serviço. Se as tendências de problema existirem, use a seção [solução de problemas do ponto de extremidade](#endpoint-troubleshooting) mais tarde neste artigo para tentar resolver o problema antes de envolver o suporte.

3. Trabalhe com a equipe de treinamento e adoção para coletar comentários diretos dos usuários (consulte [Avaliar o sentimento do usuário](#assess-user-sentiment) mais adiante neste artigo) e verificar a eficácia das atividades de conscientização e adoção.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Medir o uso (fase de habilitação) | Medir e avaliar o uso do Teams à medida que os sites continuam a ser integrados durante a fase de habilitação. Resolva problemas de uso conforme necessário. | Semanal | |
| Medir o uso | Medir e avaliar o uso do Teams na fase Valor da Unidade (após a conclusão da implantação). Resolva problemas de uso conforme necessário. | Quinzenal | |
| (fase de valor da unidade) | | | |
| Atualizar plano de adoção | Atualize seu plano de adoção com base em como o uso medido se compara às suas metas de planejamento. | Conforme necessário | |

### <a name="references"></a>Referências

[Sobre o Centro de administração do Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Relatórios de atividades no Centro de administração do Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Avaliar o sentimento do usuário

Entender o sentimento do usuário pode atuar como um indicador chave para medir o sucesso da implantação do Teams. Os comentários do usuário podem gerar alterações em sua organização; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos seus usuários.

É importante obter comentários cedo e continuar avaliando o sentimento do usuário durante todo o ciclo de vida do projeto e além. Use as seguintes diretrizes para determinar o intervalo em que sua organização buscará comentários:

- **Início do projeto**: ao avaliar o sentimento do usuário no início do projeto, você pode obter uma visão antecipada de como seus usuários se sentem sobre a experiência do Teams.

- **Após os principais marcos**: ao coletar comentários em todo o ciclo de vida do projeto, você pode medir o sentimento do usuário continuamente e fazer alterações conforme necessário. Isso é especialmente útil após grandes marcos.

- **Conclusão** do projeto: avaliar o sentimento do usuário no final de um projeto dirá o quão bem você fez e onde o trabalho ainda precisa ser feito e permitirá que você compare os resultados com a pesquisa anterior.

- **Em andamento**: continue medindo o sentimento do usuário indefinidamente. Alterações no sentimento do usuário podem ser devido a alterações no ambiente da sua organização ou alterações no serviço do Teams. Ao medir o sentimento do usuário em intervalos regulares, você pode entender o desempenho das equipes de gerenciamento de serviços e como sua organização está respondendo às alterações no serviço do Teams.

O sentimento do usuário pode ser avaliado por meio de vários métodos diferentes. Isso pode incluir pesquisas por email, entrevistas presenciais ou telefônicas ou simplesmente criar um canal de comentários no Teams ou no Yammer. Para obter mais informações, confira [Melhores práticas para métodos de comentários do usuário no Microsoft Teams](best-practices-feedback.md).

Você também pode usar uma abordagem em todo o setor para avaliar o sentimento do usuário chamado NPS (net promotor score), que é descrito na seção a seguir.

### <a name="nps"></a>Nps

A pontuação do promotor líquido (NPS) é uma métrica de fidelidade do cliente em todo o setor e uma boa abordagem a ser usada para avaliar o sentimento do usuário. O NPS pode ser calculado fazendo duas perguntas: "Qual é a probabilidade de você recomendar o Teams a um colega?", seguido pela pergunta de forma livre: "Por quê?"

O NPS é um índice que varia de –100 a 100 que mede a disposição de um cliente em recomendar o produto ou serviço de uma empresa. O NPS é baseado em uma pesquisa anônima que é entregue aos usuários por email ou outros meios eletrônicos. O NPS mede a lealdade entre um provedor e um consumidor. Ela consiste em apenas uma pergunta, que pede aos usuários que classifiquem sua experiência de 1 a 10, com a opção de fornecer comentários adicionais. Em seguida, os usuários são classificados com base nas seguintes classificações:

- 9 ou 10 são Promotores: entusiastas leais que promoverão seu serviço e alimentarão outros.

- 7 ou 8 são passivos: satisfeitos, mas não entusiasmados, vulneráveis a outro serviço ou oferta.

- De 1 a 6 há Detratores: clientes infelizes que podem danificar seu serviço e impedir o crescimento.

![Um diagrama que demonstra a escala NPS.](media/operate-my-service-image2.png "Este diagrama demonstra a escala NPS. Mostra que as classificações de 0 a 6 são detratores, 7 a 8 são passivas e 9 a 10 são promotores.")

Embora o número NPS base seja útil, você obterá o maior valor ao analisar comentários do usuário. Eles ajudarão você a entender por que o usuário recomendaria (ou não) o Teams para outras pessoas. Esses comentários podem fornecer comentários valiosos para ajudar as equipes de gerenciamento de projetos ou serviços a entender os ajustes necessários para fornecer um serviço de qualidade.

Para fornecer pesquisas NPS à sua organização, você pode aproveitar sua ferramenta de pesquisa online favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Avaliar o sentimento do usuário | Capture e avalie o sentimento do usuário usando pesquisas ou entrevistas ou por meio de um canal de comentários no Teams ou no Yammer. | Conforme necessário | |
| Atualizar planos de adoção | Promover alterações na sua organização com base nos comentários do usuário; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos seus usuários. | Conforme necessário | |

### <a name="references"></a>Referências

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Usando o Yammer para coletar comentários](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Práticas recomendadas para comentários do usuário](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gerenciar a qualidade da rede

Muitos elementos principais de planejamento vão para otimizar, dimensionar o direito e corrigir sua infraestrutura de rede para garantir um caminho eficiente e de alta qualidade para o serviço do Microsoft Teams. As tarefas de planejamento e os requisitos são [abordados em nossas diretrizes de preparação de rede](prepare-network.md) . As redes geralmente evoluem ao longo do tempo devido a atualizações, expansão ou outros requisitos comerciais. É importante que você tenha em conta seus requisitos para o Teams em suas atividades de planejamento de rede.

Embora o planejamento de rede seja um aspecto crítico de uma implantação do Teams, é igualmente importante garantir que a rede permaneça saudável e permaneça atual, com base na alteração de requisitos comerciais ou técnicos.

Para garantir a integridade da rede, várias atividades de operações precisam ser executadas em intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Monitorar IPs e URLs do Microsoft 365 ou Office 365 | Monitore as alterações nos [intervalos de endereços IP e URLs Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) usando o [feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fornecido e inicie uma solicitação de alteração para grupos de rede aplicáveis. | Diário | |
| Atualizar a rede com base em alterações no Microsoft 365 ou Office 365 IPs e URLs | Faça atualizações para os componentes de rede aplicáveis (firewalls, servidores proxy, VPNs, firewalls do lado do cliente e assim por diante) para refletir as alterações nas [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). | Conforme necessário | |
| Fornecer dados de criação | Forneça informações atualizadas de sub-rede para o campeão de qualidade (ou stakeholders relevantes) para garantir que as [definições de construção no CQD sejam mantidas](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) atualizadas. | Conforme necessário | |
| Implementar alteração | Implemente alterações na rede para dar suporte à alteração dos requisitos técnicos e de negócios do Teams. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes com fio e Wi-Fi</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul> | Conforme necessário | |
| Monitoramento e relatórios de rede | Monitore as tendências de ponta a ponta da rede para disponibilidade, utilização e capacidade usando suas ferramentas de gerenciamento de rede de terceiros existentes e recursos de relatórios disponíveis em seus provedores de rede. Use dados de tendência para planejamento de capacidade de rede. | Diariamente, semanalmente, mensalmente | |
| Planejamento de capacidade | Colabore com os proprietários de serviços do Teams para entender a alteração dos requisitos comerciais e técnicos que podem gerar alterações adicionais de capacidade.  | Conforme necessário | |
| Solução e correção de problemas de rede | Ajude os auxiliares do Teams, os proprietários de serviços e os principais stakeholders a solucionar problemas e corrigir problemas relacionados à conectividade, confiabilidade ou qualidade do Teams. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes com fio e Wi-Fi</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul> | Conforme necessário | |
| Recuperação de desastre e teste de alta disponibilidade | Execute testes regulares de alta disponibilidade e recuperação de desastres na infraestrutura de rede para garantir que ela atenda aos SLOs (objetivos de nível de serviço) ou aos SLAs (contratos de nível de serviço) para o serviço teams. | Mensal | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Criar esquema de dados](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Avaliar e garantir a qualidade

Todas as organizações precisam de um grupo ou um indivíduo para serem responsáveis pela qualidade. Essa é a função mais importante do gerenciamento do serviço. A função De Campeão de Qualidade é atribuída a uma pessoa ou grupo apaixonado pela experiência de seus usuários.
Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções. O melhor candidato para o posto de defensor da qualidade costuma ser o proprietário do serviço do cliente. Dependendo do tamanho e complexidade da organização, isso pode ser qualquer pessoa ou grupo com paixão por garantir uma experiência de usuário de alta qualidade.

O campeão de qualidade aproveita ferramentas existentes e processos documentados, como o CQD (Painel de Qualidade de Chamada) e [Aprimorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md), monitorar a experiência do usuário, identificar tendências de qualidade e impulsionar a correção quando necessário.
O campeão de qualidade deve trabalhar com as respectivas equipes para conduzir ações de correção e relatar a um comitê gestor sobre o progresso e quaisquer problemas abertos.

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md) inclui atividades que avaliam e fornecem diretrizes de correção em áreas-chave que têm o maior impacto na melhoria da experiência do usuário. As diretrizes fornecidas no Guia de Revisão de Experiência de Qualidade se concentram em usar o CQD Online como a principal ferramenta para relatar e investigar cada área, com foco no áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

Recomendamos fortemente que você nomeie o campeão de qualidade no início. Depois de serem nomeados, eles devem começar a se familiarizar com o conteúdo em [Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md) e materiais de treinamento associados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe Atribuída |
|---|---|---|---|
| Nomear e treinar campeões de qualidade | Nomear e treinar um campeão de qualidade. | Conforme necessário | |
| Executar revisões de qualidade de experiência (QERs) | Execute um QER para identificar tendências de qualidade e confiabilidade, examinar os destinos definidos e relatar aos principais stakeholders da organização. | Mensalmente (semanalmente durante implantações) | |
| Correção de unidade | Coordene os esforços de correção em toda a organização com base nas avaliações e resultados do QER. | Conforme necessário | |
| Atualizar dados de construção no CQD | Atualize ou adicione novas definições de construção no CQD quando as alterações forem feitas na rede (consulte [Carregar informações de construção](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Conforme necessário | |
| Preencher a função De Campeão de Qualidade | Responsabilidade de ponta a ponta pela qualidade na organização. Isso inclui:<ul><li>Verifique se o QER está sendo realizado regularmente.</li><li>Reporte aos principais stakeholders sobre o status de qualidade.</li><li>Verifique se as definições de dados de construção estão atualizadas.</li><li>Coordene os esforços de correção em toda a organização para garantir que os usuários tenham uma experiência de alta qualidade com o Teams.</li></ul> | Diário | |

### <a name="references"></a>Referências

[Carregar informações de construção](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gerenciar pontos de extremidade

Os pontos de extremidade do Microsoft Teams podem ser definidos como qualquer computador, Mac, tablet ou dispositivo móvel (ou qualquer outro) que execute o cliente do Teams. O termo *ponto de extremidade* não abrange apenas o dispositivo em si, mas como um usuário se conecta ao dispositivo, por exemplo, usando o microfone interno do dispositivo ou alto-falante, fones de ouvido ou um headset otimizado. Depois de implantados, os pontos de extremidade não devem ser esquecidos. Os pontos de extremidade do Teams exigem cuidados e manutenção contínuos. As seções a seguir descrevem áreas específicas para se concentrar.

### <a name="endpoint-requirements"></a>Requisitos de ponto de extremidade

Um dos principais benefícios do Teams é que o cliente é mantido atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso. Os aplicativos móveis do Teams são mantidos atuais por meio de suas respectivas lojas de aplicativos.

O cliente do Teams tem requisitos mínimos em termos da plataforma de software subjacente. Esses requisitos podem ser alterados ao longo do tempo e, portanto, é importante monitorá-los para obter alterações. Por exemplo, o cliente do Teams tem uma versão mínima do iOS. Se o cliente usar um navegador da Internet, o navegador também precisará ser mantido atual. Uma lista de plataformas com suporte pode ser encontrada em [Obter clientes para o Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Firewalls do lado do cliente podem afetar a qualidade da chamada e até mesmo impedir que uma chamada seja estabelecida. Depois que as exclusões apropriadas no firewall do cliente tiverem sido configuradas, elas precisam ser mantidas atualizadas com base nas informações em [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Seu fornecedor de terceiros terá diretrizes específicas sobre como atualizar as exclusões.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Wi-Fi drivers podem ser problemáticos. Como exemplo, um driver pode ter comportamentos de roaming muito agressivos entre pontos de acesso que podem induzir a troca desnecessária de ponto de acesso, levando à má qualidade da chamada. Um driver de Wi-Fi de baixo desempenho pode ser descoberto por meio de uma Revisão de Qualidade de Experiência (consulte [Melhorar e monitorar a qualidade da chamada do Teams para](monitor-call-quality-qos.md) obter mais detalhes). É essencial implementar um processo controlado pela qualidade que monitora novos drivers de Wi-Fi e garante que eles sejam testados antes de serem implantados na população geral de usuários.

### <a name="endpoint-management"></a>Gerenciamento de ponto de extremidade

Um catálogo de pontos de extremidade e dispositivos de interface com suporte (como headsets) deve estar disponível e mantido. Este catálogo incluirá uma lista de dispositivos aprovados que foram selecionados e validados como parte das fases Envision e Onboard. Normalmente, dispositivos específicos são selecionados para cada tipo de persona em sua organização para atender às necessidades dos atributos dessa persona. Todos os pontos de extremidade têm um ciclo de vida e você precisa gerenciar os contratos de fornecedor, a garantia, a substituição, a distribuição e as políticas de reparo associadas a esses dispositivos.

### <a name="endpoint-troubleshooting"></a>Solução de problemas do ponto de extremidade

Mesmo que você tenha seguido as diretrizes anteriores, os usuários em sua organização ainda poderão ter problemas com o Teams. Embora o problema possa não estar com o ponto de extremidade em si, os sintomas do problema normalmente são apresentados por meio do cliente para o usuário. As diretrizes a seguir destinam-se a fornecer etapas gerais que você pode tomar para resolver o problema; não se destina a ser um guia abrangente de solução de problemas. As etapas são fornecidas em uma ordem específica, mas não precisam ser seguidas explicitamente e podem não ser aplicáveis, dependendo da natureza do problema.

1. **Validar a integridade do serviço:** O problema que um usuário pode estar enfrentando pode estar relacionado a um evento que afeta negativamente o serviço teams ou seus serviços dependentes. Como primeira etapa, recomendamos que você confirme que não há problemas de serviço ativos. Consulte [Como verificar a integridade do serviço do Microsoft 365](/office365/enterprise/view-service-health). Lembre-se de verificar o status dos serviços dependentes (por exemplo, Exchange, SharePoint, OneDrive for Business). O monitoramento da integridade do serviço é discutido com mais detalhes na seção anterior, [Monitorar a integridade do serviço](#monitor-service-health).

2. **Validar a conectividade do cliente:** Problemas de conectividade causam problemas de funcionalidade ou entrada no Teams. Recomendamos (especialmente para novos sites ou locais) que você valide a conectividade com o serviço. Verifique se as [diretrizes de URLs e intervalos de endereço IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) a seguir são seguidas para cada site. Você pode aproveitar a [Ferramenta de Avaliação de Rede da Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para executar um teste de conectividade para validar se as portas de mídia foram abertas corretamente para os recursos do Teams. Etapas detalhadas sobre como executar os testes de conectividade são fornecidas nas [diretrizes de preparação de rede](prepare-network.md) .

3. **Verifique a lista de problemas conhecidos:** Consulte [solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams) para determinar se o usuário foi afetado negativamente por um desses problemas. Siga a solução alternativa fornecida (se houver uma) para resolver o problema.

4. **Visite a comunidade do Microsoft Teams:** A [comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) oferece espaços dedicados para o Teams. A comunidade do Teams fornece uma lista de discussão, postagens de blog e anúncios centrados em torno do Teams. Você pode postar uma pergunta ou pesquisar discussões anteriores em busca de soluções para o seu problema.

5. **Entre em contato com Suporte da Microsoft:** você pode entrar em contato com Suporte da Microsoft para obter problemas com o Teams online ou por telefone. Para obter informações, consulte [Suporte de contato para produtos empresariais – Administração Ajuda](/microsoft-365/admin/contact-support-for-business-products). Para clientes Premier, as solicitações de suporte podem ser iniciadas seguindo as diretrizes em [Suporte de contato para Microsoft Teams (clientes Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Requisitos de ponto de extremidade | Verifique se o ponto de extremidade do Teams continua a atender a todos os requisitos de software do Teams [listados em Obter clientes para o Microsoft Teams](get-clients.md). | Mensal | |
| Firewalls de ponto de extremidade | Mantenha as exclusões apropriadas no firewall do ponto de extremidade com base nas informações em [URLs Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Seu fornecedor de terceiros terá diretrizes específicas sobre como manter as exclusões. Assine o feed do [RSS](https://support.office.com/o365ip/rss) para ser notificado automaticamente de alterações. | Conforme necessário | |
| Drivers de Wi-Fi | Teste e atualize Wi-Fi drivers no computador. Valide os resultados usando CQD ([Aprimore e monitore a qualidade da chamada para o Teams](monitor-call-quality-qos.md)). | Conforme necessário | |
| Gerenciamento de ponto de extremidade | Mantenha o catálogo de pontos de extremidade e dispositivos de interface com suporte (como headsets). Gerenciar contratos de fornecedor, garantia, distribuição, substituição e políticas de reparo. | Mensal | |
| Solução de problemas do ponto de extremidade | As tarefas de solução de problemas podem incluir verificar conectividade, consultar a lista de problemas conhecidos, coleta, análise e escalonamento de logs para fornecedores Suporte da Microsoft ou terceiros. | Conforme necessário | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Obter clientes para o Microsoft Teams](get-clients.md)

[Comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Entre em contato com o suporte de produtos para empresas - Ajuda da Administração](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Entrar em contato com o suporte do Premier](https://support.microsoft.com/premier/contacts)

[Solução de problemas de vídeo do Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gerenciar o Teams

Depois que o serviço do Microsoft Teams tiver sido implantado, você precisará executar várias atividades relacionadas à sua administração. As atividades vão desde administrar o serviço e usuários individuais até planejamento de capacidade e provisionamento de licenciamento e números de telefone. As seções a seguir abrangem algumas dessas tarefas de administração comuns.

### <a name="service-administration"></a>Administração de serviços

O serviço teams tem várias configurações que podem ser configuradas em todo o locatário.
As alterações feitas nas configurações de locatário afetam todos os usuários habilitados para o Teams. Para obter uma lista detalhada dessas configurações, consulte [Gerenciar configurações do Microsoft Teams para sua organização](enable-features-office-365.md).

### <a name="user-administration"></a>Administração do usuário

Para dar suporte aos usuários, uma organização pode exigir qualquer número de tarefas relacionadas— as tarefas específicas variam de uma organização para outra. Em última análise, essas tarefas precisam ser gerenciadas por uma equipe de suporte que recebeu essas funções operacionais. As tarefas a seguir geralmente são necessárias para dar suporte aos usuários no Teams.

#### <a name="general-tasks"></a>Tarefas gerais

[Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Criação de equipe (opcional)

Por padrão, todos os usuários com uma caixa de correio em Exchange Online têm permissões para criar grupos do Microsoft 365 e, portanto, uma equipe no Microsoft Teams. Se você quiser ter um controle mais rígido e [restringir a criação de novas equipes](assign-roles-permissions.md) (e, portanto, a criação de novos grupos do Microsoft 365), poderá delegar direitos de criação e gerenciamento de grupo a um conjunto de administradores. Se sua organização quiser prosseguir com essa opção, consulte o processo descrito neste artigo para permitir que os usuários enviem solicitações processadas por uma equipe atribuída.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Administração de serviços | Administração de configurações do Teams em todo o locatário. | Conforme necessário | |
| Administração do usuário | Administração de configurações e licenciamento baseados no usuário no Teams. | Conforme necessário | |
| Gerenciamento de licenças | Planeje as necessidades atuais e futuras para o licenciamento baseado em usuário e consumo (Chamando Planos e Créditos de Comunicação) aproveitando o [relatório de uso PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e o relatório [de pools de minutos PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Semanal | |
| Gerenciamento de números de telefone | Gerencie os números de telefone disponíveis para crescimento futuro e ajuste os níveis de inventário para atender às suas necessidades organizacionais. | Semanal | |
| Criação de equipe (opcional) | Examine e processe solicitações para criação de equipe. | Conforme necessário | |

<!--ENDOFSECTION-->