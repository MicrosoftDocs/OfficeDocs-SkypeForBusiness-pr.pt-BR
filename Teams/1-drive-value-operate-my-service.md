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
description: Tarefas e atividades necessárias para o gerenciamento de serviços do Teams, incluindo monitoramento da saúde do serviço e avaliação e garantia de qualidade e uso da rede.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5684ad62107fa61af7c9f2f22c6f15b4bfe1da30
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112647"
---
# <a name="operate-my-service"></a>Operar meu serviço

Este artigo fornece uma visão geral dos requisitos para operar com êxito os serviços de voz na nuvem para sua organização. Ao operar corretamente seus serviços de voz na nuvem, você pode ter certeza de que está fornecendo uma experiência confiável e de alta qualidade para sua organização.

## <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações

O Guia de Operações fornece uma visão geral de todas as tarefas e atividades necessárias como parte da função de gerenciamento de serviço do Microsoft Teams.

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O serviço do Teams abrange o Microsoft 365 ou Office 365 e os componentes de infraestrutura implantados no local (por exemplo, rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Você pode já ter implementado processos e tarefas associados aos serviços existentes. Dito isso, você provavelmente pode aumentar seus processos atuais ao planejar o gerenciamento de serviços hoje para dar suporte ao Teams no futuro.

O gerenciamento de serviços abrange todas as atividades e processos envolvidos no gerenciamento do Teams de ponta a ponta. Como já foi dito anteriormente, alguns componentes do gerenciamento de serviços, a infraestrutura que o serviço do Microsoft 365 ou do Office 365 em si compreende, são de responsabilidade da Microsoft, enquanto você, o cliente, é responsável pelos usuários para gerenciar os vários aspectos do Teams, da rede e dos pontos de extremidade que você fornece.

As tarefas e atividades neste guia são agrupadas em oito categorias, conforme descrito no diagrama a seguir. Cada uma dessas categorias será expandida nas seções a seguir.

![Um diagrama que representa uma lista de categorias de tarefas e atividades](media/operate-my-service-image1.png "Um diagrama que representa uma lista de categorias de tarefas e atividades que o gerenciamento de serviços do Teams compreende. O diagrama também mostra que o gerenciamento de serviços é em grande parte uma tarefa do cliente.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida como as operações serão implementadas para o Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Revise o Guia de Operações na íntegra.</li><li>Implemente uma estratégia de operações que se alinhe com as metas da sua organização para oferecer a qualidade e a confiabilidade das cargas de trabalho de voz na nuvem.</li><li>Analisar [a qualidade da chamada do Monitor.](monitor-call-quality-qos.md)</li><li> Implemente uma estratégia de operações para executar regularmente Avaliações de Qualidade da Experiência para garantir que sua implantação de voz na nuvem está operando em seus recursos de pico.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mapeamento de funções operacionais

O planejamento que você realizou para operações durante a fase Envision é fundamental, pois as atividades de operações começam quando os primeiros usuários piloto estão habilitados. Este guia lista as atividades e tarefas que devem ser executadas diariamente, semanalmente, mensalmente ou conforme necessário para manter uma implantação do Teams de alta qualidade. Este guia fornece conhecimento e orientações sobre como executar essas atividades e tarefas críticas.

Um componente essencial de uma implantação bem-sucedida é garantir que o planejamento que você faça no início da fase Envision inclua determinar quem será responsável pela execução de atividades específicas. Depois que você descobrir quais tarefas e atividades se aplicam à sua implantação, elas precisam ser compreendidas e seguidas pelos grupos ou indivíduos que você atribui a eles.

Cada equipe identificada deve revisar e concordar com as tarefas e responsabilidades identificadas e iniciar a preparação. Isso pode incluir treinamento e preparação, fornecer atualizações para o plano de equipe ou garantir que os provedores externos estão prontos para entrega.

As atividades e funções definidas neste guia devem ser válidas na maioria dos cenários, mas cada implantação do Teams é exclusiva; portanto, você pode usar este guia como ponto de partida para personalizar as atividades e funções padrão para atender às suas necessidades.

Certifique-se de que cada equipe responsável tenha uma boa compreensão das atividades necessárias para executar o serviço. É fundamental que cada equipe aceite e desacate sua responsabilidade em sua organização antes do primeiro piloto começar.

Depois que um contrato for realizado, as equipes correspondentes devem começar a operacionalizar suas funções.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td>
<td><ul><li>Use este documento para facilitar o exercício de mapeamento de função operacional.</li><li>Reunir-se com as respectivas equipes de suporte para atribuir nomes a cada item na lista de atividades necessárias.</li><li>Obtenha aceitação ou aprovação nas funções atribuídas.</li><li>Certifique-se de que as equipes correspondentes tenham o treinamento, preparação e recursos apropriados para concluir as atividades necessárias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependências de serviço do Teams

O Microsoft Teams reúne tecnologias no Microsoft 365 ou Office 365 para fornecer um hub para o trabalho em equipe. Exemplos incluem:

-   O Azure Active Directory (Azure AD) fornece serviços de autenticação e autorização para o Teams.

-   O Exchange Online fornece recursos avançados, como ressalção legal e descoberta virtual.

-   O SharePoint Online oferece a capacidade de compartilhar arquivos em canais, e o OneDrive for Business fornece um mecanismo de compartilhamento de arquivos em um chat privado.

As organizações também podem aproveitar os investimentos existentes na infraestrutura local. Por exemplo, contas do Active Directory locais existentes podem ser usadas para autenticação aproveitando o Azure AD Connect. Determinadas versões Exchange Server podem ser usadas no lugar do Exchange Online.

Essas tecnologias se reúnem para fornecer um pacote de comunicações avançada, colaborativa e inteligente para os usuários. Essa integração forte é um benefício fundamental do Teams, mas também gera um requisito para o gerenciamento de serviços nessas tecnologias.

Este guia aborda as principais áreas de foco para gerenciar o serviço do Teams. O mais provável é que você tenha planos de gerenciamento de serviço para as tecnologias de suporte das que o Teams depende. Caso não seja, você precisará estabelecer planos de gerenciamento de serviços adequados para esses componentes de tecnologia (no local e online) também. Isso ajudará a garantir que seus usuários desfrutem de uma experiência confiável e de alta qualidade com o Teams.

#### <a name="references"></a>Referências 

[Visão geral do Microsoft Teams](teams-overview.md)

[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md)

[Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md)

[Coexistência e interoperabilidade do Microsoft Teams e skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Atividades do Guia de Operações

As seções a seguir dão uma visão geral das atividades necessárias para operar com êxito o serviço do Microsoft Teams. Eles incluem referência a ferramentas, informações contextuais e conteúdo adicional para ajudá-lo a entender a atividade e a ajudar em iniciativas de preparação.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorar a saúde do serviço

É importante que você entenda a saúde geral do serviço microsoft teams para que você possa alertar proativamente outras pessoas em sua organização de qualquer evento que afete o serviço. Conforme descrito anteriormente, o Teams depende de outros serviços do Microsoft 365 ou do Office 365, como o Azure Active Directory, o Exchange Online, o SharePoint Online e o OneDrive for Business. Por isso, é igualmente importante que você monitore a saúde dos serviços dependentes.

Incorpore essa atividade ao seu processo de gerenciamento de incidentes para informar proativamente os usuários, o helpdesk e suas equipes de operações para se prepararem para lidar com escalonamentos de usuários.

As seções a seguir descrevem as ferramentas que você pode aproveitar para monitorar [incidentes de serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) que afetam o serviço do Teams. Um resumo dos benefícios de cada ferramenta e quando você deve usar cada um deles está incluído na tabela a seguir.

| Ferramenta de Monitoramento                       | Benefícios                                            | Quando usar                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Centro de administração do Microsoft 365                     | Disponível em qualquer dispositivo com um navegador com suporte. | Use quando não precisar de notificações em tempo real.                                          |
| Aplicativo de administração do Microsoft 365 ou Office 365                  | Fornece notificações por push para seu dispositivo móvel.  | Use quando precisar ser notificado de incidentes de serviço enquanto estiver em uso.                  |
| Microsoft System Center               | Integração com o Microsoft System Center.           | Use quando precisar de recursos avançados de monitoramento e suporte de notificação.                       |
| API de Comunicações de Serviço do Microsoft 365 ou Office 365 | Acesso programático à saúde do serviço do Microsoft 365 ou office 365.   | Use quando precisar de integração com uma ferramenta de monitoramento de terceiros ou quiser criar sua própria solução. |

> [!NOTE]
> Somente indivíduos que têm a função de administrador **global** ou administrador **de** serviço podem exibir a saúde do serviço.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Monitoramento com o centro de administração do Microsoft 365

O Centro de administração do [Microsoft 365](https://portal.office.com/) fornece um painel de [Saúde](https://portal.office.com/adminportal/home#/servicehealth) do Serviço onde você pode exibir a saúde atual do serviço do Teams, além dos serviços dependentes.

### <a name="monitoring-with-the-mobile-app"></a>Monitoramento com o aplicativo móvel

O aplicativo de administração do Microsoft 365 ou Do Office 365 está disponível no Apple iOS, Android e Windows (pc e celular). O aplicativo fornece informações aos administradores de serviços sobre a saúde do serviço e as alterações futuras. O aplicativo dá suporte a notificações por push que podem alertá-lo quase imediatamente após a postagem de um aviso. Isso ajuda você a se manter atualizado sobre o status, a saúde e quaisquer alterações futuras no serviço. O suporte à notificação a torna a ferramenta de monitoramento recomendada para administradores. Para obter mais informações, consulte:

[Aplicativo Móvel de Administrador do Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Baixar o Aplicativo Móvel de Administrador do Office 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitoramento com o Microsoft System Center

O Microsoft System Center é uma plataforma de gerenciamento integrada que ajuda você a gerenciar datacenter, dispositivos cliente e ambientes de TI de nuvem híbrida. Os administradores do Office 365 que usam o System Center agora têm a opção de importar o Pacote de Gerenciamento do Office 365, o que lhes permite exibir todas as comunicações de serviço no Operations Manager no System Center. Usar essa ferramenta oferece acesso ao status de seus serviços inscritos, incidentes de serviço ativos e resolvidos e suas comunicações da Central de Mensagens (alterações futuras). Para obter mais informações, consulte a seguinte [postagem de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Se você aproveitar o System Center para monitorar a saúde do serviço do Teams (e os serviços dependentes), você poderá personalizar ainda mais o pacote de gerenciamento para alertar ou notificar grupos ou indivíduos específicos que foram identificados para reagir a incidentes.
Esses grupos podem incluir proprietários de serviços, auxiliares, grupos de suporte de segundo e terceiro nível e gerentes de incidentes em sua organização.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoramento de cenários avançados

Você pode monitorar a saúde do serviço e as alterações futuras aproveitando a API de Comunicações de Serviço do Office 365 para acessar a saúde do serviço do Office 365 e as alterações programaticamente. Use essa API para criar sua própria ferramenta de monitoramento ou conectar suas ferramentas de monitoramento existentes às comunicações de serviço do Office 365, simplificando potencialmente a maneira como você monitora seu ambiente. Para obter mais informações, consulte [Office 365 for Enterprise developers](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade               | Descrição                                                                                                                                                                                                               | Cadência   | Equipe atribuída |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorar a saúde do serviço | Monitore proativamente a saúde do serviço do Microsoft Teams(e os serviços dependentes) usando as ferramentas disponíveis. Os serviços dependentes incluem: Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory. | Em tempo real |               |
| Notificação de incidentes  | Notifique os participantes internos dos eventos que afetam o serviço do Teams. Os participantes internos podem incluir usuários, auxiliares e gerentes de incidentes.                                                                          | Conforme necessário |               |

### <a name="references"></a>Referências 

[Como verificar a saúde do serviço do Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Continuidade e Saúde do Serviço](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gerenciar alterações organizacionais

O Microsoft Teams é um serviço baseado em nuvem. Com isso, vem a capacidade de fornecer novos recursos e funcionalidades em um ritmo rápido. A entrega da inovação contínua fornece um benefício óbvio para as organizações, mas essas alterações precisam ser gerenciadas adequadamente em sua organização para evitar a resistência do usuário ou as escalonamentos para o seu helpdesk.

As atualizações do Teams são roladas automaticamente para seus usuários. Seus usuários sempre terão o cliente mais recente e os recursos disponíveis no serviço do Teams. Não é possível gerenciar a adoção de atualizações do Teams para seus usuários, portanto, é fundamentalmente importante gerenciar as alterações por meio de programas eficazes de comunicação, treinamento e adoção. Se os usuários estão cientes da mudança, instruídos sobre os benefícios e capacitados a aproveitar os novos recursos, eles poderão se adaptar mais rapidamente e receber a &mdash; mudança.

### <a name="monitoring-for-change"></a>Monitoramento de alterações

A primeira etapa no gerenciamento de alterações é monitorar as alterações planejadas para o Teams. A melhor fonte para monitorar essas alterações é o Roteiro do [Office 365](https://products.office.com/business/office-365-roadmap), que lista os recursos que estão em desenvolvimento no momento, que estão sendo lançados para os clientes ou que foram totalmente lançados. Você pode pesquisar recursos específicos do Teams usando o filtro fornecido ou pode baixar o roteiro para um arquivo do Excel para análise mais detalhada. Para cada recurso, o roteiro fornece uma breve descrição, juntamente com a data de lançamento antecipada.

No blog [do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), você pode aprender sobre práticas recomendadas, tendências e notícias sobre atualizações de produtos do Teams. Espere encontrar atualizações de recursos principais para o Teams a serem anunciadas aqui. Você também pode se inscrever no blog por meio de um feed RSS. Em seguida, você pode [adicionar o RSS feed diretamente](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) em um canal do Teams, portanto, todas as notícias importantes são entregues diretamente dentro do Teams.

Todos os recursos lançados estão documentados nas [Notas de Versão do Microsoft Teams.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
Aqui você encontrará uma lista de recursos que foram lançados para desktop, web e dispositivos móveis. O mesmo conjunto de notas de versão também está disponível na guia **Novidades** em [Ajuda](get-help-in-microsoft-teams.md).

Familiarizar-se com os recursos disponíveis e garantir que você atribua proprietários aplicáveis para monitorar a alteração.

### <a name="planning-for-change"></a>Planejamento de alterações

Agora que você está ciente das próximas alterações no serviço do Teams, a próxima etapa é preparar e planejar de acordo. Avalie cada alteração para determinar quais alterações exigem comunicação com os usuários, campanhas de conscientização, treinamento para equipes de suporte ou usuários ou campanhas de avaliação e adoção de recursos. Essa é a função principal de uma equipe de gerenciamento de alterações em sua organização. Abaixo está uma coleção de tabelas de exemplo que podem ajudá-lo a planejar as alterações.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Recurso: Gravação na Nuvem (Data de lançamento: janeiro de 2018)

**Faixa geral**

| Preparação para alterações | Status   | Observações/próximas etapas | Proprietário |
|----|----|----|-----|
| Revisão jurídica   | Concluído     | Esse recurso é um pré-requisito para a integração da equipe de treinamento. | Equipe do Project  |

**Gerenciamento de alterações técnicas**

|       Preparação para alterações       | Status |                      Observações/próximas etapas                      |    Proprietário     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Alterações de IT necessárias      |  Sim   | O administrador precisa habilitar a gravação somente para usuários identificados. | Equipe de suporte |
| Preparação técnica concluída |  Sim   |                                                            | Equipe de suporte |
|                              |        |                                                            |              |

**Gerenciamento de alterações do usuário** 

| Preparação para alterações | Status   | Observações/próximas etapas | Proprietário |
|----|----|----|-----|
| Impacto do usuário                  | Baixo                  |                                                                 |                        |
| Preparação do usuário necessária      | Sim                  |                                                                 |                        |
| Comunicações prontas         | Não                   | O email de comunicação foi redigido— revisão pendente.            | Equipe de Comunicações    |
| Treinamento pronto               | Sim                  | O treinamento aproveitará o vídeo existente da Microsoft.                | Equipe de Treinamento          |

**Faixa de status**

| Preparação para alterações | Status   | Observações/próximas etapas | Proprietário |
|----|----|----|-----|
| Status da versão               | em andamento          | Revisão pendente pelo patrocinador executivo.               | Equipe de Gerenciamento de Alterações |
| Liberação de saída             |                      |                                                                 |                        |
| Data de lançamento                 |                      |                                                                 |                        |

Para obter mais informações sobre como planejar o gerenciamento de alterações com o Teams, consulte [Create a change management strategy for Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade               | Descrição                                                                                                                                                                                                                | Cadência   | Equipe atribuída |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorar alterações     | Monitore as próximas alterações no serviço do Microsoft Teams.                                                                                                                                                                   | Diário     |               |
| Planejamento de alterações    | Avalie e planeje novos recursos e recursos, incluindo planos de comunicação, campanhas de conscientização e treinamento.                                                                                                     | Conforme necessário |               |
| Preparação do usuário             | Realize campanhas de comunicação, conscientização ou treinamento direcionadas para garantir que os usuários estão prontos para as próximas alterações.                                                                                                        | Conforme necessário |               |
| Dar suporte à preparação da equipe | Realize campanhas de comunicação, reconhecimento ou treinamento direcionadas para garantir que a equipe de suporte esteja pronta. As equipes de suporte podem incluir a equipe "white glove", helpdesks, suporte de Camada 2 ou Camada 3, parceiros externos e assim por diante. | Conforme necessário |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Avaliar o uso do Teams

Após o início do piloto inicial, é fundamental estabelecer uma cadência regular para medir o uso real do Teams. Isso permite que sua organização obtenha informações sobre como o uso real se alinha com o uso previsto durante a fase Envision. Embora esta seção se concentre no uso do Teams, isso deve fazer parte de um esforço mais amplo para medir e avaliar o uso geral do Office 365.

Analisar o uso com frequência no início da implantação oferece a você a oportunidade de:

-   Valide se os usuários estão usando o Teams.

-   Identifique possíveis desafios de adoção antes de criar problemas críticos em toda a organização.

-   Entenda se há discrepâncias entre os requisitos da fase Envision e o uso real.

Se o uso não for o que você espera, isso pode ser devido a um problema de implantação, ou o plano de adoção não está sendo executado corretamente ou algum outro problema. Dependendo do motivo real por trás do baixo uso, o administrador do serviço deve colaborar com as equipes relacionadas para ajudar a remover barreiras de uso.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Medir o uso com o centro de administração do Microsoft 365

Os dados de uso do Teams estão disponíveis no painel Relatórios. Os dados de uso do Teams podem ser encontrados em três relatórios diferentes. O primeiro relatório fornece uma visão entre produtos de como os usuários se comunicam e colaboram usando os vários serviços no Office 365. Este relatório pode ser encontrado aqui: Relatório de usuários ativos do [Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Os outros dois relatórios são específicos do Teams e fornecem mais detalhes sobre o uso do Teams de uma perspectiva de usuário e dispositivo. Os dois relatórios podem ser encontrados aqui:

[Relatório de uso de dispositivos do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Relatório de atividades do usuário do Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permissões necessárias

Os relatórios de uso no centro de administração podem ser acessados por pessoas que tenham sido atribuídas a uma função de administrador **global** ou uma função de administrador específica do produto ( administrador do **Exchange,** administrador do **Skype for Business,** administrador **do SharePoint**).

Além disso, a **função** de leitor relatórios está disponível para usuários que exigem acesso aos relatórios, mas não executam tarefas que exigem permissões no nível do administrador. Você atribui essa função para fornecer relatórios de uso a qualquer pessoa que seja um stakeholder, para monitorar e impulsionar a adoção. Para obter mais informações sobre as diferentes funções disponíveis, consulte [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Avaliando o uso

Depois de usar o painel Relatórios para medir o uso, é importante comparar o uso medido com os KSIs (indicadores de sucesso principais) que você definiu durante a fase de Envision do projeto. Você pode definir um KSI que pode ser definido como uso ativo ou um que esteja indiretamente vinculado ao uso ativo.

É importante identificar quaisquer variações entre o uso real e o planejado antes de retomar a aplicação para sites ou usuários adicionais. Você provavelmente identificará os aprendizados organizacionais como parte dessa atividade que você pode aproveitar para garantir que o próximo lote de sites ou usuários não tenha os mesmos problemas.

Primeiro, identifique se isso é uma adoção ou um problema técnico. Comece investigando os itens abaixo, para determinar onde o problema está.

1.  Valide a qualidade executando uma Análise de Qualidade da Experiência (consulte [Improve and monitor call quality for Teams para](monitor-call-quality-qos.md) obter mais detalhes).

2.  Trabalhe com a equipe de assistência técnica para verificar se não há problemas técnicos que impeçam os usuários de acessar ou usar o serviço. Se as tendências de [](#endpoint-troubleshooting) problemas existirem, use a seção solução de problemas do ponto de extremidade posteriormente neste artigo para tentar resolver o problema antes de envolver o suporte.

3.  Trabalhe com a equipe de treinamento e adoção para coletar comentários diretos dos usuários (consulte [Avaliar](#assess-user-sentiment) o sentimento do usuário posteriormente neste artigo) e verificar a eficácia das atividades de conscientização e adoção.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade                         | Descrição                                                                                                                      | Cadência   | Equipe atribuída |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Medir o uso (fase de habilitação) | Mede e avalie o uso do Teams à medida que os sites continuam a ser integrados durante a fase de habilitação. Resolver problemas de uso conforme necessário. | Semanal    |               |
| Medir o uso (fase do valor da unidade)                           | Medir e avaliar o uso do Teams na fase Valor da Unidade (após a conclusão da implantação). Resolver problemas de uso conforme necessário. | Quinzenalmente  |               |
| Atualizar plano de adoção             | Atualize seu plano de adoção com base em como o uso medido se compara às suas metas de planejamento.                                         | Conforme necessário |               |

### <a name="references"></a>Referências 

[Sobre o Centro de administração do Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Relatórios de atividades no centro de administração do Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Avaliar o sentimento do usuário

Noções básicas sobre o sentimento do usuário podem atuar como um indicador-chave para a análise do sucesso da implantação do Teams. Os comentários do usuário podem impulsionar alterações em sua organização; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos seus usuários.

É importante receber comentários cedo e continuar avaliando o sentimento do usuário durante todo o ciclo de vida do projeto e além. Use as seguintes diretrizes para determinar o intervalo no qual sua organização procurará comentários:

-   **Início do projeto**: Ao avaliar o sentimento do usuário no início do projeto, você pode obter uma visão inicial sobre como seus usuários se sentem sobre a experiência do Teams.

-   **Após etapas principais:** coletando comentários em todo o ciclo de vida do projeto, você pode medir o sentimento do usuário de forma contínua e fazer alterações conforme necessário. Isso é especialmente útil após etapas importantes.

-   **Conclusão do** projeto : Avaliar o sentimento do usuário no final de um projeto dirá o quanto você fez bem e onde o trabalho ainda precisa ser feito e permitirá que você compare os resultados com a pesquisa anterior.

-   **Em andamento:** continue a medir o sentimento do usuário indefinidamente. As alterações no sentimento do usuário podem ser devido a alterações no ambiente da sua organização ou alterações no serviço do Teams. Ao usar o sentimento do usuário em intervalos regulares, você pode entender o desempenho das equipes de gerenciamento de serviços e como sua organização está respondendo às alterações no serviço do Teams.

O sentimento do usuário pode ser avaliado por meio de vários métodos diferentes. Eles podem incluir pesquisas de email, entrevistas no estilo de telefone ou pessoalmente ou simplesmente criar um canal de comentários no Teams ou no Yammer. Para obter mais informações, consulte [Práticas recomendadas para métodos de comentários do](best-practices-feedback.md)usuário no Microsoft Teams .

Você também pode usar uma abordagem em todo o setor para avaliar o sentimento do usuário chamado NPS (net promotor score), que é descrito na seção a seguir.

### <a name="nps"></a>NPS 

O NPS (Net promoter score) é uma métrica de fidelidade do cliente em todo o setor e uma boa abordagem a ser usada para avaliar o sentimento do usuário. O NPS pode ser calculado fazendo duas perguntas: "Qual é a probabilidade de você recomendar o Teams a um colega?", seguido da pergunta de forma livre, "Por quê?"

NPS é um índice, que varia de –100 a 100, que mede a disposição de um cliente para recomendar o produto ou serviço de uma empresa. O NPS baseia-se em uma pesquisa anônima que é entregue aos usuários por email ou outros meios eletrônicos. NPS mede a fidelidade entre um provedor e um consumidor. Ele consiste em apenas uma pergunta, que pede aos usuários para taxar sua experiência de 1 a 10, com a opção de fornecer comentários adicionais. Os usuários são classificados com base nas seguintes classificações:

-   9 ou 10 são Promoters: entusiastas idados que promoverão seu serviço e alimentarão outras pessoas.

-   7 ou 8 são Passivos: satisfeitos, mas não entusiastas, vulneráveis a outro serviço ou oferta.

-   De 1 a 6 são Detratores: Clientes insatisfeitos que podem danificar seu serviço e impedir o crescimento.

![Um diagrama que demonstra a escala NPS](media/operate-my-service-image2.png "Este diagrama demonstra a escala NPS. Ele mostra que as classificações de 0 a 6 são destrators, 7 a 8 são passivas e 9 a 10 são promotores.")

Embora o número NPS base seja útil, você obterá o maior valor analisando comentários do usuário. Eles ajudarão você a entender por que o usuário recomendaria (ou não) o Teams para outras pessoas. Esses comentários podem fornecer comentários valiosos para ajudar as equipes de gerenciamento do projeto ou do serviço a entender os ajustes necessários para fornecer um serviço de qualidade.

Para fornecer pesquisas NPS à sua organização, você pode aproveitar sua ferramenta de pesquisa online favorita.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade              | Descrição                                                                                                                                                                         | Cadência   | Equipe atribuída |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Avaliar o sentimento do usuário | Capture e avalie o sentimento do usuário usando pesquisas ou entrevistas ou por meio de um canal de comentários no Teams ou no Yammer.                                                                 | Conforme necessário |               |
| Atualizar planos de adoção | Impulsionar a alteração em sua organização com base nos comentários do usuário; isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou a maneira como você oferece suporte aos seus usuários. | Conforme necessário |               |

### <a name="references"></a>Referências 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Usar o Yammer para coletar comentários](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Práticas recomendadas para comentários do usuário](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gerenciar a qualidade da rede

Muitos elementos de planejamento principais vão para otimizar, remediar e remediar sua infraestrutura de rede para garantir um caminho eficiente e de alta qualidade para o serviço do Microsoft Teams. As tarefas de planejamento e os requisitos são abordados em nossas [diretrizes de preparação de](3-envision-evaluate-my-environment.md#network-readiness) rede. As redes geralmente evoluem ao longo do tempo devido a atualizações, expansão ou outros requisitos de negócios. É importante que você contabilmente seus requisitos para o Teams em suas atividades de planejamento de rede.

Embora o planejamento de rede seja um aspecto crítico de uma implantação do Teams, é igualmente importante garantir que a rede permaneça saudável e permaneça atual, com base na alteração dos requisitos técnicos ou comerciais.

Para garantir a saúde da sua rede, várias atividades de operações precisam ser executadas em intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade                                                       | Descrição                                                                                                                                                                                                                                                                                                                                                                 | Cadência                | Equipe atribuída |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Monitorar IPs e URLs do Office 365                                | Monitore quaisquer alterações nas URLs e intervalos de endereços IP do [Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) usando o [feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fornecido e inicie uma solicitação de alteração para grupos de rede aplicáveis.                                                                                                                                | Diário                  |               |
| Atualizar a rede com base em alterações nos IPs e URLs do Office 365 | Faça atualizações para os componentes de rede aplicáveis (firewalls, servidores proxy, VPNs, firewalls do lado do cliente e assim por diante) para refletir alterações nas URLs e intervalos de endereços IP do [Office 365.](/microsoft-365/enterprise/urls-and-ip-address-ranges)                                                                                                                                                              | Conforme necessário              |               |
| Fornecer dados de construção                                          | Forneça informações atualizadas de sub-rede para o defensor da qualidade (ou partes interessadas relevantes) para garantir que as definições de construção no [CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sejam mantidas atualizadas. | Conforme necessário              |               |
| Implementar alterações                                               | Implemente alterações na rede para dar suporte à alteração dos requisitos técnicos e comerciais do Teams. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Redes com fio e Wi-Fi com fio</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul>     | Conforme necessário              |               |
| Monitoramento e relatórios de rede                               | Monitore a rede de ponta a ponta para ver as tendências de disponibilidade, utilização e capacidade usando as ferramentas de gerenciamento de rede de terceiros existentes e os recursos de relatório disponíveis em seus provedores de rede. Use dados de tendência para planejamento de capacidade de rede.                                                                                                            | Diário, semanal, mensal |               |
| Planejamento de capacidade                                              | Colabore com os proprietários de serviços do Teams para entender a alteração dos requisitos técnicos e comerciais que podem impulsionar alterações adicionais de capacidade.                                | Conforme necessário              |               |
| Solução de problemas e correção de rede                        | Ajude os auxiliares do Teams, os proprietários do serviço e os principais participantes a solucionar e solucionar problemas relacionados à conectividade, confiabilidade ou qualidade do Teams. Os elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Redes com fio e Wi-Fi com fio</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul>    | Conforme necessário              |               |
| Teste de alta disponibilidade e recuperação de desastres                | Execute testes regulares de alta disponibilidade e recuperação de desastres na infraestrutura de rede para garantir que atenda aos objetivos de nível de serviço (SLOs) ou contratos de nível de serviço (SLAs) para o serviço do Teams.                                                                                                                                                  | Mensal                |               |


### <a name="references"></a>Referências 

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Criar esquema de dados](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Avaliar e garantir a qualidade 

Todas as organizações precisam de um grupo ou indivíduo para serem responsáveis pela qualidade. Essa é a função mais importante do gerenciamento do serviço. A função Defensor da Qualidade é atribuída a uma pessoa ou grupo que é apaixonado pela experiência de seus usuários.
Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções. O melhor candidato para o posto de defensor da qualidade costuma ser o proprietário do serviço do cliente. Dependendo do tamanho e da complexidade da organização, pode ser qualquer pessoa ou grupo com uma paixão por garantir uma experiência de usuário de alta qualidade.

O defensor da qualidade aproveita ferramentas e processos documentados existentes, como o Painel de Qualidade de Chamada (CQD), para monitorar a experiência do usuário, identificar tendências de qualidade e conduzir a correção quando necessário.
O defensor da qualidade deve trabalhar com as respectivas equipes para conduzir ações de correção e relatar a um comitê de direção sobre o progresso e quaisquer problemas abertos.

Leia [Melhorar e monitorar](monitor-call-quality-qos.md)a qualidade das chamada para o Teams , que descreve inclui atividades que avaliam e fornecem orientações de correção em áreas-chave que têm o maior impacto na melhoria da experiência do usuário. As diretrizes fornecidas neste artigo se concentram no uso do CQD como a principal ferramenta para relatar e investigar cada área, com foco no áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

Recomendamos que você nomee o campeão de qualidade no início. Depois de serem nomeados, eles devem começar a se familiarizar com [o conteúdo de](monitor-call-quality-qos.md) qualidade de chamada do Monitor e materiais de treinamento associados.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade                               | Descrição                                                                                                                                                                                                                                                                                                 | Cadência                             | Equipe Atribuída |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nominar e treinar defensores de qualidade | Nomear e treinar um campeão de qualidade.                                                                                                                                                                                                                                                                   | Conforme necessário                           |               |
| Executar Avaliações de Qualidade da Experiência (QERs)     | Execute uma QER para identificar tendências de qualidade e confiabilidade, revisar em relação a destinos definidos e relatar aos principais participantes da organização.                                                                                                                            | Mensal (semanalmente durante implantações) |               |
| Correção de unidade                      | Coordena os esforços de correção em toda a organização com base nas avaliações e descobertas de QER.                                                                                                                                                                                                           | Conforme necessário                           |               |
| Atualizar dados de criação no CQD            | Atualizar ou adicionar novas definições de construção no CQD quando as alterações são feitas na rede (consulte [Upload Building information](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Conforme necessário                           |               |
| Preencher a função Defensor da Qualidade      | Responsabilidade de ponta a ponta pela qualidade na organização. Isso inclui:<ul><li>Verifique se a QER está sendo conduzida regularmente.</li><li>Reporte aos principais participantes sobre o status de qualidade.</li><li>Verifique se as definições de dados de criação estão atualizadas.</li><li>Coordena os esforços de correção em toda a organização para garantir que os usuários tenham uma experiência de alta qualidade com o Teams.</li></ul>          | Diário                               |               |



### <a name="references"></a>Referências 


[Carregar dados de locatário e construção no CQD](CQD-upload-tenant-building-data.md)

[Melhorar e monitorar a qualidade das chamada para o Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gerenciar pontos de extremidade

Os pontos de extremidade do Microsoft Teams podem ser definidos como qualquer computador, Mac, tablet ou dispositivo móvel (ou qualquer outro) que executa o cliente do Teams. O *ponto* de extremidade do termo não abrange apenas o dispositivo em si, mas como um usuário se conecta ao dispositivo, por exemplo, usando o microfone ou alto-falante interno do dispositivo, fones de ouvido ou um fone de ouvido otimizado. Depois de implantados, os pontos de extremidade não devem ser esquecidos. Os pontos de extremidade do Teams exigem manutenção e cuidado contínuos. As seções a seguir descrevem áreas específicas em que se concentrar.

### <a name="endpoint-requirements"></a>Requisitos de ponto de extremidade

Um dos principais benefícios do Teams é que o cliente é mantido atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso. Os aplicativos móveis do Teams são mantidos atualizados por meio de seus respectivos armazenamentos de aplicativos.

O cliente do Teams tem requisitos mínimos em termos da plataforma de software subjacente. Esses requisitos podem mudar ao longo do tempo e, portanto, é importante que você os monitore para alterações. Por exemplo, o cliente teams tem uma versão mínima do iOS. Se o cliente usa um navegador da Internet, o navegador também precisa ser mantido atualizado. Uma lista de plataformas com suporte pode ser encontrada em [Obter clientes para o Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Firewalls do lado do cliente podem afetar a qualidade da chamada e até mesmo impedir que uma chamada seja estabelecida. Depois que as exclusões apropriadas no firewall do cliente foram configuradas, elas precisam ser mantidas atualizadas com base nas informações em [URLs do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)e intervalos de endereços IP. O fornecedor de terceiros terá orientações específicas sobre como atualizar as exclusões.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Wi-Fi drivers podem ser problemáticos. Como exemplo, um driver pode ter comportamentos de roaming muito agressivos entre os pontos de acesso que podem induzir a alternação desnecessária de ponto de acesso, levando a uma qualidade de chamada ruim. Um driver de Wi-Fi de desempenho ruim pode ser descoberto por meio de uma Análise de Qualidade da Experiência (consulte [Improve and monitor call quality for Teams para](monitor-call-quality-qos.md) obter mais detalhes). É essencial implementar um processo orientado pela qualidade que monitora os novos drivers Wi-Fi e garante que eles são testados antes de serem implantados para a população geral de usuários.

### <a name="endpoint-management"></a>Gerenciamento de ponto de extremidade

Um catálogo de pontos de extremidade e dispositivos de interface com suporte (como fones de ouvido) deve estar disponível e mantido. Este catálogo incluirá uma lista de dispositivos aprovados que foram selecionados e validados como parte das fases Envision e Onboard. Normalmente, dispositivos específicos são selecionados para cada tipo de persona em sua organização para atender às necessidades dos atributos dessa persona. Todos os pontos de extremidade têm um ciclo de vida e você precisa gerenciar os contratos de fornecedor, garantia, substituição, distribuição e políticas de reparo associadas a esses dispositivos.

### <a name="endpoint-troubleshooting"></a>Solução de problemas de ponto de extremidade

Mesmo que você tenha seguido as diretrizes anteriores, os usuários em sua organização ainda poderão ter problemas com o Teams. Embora o problema possa não estar com o ponto de extremidade em si, os sintomas do problema normalmente são a superfície através do cliente para o usuário. As diretrizes a seguir destinam-se a fornecer etapas gerais que você pode tomar para resolver o problema; ele não deve ser um guia abrangente de solução de problemas. As etapas são fornecidas em uma ordem específica, mas não precisam ser seguidas explicitamente e podem não ser aplicáveis, dependendo da natureza do problema.

1.  **Validar a saúde do serviço:** O problema que um usuário pode estar enfrentando pode estar relacionado a um evento que afeta negativamente o serviço do Teams ou seus serviços dependentes. Como primeira etapa, recomendamos que você confirme que não há problemas de serviço ativos. Consulte Como verificar a saúde do [serviço do Office 365.](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)
    Lembre-se de verificar o status dos serviços dependentes (por exemplo, Exchange, SharePoint, OneDrive for Business). O monitoramento para a saúde do serviço é discutido em mais detalhes na seção anterior, [Monitorar a saúde do serviço.](#monitor-service-health)

2.  **Validar a conectividade do cliente:** Problemas de conectividade causam problemas de funcionalidade ou de login no Teams. Recomendamos (especialmente para novos sites ou locais) que você valide a conectividade com o serviço. Verifique se as seguintes [diretrizes de URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) são seguidas para cada site. Você pode aproveitar a [Ferramenta de Avaliação](https://www.microsoft.com/download/details.aspx?id=53885) de Rede da Microsoft para executar um teste de conectividade para validar se as portas de mídia foram abertas corretamente para recursos de voz na nuvem. As etapas detalhadas sobre como executar os testes de conectividade são fornecidas nas diretrizes [de preparação da](3-envision-evaluate-my-environment.md#network-readiness) rede.

3.  **Verifique a lista de problemas conhecidos:** Consulte [a Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams) para determinar se o usuário foi afetado negativamente por um desses problemas. Siga a solução alternativa fornecida (se houver uma) para resolver o problema.

4.  **Visite a comunidade do Microsoft Teams:** A [comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) oferece espaços dedicados para o Teams. A comunidade do Teams fornece uma lista de discussão, postagens de blog e comunicados centralizados em torno do Teams. Você pode postar uma pergunta ou pesquisar discussões anteriores em busca de soluções para seu problema.

5.  **Entre em contato com o Suporte da Microsoft:** Você pode entrar em contato com o Suporte da Microsoft para problemas com o Teams online ou por telefone. Para obter informações, consulte [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).
    Para clientes Premier, as solicitações de suporte podem ser iniciadas seguindo as diretrizes em [Suporte de contato para o Microsoft Teams (clientes Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade                 | Descrição                                                                                                                                                                                                                                                                                                                                                                     | Cadência   | Equipe atribuída |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisitos de ponto de extremidade    | Verifique se o ponto de extremidade do Teams continua a atender a todos os requisitos de software para o Teams listados em [Obter clientes para o Microsoft Teams.](get-clients.md)                                                                                                                                                                                       | Mensal   |               |
| Firewalls de ponto de extremidade       | Mantenha as exclusões apropriadas no firewall do ponto de extremidade com base nas informações em [URLs do Office 365 e intervalos de endereços IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges) O fornecedor de terceiros terá orientações específicas sobre como manter as exclusões. Inscreva-se no [feed RSS para](https://support.office.com/o365ip/rss) ser notificado automaticamente das alterações. | Conforme necessário |               |
| Drivers de Wi-Fi            | Teste e atualize Wi-Fi drivers no computador. Valide os resultados usando o CQD ([Melhorar e monitorar a qualidade das](monitor-call-quality-qos.md)chamada para o Teams ).                                                                                                                                                                                                                                                                   | Conforme necessário |               |
| Gerenciamento de ponto de extremidade      | Mantenha o catálogo de pontos de extremidade e dispositivos de interface com suporte (como fones de ouvido). Gerenciar contratos de fornecedor, garantia, distribuição, substituição e políticas de reparo.                                                                                                                                                                                                        | Mensal   |               |
| Solução de problemas de ponto de extremidade | A solução de problemas de tarefas pode incluir verificar a conectividade, consultar a lista de problemas conhecidos, coleta de log, análise e escalonamento para o Suporte da Microsoft ou fornecedores de terceiros.                                                                                                                                                                                               | Conforme necessário |               |

### <a name="references"></a>Referências 

[URLs e intervalos de endereços IP do Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Obter clientes para o Microsoft Teams](get-clients.md)

[Comunidade do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)

[Verificar a integridade do serviço do Microsoft Teams](service-health.md)

[Entre em contato com o suporte de produtos para empresas - Ajuda da Administração](/microsoft-365/admin/contact-support-for-business-products)

[Entrar em contato com o suporte premier](https://support.microsoft.com/premier/contacts)

[Solução de problemas de vídeo do Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gerenciar o Teams

Depois que o serviço do Microsoft Teams tiver sido implantado, você precisará executar várias atividades relacionadas à sua administração. As atividades variam de administrar o serviço e usuários individuais até o planejamento de capacidade e provisionamento de licenciamento e números de telefone. As seções a seguir abrangem algumas dessas tarefas comuns de administração.

### <a name="service-administration"></a>Administração de serviços

O serviço do Teams tem várias configurações que podem ser configuradas em todo o locatário.
As alterações feitas nas configurações do locatário afetam todos os usuários que foram habilitados para o Teams. Para uma lista detalhada dessas configurações, consulte [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).

### <a name="user-administration"></a>Administração do usuário

Para dar suporte aos usuários, uma organização pode exigir qualquer número de tarefas relacionadas, as tarefas específicas variam de uma organização para a próxima. Em última análise, essas tarefas precisam ser gerenciadas por uma equipe de suporte que tenha sido atribuída a essas tarefas operacionais. As tarefas a seguir são comumente necessárias para dar suporte aos usuários no Teams.

#### <a name="general-tasks"></a>Tarefas gerais

[Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Tarefas comuns para o Sistema de Telefonia

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

À medida que sua organização cresce ou contrata, é importante planejar o licenciamento para necessidades atuais e futuras. Há uma licença base do Teams, além de licenciamento para recursos de voz na nuvem ([Sistema de Telefonia](here-s-what-you-get-with-phone-system.md) [e Audioconferência](https://products.office.com/skype-for-business/audio-conferencing)).

Para o Teams, as licenças do Sistema de Telefonia exigem licenças [de Planos](calling-plan-landing-page.md) de Chamadas associados. O licenciamento do Plano de Chamadas permite que você faça e receba chamadas telefônicas domésticas e/ou internacionais. Esses planos são baseados em uso e têm pools de minutos associados a eles. Provisionar [créditos de comunicações](what-are-communications-credits.md) garantirá que você nunca ficará sem serviço.

A Audioconferência permite conferência discada com discagem discada e serviços de conferência discada domésticas. A conferência discada gratuita ou cenários de discagem não doméstica podem fazer com que você incorrer em encargos adicionais para os quais os [Créditos de](what-are-communications-credits.md) Comunicação são necessários.

Os Créditos de Comunicações podem complementar as licenças de Plano de Chamada e Audioconferência. As licenças do Plano de Chamada e os Créditos de Comunicação são baseados em uso e, portanto, precisam ser monitorados e provisionados de acordo.

Você pode aproveitar o relatório de uso [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) para ajudá-lo a monitorar o uso de minutos de Plano de Chamada e Créditos de Comunicações. Com base nos resultados dessa atividade, você pode ajustar seu licenciamento de acordo. Em breve, ofereceremos um relatório de pools de minutos [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) para ajudar mais efetivamente nessa tarefa.

### <a name="telephone-number-management"></a>Gerenciamento de números de telefone

Há dois métodos para adquirir números no Teams: você pode portuar números de telefone de outro provedor ou provisionar os números diretamente do inventário de números da Microsoft. Ambos os métodos são descritos em [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md).

Há um limite para o número de números de telefone que você pode provisionar no inventário de números da Microsoft. Os limites são determinados por vários fatores detalhados em Quantos números de telefone [você pode obter?](how-many-phone-numbers-can-you-get.md).
Os limites dependem do tipo de números— números de serviço gratuito, números de serviço de tarifação e números de assinante (usuário). Cada um tem seus próprios limites e deve ser gerenciado independentemente. Se você estiver perto do limite (ou tiver atingido o limite), poderá aplicar um incremento ao limite. Esse processo é descrito no artigo no parágrafo anterior.

Pode haver momentos em que um número não está disponível para ser provisionado em uma região onde o serviço está disponível. Para obter informações sobre o processo de solicitação de números, consulte [Manage phone numbers for your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Criação de equipe (opcional)

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Microsoft 365 e, portanto, uma equipe no Microsoft Teams. Se você quiser ter um [](assign-roles-permissions.md#permissions-to-create-teams) controle mais rígido e restringir a criação de novas equipes (e, portanto, a criação de novos grupos do Microsoft 365), você pode delegar a criação de grupos e direitos de gerenciamento a um conjunto de administradores. Se sua organização quiser prosseguir com essa opção, consulte o processo descrito neste artigo para permitir que os usuários enviem solicitações processadas por uma equipe atribuída.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diárias/semanais/mensais/conforme as necessárias

| Atividade                    | Descrição                                                                                                                                                                                                                                                                                                                                                                                                             | Cadência   | Equipe atribuída |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Administração de serviços      | Administração de configurações do Teams em todo o locatário.                                                                                                                                                                                                                                                                                                                                                                           | Conforme necessário |               |
| Administração do usuário         | Administração de configurações baseadas em usuário e licenciamento no Teams.                                                                                                                                                                                                                                                                                                                                                           | Conforme necessário |               |
| Gerenciamento de licenças          | Planeje as necessidades atuais e futuras para licenciamento baseado no usuário e no consumo (Planos de Chamada e Créditos de Comunicação) aproveitando o relatório de uso [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e o relatório de pools de minutos [PSTN.](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) | Semanal    |               |
| Gerenciamento de números de telefone | Gerencie os números de telefone disponíveis para crescimento futuro e ajuste os níveis de inventário para atender às suas necessidades organizacionais.                                                                                                                                                                                                                                                                                                | Semanal    |               |
| Criação de equipe (opcional)    | Revisar e processar solicitações para criação de equipe.                                                                                                                                                                                                                                                                                                                                                                          | Conforme necessário |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Melhorar e monitorar a qualidade da chamada

[Melhorar e monitorar](monitor-call-quality-qos.md) a qualidade das chamada para o Teams inclui um conjunto de atividades que avaliam e fornecem orientações de correção em áreas-chave que têm o maior impacto na melhoria da experiência do usuário, conforme ilustrado abaixo.

![Diagrama de áreas a examinar durante uma Análise de Qualidade de Experiência](media/plan-my-service-management-image2.png "As principais áreas a examinar durante uma Análise de Qualidade de Experiência: resultados de pesquisa de áudio, confiabilidade e usuário.")

Ao avaliar continuamente e remediar as áreas descritas no guia, você pode reduzir seu potencial para afetar negativamente a experiência do usuário. A maioria dos problemas de experiência do usuário encontrada em uma implantação pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy

-   Cobertura insatisfatória da rede Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Uso de dispositivos de áudio internos ou não otimizados

-   Dispositivos de rede ou sub-redes com problemas

As diretrizes fornecidas em Melhorar e monitorar a qualidade de chamada do [Teams](monitor-call-quality-qos.md) se concentram em usar o CQD Online como a principal ferramenta para relatar e investigar cada área descrita, com foco no áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

É altamente recomendável nomear o campeão de qualidade no início. Depois de serem nomeados, eles devem começar a se familiarizar com o conteúdo em Melhorar e monitorar a qualidade das chamada [para o Teams.](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->