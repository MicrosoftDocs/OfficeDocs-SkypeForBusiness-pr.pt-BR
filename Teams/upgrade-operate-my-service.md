---
title: Operações para Microsoft Teams | Gerenciamento de serviços | Qualidade
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Tarefas e atividades necessárias para o gerenciamento de serviços do Teams, incluindo monitorar a integridade do serviço e avaliar e garantir a qualidade e o uso da rede
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
ms.openlocfilehash: c23d5d3967e681b0b30d69c5977672063f4e648e
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085907"
---
# <a name="operate-your-service"></a>Operar seu serviço

![Atualize o diagrama de jornada, enfatizando o estágio operacional de excelência](media/upgrade-banner-op-excellence.png "Estágios da jornada da atualização, com ênfase no estágio Operational de excelência")

Este artigo faz parte do estágio operacional de excelência da sua jornada de atualização, que começa assim que você concluiu a atualização do Skype for Business para o Teams.

Este artigo apresenta uma visão geral dos requisitos para equipes com êxito para a sua organização após a atualização. Ao operar corretamente seus serviços do Microsoft Teams, você pode ter certeza de que está fornecendo uma experiência de alta qualidade e confiabilidade para sua organização.

## <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações

O guia de operações oferece uma visão geral de todas as tarefas e atividades necessárias, como parte da função de gerenciamento de serviços do Microsoft Teams.

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O serviço Teams abrange o Microsoft 365 ou o Office 365 e os componentes de infraestrutura implantados no local (por exemplo, rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Você já deve ter implementado processos e tarefas associadas a serviços existentes. Dito isso, você provavelmente pode aumentar seus processos atuais quando planejar o gerenciamento de serviços hoje para dar suporte às equipes no futuro.

O gerenciamento de serviços abrange todas as atividades e os processos envolvidos no gerenciamento do teams de ponta a ponta. Conforme observado anteriormente, alguns componentes de gerenciamento de serviços — a infraestrutura que o serviço do Microsoft 365 ou do Office 365 em si são, são responsabilidade da Microsoft, enquanto você, o cliente, é responsável pelos seus usuários gerenciar os diversos aspectos do Teams, da rede e dos pontos de extremidade que você fornece.

As tarefas e atividades neste guia são agrupadas em oito categorias, conforme mostrado no diagrama a seguir. Cada uma dessas categorias será expandida nas seções a seguir.

![Um diagrama que mostra uma lista de categorias de tarefas e atividades](media/operate-my-service-image1.png "Um diagrama que mostra uma lista de categorias de tarefas e atividades que o gerenciamento de serviços para equipes compreende. O diagrama também descreve que o gerenciamento de serviços é basicamente uma tarefa de cliente.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida como as operações serão implementadas para equipes.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Examine o guia de operações totalmente.</li><li>Implemente uma estratégia de operações que se alinhe às metas da sua organização para fornecer a qualidade e a confiabilidade das cargas de trabalho de equipes.</li><li>Examine o guia de revisão da qualidade da experiência.</li><li> Implemente uma estratégia de operações para executar regularmente análises de qualidade de experiência para garantir que a implantação de suas equipes esteja operando em seus recursos de pico.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>Mapeamento de funções operacionais

O planejamento que você fez nas operações durante a fase do enVision é crítico, pois as atividades de operações começam quando os primeiros usuários pilotos são habilitados. Este guia lista as atividades e tarefas que devem ser realizadas diariamente, semanalmente, mensalmente ou conforme necessário para manter uma implantação de equipes de alta qualidade. Este guia fornece conhecimento e orientação sobre como executar essas atividades e tarefas essenciais.

Um componente crucial de uma implantação bem-sucedida é garantir que o planejamento que você faz anteriormente na fase do enVision inclui determinar quem será responsável por realizar atividades específicas. Depois de descobrir quais tarefas e atividades se aplicam à sua implantação, elas precisam ser compreendidas e seguidas pelos grupos ou indivíduos atribuídos a elas.

Cada equipe que você identificar deve revisar e concordar com as tarefas e responsabilidades identificadas e iniciar a preparação. Isso pode incluir treinamento e preparação, fornecendo atualizações para o plano de pessoal ou garantindo que provedores externos estejam prontos para serem entregues.

As atividades e funções definidas neste guia devem ser válidas na maioria dos cenários, mas cada implantação de equipe é exclusiva; Portanto, você pode usar este guia como ponto de partida para personalizar as atividades e funções padrão para atender às suas necessidades.

Certifique-se de que cada equipe que você tem uma boa compreensão das atividades necessárias para executar o serviço. É fundamental que cada equipe aceite e se desative na responsabilidade de sua organização antes do primeiro piloto começar.

Depois que um contrato estiver em vigor, as equipes correspondentes deverão começar a realizar a operação.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td>
<td><ul><li>Use este documento para facilitar o exercício de mapeamento de funções operacionais.</li><li>Reúna-se com as respectivas equipes de suporte para atribuir nomes a cada item na lista de atividades necessárias.</li><li>Ganhe aceitação ou aprovação nas funções atribuídas.</li><li>Certifique-se de que as equipes correspondentes tenham o treinamento, preparação e recursos adequados para concluir as atividades necessárias delas.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependências do serviço Teams

O Microsoft Teams reúne tecnologias do Microsoft 365 e do Office 365 para fornecer um hub de trabalho em equipe. Os exemplos incluem:

- O Active Directory do Azure (Azure AD) fornece serviços de autenticação e autorização para Teams.

- O Exchange Online fornece recursos avançados, como retenção legal e descoberta eletrônica.

- O SharePoint Online oferece a capacidade de compartilhar arquivos em canais, e o OneDrive for Business oferece um mecanismo para compartilhar arquivos em um chat particular.

As organizações também podem aproveitar os investimentos existentes na infraestrutura local. Por exemplo, contas locais do Active Directory existentes podem ser usadas para autenticação, aproveitando o Azure AD Connect. Algumas versões do Exchange Server podem ser usadas no lugar do Exchange Online.

Essas tecnologias vêm juntas para fornecer um pacote de comunicações avançado, colaborativo e inteligente para os usuários. Essa forte integração é um benefício importante do Teams, mas também orienta a necessidade de gerenciamento de serviços nessas tecnologias.

Este guia abrange as principais áreas de foco para gerenciar o serviço do Microsoft Teams. Provavelmente, você tem planos de gerenciamento de serviços no lugar para as tecnologias de suporte das quais o Teams depende. Caso contrário, você precisará estabelecer planos de gerenciamento de serviços adequados para os componentes tecnológicos (locais e online) também. Isso ajudará a garantir que seus usuários aproveitem uma experiência de alta qualidade e confiabilidade com o Microsoft Teams.

#### <a name="references"></a>Referências

[Visão geral do Microsoft Teams](teams-overview.md)

[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md)

[Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md)

[A coexistência e interoperabilidade do Microsoft Teams e do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Atividades do guia de operações

As seções a seguir fornecem uma visão geral das atividades necessárias para operar com êxito o serviço do Microsoft Teams. Eles incluem referência a ferramentas, informações contextuais e conteúdo adicional para ajudá-lo a entender a atividade e para ajudar em iniciativas de preparação.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorar a integridade do serviço

É importante compreender a integridade geral do serviço Microsoft Teams para que você possa alertar proativamente outras pessoas em sua organização de qualquer evento que afete o serviço. Conforme descrito anteriormente, o Teams depende de outros serviços do Microsoft 365 e do Office 365, como o Azure Active Directory, o Exchange Online, o SharePoint Online e o OneDrive for Business. Por isso, é igualmente importante monitorar a integridade dos serviços dependentes.

Incorpore essa atividade ao seu processo de gerenciamento de incidentes para informar aos usuários, ao helpdesk e às suas equipes de operações a fim de se preparar para lidar com o atendimento ao usuário.

As seções a seguir descrevem as ferramentas que você pode aproveitar para monitorar [incidentes de serviço](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) que afetam o serviço Teams. Um resumo das vantagens de cada ferramenta e quando você deve usar cada uma delas está incluído na tabela a seguir.

| Ferramenta de monitoramento | Benefícios | Quando usar |
|---|---|---|
| Centro de administração do Microsoft 365 | Disponível em qualquer dispositivo com um navegador compatível. | Use quando não forem necessárias notificações em tempo real. |
| Aplicativo de administração do Microsoft 365 | Fornece notificações por push para o seu dispositivo móvel. | Use quando você precisar ser notificado sobre incidentes de serviço enquanto estiver em trânsito. |
| Centro de sistema da Microsoft | Integração com o Microsoft System Center. | Use quando precisar de recursos avançados de monitoramento e suporte de notificação. |
| API de comunicações do serviço Microsoft 365 | Acesso programático à integridade do serviço do Microsoft 365 ou do Office 365. | Use quando precisar de integração com uma ferramenta de monitoramento de terceiros ou se quiser criar sua própria solução. |

> [!NOTE]
> Somente pessoas que receberam a função de administrador **global** ou **administrador de serviço** podem exibir a integridade do serviço.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitorando com o centro de administração do Microsoft 365

O [centro de administração do Microsoft 365](https://portal.office.com/) fornece um [painel de integridade de serviço](https://portal.office.com/adminportal/home#/servicehealth) no qual você pode ver a integridade atual do serviço do Teams, além de serviços dependentes.

### <a name="monitoring-with-the-mobile-app"></a>Monitorando com o aplicativo móvel

O aplicativo de administração do Microsoft 365 está disponível em Apple iOS, Android e Windows (PC e celular). O aplicativo fornece informações de administradores de serviço sobre integridade do serviço e alterações futuras. O aplicativo dá suporte a notificações por push que podem alertá-lo quase que logo após a publicação de um comunicado. Isso ajuda você a ficar atualizado sobre o status, a integridade e todas as alterações futuras do serviço. O suporte de notificação o torna a ferramenta de monitoramento recomendada para administradores. Para obter mais informações, consulte:

[Aplicativo móvel de administração do Microsoft 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Baixar o aplicativo móvel Microsoft 365 admin](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitorando com o Microsoft System Center

O Microsoft System Center é uma plataforma de gerenciamento integrada que ajuda você a gerenciar o Data Center, dispositivos cliente e ambientes de ti híbridos da nuvem. Os administradores do Microsoft 365 ou do Office 365 que usam o System Center agora têm a opção de importar o pacote de gerenciamento, o que permite que eles vejam todas as comunicações do serviço dentro do Operations Manager do System Center. Usar essa ferramenta permite que você acesse o status de seus serviços inscritos, incidentes de serviço ativos e resolvidos e suas comunicações do centro de mensagens (alterações futuras). Para obter mais informações, consulte a seguinte [postagem de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Se você aproveitar o System Center para monitorar a integridade do serviço do Teams (e os serviços dependentes), poderá personalizar ainda mais o pacote de gerenciamento para alertar ou notificar grupos específicos ou pessoas que foram identificadas para reagir a incidentes.
Esses grupos podem incluir proprietários de serviços, helpdesks, grupos de suporte de segundo nível e terceiro e gerentes de incidentes em sua organização.

### <a name="monitoring-for-advanced-scenarios"></a>Monitorando cenários avançados

Você pode monitorar a integridade do serviço e as alterações futuras aproveitando a API de comunicações do serviço para acessar a integridade do serviço e as alterações de forma programática. Use essa API para criar sua própria ferramenta de monitoramento ou conecte suas ferramentas de monitoramento existentes às comunicações do serviço do Microsoft 365 ou do Office 365, o que pode simplificar o modo como você monitora o ambiente. Para obter mais informações, consulte [Microsoft 365 ou Office 365 para desenvolvedores corporativos](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/necessárias

| Atividade | Descrição | Cadência | Equipe designada |
|---|---|---|---|
| Monitorar a integridade do serviço | Monitorar proativamente o funcionamento do Microsoft Teams Service (e dos serviços dependentes) usando as ferramentas disponíveis. Os serviços dependentes incluem: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Tempo real | |
| Notificação de incidente | Notifique os participantes internos de eventos que afetam o serviço Teams. Os participantes internos podem incluir usuários, helpdesks e gerentes de incidentes. | Conforme necessário | |

### <a name="references"></a>Referências

[Como verificar a integridade do serviço do Microsoft 365 ou do Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Integridade e continuidade do serviço](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gerenciar alterações organizacionais

O Microsoft Teams é um serviço baseado em nuvem. Com isso, vem a capacidade de fornecer novos recursos e funcionalidades a um ritmo rápido. O fornecimento de inovação contínua oferece um benefício óbvio para as organizações, mas essas mudanças precisam ser gerenciadas apropriadamente em sua organização para evitar a resistência do usuário ou escalonamentos à sua assistência técnica.

As atualizações para o Microsoft Teams são distribuídas automaticamente para seus usuários. Seus usuários sempre terão o cliente e os recursos mais recentes disponíveis no serviço Teams. Não é possível gerenciar a distribuição de atualizações do teams para seus usuários, portanto, é extremamente importante gerenciar a mudança através de programas de comunicação, treinamento e adoção efetivos. Se seus usuários estiverem cientes da alteração, instruído sobre os benefícios e habilitados para aproveitar os novos recursos, &mdash; eles poderão se adaptar mais rapidamente e bem como a mudança.

### <a name="monitoring-for-change"></a>Monitorando alterações

A primeira etapa no gerenciamento de alterações é monitorar as alterações planejadas para equipes. A melhor fonte para monitorar essas alterações é o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap), que lista recursos que estão em desenvolvimento, sendo implantados para clientes ou inicializados completamente. Você pode pesquisar recursos específicos do teams usando o filtro fornecido ou baixar o mapa para um arquivo do Excel para análise adicional. Para cada recurso, o mapa fornece uma breve descrição, juntamente com a data de lançamento prevista.

No [blog do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), você pode saber mais sobre as práticas recomendadas, tendências e novidades sobre atualizações de produtos da Teams. Espere encontrar as principais atualizações de recursos para que as equipes sejam anunciadas aqui. Você também pode assinar o blog por meio de um RSS feed. Em seguida, você pode adicionar [o RSS feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) diretamente a um canal do Teams, para que todas as notícias importantes sejam fornecidas diretamente dentro do teams.

Todos os recursos lançados estão documentados nas [notas de versão do Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aqui você encontrará uma lista de recursos que foram lançados para área de trabalho, Web e dispositivos móveis. O mesmo conjunto de notas de versão também está disponível na guia **o que há de novo** na [ajuda](get-help-in-microsoft-teams.md).

Familiarize-se com os recursos disponíveis e certifique-se de atribuir proprietários aplicáveis para monitorar alterações.

### <a name="planning-for-change"></a>Planejar a mudança

Agora que você está ciente das futuras alterações no serviço Teams, a próxima etapa é preparar e planejar de acordo com isso. Avalie cada alteração para determinar quais alterações exigem comunicação com os usuários, campanhas de conscientização, treinamento para equipes de suporte ou usuários ou campanhas de avaliação de recursos e de adoção. Esta é a função principal de uma equipe de gerenciamento de alterações em sua organização. Veja a seguir um conjunto de tabelas de exemplo que podem ajudá-lo a planejar alterações.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Recurso: gravação na nuvem (data do lançamento: 2018 de Janeiro)

**Faixa geral**

| Alterar preparação | Situação | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| Revisão legal | Feito | Esse recurso é um pré-requisito para a integração da equipe de treinamento. | Equipe do projeto |

**Gerenciamento de alterações técnicas**

| Alterar preparação | Situação | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| É necessário alterar | Sim | O administrador precisa habilitar a gravação somente para usuários identificados. | Equipe de suporte |
| Preparação técnica concluída | Sim | | Equipe de suporte |
| | | | |

**Gerenciamento de alterações do usuário**

| Alterar preparação | Situação | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| Impacto do usuário | Baixo | | |
| Necessidade de preparação do usuário | Sim | | |
| Comunicações prontas | Não | O email de comunicação foi retirado — pendência de revisão. | Equipe de comunicações |
| Treinamento pronto | Sim | O treinamento usará o vídeo da Microsoft existente. | Equipe de treinamento |

**Faixa de status**

| Alterar preparação | Situação | Observações/próximas etapas | Proprietário |
|---|---|---|---|
| Status da versão | em andamento | Revisão pendente por patrocinador executivo. | Equipe de gerenciamento de alterações |
| Liberar a aprovação | | | |
| Data do lançamento | | | |

Para obter mais informações sobre como planejar o gerenciamento de alterações com o Teams, consulte [criar uma estratégia de gerenciamento de alterações para o Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/necessárias

| Atividade| Descrição| Cadência| Equipe designada |
|---|---|---|---|
| Monitorar para alterar| Monitore as alterações futuras do serviço Microsoft Teams.| Diário||
| Planejar a mudança| Avalie e planeje novos recursos e funcionalidades, incluindo planos de comunicação, campanhas de conscientização e treinamento.| Conforme necessário ||
| Preparação do usuário| Realize campanhas de comunicação, conscientização ou treinamento direcionadas para garantir que os usuários estejam prontos para a próxima mudança.| Conforme necessário ||
| Preparação da equipe de suporte | Realize campanhas de comunicação, conscientização ou treinamento direcionadas para garantir que a equipe de suporte esteja pronta. As equipes de suporte podem incluir a equipe "White Glove", os helpdesks, o suporte do nível 2 ou da camada 3, os parceiros externos e assim por diante. | Conforme necessário ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Avaliar o uso do teams

Após o início do piloto inicial, é fundamental estabelecer uma cadência regular para medir o uso de equipes reais. Isso permite que sua organização Obtenha ideias sobre como o uso real se alinha com o uso previsto durante a fase enVision. Embora esta seção se concentre no uso do Teams, isso deve fazer parte de um esforço mais amplo para medir e avaliar o Microsoft 365 ou o uso geral do Office 365.

A revisão do uso mais rápido na implantação oferece a oportunidade de:

- Valide se os usuários estão usando o Microsoft Teams.

- Identifique possíveis desafios de adoção antes de criarem problemas críticos em toda a organização.

- Compreender se há discrepâncias entre os requisitos da fase do enVision e o uso real.

Se o uso não for o esperado, isso pode ser devido a um problema de implantação, ou o plano de adoção não está sendo executado corretamente ou algum outro problema. Dependendo da razão real por trás do uso baixo, o administrador do serviço deve colaborar com as equipes relacionadas para ajudar a remover barreiras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medindo o uso com o centro de administração do Microsoft 365

Os dados de uso do teams estão disponíveis no painel relatório. Os dados de uso do teams podem ser encontrados em três relatórios diferentes. O primeiro relatório fornece um modo de exibição de produto cruzado de como os usuários se comunicam e colaboram usando os vários serviços no Microsoft 365 ou no Office 365. Este relatório pode ser encontrado aqui: [relatórios do Microsoft 365 no centro de administração – usuários ativos](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Os outros dois relatórios são específicos do Teams e fornecem mais detalhes sobre o uso do teams a partir de uma perspectiva de usuário e dispositivo. Os dois relatórios podem ser encontrados aqui:

[Relatório de uso de dispositivos do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Relatório de atividades do usuário do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permissões necessárias

Os relatórios de uso no centro de Administração podem ser acessados por pessoas que receberam uma função de **administrador global** ou por uma função de administrador específica do produto (**administrador do Exchange**, **administrador do Skype for Business**, **administrador do SharePoint**).

Além disso, a função de **leitor de relatórios** está disponível para os usuários que precisam acessar os relatórios, mas não executam nenhuma tarefa que exija permissões no nível de administrador. Você atribui esta função para fornecer relatórios de uso para qualquer pessoa que seja um participante, para monitorar e impulsionar a adoção. Para obter mais informações sobre as diferentes funções disponíveis, consulte [sobre as funções de administração do Microsoft 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Avaliando o uso

Depois de usar o painel relatório para medir o uso, é importante comparar o uso medido com relação a qualquer um dos indicadores de sucesso (KSIs) que você definiu durante a fase do enVision do projeto. Você pode definir um KSI que pode ser definido como uso ativo ou um que está indiretamente vinculado ao uso ativo.

É importante identificar todas as variações entre o uso real e planejado antes de retomar a distribuição para outros sites ou usuários. Você provavelmente identificará as informações organizacionais como parte dessa atividade que pode ser aproveitada para garantir que o próximo lote de sites ou usuários não encontrem os mesmos problemas.

Em primeiro lugar, identifique se esse é um problema de adoção ou técnico. Comece investigando os itens abaixo, em ordem, para determinar onde está o problema.

1. Valide a qualidade executando uma [avaliação da qualidade da experiência](upgrade-monitor-quality.md).

2. Trabalhe com a equipe da assistência técnica para verificar se não há problemas técnicos de tendência para impedir os usuários de acessar ou usar o serviço. Se houver tendências do problema, use a seção [solução de problemas do ponto de extremidade](#endpoint-troubleshooting) mais adiante neste artigo para tentar solucionar o problema antes de envolver o suporte.

3. Trabalhe com a equipe de treinamento e adoção para reunir comentários diretos dos usuários (consulte [avaliar as opiniões do usuário](#assess-user-sentiment) mais adiante neste artigo) e verificar a eficácia das atividades de conscientização e adoção.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/necessárias

| Atividade | Descrição | Cadência | Equipe designada |
|---|---|---|---|
| Medir o uso (fase de habilitação) | Meça e avalie o uso da equipe, pois os sites continuam a ser integrados durante a fase de capacitação. Solucionar problemas de uso conforme necessário. | Semanal | |
| Medir o uso | Medir e avaliar o uso da equipe na fase valor da unidade (após a conclusão da implantação). Solucionar problemas de uso conforme necessário. | Newsletter | |
| (fase valor da unidade) | | | |
| Atualizar plano de adoção | Atualize seu plano de adoção com base em como a medida de uso se compara aos seus objetivos de planejamento. | Conforme necessário | |

### <a name="references"></a>Referências

[Sobre o centro de administração do Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Relatórios de atividades no centro de administração do Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Avaliar o usuário do usuário

Entender o gauging do usuário pode atuar como um indicador chave para o sucesso da implantação de suas equipes. Os comentários dos usuários podem orientar as alterações em sua organização; Isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte a seus usuários.

É importante fazer comentários com antecedência e continuar avaliando os comentários dos usuários durante todo o ciclo de vida do projeto e além disso. Use as diretrizes a seguir para determinar o intervalo no qual sua organização buscará Comentários:

- **Início do projeto**: ao avaliar o Invista do usuário no início do projeto, você pode obter uma visão antecipada de como os usuários sentem a experiência da equipe.

- **Após marcos importantes**: coletar comentários durante todo o ciclo de vida do projeto, você pode avaliar os comentários dos usuários continuamente e fazer as alterações necessárias. Isso é especialmente útil após marcos importantes.

- **Conclusão do projeto**: avaliar as diferenças do usuário no final de um projeto informará o que você concluiu e onde ainda precisa ser feito o trabalho e permite que você compare os resultados com a pesquisa anterior.

- Em **andamento**: Continue medindo as infinitamente o usuário. As alterações nas alterações do usuário podem ser devido às alterações no ambiente da sua organização ou alterações no serviço do teams. Por gauging de um usuário em intervalos regulares, você pode entender como as equipes de gerenciamento de serviços estão funcionando e como sua organização está respondendo às alterações no serviço Teams.

Os totais do usuário podem ser avaliados com vários métodos diferentes. Eles podem incluir pesquisas de email, entrevistas no estilo de telefone ou de uma pessoa, ou simplesmente criar um canal de feedback no Teams ou no Yammer. Para obter mais informações, consulte [práticas recomendadas para métodos de comentários do usuário no Microsoft Teams](best-practices-feedback.md).

Você também pode usar uma abordagem industrywide para avaliar o erro do usuário chamado net promotor Score (NPS), descrito na seção a seguir.

### <a name="nps"></a>FUNCIONA

O protocolo de promoção da rede (NPS) é uma métrica de lealdade do cliente industrywide e uma boa abordagem para usar para avaliar as do usuário. O NPS pode ser calculado fazendo duas perguntas: "Qual é a probabilidade de você recomendar o Microsoft Teams para um colega?", seguido pela pergunta de forma livre, "por quê?"

NPS é um índice que varia de – 100 a 100 que mede a vontade do cliente de recomendar o produto ou serviço de uma empresa. O NPS é baseado em uma pesquisa anônima entregue aos usuários por e-mail ou por outros meios eletrônicos. O NPS mede a lealdade entre um provedor e um consumidor. Ele consiste apenas em uma pergunta, que solicita aos usuários que avaliem a experiência de 1 a 10, com a opção de fornecer comentários adicionais. Os usuários são classificados com base nas seguintes classificações:

- 9 ou 10 são responsáveis pela promoção: entusiastas da leais que promoverão seu serviço e combustívelão outras pessoas.

- 7 ou 8 são passivos: satisfeitos, mas não entusiastas, vulneráveis a outro serviço ou oferta.

- Entre 1 e 6 são desviadores: clientes insatisfeitos que podem danificar seu serviço e impedir o crescimento.

![Um diagrama que demonstra a escala do NPS](media/operate-my-service-image2.png "Este diagrama demonstra a escala do NPS. Ele mostra que as classificações de 0 a 6 são detratores, 7 a 8 são passivos e 9 a 10 são promodores.")

Embora o número de base do NPS seja útil, você obterá o valor máximo de análise de comentários do usuário. Elas o ajudarão a entender por que o usuário faria (ou não) recomendaria equipes para outras pessoas. Esses comentários podem fornecer feedback importante para ajudar as equipes de gerenciamento de projeto ou serviço a entender os ajustes necessários para fornecer um serviço de qualidade.

Para fornecer pesquisas de NPS à sua organização, você pode aproveitar sua ferramenta de pesquisa online favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Diário/semanal/mensal/de tarefas necessárias

| Atividade | Descrição | Cadência | Equipe designada |
|---|---|---|---|
| Avaliar o usuário do usuário | Capture e avalie opiniões do usuário usando pesquisas ou entrevistas, ou por meio de um canal de feedback no Teams ou no Yammer. | Conforme necessário | |
| Atualizar planos de adoção | Altere a mudança de unidade em sua organização com base nos comentários dos usuários; Isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte a seus usuários. | Conforme necessário | |

### <a name="references"></a>Referências

[Pontuação do promovedor líquido](https://en.wikipedia.org/wiki/Net_Promoter)

[Usar o Yammer para coletar comentários](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Práticas recomendadas para comentários dos usuários](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gerenciar a qualidade da rede

Muitos elementos básicos de planejamento vão até a otimização, o dimensionamento correto e a correção da infraestrutura de rede para garantir um caminho eficiente e de alta qualidade para o serviço do Microsoft Teams. As tarefas e os requisitos de planejamento são abordados na nossa orientação de [preparação de rede](prepare-network.md) . Muitas vezes, as redes evoluem ao longo do tempo devido a atualizações, expansão ou outras necessidades de negócios. É importante que você atenda às suas necessidades do teams em suas atividades de planejamento de rede.

Embora o planejamento de rede seja um aspecto crítico de uma implantação de equipe, é igualmente importante garantir que a rede permaneça íntegra e permaneça atualizada, com base em mudanças nos negócios ou nos requisitos técnicos.

Para garantir a integridade da sua rede, várias atividades de operações precisam ser realizadas em intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/necessárias

| Atividade | Descrição | Cadência | Equipe designada |
|---|---|---|---|
| Monitorar o Microsoft 365 ou as URLs e IPs do Office 365 | Monitore as alterações nas [URLs e nos intervalos de endereços IP do Office 365](https://aka.ms/o365ips) usando o [RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) fornecido e inicie uma solicitação de alteração para grupos de rede aplicáveis. | Diário | |
| Atualizar a rede com base nas alterações do Microsoft 365 ou do Office 365 IPs e URLs | Faça atualizações nos componentes de rede aplicáveis (firewalls, servidores proxy, VPNs, firewalls do lado do cliente e assim por diante) para refletir as alterações nas [URLs e nos intervalos de endereços IP do Office 365](https://aka.ms/o365ips). | Conforme necessário | |
| Fornecer dados de construção | Forneça informações atualizadas de sub-rede para o especialista em qualidade (ou stakeholders relevantes) para garantir que as [definições de construção no CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sejam mantidas atualizadas. | Conforme necessário | |
| Implementar alteração | Implementar alterações na rede para dar suporte às mudanças nos requisitos técnicos e comerciais da equipe. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Redes com fio e Wi-Fi</li><li>Conectividade à Internet e rota expressa</li><li>DNS</li></ul> | Conforme necessário | |
| Monitoramento de rede e relatórios | Monitore a rede de ponta a ponta para obter disponibilidade, utilização e tendências de capacidade usando suas ferramentas de gerenciamento de rede e recursos de emissão de relatórios existentes disponíveis em seus provedores de rede. Use os dados de tendências para o planejamento da capacidade de rede. | Diária, semanal, mensal | |
| Planejamento de capacidade | Colabore com os proprietários de serviços do teams para compreender mudanças nos requisitos técnicos e comerciais que podem gerar alterações adicionais de capacidade.  | Conforme necessário | |
| Solução de problemas e correção da rede | Ajude os helpdesks do Teams, os proprietários de serviços e os principais participantes a solucionar problemas e corrigir problemas relacionados à conectividade, à confiabilidade ou à qualidade das equipes. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Redes com fio e Wi-Fi</li><li>Conectividade à Internet e rota expressa</li><li>DNS</li></ul> | Conforme necessário | |
| Recuperação de desastres e testes de alta disponibilidade | Realize uma alta disponibilidade regular e teste de recuperação de desastres na infraestrutura de rede para garantir que ela atenda aos objetivos de nível de serviço (SLOs) ou contratos de nível de serviço (SLAs) estabelecidos para o serviço do teams. | Mensal | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips)

[Criando esquema de dados](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Avaliar e garantir a qualidade

Todas as organizações precisam de um grupo ou indivíduo para serem contados por qualidade. Essa é a função mais importante do gerenciamento do serviço. A função de especialista em qualidade é atribuída a uma pessoa ou grupo que seja apaixonado pela experiência dos usuários.
Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções. O melhor candidato para o posto de defensor da qualidade costuma ser o proprietário do serviço do cliente. Dependendo do tamanho e da complexidade da organização, isso pode ser qualquer pessoa ou grupo com entusiasmo para garantir uma experiência de usuário de alta qualidade.

O especialista em qualidade aproveita as ferramentas existentes e os processos documentados, como o CQD (painel de qualidade da chamada) e [aprimorar e monitorar a qualidade das chamadas para as equipes](monitor-call-quality-qos.md), monitorar a experiência do usuário, identificar tendências de qualidade e remediação quando necessário.
O especialista em qualidade deve funcionar com as respectivas equipes para direcionar ações de correção e reportar para um Comitê de direcionamento sobre o progresso e quaisquer problemas de abertura.

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md) inclui atividades que avaliam e fornecem orientação de correção em áreas importantes com impacto maior na melhoria da experiência do usuário. A orientação fornecida no guia de revisão da experiência de qualidade concentra-se em usar o CQD online como a principal ferramenta para denunciar e investigar cada área, com foco no áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

É altamente recomendável que você Innomine o especialista de qualidade em início. Depois de serem nomeados, eles devem começar a se familiarizar com o conteúdo em [aprimorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md) e material de treinamento associado.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/necessárias

| Atividade | Descrição | Cadência | Equipe designada |
|---|---|---|---|
| Indicar e treinar a (s) Champion (s) de qualidade | Innomeado e treine um especialista em qualidade. | Conforme necessário | |
| Executar análises de qualidade de experiência (QERs) | Execute um QER para identificar as tendências de qualidade e confiabilidade, a análise em relação a destinos definidos e a saída para os principais participantes da organização. | Mensalmente (semanal durante implantações) | |
| Correção de unidade | Coordene os esforços de correção em toda a organização com base nas avaliações e resultados do QER. | Conforme necessário | |
| Atualizar a construção de dados no CQD | Atualize ou adicione novas definições de construção no CQD quando forem feitas alterações na rede (consulte [carregar informações de edifício](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Conforme necessário | |
| Preencher a função de especialista em qualidade | Responsabilidade de ponta a ponta por qualidade na organização. Isso inclui:<ul><li>Certifique-se de que a QER está sendo conduzida regularmente.</li><li>Informe-se aos principais stakeholders sobre o status de qualidade.</li><li>Verifique se as definições de criação de dados estão atualizadas.</li><li>Coordene os esforços de correção em toda a organização para garantir que os usuários tenham uma experiência de alta qualidade com o Teams.</li></ul> | Diário | |

### <a name="references"></a>Referências

[Carregar informações de construção](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gerenciar pontos de extremidade

Os pontos de extremidade do Microsoft Teams podem ser definidos como qualquer dispositivo de PC, Mac, Tablet ou celular (ou qualquer outro) que esteja executando o cliente do teams. O *ponto de extremidade* de termo não só abrange o dispositivo em si, mas como um usuário se conecta ao dispositivo, por exemplo, usando o microfone ou o alto-falante interno do dispositivo, o fones ou um fone de ouvido otimizado. Após a implantação, os pontos de extremidade não devem ser esquecidos. Os pontos de extremidade do teams exigem cuidados e manutenção contínuos. As seções a seguir descrevem áreas específicas nas quais se concentrar.

### <a name="endpoint-requirements"></a>Requisitos de ponto de extremidade

Um dos principais benefícios do teams é que o cliente é mantido atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso. Os aplicativos móveis do teams são mantidos em dia por meio de suas respectivas lojas de aplicativos.

O cliente do teams tem requisitos mínimos em termos da plataforma de software subjacente. Esses requisitos podem mudar ao longo do tempo e, portanto, é importante que você os Monitore para alterações. Por exemplo, o cliente do teams tem uma versão mínima do iOS. Se o cliente usar um navegador da Internet, o navegador também precisará ser mantido atual. Uma lista de plataformas com suporte pode ser encontrada em [obter clientes para o Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Os firewalls do lado do cliente podem afetar a qualidade das chamadas e até mesmo impedir que uma chamada seja estabelecida. Depois que as exclusões apropriadas no firewall do cliente foram configuradas, elas precisam ser mantidas atualizadas com base nas informações nas [URLs e nos intervalos de endereços IP do Office 365](https://aka.ms/o365ips). Seu fornecedor de terceiros terá orientação específica sobre como atualizar as exclusões.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Os drivers de Wi-Fi podem ser problemáticos. Como exemplo, um driver pode ter comportamentos de roaming muito agressivos entre pontos de acesso que podem induzir comutação de ponto de acesso desnecessária, que leva a uma qualidade de chamada ruim. Um driver de Wi-Fi com mau desempenho pode ser descoberto por meio de uma análise da qualidade da experiência (consulte [melhorar e monitorar a qualidade da chamada para o Microsoft Teams](monitor-call-quality-qos.md) para obter mais detalhes). É essencial implementar um processo orientado por qualidade que monitora novos drivers Wi-Fi e garante que eles sejam testados antes de serem implantados na população geral do usuário.

### <a name="endpoint-management"></a>Gerenciamento de ponto de extremidade

Um catálogo de pontos de extremidade compatíveis e dispositivos de interface (como fones de ouvido com microfone) devem estar disponíveis e mantidos. Este catálogo incluirá uma lista de dispositivos aprovados que foram selecionados e validados como parte das fases do enVision e da diretoria. Geralmente, dispositivos específicos são selecionados para cada tipo de pessoa em sua organização para atender às necessidades dos atributos da pessoa. Todos os pontos de extremidade têm um ciclo de vida, e você precisa gerenciar as políticas de contratos de fornecedor, garantia, substituição, distribuição e reparo associadas a esses dispositivos.

### <a name="endpoint-troubleshooting"></a>Solução de problemas de ponto de extremidade

Mesmo que você tenha seguido a orientação anterior, os usuários da sua organização ainda podem ter problemas com o Microsoft Teams. Embora o problema não seja com o ponto de extremidade propriamente dito, os sintomas do problema são normalmente exibidos pelo cliente para o usuário. A orientação a seguir destina-se a fornecer etapas gerais que você pode tomar para resolver o problema; Não se destina a ser um guia de solução de problemas abrangente. As etapas são fornecidas em uma ordem específica, mas não precisam ser seguidas explicitamente e podem não ser aplicáveis, dependendo da natureza do problema.

1. **Validar a integridade do serviço:** O problema que um usuário pode estar enfrentando pode estar relacionado a um evento que afeta negativamente o serviço do teams ou seus serviços dependentes. Como primeiro passo, recomendamos que você confirme que não há problemas de serviço ativos. Consulte [como verificar a integridade do serviço do Microsoft 365](https://docs.microsoft.com/office365/enterprise/view-service-health). Lembre-se de verificar o status dos serviços dependentes (por exemplo, Exchange, SharePoint, OneDrive for Business). O monitoramento da integridade do serviço é discutido mais detalhadamente na seção anterior, [monitorar a integridade do serviço](#monitor-service-health).

2. **Validar a conectividade do cliente:** Problemas de conectividade causam funcionalidades ou problemas de entrada no Teams. Recomendamos (especialmente para novos sites ou locais) que você valida a conectividade com o serviço. Verifique se as seguintes [URLs do Office 365 e diretrizes de intervalos de endereços IP](https://aka.ms/o365ips) são seguidas para cada site. Você pode aproveitar a [ferramenta de avaliação de rede da Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para executar um teste de conectividade para validar que as portas de mídia foram abertas corretamente para recursos do teams. As etapas detalhadas sobre como executar os testes de conectividade são fornecidas na orientação de [preparação de rede](prepare-network.md) .

3. **Verifique a lista de problemas conhecidos:** Consulte [solução de problemas do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) para determinar se o usuário foi afetado negativamente por um desses problemas. Siga a solução alternativa fornecida (se houver uma) para resolver o problema.

4. **Acesse a Comunidade do Microsoft Teams:** A [comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) oferece espaços dedicados para equipes. A comunidade de equipes fornece uma lista de discussão, Postagens de blog e anúncios centralizados em relação ao Teams. Você pode postar uma pergunta ou Pesquisar discussões anteriores sobre soluções para o seu problema.

5. **Entre em contato com o suporte da Microsoft:** Você pode entrar em contato com o suporte da Microsoft para obter problemas com o Teams online ou por telefone. Para obter informações, consulte [contatar o suporte para produtos empresariais-ajuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). Para clientes Premier, as solicitações de suporte podem ser iniciadas seguindo-se a orientação em [contatar o suporte para o Microsoft Teams (clientes Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/necessárias

| Atividade | Descrição | Cadência | Equipe designada |
|---|---|---|---|
| Requisitos de ponto de extremidade | Certifique-se de que o ponto de extremidade do teams continua a atender a todos os requisitos de software para as equipes listadas em [obter clientes para Microsoft Teams](get-clients.md). | Mensal | |
| Firewalls de ponto de extremidade | Mantenha as exclusões apropriadas no firewall da empresa com base nas informações nas [URLs e nos intervalos de endereços IP do Office 365](https://aka.ms/o365ips). Seu fornecedor de terceiros terá orientação específica para manter as exclusões. Assine o [RSS feed](https://support.office.com/o365ip/rss) para ser notificado automaticamente sobre as alterações. | Conforme necessário | |
| Drivers de Wi-Fi | Testar e atualizar drivers Wi-Fi no PC. Valide os resultados usando CQD ([melhore e monitore a qualidade das chamadas para o Teams](monitor-call-quality-qos.md)). | Conforme necessário | |
| Gerenciamento de ponto de extremidade | Mantenha o catálogo de pontos de extremidade compatíveis e dispositivos de interface (como fones de ouvido com microfone). Gerenciar contratos de fornecedor, garantia, distribuição, substituição e políticas de reparo. | Mensal | |
| Solução de problemas de ponto de extremidade | As tarefas de solução de problemas podem incluir verificação de conectividade, consultoria na lista de problemas conhecidos, coleta de registros, análise e escalonamento ao suporte da Microsoft ou a outros fornecedores. | Conforme necessário | |

### <a name="references"></a>Referências

[URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips)

[Obter clientes para o Microsoft Teams](get-clients.md)

[Comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Entre em contato com o suporte para produtos para empresas - ajuda para administradores](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Contatar o suporte Premier](https://support.microsoft.com/premier/contacts)

[Vídeo para solução de problemas de equipe](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gerenciar o Teams

Após a implantação do Microsoft Teams Service, você precisará realizar várias atividades relacionadas à administração. As atividades vão desde a administração do serviço e dos usuários individuais até o planejamento de capacidade e o provisionamento de licenciamento e números de telefone. As seções a seguir abordam algumas dessas tarefas comuns de administração.

### <a name="service-administration"></a>Administração de serviços

O serviço Teams tem várias configurações que podem ser configuradas em todo o locatário.
As alterações feitas nas configurações do locatário afetam todos os usuários que foram habilitados para o Teams. Para obter uma lista detalhada dessas configurações, consulte [gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md).

### <a name="user-administration"></a>Administração de usuários

Para dar suporte a usuários, uma organização pode exigir qualquer número de tarefas relacionadas — as tarefas específicas variam de uma organização para a outra. Em última análise, essas tarefas precisam ser gerenciadas por uma equipe de suporte que tenha atribuído essas obrigações operacionais. As tarefas a seguir são comumente necessárias para dar suporte a usuários no Teams.

#### <a name="general-tasks"></a>Tarefas gerais

[Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Criação da equipe (opcional)

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Microsoft 365 e, portanto, uma equipe no Microsoft Teams. Se quiser ter um controle mais rígido e [restringir a criação de novas equipes](assign-roles-permissions.md#permissions-to-create-teams) (e, portanto, a criação de novos grupos do Microsoft 365), você pode delegar direitos de criação e gerenciamento de grupos a um conjunto de administradores. Se a sua organização quiser buscar essa opção, consulte o processo descrito neste artigo para permitir que os usuários enviem solicitações que são processadas por uma equipe atribuída.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/necessárias

| Atividade | Descrição | Cadência | Equipe designada |
|---|---|---|---|
| Administração de serviços | Administração de configurações de equipes de todo o locatário. | Conforme necessário | |
| Administração de usuários | Administração de configurações baseadas no usuário e licenciamento no Microsoft Teams. | Conforme necessário | |
| Gerenciamento de licenças | Planeje as necessidades atuais e futuras para licenciamento baseado em usuário e consumo (planos de chamada e créditos de comunicação), aproveitando o [relatório de uso PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e o relatório de [grupos de minutos PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Semanal | |
| Gerenciamento de número de telefone | Gerencie os números de telefone disponíveis para futuros crescimentos e ajuste os níveis de estoque para atender às suas necessidades organizacionais. | Semanal | |
| Criação da equipe (opcional) | Revisar e processar solicitações de criação da equipe. | Conforme necessário | |

<!--ENDOFSECTION-->
