---
title: Guia de Operações do Microsoft Teams
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Tarefas e atividades necessárias para o Teams de serviços, incluindo o monitoramento da integridade do serviço e a avaliação e garantia da qualidade e do uso da rede.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 614b3a16a5c0d59a63f06d1328c68f42e3497af5
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823416"
---
# <a name="operate-my-service"></a>Operar meu serviço

Este artigo fornece uma visão geral dos requisitos para operar com êxito os serviços de voz de nuvem para sua organização. Ao operar corretamente seus serviços de voz na nuvem, você pode ter certeza de que está fornecendo uma experiência confiável e de alta qualidade para sua organização.

## <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações

O Guia de Operações fornece uma visão geral de todas as tarefas e atividades necessárias como parte da função de gerenciamento de serviços para Microsoft Teams.

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O Teams serviço abrange Microsoft 365 ou Office 365 e os componentes de infraestrutura implantados localmente (por exemplo, rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Talvez você já tenha implementado processos e tarefas associados aos serviços existentes. Dito isso, você provavelmente poderá aumentar seus processos atuais ao planejar o gerenciamento de serviços hoje para dar suporte Teams no futuro.

O gerenciamento de serviços abrange todas as atividades e processos envolvidos no gerenciamento Teams ponta a ponta. Conforme mostrado anteriormente, alguns componentes do gerenciamento de serviços , a infraestrutura que o próprio serviço Microsoft 365 ou Office 365 compreende, são de responsabilidade da Microsoft, enquanto você, o cliente, é responsável pelos usuários para gerenciar os vários aspectos do Teams, da rede e dos pontos de extremidade que você fornece.

As tarefas e atividades neste guia são agrupadas em oito categorias, conforme descrito no diagrama a seguir. Cada uma dessas categorias será expandida nas seções a seguir.

![Um diagrama ilustrando uma lista de categorias de tarefas e atividades.](media/operate-my-service-image1.png "Um diagrama ilustrando uma lista de categorias de tarefas e atividades que o gerenciamento de serviços Teams inclui. O diagrama também mostra que o gerenciamento de serviços é, em grande parte, uma tarefa do cliente.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida como as operações serão implementadas para Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Examine o Guia de Operações na completa.</li><li>Implemente uma estratégia de operações que se alinhe às metas da sua organização para fornecer a qualidade e a confiabilidade das cargas de trabalho de voz na nuvem.</li><li>Examine [a qualidade da chamada do Monitor](monitor-call-quality-qos.md).</li><li> Implemente uma estratégia de operações para executar regularmente revisões de qualidade da experiência para garantir que sua implantação de voz na nuvem esteja operando em seus recursos de pico.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mapeamento de funções operacionais

O planejamento que você realizou para operações durante a fase de Concepção é essencial, pois as atividades de operações começam quando os primeiros usuários piloto são habilitados. Este guia lista as atividades e tarefas que devem ser executadas diariamente, semanalmente, mensalmente ou conforme necessário para manter uma implantação de Teams de alta qualidade. Este guia fornece conhecimento e diretrizes sobre como executar essas atividades e tarefas críticas.

Um componente crucial de uma implantação bem-sucedida é garantir que o planejamento que você faz no início da fase de Concepção inclua determinar quem será responsável por executar atividades específicas. Depois de descobrir quais tarefas e atividades se aplicam à sua implantação, elas precisam ser compreendidas e seguidas pelos grupos ou indivíduos que você atribui a eles.

Cada equipe que você identificar deve revisar e concordar com as tarefas e responsabilidades identificadas e iniciar a preparação. Isso pode incluir treinamento e preparação, fornecer atualizações para o plano de equipe ou garantir que os provedores externos estejam prontos para entrega.

As atividades e funções definidas neste guia devem ser válidas na maioria dos cenários, mas cada implantação do Teams é exclusiva; portanto, você pode usar este guia como um ponto de partida para personalizar as atividades e as funções padrão para atender às suas necessidades.

Certifique-se de que cada equipe aceitável tenha uma boa compreensão das atividades necessárias para executar o serviço. É fundamental que cada equipe aceite e saia da responsabilidade em sua organização antes do início do primeiro piloto.

Depois que um contrato estiver em vigor, as equipes correspondentes devem começar a operacionalizar suas funções.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td>
<td><ul><li>Use este documento para facilitar o exercício de mapeamento de função operacional.</li><li>Reúna-se com as respectivas equipes de suporte para atribuir nomes a cada item na lista de atividades necessárias.</li><li>Obtenha aceitação ou aprovação nas funções atribuídas.</li><li>Verifique se as equipes correspondentes têm o treinamento, a preparação e os recursos apropriados para concluir as atividades necessárias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams de serviço

Microsoft Teams reúne tecnologias entre Microsoft 365 ou Office 365 para fornecer um hub para trabalho em equipe. Os exemplos incluem:

-   Azure Active Directory (Azure AD) fornece serviços de autenticação e autorização para Teams.

-   Exchange Online fornece recursos avançados, como retenção legal e descoberta eletrônica.

-   SharePoint Online fornece a capacidade de compartilhar arquivos em canais e OneDrive for Business fornece um mecanismo para compartilhar arquivos em um chat privado.

As organizações também podem aproveitar os investimentos existentes na infraestrutura local. Por exemplo, as contas Active Directory local existentes podem ser usadas para autenticação aproveitando Azure AD Conexão. Determinadas versões Exchange Server podem ser usadas no lugar de Exchange Online.

Essas tecnologias se reúnem para fornecer um pacote de comunicações avançado, colaborativo e inteligente para os usuários. Essa integração rígida é um dos principais Teams, mas também impulsiona um requisito para o gerenciamento de serviços nessas tecnologias.

Este guia aborda as principais áreas de foco para gerenciar o Teams serviço. Provavelmente, você tem planos de gerenciamento de serviços em vigor para as tecnologias de suporte das quais Teams depende. Caso contrário, você também precisará estabelecer planos de gerenciamento de serviços adequados para esses componentes de tecnologia (locais e online). Isso ajudará a garantir que os usuários aproveitem uma experiência confiável e de alta qualidade com Teams.

#### <a name="references"></a>Referências 

[Visão geral do Microsoft Teams](teams-overview.md)

[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md)

[Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Atividades do Guia de Operações

As seções a seguir fornecem uma visão geral das atividades necessárias para operar com êxito o Microsoft Teams serviço. Eles incluem referência a ferramentas, informações contextuais e conteúdo adicional para ajudá-lo a entender a atividade e ajudar nas iniciativas de preparação.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorar a integridade do serviço

É importante que você entenda a integridade geral do serviço Microsoft Teams para que você possa alertar proativamente outras pessoas em sua organização de qualquer evento que afete o serviço. Conforme descrito anteriormente, Teams depende de outros serviços Microsoft 365 ou Office 365, como Azure Active Directory, Exchange Online, SharePoint Online e OneDrive for Business. Por isso, é igualmente importante que você monitore a integridade dos serviços dependentes.

Incorpore essa atividade em seu processo de gerenciamento de incidentes para informar proativamente os usuários, a assistência técnica e suas equipes de operações para se prepararem para lidar com escalonamentos de usuários.

As seções a seguir descrevem as ferramentas que você pode aproveitar para monitorar [incidentes de serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) que afetam o Teams serviço. Um resumo dos benefícios de cada ferramenta e quando você deve usar cada uma delas é incluído na tabela a seguir.

| Ferramenta de Monitoramento                       | Benefícios                                            | Quando usar                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Centro de administração do Microsoft 365                     | Disponível em qualquer dispositivo com um navegador com suporte. | Use quando não precisar de notificações em tempo real.                                          |
| Microsoft 365 ou Office 365 Administração aplicativo                  | Fornece notificações por push para seu dispositivo móvel.  | Use quando precisar ser notificado sobre incidentes de serviço enquanto estiver em qualquer lugar.                  |
| Microsoft System Center               | Integração com o Microsoft System Center.           | Use quando precisar de recursos avançados de monitoramento e suporte de notificação.                       |
| Microsoft 365 ou api Office 365 De comunicações de serviço | Acesso programático à integridade Microsoft 365 ou Office 365 serviço.   | Use quando precisar de integração com uma ferramenta de monitoramento de terceiros ou quiser criar sua própria solução. |

> [!NOTE]
> Somente indivíduos que recebem a função de administrador **global** ou administrador **de** serviços podem exibir a integridade do serviço.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoramento com o Centro de administração do Microsoft 365

O [Centro de administração do Microsoft 365](https://portal.office.com/) fornece um painel de [Integridade](https://portal.office.com/adminportal/home#/servicehealth) do Serviço em que você pode exibir a integridade atual do serviço Teams além dos serviços dependentes.

### <a name="monitoring-with-the-mobile-app"></a>Monitoramento com o aplicativo móvel

O Microsoft 365 ou Office 365 Administração está disponível no Apple iOS, Android e Windows (PC e dispositivos móveis). O aplicativo fornece informações aos administradores de serviços sobre a integridade do serviço e as alterações futuras. O aplicativo dá suporte a notificações por push que podem alertá-lo quase imediatamente após a postagem de um aviso. Isso ajuda você a se manter atualizado sobre o status, a integridade e quaisquer alterações futuras no serviço. O suporte à notificação o torna a ferramenta de monitoramento recomendada para administradores. Para obter mais informações, consulte:

[Office 365 Administração Aplicativo Móvel](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Baixar o Office 365 Administração Móvel](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoramento com o Microsoft System Center

O Microsoft System Center é uma plataforma de gerenciamento integrado que ajuda você a gerenciar datacenter, dispositivos cliente e ambientes de TI de nuvem híbrida. Office 365 administradores que usam o System Center agora têm a opção de importar o Pacote de Gerenciamento do Office 365, o que permite que eles exibam todas as comunicações de serviço no Operations Manager no System Center. Usar essa ferramenta fornece acesso ao status de seus serviços assinados, incidentes de serviço ativos e resolvidos e suas comunicações do Centro de Mensagens (alterações futuras). Para obter mais informações, consulte a seguinte [postagem no blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Se você aproveitar o System Center para monitorar Teams integridade do serviço (e serviços dependentes), poderá personalizar ainda mais o pacote de gerenciamento para alertar ou notificar grupos ou indivíduos específicos que foram identificados para reagir a incidentes.
Esses grupos podem incluir proprietários de serviços, assistência técnica, grupos de suporte de segundo e terceiro níveis e gerentes de incidentes em sua organização.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoramento de cenários avançados

Você pode monitorar a integridade do serviço e as alterações futuras aproveitando a API Office 365 Service Communications para acessar Office 365 de serviço e as alterações programaticamente. Use essa API para criar sua própria ferramenta de monitoramento ou conectar suas ferramentas de monitoramento existentes Office 365 comunicações de serviço, possivelmente simplificando a maneira como você monitora seu ambiente. Para obter mais informações, [consulte Office 365 para Enterprise desenvolvedores](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade               | Descrição                                                                                                                                                                                                               | Cadência   | Equipe atribuída |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorar a integridade do serviço | Monitore proativamente Microsoft Teams integridade do serviço (e serviços dependentes) usando as ferramentas disponíveis. Os serviços dependentes incluem: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Em tempo real |               |
| Notificação de incidente  | Notifique os stakeholders internos dos eventos que afetam o Teams serviço. Os stakeholders internos podem incluir usuários, assistências auxiliares e gerenciadores de incidentes.                                                                          | Conforme necessário |               |

### <a name="references"></a>Referências 

[Como verificar a integridade Office 365 serviço](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Integridade e continuidade do serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gerenciar alterações organizacionais

Microsoft Teams é um serviço baseado em nuvem. Com isso, vem a capacidade de fornecer novos recursos e funcionalidades em um ritmo rápido. Fornecer inovação contínua fornece um benefício óbvio para as organizações, mas essas alterações precisam ser gerenciadas adequadamente em sua organização para evitar a resistência do usuário ou escalonamentos para sua assistência técnica.

As atualizações Teams são implantadas automaticamente para seus usuários. Seus usuários sempre terão o cliente e os recursos mais recentes disponíveis no Teams serviço. Não é possível gerenciar a distribuição de atualizações Teams para seus usuários, portanto, é extremamente importante gerenciar a mudança por meio de programas eficazes de comunicação, treinamento e adoção. Se os usuários estiverem cientes da alteração,&mdash;instruídos sobre os benefícios e capacitados a aproveitar os novos recursos, eles poderão se adaptar mais rapidamente e dar as boas-vindas à alteração.

### <a name="monitoring-for-change"></a>Monitoramento de alterações

A primeira etapa no gerenciamento de alterações é monitorar as alterações planejadas para Teams. A melhor fonte para monitorar essas alterações é o [Office 365 Roadmap](https://products.office.com/business/office-365-roadmap), que lista os recursos que estão atualmente em desenvolvimento, que estão sendo distribuídos para os clientes ou que foram totalmente iniciados. Você pode pesquisar Teams recursos específicos usando o filtro fornecido ou pode baixar o roteiro para um arquivo Excel para análise posterior. Para cada recurso, o roteiro fornece uma breve descrição, juntamente com a data de lançamento prevista.

No blog [Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), você pode aprender sobre práticas recomendadas, tendências e notícias sobre Teams de produtos. Espere encontrar as principais atualizações de recursos Teams ser anunciadas aqui. Você também pode assinar o blog por meio de um RSS feed. Em seguida, você pode adicionar o [RSS feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) diretamente em um canal Teams, para que todas as notícias importantes são entregues diretamente dentro de Teams.

Todos os recursos lançados estão documentados nas Notas [de Versão para Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aqui, você encontrará uma lista de recursos que foram lançados para dispositivos móveis, web e desktop. O mesmo conjunto de notas de versão também está disponível na guia  Novidades na [Ajuda](get-help-in-microsoft-teams.md).

Familiarize-se com os recursos disponíveis e certifique-se de atribuir proprietários aplicáveis para monitorar a alteração.

### <a name="planning-for-change"></a>Planejando alterações

Agora que você está ciente das alterações futuras no serviço Teams, a próxima etapa é preparar e planejar adequadamente. Avalie cada alteração para determinar quais alterações exigem comunicação com usuários, campanhas de conscientização, treinamento para equipes de suporte ou usuários ou campanhas de avaliação e adoção de recursos. Essa é a função principal de uma equipe de gerenciamento de alterações em sua organização. Veja abaixo uma coleção de tabelas de exemplo que podem ajudá-lo a planejar alterações.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Recurso: Gravação na nuvem (data de lançamento: janeiro de 2018)

**Faixa geral**

| Preparação para alterações | Status   | Anotações/próximas etapas | Proprietário |
|----|----|----|-----|
| Revisão legal   | Concluído     | Esse recurso é um pré-requisito para integrar a equipe de treinamento. | Project equipe  |

**Gerenciamento técnico de alterações**

|       Preparação para alterações       | Status |                      Anotações/próximas etapas                      |    Proprietário     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Alterações de TI necessárias      |  Sim   | Administração precisa habilitar a gravação somente para usuários identificados. | Equipe de suporte |
| Preparação técnica concluída |  Sim   |                                                            | Equipe de suporte |
|                              |        |                                                            |              |

**Gerenciamento de alterações do usuário** 

| Preparação para alterações | Status   | Anotações/próximas etapas | Proprietário |
|----|----|----|-----|
| Impacto do usuário                  | Baixo                  |                                                                 |                        |
| Preparação do usuário necessária      | Sim                  |                                                                 |                        |
| Comunicações prontas         | Não                   | O email de comunicação foi redigido — revisão pendente.            | Equipe de Comunicações    |
| Treinamento pronto               | Sim                  | O treinamento aproveitará o vídeo existente da Microsoft.                | Equipe de treinamento          |

**Faixa de status**

| Preparação para alterações | Status   | Anotações/próximas etapas | Proprietário |
|----|----|----|-----|
| Status da versão               | em andamento          | Revisão pendente pelo patrocinador executivo.               | Equipe de Gerenciamento de Alterações |
| Liberação de logoff             |                      |                                                                 |                        |
| Data de lançamento                 |                      |                                                                 |                        |

Para obter mais informações sobre como planejar o gerenciamento de alterações com Teams, consulte [Criar uma estratégia de gerenciamento de alterações para Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade               | Descrição                                                                                                                                                                                                                | Cadência   | Equipe atribuída |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorar alterações     | Monitore as alterações futuras no Microsoft Teams serviço.                                                                                                                                                                   | Diário     |               |
| Planejando alterações    | Avalie e planeje novos recursos e funcionalidades, incluindo planos de comunicação, campanhas de conscientização e treinamento.                                                                                                     | Conforme necessário |               |
| Preparação do usuário             | Execute campanhas de comunicação, reconhecimento ou treinamento direcionadas para garantir que os usuários estejam prontos para a próxima alteração.                                                                                                        | Conforme necessário |               |
| Dar suporte à preparação da equipe | Execute campanhas direcionadas de comunicação, reconhecimento ou treinamento para garantir que a equipe de suporte esteja pronta. As equipes de suporte podem incluir a equipe de "luva branca", assistência técnica, suporte de Camada 2 ou Camada 3, parceiros externos e assim por diante. | Conforme necessário |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Avaliar Teams uso

Após o início do piloto inicial, é essencial estabelecer uma cadência regular para medir o uso Teams uso real. Isso permite que sua organização obtenha insights sobre como o uso real se alinha com o uso previsto durante a fase de Concepção. Embora esta seção se concentre Teams uso, isso deve fazer parte de um esforço mais amplo para medir e avaliar Office 365 uso geral.

Examinar o uso com frequência no início da implantação oferece a oportunidade de:

-   Valide se os usuários estão usando Teams.

-   Identifique possíveis desafios de adoção antes que eles criem problemas críticos em toda a organização.

-   Entenda se há discrepâncias entre os requisitos da fase de Concepção e o uso real.

Se o uso não for o que você espera, isso pode ser devido a um problema de implantação ou o plano de adoção não está sendo executado corretamente ou algum outro problema. Dependendo do motivo real por trás do baixo uso, o administrador de serviços deve colaborar com as equipes relacionadas para ajudar a remover as barreiras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medir o uso com o Centro de administração do Microsoft 365

Os dados de uso Teams estão disponíveis no painel Relatórios. Teams dados de uso podem ser encontrados em três relatórios diferentes. O primeiro relatório fornece uma exibição entre produtos de como os usuários se comunicam e colaboram usando os vários serviços no Office 365. Este relatório pode ser encontrado aqui: Office 365 [relatório de usuários ativos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Os outros dois relatórios são Teams específicos e fornecem mais detalhes sobre Teams uso de uma perspectiva de usuário e dispositivo. Os dois relatórios podem ser encontrados aqui:

[Relatório de uso de dispositivos do Microsoft Teams](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Relatório de atividades do usuário do Microsoft Teams](/microsoftteams/teams-analytics-and-reports/user-activity-report)

#### <a name="required-permissions"></a>Permissões necessárias

Os relatórios de uso no centro de administração podem ser acessados por pessoas que foram atribuídas a uma função **de Administrador global** ou uma função de administrador específica do produto (**administrador do Exchange**, administrador **Skype for Business**, SharePoint **administrador**).

Além disso, a **função** leitor de Relatórios está disponível para usuários que exigem acesso aos relatórios, mas não executam nenhuma tarefa que exija permissões de nível de administrador. Você atribui essa função para fornecer relatórios de uso a qualquer pessoa que seja um stakeholder, para monitorar e impulsionar a adoção. Para obter mais informações sobre as diferentes funções disponíveis, consulte [About Office 365 admin.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>Avaliar o uso

Depois de usar o painel Relatórios para medir o uso, é importante comparar o uso medido com os KSIs (indicadores chave de sucesso) que você definiu durante a fase de Concepção do projeto. Você pode definir um KSI que pode ser definido como uso ativo ou um que esteja indiretamente vinculado ao uso ativo.

É importante identificar as variações entre o uso real e o planejado antes de retomar a distribuição para sites ou usuários adicionais. Você provavelmente identificará os aprendizados organizacionais como parte dessa atividade que você pode aproveitar para garantir que o próximo lote de sites ou usuários não encontre os mesmos problemas.

Primeiro, identifique se isso é um problema técnico ou de adoção. Comece investigando os itens abaixo, em ordem, para determinar onde o problema está.

1.  Valide a qualidade executando uma Revisão de Qualidade da Experiência (consulte [Melhorar e monitorar a](monitor-call-quality-qos.md) qualidade da chamada Teams para obter mais detalhes).

2.  Trabalhe com a equipe de assistência técnica para verificar se não há problemas técnicos mais populares impedindo que os usuários acessem ou usem o serviço. Se as tendências de problemas existirem[](#endpoint-troubleshooting), use a seção de solução de problemas do ponto de extremidade mais adiante neste artigo para tentar resolver o problema antes de envolver o suporte.

3.  Trabalhe com a equipe de treinamento e adoção para coletar comentários diretos [](#assess-user-sentiment) dos usuários (consulte Avaliar o sentimento do usuário mais adiante neste artigo) e verificar a eficácia das atividades de conscientização e adoção.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade                         | Descrição                                                                                                                      | Cadência   | Equipe atribuída |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Medir o uso (fase de habilitação) | Meça e avalie Teams uso à medida que os sites continuam a ser integrados durante a fase de habilitação. Resolver problemas de uso conforme necessário. | Semanal    |               |
| Medir o uso (fase de valor da unidade)                           | Meça e avalie Teams uso na fase Valor da Unidade (após a conclusão da implantação). Resolver problemas de uso conforme necessário. | Quinzenal  |               |
| Atualizar plano de adoção             | Atualize seu plano de adoção com base em como o uso medido se compara às suas metas de planejamento.                                         | Conforme necessário |               |

### <a name="references"></a>Referências 

[Sobre o Centro de administração do Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Relatórios de atividade no Centro de administração do Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Avaliar o sentimento do usuário

Entender o sentimento do usuário pode atuar como um indicador fundamental para medir o sucesso da implantação Teams usuário. Os comentários do usuário podem impulsionar alterações em sua organização; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos usuários.

É importante obter comentários antecipadamente e continuar avaliando o sentimento do usuário durante todo o ciclo de vida do projeto e além. Use as diretrizes a seguir para determinar o intervalo no qual sua organização buscará comentários:

-   **Início do projeto**: ao avaliar o sentimento do usuário no início do projeto, você pode obter uma visão antecipada de como os usuários se sentem sobre a experiência Teams experiência.

-   **Após os principais marcos**: coletando comentários em todo o ciclo de vida do projeto, você pode medir o sentimento do usuário continuamente e fazer alterações conforme necessário. Isso é especialmente útil após os principais marcos.

-   **Project** conclusão: avaliar o sentimento do usuário no final de um projeto informará o quão bem você fez e onde o trabalho ainda precisa ser feito e permitirá que você compare os resultados com a pesquisa anterior.

-   **Em andamento**: continue a medir o sentimento do usuário indefinidamente. As alterações no sentimento do usuário podem ocorrer devido a alterações no ambiente da sua organização ou alterações no Teams serviço. Ao medir o sentimento do usuário em intervalos regulares, você pode entender o desempenho das equipes de gerenciamento de serviços e como sua organização está respondendo às alterações no Teams serviço.

O sentimento do usuário pode ser avaliado por meio de vários métodos diferentes. Eles podem incluir pesquisas por email, entrevistas presenciais ou telefônicas ou simplesmente criar um canal de comentários no Teams ou Yammer. Para obter mais informações, consulte [As práticas recomendadas para métodos de comentários do usuário Microsoft Teams](best-practices-feedback.md).

Você também pode usar uma abordagem em todo o setor para avaliar o sentimento do usuário chamado NPS (net promotor score), que é descrito na seção a seguir.

### <a name="nps"></a>NPS 

O NPS (Net Promoter Score) é uma métrica de fidelidade do cliente em todo o setor e uma boa abordagem a ser usada para avaliar o sentimento do usuário. O NPS pode ser calculado fazendo duas perguntas: "Qual é a probabilidade de você recomendar o Teams a um colega?", seguido da pergunta de forma livre, "Por quê?"

O NPS é um índice, que varia de –100 a 100, que mede a disposição de um cliente em recomendar o produto ou serviço de uma empresa. O NPS é baseado em uma pesquisa anônima que é entregue aos usuários por email ou outros meios eletrônicos. O NPS mede a fidelidade entre um provedor e um consumidor. Ele consiste em apenas uma pergunta, que pede aos usuários para classificar sua experiência de 1 a 10, com a opção de fornecer comentários adicionais. Em seguida, os usuários são classificados com base nas seguintes classificações:

-   9 ou 10 são Promotores: entusiastas leais que promoverão seu serviço e alimentarão outros.

-   7 ou 8 são Passivos: satisfeitos, mas não entusiastas, vulneráveis a outro serviço ou oferta.

-   De 1 a 6 são Detrators: clientes infelizes que podem danificar seu serviço e impedir o crescimento.

![Um diagrama que demonstra a escala do NPS.](media/operate-my-service-image2.png "Este diagrama demonstra a escala do NPS. Ele mostra que as classificações de 0 a 6 são detrators, 7 a 8 são passivas e 9 a 10 são promotores.")

Embora o número npS base seja útil, você obterá o maior valor da análise de comentários do usuário. Eles ajudarão você a entender por que o usuário recomendaria (ou não) a Teams outras pessoas. Esses comentários podem fornecer comentários valiosos para ajudar as equipes de gerenciamento de projetos ou serviços a entender os ajustes necessários para fornecer um serviço de qualidade.

Para fornecer pesquisas nps à sua organização, você pode aproveitar sua ferramenta de pesquisa online favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade              | Descrição                                                                                                                                                                         | Cadência   | Equipe atribuída |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Avaliar o sentimento do usuário | Capture e avalie o sentimento do usuário usando pesquisas ou entrevistas ou por meio de um canal de comentários Teams ou Yammer.                                                                 | Conforme necessário |               |
| Atualizar planos de adoção | Impulsionar a alteração em sua organização com base nos comentários dos usuários; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos usuários. | Conforme necessário |               |

### <a name="references"></a>Referências 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Usando Yammer para coletar comentários](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Práticas recomendadas para comentários do usuário](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gerenciar a qualidade da rede

Muitos elementos de planejamento principais vão para otimizar, dimensionar com o botão direito e corrigir sua infraestrutura de rede para garantir um caminho eficiente e de alta qualidade para o serviço de Microsoft Teams. As tarefas de planejamento e os requisitos são abordados em nossas [diretrizes de preparação de](3-envision-evaluate-my-environment.md#network-readiness) rede. As redes geralmente evoluem ao longo do tempo devido a atualizações, expansão ou outros requisitos de negócios. É importante que você conta com seus requisitos para Teams atividades de planejamento de rede.

Embora o planejamento de rede seja um aspecto crítico de uma implantação de Teams, é igualmente importante garantir que a rede permaneça íntegra e permaneça atual, com base na alteração dos requisitos técnicos ou de negócios.

Para garantir a integridade da rede, várias atividades de operações precisam ser executadas em intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade                                                       | Descrição                                                                                                                                                                                                                                                                                                                                                                 | Cadência                | Equipe atribuída |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Monitorar Office 365 IPs e URLs                                | Monitore todas as alterações nos [intervalos de endereços IP e URLs](/microsoft-365/enterprise/urls-and-ip-address-ranges) do Office 365 usando o [feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fornecido e inicie uma solicitação de alteração para grupos de rede aplicáveis.                                                                                                                                | Diário                  |               |
| Atualizar a rede com base nas alterações feitas Office 365 IPs e URLs | Faça atualizações nos componentes de rede aplicáveis (firewalls, servidores proxy, VPNs, firewalls do lado do cliente e assim por diante) para refletir as alterações nas [URLs do Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).                                                                                                                                                              | Conforme necessário              |               |
| Fornecer dados de criação                                          | Forneça informações atualizadas da sub-rede para o defensor da qualidade (ou partes interessadas relevantes) para garantir que as definições de construção no [CQD sejam mantidas](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) atualizadas. | Conforme necessário              |               |
| Implementar alteração                                               | Implemente alterações na rede para dar suporte à alteração Teams requisitos técnicos e de negócios. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes com e Wi-Fi com fio</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul>     | Conforme necessário              |               |
| Monitoramento e relatórios de rede                               | Monitore a rede de ponta a ponta para ver tendências de disponibilidade, utilização e capacidade usando as ferramentas de gerenciamento de rede de terceiros existentes e os recursos de relatório disponíveis em seus provedores de rede. Use dados populares para planejamento de capacidade de rede.                                                                                                            | Diário, semanal, mensal |               |
| Planejamento de capacidade                                              | Colabore com os Teams de serviço para entender as mudanças nos requisitos técnicos e comerciais que podem impulsionar alterações de capacidade adicionais.                                | Conforme necessário              |               |
| Solução de problemas e correção de rede                        | Ajude os Teams, os proprietários de serviços e os principais stakeholders a solucionar e corrigir problemas relacionados Teams conectividade, confiabilidade ou qualidade. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes com e Wi-Fi com fio</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul>    | Conforme necessário              |               |
| Recuperação de desastre e teste de alta disponibilidade                | Execute testes regulares de alta disponibilidade e recuperação de desastre na infraestrutura de rede para garantir que ele atenda aos SLOs (objetivos de nível de serviço) ou SLAs (contratos de nível de serviço) declarados para o serviço Teams serviço.                                                                                                                                                  | Mensal                |               |


### <a name="references"></a>Referências 

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Criar esquema de dados](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Avaliar e garantir a qualidade 

Todas as organizações precisam que um grupo ou indivíduo seja aceitável para a qualidade. Essa é a função mais importante do gerenciamento do serviço. A função Defensor da Qualidade é atribuída a uma pessoa ou grupo que é apaixonada pela experiência dos usuários.
Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções. O melhor candidato para o posto de defensor da qualidade costuma ser o proprietário do serviço do cliente. Dependendo do tamanho e da complexidade da organização, isso pode ser qualquer pessoa ou grupo com uma paixão por garantir uma experiência de usuário de alta qualidade.

O defensor da qualidade aproveita ferramentas existentes e processos documentados, como o CQD (Painel de Qualidade de Chamada), para monitorar a experiência do usuário, identificar tendências de qualidade e conduzir a correção quando necessário.
O campeão de qualidade deve trabalhar com as respectivas equipes para conduzir ações de correção e relatar a um comitê gestor sobre o progresso e quaisquer problemas em aberto.

Leia Melhorar e monitorar a qualidade da chamada [para Teams](monitor-call-quality-qos.md), que descreve as atividades que avaliam e fornecem diretrizes de correção nas principais áreas que têm o maior impacto na melhoria da experiência do usuário. As diretrizes fornecidas neste artigo se concentram no uso do CQD como a principal ferramenta para relatar e investigar cada área, com foco no áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

É altamente recomendável que você nomeie o campeão de qualidade no início. Depois de indicados, eles devem começar a se familiarizar com o [conteúdo de](monitor-call-quality-qos.md) qualidade de chamada do Monitor e os materiais de treinamento associados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade                               | Descrição                                                                                                                                                                                                                                                                                                 | Cadência                             | Equipe Atribuída |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nominar e treinar campeão(s) de qualidade | Nomear e treinar um campeão de qualidade.                                                                                                                                                                                                                                                                   | Conforme necessário                           |               |
| Executar análises de qualidade de experiência (QERs)     | Execute uma QER para identificar tendências de qualidade e confiabilidade, examinar as metas definidas e relatar para os principais stakeholders da organização.                                                                                                                            | Mensalmente (semanalmente durante implantações) |               |
| Correção de unidade                      | Coordem os esforços de correção em toda a organização com base nas avaliações e descobertas de QER.                                                                                                                                                                                                           | Conforme necessário                           |               |
| Atualizar dados de criação no CQD            | Atualize ou adicione novas definições de construção no CQD quando forem feitas alterações na rede (consulte [Upload Informações de criação](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Conforme necessário                           |               |
| Preencher a função Campeão de Qualidade      | Responsabilidade de ponta a ponta pela qualidade na organização. Isso inclui:<ul><li>Verifique se o QER está sendo realizado regularmente.</li><li>Relate-se aos principais stakeholders sobre o status de qualidade.</li><li>Verifique se as definições de dados de compilação estão atualizadas.</li><li>Coordem esforços de correção em toda a organização para garantir que os usuários tenham uma experiência de alta qualidade com Teams.</li></ul>          | Diário                               |               |



### <a name="references"></a>Referências 


[Upload locatário e criação de dados no CQD](CQD-upload-tenant-building-data.md)

[Melhorar e monitorar a qualidade da chamada para Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gerenciar pontos de extremidade

Microsoft Teams pontos de extremidade podem ser definidos como qualquer computador, Mac, tablet ou dispositivo móvel (ou qualquer outro) que executa o Teams cliente. O termo  ponto de extremidade não abrange apenas o próprio dispositivo, mas como um usuário se conecta ao dispositivo, por exemplo, usando o microfone ou alto-falante interno do dispositivo, fones de ouvido ou um fone de ouvido otimizado. Depois de implantados, os pontos de extremidade não devem ser esquecidos. Os Teams de extremidade exigem manutenção e cuidado contínuos. As seções a seguir descrevem áreas específicas nas qual se concentrar.

### <a name="endpoint-requirements"></a>Requisitos do ponto de extremidade

Um dos principais benefícios do Teams é que o cliente é mantido atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso. Os Teams aplicativos móveis são mantidos atualizados por meio de suas respectivas lojas de aplicativos.

O Teams cliente tem requisitos mínimos em termos da plataforma de software subjacente. Esses requisitos podem mudar ao longo do tempo e, portanto, é importante monitorá-los quanto a alterações. Por exemplo, o Teams cliente tem uma versão iOS mínima. Se o cliente usar um navegador da Internet, o navegador também precisará ser mantido atualizado. Uma lista de plataformas com suporte pode ser encontrada em [Obter clientes para Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Os firewalls do lado do cliente podem afetar a qualidade da chamada e até mesmo impedir que uma chamada seja estabelecida. Depois que as exclusões apropriadas no firewall do cliente tiverem sido configuradas, elas precisarão ser mantidas atualizadas com base nas informações em [URLs de Office 365 e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Seu fornecedor de terceiros terá diretrizes específicas sobre como atualizar as exclusões.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Wi-Fi drivers podem ser problemáticos. Por exemplo, um driver pode ter comportamentos de roaming muito agressivos entre pontos de acesso que podem induzir a mudança desnecessária de ponto de acesso, levando à baixa qualidade da chamada. Um driver de Wi-Fi pode ser descoberto por meio de uma Revisão de Qualidade da Experiência (consulte Melhorar e monitorar a qualidade da chamada [Teams para obter](monitor-call-quality-qos.md) mais detalhes). É essencial implementar um processo orientado por qualidade que monitora novos drivers Wi-Fi e garante que eles sejam testados antes de serem implantados na população geral do usuário.

### <a name="endpoint-management"></a>Gerenciamento de ponto de extremidade

Um catálogo de pontos de extremidade e dispositivos de interface com suporte (como headsets) deve estar disponível e mantido. Esse catálogo incluirá uma lista de dispositivos aprovados que foram selecionados e validados como parte das fases Concepção e Integração. Normalmente, dispositivos específicos são selecionados para cada tipo de persona em sua organização para atender às necessidades dos atributos dessa persona. Todos os pontos de extremidade têm um ciclo de vida e você precisa gerenciar os contratos de fornecedor, garantia, substituição, distribuição e políticas de reparo associadas a esses dispositivos.

### <a name="endpoint-troubleshooting"></a>Solução de problemas de ponto de extremidade

Mesmo que você tenha seguido as diretrizes anteriores, os usuários em sua organização ainda poderão ter problemas com Teams. Embora o problema possa não ser com o ponto de extremidade em si, os sintomas do problema normalmente são exibidos por meio do cliente para o usuário. As diretrizes a seguir destinam-se a fornecer etapas gerais que você pode executar para resolver o problema; não se destina a ser um guia abrangente de solução de problemas. As etapas são fornecidas em uma ordem específica, mas não precisam ser seguidas explicitamente e podem não ser aplicáveis, dependendo da natureza do problema.

1.  **Validar a integridade do serviço:** O problema que um usuário pode estar enfrentando pode estar relacionado a um evento que afeta negativamente o Teams serviço ou seus serviços dependentes. Como primeira etapa, recomendamos que você confirme que não há nenhum problema de serviço ativo. Consulte [Como verificar a Office 365 do serviço](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Lembre-se de verificar o status dos serviços dependentes (por exemplo, Exchange, SharePoint, OneDrive for Business). O monitoramento da integridade do serviço é discutido mais detalhadamente na seção anterior, [Monitorar a integridade do serviço](#monitor-service-health).

2.  **Valide a conectividade do cliente:** Problemas de conectividade causam problemas de funcionalidade ou de entrada Teams. Recomendamos (especialmente para novos sites ou locais) que você valide a conectividade com o serviço. Verifique se as [diretrizes Office 365 URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) a seguir são seguidas para cada site. Você pode aproveitar a [Ferramenta de](https://www.microsoft.com/download/details.aspx?id=53885) Avaliação de Rede da Microsoft para executar um teste de conectividade para validar se as portas de mídia foram abertas corretamente para recursos de voz na nuvem. As etapas detalhadas sobre como executar os testes de conectividade são fornecidas nas diretrizes [de preparação de](3-envision-evaluate-my-environment.md#network-readiness) rede.

3.  **Verifique a lista de problemas conhecidos:** Consulte [Teams solução de](/MicrosoftTeams/troubleshoot/teams) problemas para determinar se o usuário foi afetado negativamente por um desses problemas. Siga a solução alternativa fornecida (se houver) para resolver o problema.

4.  **Visite a Microsoft Teams:** a [comunidade Microsoft Teams oferece](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) espaços dedicados para Teams. A Teams comunidade fornece uma lista de discussão, postagens no blog e comunicados centralizados em torno Teams. Você pode postar uma pergunta ou pesquisar discussões anteriores em busca de soluções para o problema.

5.  **Entre em Suporte da Microsoft:** entre em contato com Suporte da Microsoft para problemas com Teams online ou por telefone. Para obter informações, consulte [Contatar o suporte para produtos de negócios](/microsoft-365/admin/contact-support-for-business-products).
    Para clientes Premier, as solicitações de suporte podem ser iniciadas seguindo as diretrizes em Contatar o suporte [para Microsoft Teams (clientes Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade                 | Descrição                                                                                                                                                                                                                                                                                                                                                                     | Cadência   | Equipe atribuída |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisitos do ponto de extremidade    | Verifique se o ponto de Teams continua a atender a todos os requisitos de software para Teams listados em Obter clientes [para Microsoft Teams](get-clients.md).                                                                                                                                                                                       | Mensal   |               |
| Firewalls de ponto de extremidade       | Mantenha as exclusões apropriadas no firewall do ponto de extremidade com base [nas informações Office 365 URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Seu fornecedor de terceiros terá diretrizes específicas sobre como manter as exclusões. Assine o [RSS feed para](https://support.office.com/o365ip/rss) ser notificado automaticamente das alterações. | Conforme necessário |               |
| Drivers de Wi-Fi            | Teste e atualize Wi-Fi drivers no computador. Valide os resultados usando o CQD ([melhorar e monitorar a qualidade da chamada para Teams](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | Conforme necessário |               |
| Gerenciamento de ponto de extremidade      | Mantenha o catálogo de pontos de extremidade e dispositivos de interface com suporte (como headsets). Gerencie contratos de fornecedor, garantia, distribuição, substituição e políticas de reparo.                                                                                                                                                                                                        | Mensal   |               |
| Solução de problemas de ponto de extremidade | A solução de problemas de tarefas pode incluir verificar a conectividade, consultar a lista de problemas conhecidos, coleta de log, análise e escalonamento para Suporte da Microsoft ou fornecedores de terceiros.                                                                                                                                                                                               | Conforme necessário |               |

### <a name="references"></a>Referências 

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Obter clientes para o Microsoft Teams](get-clients.md)

[Microsoft Teams comunidade](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Entre em contato com o suporte de produtos para empresas - Ajuda da Administração](/microsoft-365/admin/contact-support-for-business-products)

[Entre em contato com o suporte Premier](https://support.microsoft.com/premier/contacts)

[Solução de problemas Teams vídeo](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gerenciar o Teams

Depois que Microsoft Teams serviço de gerenciamento tiver sido implantado, você precisará executar várias atividades relacionadas à administração dele. As atividades vão desde administrar o serviço e usuários individuais até o planejamento de capacidade e provisionamento de licenciamento e números de telefone. As seções a seguir abrangem algumas dessas tarefas comuns de administração.

### <a name="service-administration"></a>Administração de serviços

O Teams serviço tem várias configurações que podem ser configuradas em todo o locatário.
As alterações feitas nas configurações de locatário afetam todos os usuários que foram habilitados para Teams. Para obter uma lista detalhada dessas configurações, consulte [Gerenciar Microsoft Teams configurações para sua organização](enable-features-office-365.md).

### <a name="user-administration"></a>Administração do usuário

Para dar suporte aos usuários, uma organização pode exigir qualquer número de tarefas relacionadas. As tarefas específicas variam de uma organização para outra. Por fim, essas tarefas precisam ser gerenciadas por uma equipe de suporte que tenha sido atribuída a essas tarefas operacionais. As tarefas a seguir normalmente são necessárias para dar suporte a usuários no Teams.

#### <a name="general-tasks"></a>Tarefas gerais

[Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Tarefas comuns para Sistema de Telefonia

[Atribuir, alterar ou remover o número de telefone de um usuário](./assign-change-or-remove-a-phone-number-for-a-user.md)

[Atribuir ou alterar o endereço de emergência de um usuário](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Adicionar, alterar ou remover um local de emergência para sua organização](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Tarefas comuns para Audioconferência

[Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md)

[Alterar os números de telefone em sua ponte de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Gerenciamento de licenças

À medida que sua organização cresce ou se contrai, é importante planejar o licenciamento para as necessidades atuais e futuras. Há uma licença de Teams base, além do licenciamento para recursos de voz na [nuvem Sistema de Telefonia](here-s-what-you-get-with-phone-system.md) e [Audioconferência](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing#requirements-for-audio-conferencing).

Por Teams, Sistema de Telefonia licenças de planos de [chamadas associadas](calling-plan-landing-page.md). O licenciamento do Plano de Chamadas permite que você faça e receba chamadas telefônicas domésticas e/ou internacionais. Esses planos são baseados em uso e têm pools de minutos associados a eles. O [provisionamento de Créditos de](what-are-communications-credits.md) Comunicações garantirá que você nunca ficará sem serviço.

Audioconferência permite conferência discada tarifada e serviços de conferência discada doméstica. A conferência discada gratuita ou cenários de discagem não doméstica podem fazer com que você incorrer em encargos adicionais para os quais os [Créditos](what-are-communications-credits.md) de Comunicação são necessários.

Os Créditos de Comunicação podem complementar o Plano de Chamadas e Audioconferência licenças. As licenças do Plano de Chamadas e os Créditos de Comunicação são baseados em uso e, portanto, precisam ser monitorados e provisionados adequadamente.

Você pode aproveitar o relatório [de uso de PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) para ajudá-lo a monitorar o uso de minutos de Plano de Chamadas e Créditos de Comunicações. Com base nos resultados dessa atividade, você pode ajustar seu licenciamento adequadamente. Em breve, ofereceremos um relatório de [pools de minutos PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) para auxiliar com mais eficiência essa tarefa.

### <a name="telephone-number-management"></a>Gerenciamento de números de telefone

Há dois métodos para adquirir números no Teams: você pode portar números de telefone de outro provedor ou provisionar os números diretamente do inventário de números da Microsoft. Ambos os métodos são descritos em [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md).

Há um limite para o número de números de telefone que você pode provisionar no inventário de números da Microsoft. Os limites são determinados por vários fatores detalhados em Quantos números [de telefone você pode obter?](how-many-phone-numbers-can-you-get.md).
Os limites dependem do tipo de números: números de serviço de chamada gratuita, números de serviço de chamada tarifada e números de assinante (usuário). Cada um tem seus próprios limites e deve ser gerenciado independentemente. Se você estiver se aproximando do limite (ou tiver atingido o limite), poderá solicitar um incremento ao limite. Esse processo é descrito no artigo do parágrafo anterior.

Pode haver ocasiões em que um número não está disponível para ser provisionado em uma região em que o serviço está disponível. Para obter informações sobre o processo de solicitação de números, consulte [Gerenciar números de telefone para sua organização](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Criação de equipe (opcional)

Por padrão, todos os usuários com uma caixa de correio Exchange Online têm permissões para criar grupos Microsoft 365 e, portanto, uma equipe no Microsoft Teams. Se você quiser ter um controle mais rígido e restringir a criação de novas equipes [(e](assign-roles-permissions.md#permissions-to-create-teams), portanto, a criação de novos grupos de Microsoft 365), poderá delegar direitos de criação e gerenciamento de grupo a um conjunto de administradores. Se sua organização quiser buscar essa opção, consulte o processo descrito neste artigo para permitir que os usuários enviem solicitações que são processadas por uma equipe atribuída.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade                    | Descrição                                                                                                                                                                                                                                                                                                                                                                                                             | Cadência   | Equipe atribuída |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Administração de serviços      | Administração de configurações de Teams locatário.                                                                                                                                                                                                                                                                                                                                                                           | Conforme necessário |               |
| Administração do usuário         | Administração de configurações baseadas em usuário e licenciamento Teams.                                                                                                                                                                                                                                                                                                                                                           | Conforme necessário |               |
| Gerenciamento de licenças          | Planeje as necessidades atuais e futuras para licenciamento baseado em consumo e usuário (Planos de Chamadas e Créditos de Comunicação) aproveitando o relatório de uso [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e o relatório de [pools de minutos PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Semanal    |               |
| Gerenciamento de números de telefone | Gerencie os números de telefone disponíveis para crescimento futuro e ajuste os níveis de inventário para atender às suas necessidades organizacionais.                                                                                                                                                                                                                                                                                                | Semanal    |               |
| Criação de equipe (opcional)    | Examine e processe solicitações para a criação da equipe.                                                                                                                                                                                                                                                                                                                                                                          | Conforme necessário |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Melhorar e monitorar a qualidade da chamada

Melhorar e monitorar a qualidade da chamada [para Teams](monitor-call-quality-qos.md) inclui um conjunto de atividades que avaliam e fornecem diretrizes de correção em áreas-chave que têm o maior impacto na melhoria da experiência do usuário, conforme ilustrado abaixo.

![Diagrama de áreas a serem examinadas durante uma revisão de qualidade da experiência.](media/plan-my-service-management-image2.png "As principais áreas a serem examinadas durante uma Revisão de Qualidade da Experiência: áudio, confiabilidade e resultados da pesquisa do usuário.")

Ao avaliar e corrigir continuamente as áreas descritas no guia, você pode reduzir seu potencial para afetar negativamente a experiência do usuário. A maioria dos problemas de experiência do usuário encontrada em uma implantação pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy

-   Cobertura insatisfatória da rede Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Uso de dispositivos de áudio internos ou não otimizados

-   Dispositivos de rede ou sub-redes com problemas

As diretrizes fornecidas em Melhorar e monitorar a qualidade de chamadas do Teams se concentram no uso do CQD (Painel de Qualidade de Chamadas) Online como a principal ferramenta para relatar e investigar cada área descrita, com foco no áudio para maximizar [a](monitor-call-quality-qos.md) adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

É altamente recomendável que você nomeie o campeão de qualidade no início. Depois de indicados, eles devem começar a se familiarizar com o conteúdo em Melhorar e monitorar a qualidade da chamada [para Teams](monitor-call-quality-qos.md).

<!--ENDOFSECTION-->