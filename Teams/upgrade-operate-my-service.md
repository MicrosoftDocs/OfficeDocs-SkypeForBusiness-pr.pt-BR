---
title: Operações do Microsoft Teams| Gerenciamento de | Qualidade
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Tarefas e atividades necessárias para o gerenciamento de serviços do Teams, incluindo monitorar a saúde do serviço e avaliar e garantir a qualidade e o uso da rede
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3180eabe2886faaade690f7a5bc0f3f97226589
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841492"
---
# <a name="operate-your-service"></a>Operar seu serviço

![Diagrama de atualização da jornada, enfatizando o estágio de Excelência Operacional](media/upgrade-banner-op-excellence.png "Estágios da jornada de atualização, com ênfase no estágio de Excelência Operacional")

Este artigo faz parte do estágio de Excelência Operacional da sua jornada de atualização, que começa assim que você conclui a atualização do Skype for Business para o Teams.

Este artigo apresenta uma visão geral dos requisitos para operar com êxito o Teams em sua organização após a atualização. Ao operar corretamente seus serviços do Teams, você pode ter certeza de que está fornecendo uma experiência confiável e de alta qualidade para sua organização.

## <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações

O Guia de Operações oferece uma visão geral de todas as tarefas e atividades necessárias como parte da função de gerenciamento de serviço do Microsoft Teams.

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O serviço do Teams engloba o Microsoft 365 ou o Office 365 e os componentes de infraestrutura implantados no local (por exemplo, rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Talvez você já tenha implementado processos e tarefas associados aos serviços existentes. Dito isso, você provavelmente pode ampliar seus processos atuais ao planejar o gerenciamento de serviços hoje para dar suporte ao Teams no futuro.

O gerenciamento de serviços engloba todas as atividades e processos envolvidos no gerenciamento de equipes de ponta a ponta. Conforme já foi dito anteriormente, alguns componentes do gerenciamento de serviço ( a infraestrutura que o serviço do Microsoft 365 ou do Office 365 compreende ) são de responsabilidade da Microsoft, enquanto você, o cliente, é responsável pelos usuários para gerenciar os vários aspectos do Teams, da rede e dos pontos de extremidade que você fornece.

As tarefas e atividades neste guia são agrupadas em oito categorias, conforme ilustrado no diagrama a seguir. Cada uma dessas categorias será expandida nas seções a seguir.

![Um diagrama representando uma lista de categorias de tarefas e atividades](media/operate-my-service-image1.png "Um diagrama que representa uma lista de categorias de tarefas e atividades composta pelo gerenciamento de serviços do Teams. O diagrama também representa que o gerenciamento de serviços é, em grande parte, uma tarefa do cliente.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida como as operações serão implementadas para o Teams.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Revise o Guia de Operações na íntegra.</li><li>Implemente uma estratégia de operações que se alinhe às metas da sua organização para oferecer a qualidade e a confiabilidade das cargas de trabalho do Teams.</li><li>Confira o guia Revisão de Qualidade da Experiência.</li><li> Implemente uma estratégia de operações para executar regularmente as Avaliações de Qualidade da Experiência para garantir que sua implantação do Teams está funcionando em seus recursos máximos.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>Mapeamento de funções operacionais

O planejamento das operações durante a fase Previsão é fundamental, pois as atividades de operações começam quando os primeiros usuários piloto são habilitados. Este guia lista as atividades e tarefas que devem ser executadas diariamente, semanalmente, mensalmente ou conforme necessário para manter uma implantação de alta qualidade do Teams. Este guia fornece conhecimento e orientações sobre como realizar essas atividades e tarefas críticas.

Um componente crucial de uma implantação bem-sucedida é garantir que o planejamento que você faz no início da fase Previsão inclua determinar quem será responsável pela execução de atividades específicas. Depois que você descobrir quais tarefas e atividades se aplicam à sua implantação, elas precisam ser compreendidas e seguidas pelos grupos ou indivíduos que você atribui a eles.

Cada equipe que você identificar deve revisar e concordar com as tarefas e responsabilidades identificadas e iniciar a preparação. Isso pode incluir treinamento e preparação, fornecer atualizações para o plano de equipe ou garantir que os provedores externos estão prontos para entregar.

As atividades e funções definidas neste guia devem ser válidas na maioria dos cenários, mas todas as implantações do Teams são exclusivas; portanto, você pode usar este guia como ponto de partida para personalizar as atividades e funções padrão para atender às suas necessidades.

Certifique-se de que cada equipe responsável tenha um bom entendimento das atividades necessárias para executar o serviço. É fundamental que cada equipe aceite e se desacate em sua responsabilidade em sua organização antes do primeiro piloto começar.

Após a adoção de um contrato, as equipes correspondentes devem começar a operacionalizar suas funções.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td>
<td><ul><li>Use este documento para facilitar o exercício de mapeamento de função operacional.</li><li>Reunir-se com as respectivas equipes de suporte para atribuir nomes a cada item na lista de atividades necessárias.</li><li>Obtenha aceitação ou aprovação nas funções atribuídas.</li><li>Certifique-se de que as equipes correspondentes tenham o treinamento, preparação e recursos apropriados para concluir as atividades necessárias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependências de serviço do Teams

O Microsoft Teams reúne tecnologias no Microsoft 365 e no Office 365 para fornecer um hub para o trabalho em equipe. Exemplos incluem:

- O Azure Active Directory (Azure AD) fornece serviços de autenticação e autorização para o Teams.

- O Exchange Online fornece recursos avançados, como a proteção legal e a descoberta online.

- O SharePoint Online oferece a capacidade de compartilhar arquivos em canais, e o OneDrive for Business fornece um mecanismo para o compartilhamento de arquivos em um chat privado.

As organizações também podem aproveitar os investimentos existentes na infraestrutura local. Por exemplo, contas existentes do Active Directory local podem ser usadas para autenticação aproveitando o Azure AD Connect. Determinadas versões do Exchange Server podem ser usadas no lugar do Exchange Online.

Essas tecnologias se reúnem para fornecer um pacote de comunicações inteligente, colaborativo e abrangente para os usuários. Essa integração justa é um dos principais benefícios do Teams, mas também gera um requisito para o gerenciamento de serviços nessas tecnologias.

Este guia aborda as principais áreas de foco para gerenciar o serviço do Teams. Provavelmente, você tem planos de gerenciamento de serviço para as tecnologias de suporte das que o Teams depende. Caso não o seja, você também precisará estabelecer planos adequados de gerenciamento de serviço para esses componentes de tecnologia (no local e online). Isso ajudará a garantir que os usuários desfrutem de uma experiência confiável e de alta qualidade com o Teams.

#### <a name="references"></a>Referências

[Visão geral do Microsoft Teams](teams-overview.md)

[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md)

[Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md)

[Coexistência e interoperabilidade do Microsoft Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Atividades do Guia de Operações

As seções a seguir dão uma visão geral das atividades necessárias para operar com êxito o serviço do Microsoft Teams. Elas incluem referência a ferramentas, informações contextuais e conteúdo adicional para ajudá-lo a entender a atividade e auxiliar nas iniciativas de preparação.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorar a saúde do serviço

É importante que você entenda a saúde geral do serviço microsoft teams para que possa alertar proativamente outras pessoas em sua organização sobre qualquer evento que afete o serviço. Conforme descrito anteriormente, o Teams depende de outros serviços do Microsoft 365 e do Office 365, como o Azure Active Directory, o Exchange Online, o SharePoint Online e o OneDrive for Business. Por isso, é igualmente importante que você monitore a saúde dos serviços dependentes.

Incorpore essa atividade ao seu processo de gerenciamento de incidentes para informar proativamente os usuários, a ajuda e suas equipes de operações para se prepararem para lidar com escalonamentos de usuários.

As seções a seguir descrevem as ferramentas que você pode aproveitar para monitorar [incidentes de serviço](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) que afetam o serviço do Teams. Um resumo dos benefícios de cada ferramenta e quando você deve usar cada uma delas é incluída na tabela a seguir.

| Ferramenta de Monitoramento | Benefícios | Quando usar |
|---|---|---|
| Centro de administração do Microsoft 365 | Disponível em qualquer dispositivo com um navegador com suporte. | Use quando não precisar de notificações em tempo real. |
| Aplicativo de administração do Microsoft 365 | Fornece notificações por push para seu dispositivo móvel. | Use quando precisar ser notificado de incidentes de serviço enquanto estiver em qualquer lugar. |
| Centro de Sistema da Microsoft | Integração com o Microsoft System Center. | Use quando precisar de recursos avançados de monitoramento e suporte de notificação. |
| API de Comunicações de Serviço do Microsoft 365 | Acesso programático à saúde do serviço microsoft 365 ou office 365. | Use quando precisar de integração com uma ferramenta de monitoramento de terceiros ou quiser criar sua própria solução. |

> [!NOTE]
> Somente as pessoas que têm a função **de administrador global** ou administrador **de** serviço podem ver a saúde do serviço.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoramento com o Centro de administração do Microsoft 365

O Centro de administração do [Microsoft 365](https://portal.office.com/) fornece um painel de Saúde do Serviço onde você pode ver [a](https://portal.office.com/adminportal/home#/servicehealth) saúde atual do serviço teams além dos serviços dependentes.

### <a name="monitoring-with-the-mobile-app"></a>Monitoramento com o aplicativo móvel

O aplicativo Microsoft 365 Admin está disponível no Apple iOS, Android e Windows (PC e celular). O aplicativo fornece aos administradores de serviços informações sobre a saúde do serviço e alterações futuras. O aplicativo dá suporte a notificações por push que podem alertá-lo quase imediatamente depois que um aviso foi publicado. Isso ajuda você a se manter atualizado sobre o status, a saúde e quaisquer alterações futuras no serviço. O suporte à notificação o torna a ferramenta de monitoramento recomendada para administradores. Para obter mais informações, consulte:

[Aplicativo Móvel do Microsoft 365 Admin](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Baixar o aplicativo móvel Microsoft 365 Admin](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoramento com o Microsoft System Center

O Microsoft System Center é uma plataforma de gerenciamento integrada que ajuda você a gerenciar datacenter, dispositivos cliente e ambientes de TI de nuvem híbrida. Os administradores do Microsoft 365 ou do Office 365 que usam o System Center agora têm a opção de importar o Pacote de Gerenciamento, que permite exibir todas as comunicações de serviço no Gerenciador de Operações no System Center. Usar esta ferramenta oferece acesso ao status dos serviços inscritos, a incidentes de serviço ativos e resolvidos e às comunicações do Centro de Mensagens (alterações futuras). Para obter mais informações, consulte a seguinte postagem [de blog.](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/)

Se você aproveitar a Central de Sistemas para monitorar a saúde do serviço do Teams (e os serviços dependentes), poderá personalizar ainda mais o pacote de gerenciamento para alertar ou notificar grupos ou indivíduos específicos que foram identificados para reagir a incidentes.
Esses grupos podem incluir proprietários de serviços, assistências, grupos de suporte de segundo e terceiro níveis e gerentes de incidentes em sua organização.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoramento de cenários avançados

Você pode monitorar a saúde do serviço e as alterações futuras aproveitando a API de Comunicações de Serviço para acessar a saúde do serviço e as alterações programaticamente. Use esta API para criar sua própria ferramenta de monitoramento ou conectar suas ferramentas de monitoramento existentes às comunicações de serviço do Microsoft 365 ou do Office 365, o que pode simplificar a maneira como você monitora seu ambiente. Para saber mais, confira [o Microsoft 365 ou o Office 365 para desenvolvedores corporativos.](https://docs.microsoft.com/office/developer-program/microsoft-365-developer-program-faq)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Monitorar a saúde do serviço | Monitore proativamente a saúde do serviço do Microsoft Teams (e os serviços dependentes) usando as ferramentas disponíveis. Os serviços dependentes incluem: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Em tempo real | |
| Notificação de incidente | Notifique os participantes internos dos eventos que afetam o serviço do Teams. Os participantes internos podem incluir usuários, auxiliares e gerentes de incidentes. | Conforme necessário | |

### <a name="references"></a>Referências

[Como verificar a saúde do serviço do Microsoft 365 ou do Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Continuidade e Saúde do Serviço](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gerenciar alterações organizacionais

O Microsoft Teams é um serviço baseado em nuvem. Com isso, vem a capacidade de fornecer novos recursos e funcionalidades rapidamente. Oferecer inovação contínua fornece um benefício óbvio para as organizações, mas essas alterações precisam ser gerenciadas adequadamente em sua organização para evitar a resistência do usuário ou escalonamentos à sua ajuda.

As atualizações do Teams são automaticamente para seus usuários. Os usuários sempre terão o cliente e os recursos mais recentes disponíveis no serviço do Teams. Não é possível gerenciar a adoção de atualizações do Teams para seus usuários, portanto, é fundamentalmente importante gerenciar as alterações por meio de programas eficazes de comunicação, treinamento e adoção. Se os usuários estão cientes da mudança, instruídos sobre os benefícios e capacitados a aproveitar os novos recursos, eles poderão se adaptar mais rapidamente e dar boas-vindas &mdash; à mudança.

### <a name="monitoring-for-change"></a>Monitoramento de alterações

A primeira etapa no gerenciamento de alterações é monitorar as alterações planejadas para o Teams. A melhor fonte para monitorar essas alterações é o Mapa do [Microsoft 365,](https://www.microsoft.com/microsoft-365/roadmap)que lista os recursos que estão em desenvolvimento, que estão sendo lançados para os clientes ou que foram totalmente lançados. Você pode pesquisar recursos específicos do Teams usando o filtro fornecido ou pode baixar o roteiro para um arquivo do Excel para análise posterior. Para cada recurso, o roteiro fornece uma breve descrição, juntamente com a data de lançamento prevista.

No blog [do Microsoft Teams,](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)você pode saber mais sobre as práticas recomendadas, tendências e notícias sobre atualizações de produtos do Teams. Espere que as principais atualizações de recursos do Teams sejam anunciadas aqui. Você também pode se inscrever no blog por meio de um RSS feed. Em seguida, você pode [adicionar o RSS feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) diretamente em um canal do Teams, para que todas as notícias importantes são entregues diretamente dentro do Teams.

Todos os recursos lançados são documentados nas Notas [de Versão do Microsoft Teams.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
Aqui você encontrará uma lista de recursos que foram lançados para desktop, Web e dispositivos móveis. O mesmo conjunto de notas de  versão também está disponível na guia Novidades da [Ajuda.](get-help-in-microsoft-teams.md)

Familiarizar-se com os recursos disponíveis e garantir que você atribua proprietários aplicáveis para monitorar a alteração.

### <a name="planning-for-change"></a>Planejamento de alterações

Agora que você está ciente das alterações futuras no serviço do Teams, a próxima etapa é se preparar e planejar de acordo. Avalie cada alteração para determinar quais alterações exigem comunicação com os usuários, campanhas de reconhecimento, treinamento para equipes de suporte ou usuários, ou campanhas de avaliação e adoção de recursos. Essa é a função principal de uma equipe de gerenciamento de alterações em sua organização. Veja a seguir um conjunto de exemplos de tabelas que podem ajudá-lo a planejar alterações.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Recurso: Gravação na Nuvem (data de lançamento: janeiro de 2018)

**Faixa geral**

| Alterar preparação | Status | Anotações/próximas etapas | Proprietário |
|---|---|---|---|
| Revisão legal | Concluído | Este recurso é um pré-requisito para a integração da equipe de treinamento. | Equipe do Project |

**Gerenciamento de alterações técnicas**

| Alterar preparação | Status | Anotações/próximas etapas | Proprietário |
|---|---|---|---|
| Alterações de IT necessárias | Sim | O administrador precisa habilitar a gravação somente para usuários identificados. | Equipe de suporte |
| Preparação técnica concluída | Sim | | Equipe de suporte |
| | | | |

**Gerenciamento de alterações do usuário**

| Alterar preparação | Status | Anotações/próximas etapas | Proprietário |
|---|---|---|---|
| Impacto do usuário | Baixo | | |
| Preparação do usuário necessária | Sim | | |
| Comunicações prontas | Não | O email de comunicação foi redigido, com revisão pendente. | Equipe de Comunicações |
| Treinamento pronto | Sim | O treinamento aproveitará o vídeo da Microsoft existente. | Equipe de Treinamento |

**Controle de status**

| Alterar preparação | Status | Anotações/próximas etapas | Proprietário |
|---|---|---|---|
| Status do lançamento | em andamento | Revisão pendente pelo patrocinador executivo. | Equipe de Gerenciamento de Alterações |
| Liberação de assinatura | | | |
| Data do lançamento | | | |

Para saber mais sobre o planejamento de gerenciamento de alterações com o Teams, consulte Criar uma estratégia [de gerenciamento de alterações para o Microsoft Teams.](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade| Descrição| Cadência| Equipe atribuída |
|---|---|---|---|
| Monitorar a alteração| Monitore as alterações futuras no serviço do Microsoft Teams.| Diário||
| Planejamento de alterações| Avalie e planeje novos recursos e recursos, incluindo planos de comunicação, campanhas de reconhecimento e treinamento.| Conforme necessário ||
| Preparação do usuário| Realize campanhas de comunicação, reconhecimento ou treinamento direcionados para garantir que os usuários estão prontos para as próximas alterações.| Conforme necessário ||
| Preparação da equipe de suporte | Realize campanhas de comunicação, reconhecimento ou treinamento direcionados para garantir que a equipe de suporte esteja pronta. As equipes de suporte podem incluir a equipe "white" (white) team, helpdesks, suporte de Nível 2 ou Nível 3, parceiros externos e assim por diante. | Conforme necessário ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Avaliar o uso do Teams

Depois que o piloto inicial começar, é fundamental estabelecer uma cadência regular para medir o uso real do Teams. Isso permite que sua organização obtenha informações sobre como o uso real se alinha ao uso previsto durante a fase Previsão. Embora esta seção se concentre no uso do Teams, isso deve fazer parte de um esforço mais amplo para medir e avaliar o uso geral do Microsoft 365 ou do Office 365.

Revisar o uso com frequência no início da implantação oferece a oportunidade de:

- Validar se os usuários estão usando o Teams.

- Identifique possíveis desafios de adoção antes de criar problemas críticos em toda a organização.

- Entenda se há discrepâncias entre os requisitos de fases de Previsão e o uso real.

Se o uso não for o que você espera, isso pode ser devido a um problema de implantação, se o plano de adoção não está sendo executado corretamente ou algum outro problema. Dependendo do motivo real por trás do baixo uso, o administrador do serviço deve colaborar com as equipes relacionadas para ajudar a remover barreiras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medir o uso com o Centro de administração do Microsoft 365

Os dados de uso do Teams estão disponíveis no painel Relatório. Os dados de uso das equipes podem ser encontrados em três relatórios diferentes. O primeiro relatório fornece uma exibição entre produtos de como os usuários se comunicam e colaboram usando os vários serviços no Microsoft 365 ou no Office 365. Este relatório pode ser encontrado aqui: [Relatórios do Microsoft 365 no centro de administração – Usuários Ativos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Os outros dois relatórios são específicos do Teams e fornecem mais detalhes sobre o uso do Teams de uma perspectiva de usuário e dispositivo. Os dois relatórios podem ser encontrados aqui:

[Relatório de uso de dispositivos do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Relatório de atividades do usuário do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permissões necessárias

Os relatórios de uso no centro de administração podem ser acessados por pessoas que têm uma função de administrador **global** ou uma função de administrador específica do produto (administrador do **Exchange,** administrador do **Skype for Business,** administrador do **SharePoint).**

Além disso, a **função** Leitor de Relatórios está disponível para usuários que exigem acesso aos relatórios, mas não executam tarefas que exigem permissões no nível do administrador. Você atribui essa função para fornecer relatórios de uso a qualquer pessoa que seja um stakeholder, para monitorar e impulsionar a adoção. Para saber mais sobre as diferentes funções disponíveis, consulte Sobre as funções de administrador do [Microsoft 365.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>Avaliando o uso

Depois de usar o painel Relatório para medir o uso, é importante comparar o uso medido em relação a quaisquer KSIs (indicadores chave de sucesso) que você definiu durante a fase de Previsão do projeto. Você pode definir um KSI que pode ser definido como uso ativo ou um que esteja indiretamente vinculado ao uso ativo.

É importante identificar as variações entre o uso real e o planejado antes de retomar a aplicação para sites ou usuários adicionais. Você provavelmente identificará os aprendizados organizacionais como parte dessa atividade que pode aproveitar para garantir que o próximo lote de sites ou usuários não tenha os mesmos problemas.

Primeiro, identifique se isso é uma adoção ou um problema técnico. Comece investigando os itens abaixo, na ordem, para determinar onde está o problema.

1. Valide a qualidade executando uma [Revisão de Qualidade da Experiência.](upgrade-monitor-quality.md)

2. Trabalhe com a equipe de assistência técnica para verificar se não há problemas técnicos mais importantes que impeçam os usuários de acessar ou usar o serviço. Se as tendências de [](#endpoint-troubleshooting) problemas existirem, use a seção de solução de problemas do ponto de extremidade mais adiante neste artigo para tentar resolver o problema antes de entrar em contato com o suporte.

3. Trabalhe com a equipe de treinamento e adoção para coletar comentários diretos dos usuários (consulte Avaliar o sentimentos do usuário mais adiante neste artigo) e verificar a eficácia das atividades de reconhecimento e adoção. [](#assess-user-sentiment)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Medir o uso (fase de habilitação) | Mede e avalie o uso do Teams à medida que os sites continuarem a ser integrados durante a fase de habilitação. Resolver problemas de uso conforme necessário. | Semanal | |
| Medir o uso | Mede e avalie o uso do Teams na fase Valor da Unidade (após a conclusão da implantação). Resolver problemas de uso conforme necessário. | Quinzenal | |
| (fase do valor da unidade) | | | |
| Atualizar plano de adoção | Atualize seu plano de adoção com base em como o uso medido se compara às suas metas de planejamento. | Conforme necessário | |

### <a name="references"></a>Referências

[Sobre o Centro de administração do Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Relatórios de atividades no Centro de administração do Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Avaliar o sentimento do usuário

Compreender os sentimentos do usuário pode atuar como um indicador fundamental para o sucesso da sua implantação do Teams. Os comentários do usuário podem impulsionar as alterações em sua organização; isso pode incluir alterações nos planos de comunicação, programas de treinamento ou na maneira como você oferece suporte aos usuários.

É importante receber comentários mais cedo e continuar avaliando o sentimento do usuário durante todo o ciclo de vida do projeto e além. Use as seguintes orientações para determinar o intervalo no qual sua organização buscará comentários:

- **Início do projeto:** ao avaliar o sentimento do usuário no início do projeto, você pode obter uma visão antecipada de como seus usuários se sentem sobre a experiência do Teams.

- **Após os principais marcos:** coletando comentários em todo o ciclo de vida do projeto, você pode avaliar o sentimento do usuário continuamente e fazer alterações conforme necessário. Isso é especialmente útil após os principais marcos.

- **Conclusão do** projeto: Avaliar o sentimento do usuário no final de um projeto mostrará o quanto você fez e onde o trabalho ainda precisa ser feito e permitirá que você compare os resultados com a pesquisa anterior.

- **Em andamento:** continue a medir o sentimento do usuário indefinidamente. As alterações nos sentimentos do usuário podem ser devido a alterações no ambiente da sua organização ou alterações no serviço do Teams. Ao lidar com os sentimentos dos usuários em intervalos regulares, você pode entender o desempenho das equipes de gerenciamento de serviços e como sua organização está respondendo às alterações no serviço do Teams.

Os sentimentos do usuário podem ser avaliados por meio de vários métodos diferentes. Isso pode incluir pesquisas por email, entrevistas presenciais ou telefônicas ou simplesmente criar um canal de comentários no Teams ou no Yammer. Para saber mais, confira [as práticas recomendadas para os métodos de comentários do usuário no Microsoft Teams.](best-practices-feedback.md)

Você também pode usar uma abordagem de todo o setor para avaliar o sentimento do usuário chamado NPS (net npS score), que é descrito na seção a seguir.

### <a name="nps"></a>Nps

O NPS (Net Promoter Score) é uma métrica de fidelização de clientes de todo o setor e uma boa abordagem a ser usada para avaliar o sentimento do usuário. O NPS pode ser calculado fazendo duas perguntas: "Qual é a probabilidade de você recomendar o Teams para um colega?", seguido da pergunta de forma livre, "Por quê?"

NPS é um índice que varia de –100 a 100 que mede a disposição de um cliente em recomendar o produto ou serviço de uma empresa. O NPS baseia-se em uma pesquisa anônima que é entregue aos usuários por email ou outros meios eletrônicos. O NPS mede a fidelidade entre um provedor e um consumidor. Ela consiste em apenas uma pergunta, que solicita aos usuários que adem sua experiência de 1 a 10, com a opção de fornecer comentários adicionais. Os usuários são classificados com base nas seguintes classificações:

- 9 ou 10 são Promoters: entusiastas fidelistas que promoverão seu serviço e vão incentivar outras pessoas.

- 7 ou 8 são passivos: satisfeitos, mas não entusiastas, vulneráveis a outro serviço ou oferta.

- De 1 a 6 são Detratores: clientes insatisfeitos que podem danificar seu serviço e impedir o crescimento.

![Um diagrama que demonstra a escala NPS](media/operate-my-service-image2.png "Este diagrama demonstra a escala NPS. Ele mostra que as classificações de 0 a 6 são desbaixadores, 7 a 8 são passivos e 9 a 10 são promovedores.")

Embora o número NPS base seja útil, você obterá o máximo valor ao analisar comentários do usuário. Eles ajudarão você a entender por que o usuário recomendaria (ou não recomendaria) o Teams para outras pessoas. Esses comentários podem fornecer valiosos comentários para ajudar as equipes de gerenciamento de projetos ou serviços a entender os ajustes necessários para fornecer um serviço de qualidade.

Para fornecer pesquisas nps à sua organização, você pode aproveitar sua ferramenta de pesquisa online favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Avaliar o sentimento do usuário | Capture e avalie os sentimentos dos usuários usando pesquisas ou entrevistas ou por meio de um canal de comentários no Teams ou no Yammer. | Conforme necessário | |
| Atualizar planos de adoção | Impulsionar a alteração em sua organização com base nos comentários dos usuários; isso pode incluir alterações nos planos de comunicação, programas de treinamento ou na maneira como você oferece suporte aos usuários. | Conforme necessário | |

### <a name="references"></a>Referências

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Usar o Yammer para coletar comentários](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Práticas recomendadas para comentários do usuário](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gerenciar a qualidade da rede

Muitos dos principais elementos de planejamento vão para otimizar, fazer o reacionamento e a correção da infraestrutura de rede para garantir um caminho eficiente e de alta qualidade para o serviço do Microsoft Teams. As tarefas de planejamento e os requisitos são abordados em nossas [diretrizes de preparação de](prepare-network.md) rede. As redes geralmente evoluem ao longo do tempo devido a atualizações, expansão ou outros requisitos comerciais. É importante que você seja responsável pelos requisitos do Teams em suas atividades de planejamento de rede.

Embora o planejamento de rede seja um aspecto crítico de uma implantação do Teams, é igualmente importante garantir que a rede permaneça saudável e permaneça atual, com base na alteração de requisitos técnicos ou comerciais.

Para garantir a saúde da sua rede, várias atividades de operações precisam ser executadas em intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Monitorar IPs e URLs do Microsoft 365 ou office 365 | Monitore quaisquer alterações nas URLs e intervalos de endereços IP do [Office 365](https://aka.ms/o365ips) usando o [RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) fornecido e inicie uma solicitação de alteração para grupos de rede aplicáveis. | Diário | |
| Atualizar a rede com base em alterações em IPs e URLs do Microsoft 365 ou office 365 | Faça atualizações nos componentes de rede aplicáveis (firewalls, servidores proxy, VPNs, firewalls do lado do cliente e assim por diante) para refletir alterações nas URLs e intervalos de endereços IP do [Office 365.](https://aka.ms/o365ips) | Conforme necessário | |
| Fornecer dados de criação | Forneça informações atualizadas da sub-rede para o defensor da qualidade (ou participantes relevantes) para garantir que as definições de construção no [CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sejam atualizadas. | Conforme necessário | |
| Implementar alterações | Implemente alterações na rede para dar suporte à alteração de requisitos técnicos e comerciais do Teams. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes com fio e Wi-Fi com fio</li><li>Conectividade com a Internet e Rota Expressa</li><li>DNS</li></ul> | Conforme necessário | |
| Monitoramento e relatórios de rede | Monitore as tendências de disponibilidade, utilização e capacidade de rede de ponta a ponta usando as ferramentas de gerenciamento de rede de terceiros e os recursos de relatório de terceiros disponíveis em seus provedores de rede. Use dados mais recentes para o planejamento da capacidade de rede. | Diariamente, semanalmente, mensalmente | |
| Planejamento de capacidade | Colabore com os proprietários de serviços do Teams para entender as mudanças de requisitos técnicos e comerciais que podem impulsionar alterações de capacidade adicionais.  | Conforme necessário | |
| Solução de problemas e correção de rede | Ajude os auxiliares do Teams, os proprietários de serviços e os principais participantes a solucionar e a solucionar problemas relacionados à conectividade, confiabilidade ou qualidade do Teams. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>Vpns</li><li>Redes com fio e Wi-Fi com fio</li><li>Conectividade com a Internet e Rota Expressa</li><li>DNS</li></ul> | Conforme necessário | |
| Recuperação de desastres e teste de alta disponibilidade | Realize testes regulares de alta disponibilidade e recuperação de desastres na infraestrutura de rede para garantir que ela atenda aos SLOs (objetivos de nível de serviço) ou contratos de nível de serviço (SLAs) declarados para o serviço do Teams. | Mensal | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips)

[Esquema de construção de dados](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Avaliar e garantir a qualidade

Todas as organizações precisam que um grupo ou indivíduo seja responsável pela qualidade. Essa é a função mais importante do gerenciamento do serviço. A função Descampo da Qualidade é atribuída a uma pessoa ou grupo que é entusiasmado com a experiência de seus usuários.
Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções. O melhor candidato para o posto de defensor da qualidade costuma ser o proprietário do serviço do cliente. Dependendo do tamanho e da complexidade da organização, pode ser qualquer pessoa ou grupo com uma paixão para garantir uma experiência de usuário de alta qualidade.

O defensor da qualidade aproveita ferramentas existentes e processos documentados, como CQD (Painel de Qualidade de Chamada) e Melhorar e monitorar a qualidade das chamada para [o Teams,](monitor-call-quality-qos.md)para monitorar a experiência do usuário, identificar tendências de qualidade e impulsionar a correção quando necessário.
O defensor da qualidade deve trabalhar com as respectivas equipes para conduzir ações de correção e relatar a um comitê de direção sobre o progresso e quaisquer problemas abertos.

[Aprimorar e monitorar](monitor-call-quality-qos.md) a qualidade da chamada para o Teams inclui atividades que avaliam e fornecem orientações de correção em áreas principais que têm maior impacto na melhoria da experiência do usuário. As diretrizes fornecidas no Guia de Revisão da Experiência de Qualidade se concentram no uso do CQD Online como a ferramenta principal para relatar e investigar cada área, com foco no áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

Recomendamos que você nomeia o campeão de qualidade desde o início. Depois de indicados, eles devem começar a se familiarizar com o conteúdo em Melhorar e monitorar a qualidade da chamada para [o Teams](monitor-call-quality-qos.md) e materiais de treinamento associados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe Atribuída |
|---|---|---|---|
| Nominar e melhorar a qualidade do trem | Nomear e treinar um campeão de qualidade. | Conforme necessário | |
| Executar Avaliações de Qualidade da Experiência (QERs) | Execute uma QER para identificar tendências de qualidade e confiabilidade, revisar as metas definidas e informar-se aos principais participantes na organização. | Mensal (semanalmente durante implantações) | |
| Correção da unidade | Coordene os esforços de correção em toda a organização com base nas avaliações e descobertas de QER. | Conforme necessário | |
| Atualizar dados de criação no CQD | Atualize ou adicione novas definições de construção no CQD quando as alterações são feitas na rede (consulte As informações [do Upload Building).](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) | Conforme necessário | |
| Preencher a função Descampo da Qualidade | Responsabilidade de ponta a ponta pela qualidade na organização. Isso inclui:<ul><li>Verifique se a QER está sendo realizada regularmente.</li><li>Informe-se aos principais participantes sobre o status de qualidade.</li><li>Verifique se as definições de dados de construção estão atualizadas.</li><li>Coordene os esforços de correção em toda a organização para garantir que os usuários tenham uma experiência de alta qualidade com o Teams.</li></ul> | Diário | |

### <a name="references"></a>Referências

[Carregar informações do Building](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gerenciar pontos de extremidade

Os pontos de extremidade do Microsoft Teams podem ser definidos como qualquer computador, Mac, tablet ou dispositivo móvel (ou qualquer outro) que executa o cliente teams. O *ponto* de extremidade do termo não apenas engloba o dispositivo em si, mas como um usuário se conecta ao dispositivo, por exemplo, usando o microfone ou alto-falante interno do dispositivo, fones de ouvido ou um fone de ouvido otimizado. Depois de implantados, os pontos de extremidade não devem ser esquecidos. Os pontos de extremidade do Teams exigem manutenção e cuidados contínuos. As seções a seguir descrevem áreas específicas para se concentrarem.

### <a name="endpoint-requirements"></a>Requisitos do ponto de extremidade

Um dos principais benefícios do Teams é que o cliente é atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso. Os aplicativos móveis do Teams são mantidos atualizados por meio de suas respectivas lojas de aplicativos.

O cliente do Teams tem requisitos mínimos em termos da plataforma de software subjacente. Esses requisitos podem mudar ao longo do tempo e, portanto, é importante que você os monitore para alterações. Por exemplo, o cliente do Teams tem uma versão mínima para iOS. Se o cliente usar um navegador da Internet, o navegador também precisará ser atualizado. Uma lista de plataformas com suporte pode ser encontrada em [Obter clientes para o Microsoft Teams.](get-clients.md)

### <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Firewalls do lado do cliente podem afetar a qualidade da chamada e até mesmo impedir que uma chamada seja estabelecida. Depois que as exclusões apropriadas no firewall do cliente foram configuradas, elas precisam ser atualizadas com base nas informações nas URLs e intervalos de endereços IP do [Office 365.](https://aka.ms/o365ips) Seu fornecedor de terceiros terá orientações específicas sobre como atualizar as exclusões.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Wi-Fi drivers podem ser problemáticos. Por exemplo, um driver pode ter comportamentos de roaming muito agressivos entre pontos de acesso que podem induzir a mudança desnecessária de ponto de acesso, o que leva à baixa qualidade da chamada. Um driver de Wi-Fi com desempenho ruim pode ser descoberto por meio de uma Revisão de Qualidade da Experiência (consulte Melhorar e monitorar a qualidade das chamada para [o Teams](monitor-call-quality-qos.md) para obter mais detalhes). É essencial implementar um processo orientado pela qualidade que monitora novos drivers Wi-Fi e garante que eles são testados antes de serem implantados para a população geral de usuários.

### <a name="endpoint-management"></a>Gerenciamento de pontos de extremidade

Um catálogo de pontos de extremidade e dispositivos de interface compatíveis (como fones de ouvido) deve estar disponível e mantido. Este catálogo incluirá uma lista de dispositivos aprovados que foram selecionados e validados como parte das fases Previsão e Integração. Normalmente, dispositivos específicos são selecionados para cada tipo de persona em sua organização para atender às necessidades dos atributos dessa pessoa. Todos os pontos de extremidade têm um ciclo de vida e você precisa gerenciar os contratos do fornecedor, garantia, substituição, distribuição e políticas de reparo associadas a esses dispositivos.

### <a name="endpoint-troubleshooting"></a>Solução de problemas do ponto de extremidade

Mesmo que você tenha seguido as orientações anteriores, os usuários em sua organização ainda poderão ter problemas com o Teams. Embora o problema possa não estar no ponto de extremidade em si, os sintomas do problema normalmente são despontados pelo cliente para o usuário. A orientação a seguir destina-se a fornecer etapas gerais que você pode tomar para resolver o problema; não se trata de um guia de solução de problemas abrangente. As etapas são fornecidas em uma ordem específica, mas não precisam ser seguidas explicitamente e podem não ser aplicáveis, dependendo da natureza do problema.

1. **Validar a saúde do serviço:** O problema que um usuário pode estar enfrentando pode estar relacionado a um evento que afeta negativamente o serviço do Teams ou seus serviços dependentes. Como primeira etapa, recomendamos que você confirme que não há problemas de serviço ativo. Consulte Como verificar a saúde do [serviço microsoft 365.](https://docs.microsoft.com/office365/enterprise/view-service-health) Lembre-se de verificar o status dos serviços dependentes (por exemplo, Exchange, SharePoint, OneDrive for Business). O monitoramento da saúde do serviço é discutido em mais detalhes na seção anterior, [Monitorar a saúde do serviço.](#monitor-service-health)

2. **Validar a conectividade do cliente:** Problemas de conectividade causam problemas de funcionalidade ou de conexão no Teams. Recomendamos (especialmente para novos sites ou locais) que você valide a conectividade com o serviço. Certifique-se de que as seguintes URLs e intervalos de endereços IP do [Office 365](https://aka.ms/o365ips) são seguidos para cada site. Você pode aproveitar a [Ferramenta de Avaliação](https://www.microsoft.com/download/details.aspx?id=53885) de Rede da Microsoft para executar um teste de conectividade para validar que as portas de mídia foram abertas corretamente para recursos do Teams. As etapas detalhadas sobre como executar os testes de conectividade são fornecidas na orientação [de preparação da](prepare-network.md) rede.

3. **Verifique a lista de problemas conhecidos:** Consulte [a solução de problemas](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) do Teams para determinar se o usuário foi afetado negativamente por um desses problemas. Siga a solução alternativa fornecida (se houver uma) para resolver o problema.

4. **Visite a comunidade do Microsoft Teams:** A [comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) oferece espaços dedicados para o Teams. A comunidade do Teams fornece uma lista de discussão, postagens de blog e comunicados centralizados em torno do Teams. Você pode postar uma pergunta ou pesquisar discussões anteriores em busca de soluções para o problema.

5. **Entre em contato com o Suporte da Microsoft:** Você pode entrar em contato com o Suporte da Microsoft para problemas com o Teams online ou por telefone. Para obter informações, consulte [Contatar o suporte para produtos comerciais – Ajuda para Administradores.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) Para clientes Premier, as solicitações de suporte podem ser iniciadas seguindo as orientações em Contatar o suporte [do Microsoft Teams (clientes Premier).](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Requisitos do ponto de extremidade | Certifique-se de que o ponto de extremidade do Teams continue a atender a todos os requisitos de software do Teams listados em [Obter clientes para o Microsoft Teams.](get-clients.md) | Mensal | |
| Firewalls de ponto de extremidade | Mantenha as exclusões apropriadas no firewall do ponto de extremidade com base nas informações em URLs e intervalos de endereços IP do [Office 365.](https://aka.ms/o365ips) Seu fornecedor de terceiros terá orientações específicas sobre como manter as exclusões. Assine o [RSS feed para](https://support.office.com/o365ip/rss) ser notificado automaticamente das alterações. | Conforme necessário | |
| Drivers de Wi-Fi | Teste e atualize Wi-Fi drivers no computador. Valide os resultados usando o CQD ( Melhorar e monitorar a qualidade da chamada[para o Teams).](monitor-call-quality-qos.md) | Conforme necessário | |
| Gerenciamento de pontos de extremidade | Mantenha o catálogo de pontos de extremidade e dispositivos de interface compatíveis (como fones de ouvido). Gerencie contratos, garantia, distribuição, substituição e políticas de reparo do fornecedor. | Mensal | |
| Solução de problemas do ponto de extremidade | A solução de problemas de tarefas pode incluir verificar a conectividade, consultar a lista de problemas conhecidos, reunir log, analisar e escalonar para o Suporte da Microsoft ou fornecedores de terceiros. | Conforme necessário | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips)

[Obter clientes para o Microsoft Teams](get-clients.md)

[Comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Entre em contato com o suporte de produtos para empresas - Ajuda da Administração](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Entrar em contato com o suporte Premier](https://support.microsoft.com/premier/contacts)

[Solução de problemas de vídeo do Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gerenciar o Teams

Depois que o serviço do Microsoft Teams tiver sido implantado, você precisará executar várias atividades relacionadas à sua administração. As atividades variam desde a administração do serviço e usuários individuais até o planejamento da capacidade e o provisionamento de licenciamento e números de telefone. As seções a seguir abrangem algumas dessas tarefas comuns de administração.

### <a name="service-administration"></a>Administração do serviço

O serviço do Teams tem várias configurações que podem ser configuradas em todo o locatário.
As alterações feitas nas configurações de locatário afetam todos os usuários que foram habilitados para o Teams. Para ver uma lista detalhada dessas configurações, consulte [Gerenciar as configurações do Microsoft Teams para sua organização.](enable-features-office-365.md)

### <a name="user-administration"></a>Administração do usuário

Para dar suporte aos usuários, uma organização pode exigir qualquer número de tarefas relacionadas— as tarefas específicas variam de uma organização para outra. Em última análise, essas tarefas precisam ser gerenciadas por uma equipe de suporte que recebeu essas funções operacionais. As tarefas a seguir são normalmente necessárias para dar suporte aos usuários no Teams.

#### <a name="general-tasks"></a>Tarefas gerais

[Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Criação de equipe (opcional)

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Microsoft 365 e, portanto, uma equipe no Microsoft Teams. Se você quiser ter um [](assign-roles-permissions.md#permissions-to-create-teams) controle mais apertado e restringir a criação de novas equipes (e, portanto, a criação de novos grupos do Microsoft 365), poderá delegar os direitos de criação e gerenciamento de grupos a um conjunto de administradores. Se sua organização quiser prosseguir com essa opção, consulte o processo descrito neste artigo para permitir que os usuários enviem solicitações que são processadas por uma equipe atribuída.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme necessário

| Atividade | Descrição | Cadência | Equipe atribuída |
|---|---|---|---|
| Administração do serviço | Administração de configurações do Teams em todo o locatário. | Conforme necessário | |
| Administração do usuário | Administração de configurações baseadas em usuário e licenciamento no Teams. | Conforme necessário | |
| Gerenciamento de licenças | Planeje as necessidades atuais e futuras para o licenciamento baseado em consumo e usuário (Planos de Chamada e Créditos de Comunicação) aproveitando o relatório de uso [de PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e o relatório de pools de minutos [PSTN.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) | Semanal | |
| Gerenciamento de números de telefone | Gerencie os números de telefone disponíveis para crescimento futuro e ajuste os níveis de estoque para atender às suas necessidades organizacionais. | Semanal | |
| Criação de equipe (opcional) | Revisar e processar solicitações de criação de equipe. | Conforme necessário | |

<!--ENDOFSECTION-->
