---
title: Guia de operações para equipes da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Tarefas e atividades necessárias para gerenciamento de serviço de equipes, incluindo o monitoramento de integridade do serviço, como avaliar e garantir a qualidade da rede e uso.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ab8749dc71e124dcf723444208aab6eae95a665
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="operate-my-service"></a>Operar o meu serviço

Este artigo fornece uma visão geral dos requisitos de operando com êxito os serviços de voz de nuvem para sua organização. Por operando corretamente seus serviços de voz de nuvem, você pode ser se que você estiver fornecendo uma experiência de alta qualidade, confiável para sua organização.

## <a name="introduction-to-the-operations-guide"></a>Introdução ao guia de operações

Guia de operações oferece uma visão geral de todas as tarefas e atividades necessárias como parte da função de gerenciamento de serviço for Microsoft Teams.

Gerenciamento de serviço é um tópico amplo que cobre as operações diárias do serviço Microsoft Teams depois que ele tenha sido implantado e habilitado para usuários. O serviço de equipes engloba Microsoft Office 365 e os componentes de infraestrutura que são implantados no local (por exemplo, de rede).

A noção do gerenciamento de serviços não mais provável é um novo conceito na maioria das organizações. Você talvez já implementou processos e as tarefas associadas com serviços existentes. Além disso, você provavelmente pode incrementar seus processos atuais quando você planejar gerenciamento de serviço de hoje a equipes de suporte no futuro.

Gerenciamento de serviço abrange todas as atividades e processos envolvidos na Gerenciando as equipes de ponta a ponta. Conforme observado anteriormente, alguns componentes do gerenciamento de serviços — a infraestrutura que compõe o próprio serviço Office 365 — são responsabilidade da Microsoft, enquanto você, o cliente, é responsáveis aos usuários sobre como gerenciar os vários aspectos da rede, equipes e pontos de extremidade que você fornecer.

As tarefas e atividades neste guia são agrupadas em oito categorias, conforme ilustrado no diagrama a seguir. Cada uma dessas categorias será expandida após nas seções a seguir.

Diagrama de ![uma ilustrando uma lista de categorias de tarefas e atividades que compõem o gerenciamento de serviço para equipes. O diagrama também mostra que o gerenciamento de serviço é basicamente uma tarefa do cliente.] Diagrama de (media/operate-my-service-image1.png "uma ilustrando uma lista de categorias de tarefas e atividades que compõem o gerenciamento de serviço para equipes. O diagrama também mostra que o gerenciamento de serviço é basicamente uma tarefa do cliente.")


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida como as operações serão implementadas para equipes.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Revise o guia de operações por completo.</li><li>Implemente uma estratégia de operações que se alinha com as metas da sua organização para oferecer a qualidade e a confiabilidade da nuvem cargas de trabalho de voz.</li><li>Revise o guia revisão de experiência de qualidade.</li><li> Implemente uma estratégia de operações para executar regularmente avaliações de experiência de qualidade para certificar-se de que sua implantação de voz de nuvem está operando em recursos de pico.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mapeamento de função operacionais

O planejamento que você executou para operações durante a fase de Envision é fundamental, porque as atividades de operações começam quando os usuários piloto primeiro estão habilitados. Este guia lista as atividades e as tarefas que devem ser executadas em uma base diária, semanal, mensal ou conforme necessário para manter uma implantação de equipes de alta qualidade. Este guia fornece conhecimento e orientação sobre como realizar essas tarefas e atividades essenciais.

Certifique-se de que o planejamento que você faça logo no início da fase Envision inclui determinar quem será responsável pela execução de atividades específicas é um componente essencial de uma implantação bem-sucedida. Depois que você calculou que tarefas e atividades que se aplicam à sua implantação, elas precisam ser compreendidos e seguido de grupos ou indivíduos que podem ser atribuídos a eles.

Cada equipe identificado deve revisar e concordam com as tarefas e responsabilidades identificadas e iniciar a preparação. Isso pode incluir o treinamento e preparação, fornecendo atualizações para a equipe ou garantindo provedores externas estão prontos para entregar.

As atividades e funções definidas neste guia devem ser válidas na maioria dos cenários, mas todas as implantações de equipes é exclusiva; Portanto, você pode usar este guia como ponto de partida para personalizar as atividades e funções de padrão para atender às suas necessidades.

Certifique-se de que cada equipe responsável tem um bom entendimento das atividades que são necessários para executar o serviço. É essencial que cada equipe aceita e aprova em sua responsabilidade em sua organização antes de inicia o primeiro piloto.

Depois de um contrato é estabelecido, as equipes correspondentes deverá começar tornem operacional suas funções.

<table>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td>
<td><ul><li>Use este documento para facilitar o exercício de mapeamento de função operacionais.</li><li>Se encontrar com as equipes de suporte respectivos para atribuir nomes a cada item na lista de atividades necessárias.</li><li>Obter a aceitação ou aprovação nas funções atribuídas.</li><li>Certifique-se de que as equipes correspondentes tenham o treinamento adequado, preparação e recursos para concluir suas atividades necessárias.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dependências de serviços de equipes

Microsoft Teams reúne tecnologias across Office 365 para fornecer um hub de trabalho em equipe. Alguns exemplos incluem;

-   Azure Active Directory fornece serviços de autenticação e autorização para equipes.

-   O Exchange Online oferece recursos avançados, como o estado de retenção legal e descoberta eletrônica.

-   SharePoint Online oferece a capacidade de compartilhar arquivos em canais e OneDrive for Business oferece um mecanismo para o compartilhamento de arquivos dentro de um bate-papo privado.

As organizações também podem aproveitar os investimentos existentes na infraestrutura local. Por exemplo, contas existentes de Active Directory local podem ser usadas para autenticação aproveitando Connect do Azure AD. Determinadas versões do Exchange Server podem ser usados no lugar do Exchange Online.

Essas tecnologias se unem para oferecer um pacote de comunicações inteligente rica e colaboração para os usuários. Essa integração conjunta é dos principais benefícios de equipes, mas ele também conduz um requisito para gerenciamento de serviço entre essas tecnologias.

Este guia abrange as principais áreas de foco para gerenciar o serviço de equipes. Provavelmente, você tem planos de gerenciamento de serviço em vigor para as tecnologias de suporte que depende de equipes. Se não, você precisará estabelecer planos de gerenciamento de serviços adequado para esses componentes da tecnologia (tanto no local e online) também. Isso ajudará a garantir que seus usuários tenham uma experiência de alta qualidade, confiável com equipes.

#### <a name="references"></a>Referências 

[Visão geral do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)

[Como o Exchange e o Microsoft Teams interagem](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact)

[Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact)

[Microsoft Teams e Skype para a interoperabilidade de negócios](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Atividades do guia de operações

As próximas seções fornecem uma visão geral das atividades que são necessários para operar com êxito o serviço de Teams da Microsoft. Eles incluem referência às ferramentas, informações contextuais e conteúdo adicional para ajudá-lo a entender a atividade e para auxiliar iniciativas de preparação.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Monitorar a integridade de serviço

É importante que você entenda a integridade geral do serviço Teams da Microsoft para que você proativamente alertando outras pessoas em sua organização de qualquer evento que afeta o serviço. Conforme descrito anteriormente, equipes é dependente a outros serviços do Office 365, como o Azure Active Directory, o Exchange Online, SharePoint Online e OneDrive for Business. Por isso, é igualmente importante monitorar a integridade dos serviços dependentes.

Incorpore esta atividade ao seu processo de gerenciamento de incidentes para proativamente informar aos usuários, a assistência técnica e suas equipes de operações para se preparar para lidar com escalonamentos de usuário.

As seções a seguir descrevem as ferramentas que você pode aproveitar para monitorar a [incidentes de serviço] (https://technet.microsoft.com/library/office-365-service-health.aspx?f=255&MSPPError=-2147217396#Service incidentes) que afetam o serviço de equipes. Um resumo dos benefícios do cada ferramenta e, quando você deve usar cada uma delas é incluído na tabela a seguir.

| Ferramenta de monitoramento                       | Benefícios                                            | Quando usar                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Portal do Office 365                     | Disponível a partir de qualquer dispositivo com um navegador com suporte. | Use quando você não exige notificações em tempo real.                                          |
| Aplicativo de administração do Office 365                  | Fornece notificações de push para seu dispositivo móvel.  | Quando você precisa de notificação de incidentes de serviço enquanto você estiver em trânsito.                  |
| Microsoft System Center               | Integração com o Microsoft System Center.           | Você requer recursos avançados de monitoramento e suporte de notificação.                       |
| Comunicações de serviço do Office 365 API | Acesso programático a integridade do serviço Office 365.   | Exigir a integração com um participante 3º ferramenta de monitoramento ou deseja compilar sua própria solução. |

> [!NOTE]
> Apenas pessoas que são atribuídas à função de **administrador global** ou **administrador de serviço** podem exibir a integridade do serviço.

### <a name="monitoring-with-the-office-365-portal"></a>Monitorando com o portal do Office 365

O [portal do Office 365](https://portal.office.com/) fornece um [Painel de integridade do serviço](https://portal.office.com/adminportal/home#/servicehealth) onde você pode exibir o estado atual do serviço equipes além serviços dependentes.

### <a name="monitoring-with-the-mobile-app"></a>Monitorando com o aplicativo móvel

O aplicativo de administração do Office 365 está disponível no Apple iOS, Android e Windows (PC e celular). O aplicativo fornece informações sobre futuras alterações e de integridade do serviço de administradores de serviço. O aplicativo dá suporte a notificações de push alertando você quase imediatamente após um comunicado ter sido enviado. Isso ajuda a manter-se atualizado sobre o status, integridade e qualquer futuras alterações ao serviço. O suporte de notificação torna a ferramenta de monitoramento recomendada para administradores. Para obter mais informações, consulte:

[O Office 365 Admin Mobile App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Baixe o aplicativo de administração móvel do Office 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Monitorando com o Microsoft System Center

Microsoft System Center é uma plataforma de gerenciamento integrado que ajuda você a gerenciar datacenter, dispositivos cliente e híbrido em nuvem ambientes de TI. Os administradores do Office 365 que usam o System Center agora tem a opção de importar o pacote de gerenciamento do Office 365, que permite que eles vejam todas as comunicações de serviço no Operations Manager no System Center. Usando essa ferramenta fornece acesso ao status de seus serviços inscritos, serviço ativas e resolvidas incidentes e suas comunicações do Centro de mensagens (futuras alterações). Para obter mais informações, consulte o seguinte [postagem de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Se você aproveitar o System Center para monitorar a integridade de serviço de equipes (e serviços dependentes), você pode personalizar o pacote de gerenciamento para alertar ou notificar grupos específicos ou indivíduos que foram identificados reagir a incidentes.
Esses grupos podem incluir os proprietários de serviços, los, grupos de suporte de segundo nível e de terceiro nível e os gerentes de incidentes em sua organização.

### <a name="monitoring-for-advanced-scenarios"></a>Monitoramento para cenários avançados

Você pode monitorar a integridade do serviço e futuras alterações aproveitando a API de comunicações do Office 365 Service para acessar as alterações e a integridade do serviço Office 365 programaticamente. Use essa API para criar seu próprio monitoring ferramenta ou conecte suas ferramentas de monitoramento existentes para as comunicações de serviço do Office 365, simplificando potencialmente como monitorar o seu ambiente. Para obter mais informações, consulte [Office 365 para desenvolvedores do Enterprise](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diariamente/semanalmente/mensal/conforme necessário

| Atividade               | Descrição                                                                                                                                                                                                               | Cadência   | Equipe atribuído |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitorar a integridade de serviço | Monitore proativamente a integridade do serviço Microsoft Teams (e serviços dependentes) usando as ferramentas disponíveis. Incluem serviços dependentes: OneDrive do Exchange Online, SharePoint Online para empresas, Azure Active Directory. | Em tempo real |               |
| Notificação de incidentes  | Notifica os participantes internos de eventos que afetam o serviço de equipes. Participantes internos podem incluir usuários, los e gerentes de incidentes.                                                                          | Conforme necessário |               |

### <a name="references"></a>Referências 

[Como verificar a integridade do serviço Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Verificar a integridade do serviço para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/service-health)

[Continuidade e a integridade do serviço](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gerenciamento de mudanças organizacionais

Microsoft Teams é um serviço baseado em nuvem. Com o que vem a capacidade de oferecer novos recursos e funcionalidades em um ritmo acelerado. Fornecer inovações contínuas proporciona uma vantagem óbvia para as organizações, mas essas alterações precisam ser gerenciados de forma adequada dentro da sua organização para evitar resistência dos usuários ou escalonamentos para a assistência técnica.

Atualizações para equipes são distribuídas automaticamente para seus usuários. Os usuários sempre terão o cliente e os recursos disponíveis no serviço de equipes a mais recente. Não é possível gerenciar a distribuição das atualizações de equipes para seus usuários, portanto é extremamente importante gerenciar a alteração através de programas de comunicação, treinamento e adoção efetivas. Se os usuários estão cientes da alteração, instruídos sobre os benefícios e autonomia para aproveitar os novos recursos&mdash;eles serão capazes de se adaptar mais rapidamente e a alteração de boas-vindas.

### <a name="monitoring-for-change"></a>Monitoramento da alteração

A primeira etapa no gerenciamento de alterações está monitorando as alterações que estão planejadas para equipes. A melhor fonte para essas alterações de monitoramento é o [Mapa do Office 365](https://products.office.com/business/office-365-roadmap), que lista os recursos que estão atualmente em desenvolvimento, sendo distribuído aos clientes, ou totalmente tenham sido iniciados. Você pode pesquisar recursos específicos de equipes, usando o filtro fornecido ou você pode baixar o mapa para um arquivo do Excel para análise adicional. Para cada recurso, o mapa dá uma breve descrição, juntamente com a data de lançamento previstas.

No [blog de equipes da Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), pode aprender sobre práticas recomendadas, tendências e notícias sobre atualizações de produto de equipes. Espere localizar as atualizações dos principais recursos para equipes a ser anunciado aqui. Você também pode assinar o blog por meio de um RSS feed. Em seguida, você pode adicionar [o RSS feed](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) diretamente em um canal de equipes, para que todas as notícias importantes é entregue diretamente dentro de equipes.

Todos os recursos que são lançados estão documentados nas [Notas de versão para equipes da Microsoft](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Aqui, você encontrará uma lista dos recursos que foram lançadas para desktop, web e dispositivos móveis. O mesmo conjunto de notas de versão também estão disponíveis na guia Notas de versão no [Microsoft equipes T-Bot](https://docs.microsoft.com/microsoftteams/t-bot).

Familiarize-se com os recursos disponíveis e certifique-se de que você atribuir proprietários aplicáveis para o monitoramento de alteração.

### <a name="planning-for-change"></a>Planejamento de alterações

Agora que você esteja ciente das futuras alterações para o serviço de equipes, a próxima etapa é preparar e planeje apropriadamente. Avalie a cada alteração para determinar quais alterações exigem a comunicação com usuários, campanhas de divulgação, treinamento para equipes de suporte ou usuários ou campanhas de avaliação e adoção do recurso. Essa é a função principal de uma equipe de gerenciamento de alteração em sua organização. A seguir, é uma coleção de tabelas que podem ajudá-lo a planejar as mudanças de amostra.

[//]: # (A extensão da coluna e o intervalo de linha nesta tabela são graça, mas sem suporte na redução, pelo menos que o rowspan é. Isso é tão perto quanto poderia recebo. Talvez tudo precisa reprojetando.)

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Recurso: Gravação na nuvem (data de lançamento: janeiro de 2018)

**Acompanhar geral**
| Preparação de alteração | Status   | Notas/próximas etapas | Proprietário |
|----|----|----|-----|
| Revisão legal   | Concluído     | Esse recurso é um pré-requisito para a equipe de treinamento de inclusão. | Equipe de projeto  |

**Gerenciamento de alteração técnica**
| Preparação de alteração | Status   | Notas/próximas etapas | Proprietário |
|----|----|----|-----|
| Alterações IT necessárias          | Sim                  | Administrador precisa habilitar gravação identificados apenas para usuários.      | Equipe de suporte           |
| Prontidão técnica completa | Sim                  |                                                                 | Equipe de suporte  
         |
**Gerenciamento de alterações do usuário** 
| Preparação de alteração | Status   | Notas/próximas etapas | Proprietário |
|----|----|----|-----|
| Impacto do usuário                  | Baixo                  |                                                                 |                        |
| Preparação do usuário necessária      | Sim                  |                                                                 |                        |
| Comunicações prontas         | Não                   | Email de comunicação foram escreveu — pendentes para revisão.            | Equipe de comunicações    |
| Treinamento pronto               | Sim                  | Treinamento irá alavancar o vídeo da Microsoft existente.                | Equipe de treinamento          |

**Faixa de status**
| Preparação de alteração | Status   | Notas/próximas etapas | Proprietário |
|----|----|----|-----|
| Status de lançamento               | em andamento          | Revisão pendente por patrocinador executivo.               | Equipe de gerenciamento de alterações |
| Aprovação da versão             |                      |                                                                 |                        |
| Data de lançamento                 |                      |                                                                 |                        |

Para obter mais informações sobre o planejamento de gerenciamento de alteração com equipes, consulte [criar uma estratégia de gerenciamento de alteração para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/change-management-strategy).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diariamente/semanalmente/mensal/conforme necessário

| Atividade               | Descrição                                                                                                                                                                                                                | Cadência   | Equipe atribuído |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Monitor da alteração     | Monitorar a existência de futuras alterações ao serviço Teams da Microsoft.                                                                                                                                                                   | Diariamente     |               |
| Planejamento de alterações    | Avaliar e planejar a novos recursos e capacidades, incluindo planos de comunicação, campanhas de divulgação e treinamento.                                                                                                     | Conforme necessário |               |
| Preparação do usuário             | Execute a comunicação direcionada, divulgação ou campanhas de treinamento para garantir que os usuários estão prontos para as futuras alterações.                                                                                                        | Conforme necessário |               |
| Preparação da equipe de suporte | Execute a comunicação direcionada, divulgação ou campanhas de treinamento para garantir que a equipe de suporte está pronta. Equipes de suporte podem incluir a equipe "luva branco", los, camada 2 ou camada 3 suporte, parceiros externos e assim por diante. | Conforme necessário |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Avaliar o uso de equipes

Depois que o piloto inicial começa, é essencial para estabelecer uma cadência regular para medir o uso de equipes real. Isso permite que sua organização para obter ideias para uso como real se alinha com o uso previstos por você durante a fase de Envision. Embora esta seção foca no uso de equipes, isso deve ser parte de um esforço amplo para medir e avaliar o uso do Office 365 geral.

Analisar o uso com frequência no início na implantação oferece a oportunidade de:

-   Valide se os usuários estiverem usando equipes.

-   Identifique os desafios de adoção potenciais antes que eles criam problemas críticos em toda a organização.

-   Compreenda se há discrepâncias entre os requisitos de fase do Envision e o uso real.

Se o uso não for o que você espera, isso poderia ser devido a um problema de implantação ou o plano de adoção não está sendo executado corretamente ou outro problema. Dependendo do motivo real por trás de pouco uso, o administrador do serviço deve colaborar com as equipes relacionadas para ajudar a remover as barreiras de uso.

### <a name="measuring-usage-with-the-office-365-admin-center"></a>Medindo o uso com o Centro de administração do Office 365

Dados de uso de equipes estão disponíveis no painel do relatório. Dados de uso de equipes podem ser encontrados em três relatórios diferentes. O primeiro relatório fornece um modo de exibição entre produtos de como os usuários se comuniquem e colaborem com os vários serviços no Office 365. Este relatório pode ser encontrado aqui: [relatório de usuários ativos do Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Os dois relatórios são específicos de equipes e eles fornecem mais detalhes sobre o uso de equipes de uma perspectiva de dispositivo e de usuário. Ambos os relatórios podem ser encontrados aqui:

[Relatório de uso do dispositivo Teams da Microsoft](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Relatório de atividades do usuário Teams da Microsoft](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Permissões necessárias

Os relatórios de uso no Centro de administração podem ser acessados por pessoas que tiverem sido atribuídas a uma função de **Administrador Global** ou uma função de administrador de produtos específicos (**administrador do Exchange**, **Skype do administrador de negócios**, **do SharePoint administrador**).

Além disso, a função de **leitor de relatórios** está disponível para usuários que exigem o acesso aos relatórios, mas não realiza tarefas que exijam permissões de nível de administrador. Você atribuir esta função para fornecer relatórios de uso para qualquer pessoa que é das partes interessadas, para monitorar e impulsionar a adoção. Para obter mais informações sobre as diferentes funções disponíveis, consulte [funções de administrador do Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Avaliando o uso

Depois de usar o painel de relatórios para medir o uso, é importante comparar o uso medido contra quaisquer indicadores de sucesso fundamental (KSIs) que você definiu durante a fase de Envision do projeto. Você pode definir um KSI que pode ser definido como uso ativo ou que é indiretamente vinculadas para ativo de uso.

É importante identificar quaisquer variações entre uso real e planejado antes de continuar a distribuição para outros sites ou usuários. Provavelmente você vai identificar lições organizacionais como parte dessa atividade que você pode aproveitar para garantir que o próximo lote de sites ou usuários não encontra os mesmos problemas.

Primeiro, identifique se este é um problema técnico e/ou adoção. Comece investigando os itens abaixo, em ordem, para determinar onde está o problema.

1.  Valide a qualidade, executando uma [Análise de experiência de qualidade](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#quality-of-experience-review-guide).

2.  Trabalhar com a equipe de assistência técnica para verificar que não existem problemas técnicos tendências impedindo que os usuários acessando ou usando o serviço. Se as tendências de problema existir, use a seção [solução de problemas do ponto de extremidade](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#endpoint-troubleshooting) mais adiante neste artigo para tentar resolver o problema antes de contratar suporte.

3.  Trabalhar com a equipe de adoção e treinamento para obter feedback direto de usuários (consulte [Assess sentimento de usuário](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#assess-user-sentiment) neste artigo) e para verificar a eficácia das atividades de divulgação e adoção.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diariamente/semanalmente/mensal/conforme necessário

| Atividade                         | Descrição                                                                                                                      | Cadência   | Equipe atribuído |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Uso de medida (fase de habilitação) | Medir e avaliar o uso de equipes durante a fase de habilitação, como sites continuam a ser onboarded. Solucionar problemas de uso conforme necessário. | Por semana    |               |
| Uso de medida                    | Medir e avaliar o uso de equipes na fase de unidade de valor (após a conclusão da implantação). Solucionar problemas de uso conforme necessário. | Duas  |               |
| (fase de valor de unidade)              |                                                                                                                                  |           |               |
| Plano de adoção de atualização             | Atualização do seu plano de adoção com base no uso como medido compara a suas metas de planejamento.                                         | Conforme necessário |               |

### <a name="references"></a>Referências 

[Sobre o Centro de administração do Office 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Relatórios de atividades no Centro de administração do Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Avaliar sentimento de usuário

Noções básicas sobre sentimento de usuário pode atuar como um indicador de chave para avaliar o êxito da sua implantação de equipes. Comentários do usuário podem orientar alterações em sua organização; Isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou da maneira que você ofereça suporte aos seus usuários.

É importante obter feedback no início e continue em avaliar sentimento de usuário em todo o ciclo de vida do projeto e além. Use as orientações a seguir para determinar o intervalo no qual a sua organização buscará check-out de comentários:

-   **Início do projeto**: avaliando sentimento de usuário no início do projeto, você pode obter um modo de exibição inicial em como os usuários se sente sobre sua experiência de equipes.

-   **Depois de etapas principais**: ao coletar comentários em todo o ciclo de vida do projeto, você pode medir sentimento de usuário em uma base contínua e fazer alterações, conforme necessário. Isso é especialmente útil após principais marcos.

-   **Conclusão do projeto**: avaliar sentimento de usuário no final de um projeto informará quão bem tiver concluído e onde trabalho ainda precisa ser feito e permitem que você compare resultados com a pesquisa anterior.

-   **Contínuo**: continuar medir sentimento usuário indefinidamente. Alterações no sentimento de usuário podem ser devido às alterações no ambiente da sua organização ou alterações no serviço de equipes. Por avaliar sentimento do usuário a intervalos regulares, é possível entender como suas equipes de gerenciamento de serviço são desempenho e como a sua organização está respondendo às alterações no serviço de equipes.

Sentimento de usuário pode ser avaliado por meio de vários métodos diferentes. Eles podem incluir pesquisas de email, pessoalmente ou entrevistas estilo telefônica ou simplesmente criando um canal de comentários no equipes ou Yammer. Para obter mais informações, consulte [práticas recomendadas para métodos de comentários do usuário em equipes da Microsoft](https://docs.microsoft.com/microsoftteams/best-practices-feedback).

Você também pode usar uma abordagem no setor para avaliar sentimento usuário chamado promotor net pontuação (NPS), que é descrita na seção a seguir.

### <a name="nps"></a>NPS 

Pontuação Promotores NET (NPS) é uma métrica de fidelidade do cliente industrywide e uma boa abordagem usar para avaliar sentimento de usuário.

NPS pode ser calculado por fazer duas perguntas: "como provável estão você recomendar equipes para um colega?", seguido a pergunta de forma livre, "Por quê?"

O NPS é um índice, que varia de – 100 a 100, que mede a disposição do cliente para recomendar produto ou serviço de uma empresa. NPS se baseia em uma pesquisa anônima que é entregue aos usuários através de email ou outros meios eletrônicos. NPS mede a fidelidade entre um provedor e um consumidor. Ele consiste em apenas uma pergunta que solicita aos usuários que classifique sua experiência de 1 a 10, com a opção de fornecer comentários adicionais. Os usuários, em seguida, são classificados com base nos seguintes classificações:

-   9 ou 10 são Promoters: entusiastas leais quem irá promover seu serviço e combustível outras pessoas.

-   7 ou 8 são passivos: satisfeito, mas unenthusiastic, vulneráveis a outra oferta ou serviço.

-   A partir de 1 a 6 são detratores: insatisfeitos clientes que podem danificar seu serviço e impedem o crescimento.

![Este diagrama demonstra a escala NPS. Ele mostra que classificações de 0 a 6 são detratores, são passiva de 7 e 8 e 9-10 promoters.] (media/operate-my-service-image2.png "Este diagrama demonstra a escala NPS. Ele mostra que classificações de 0 a 6 são detratores, são passiva de 7 e 8 e 9-10 promoters.")

Embora o número base do NPS seja útil, você obterá o valor máximo da análise de comentários do usuário. Eles vai ajudá-lo a entender por que o usuário seria (ou não seria) recomendar equipes para outras pessoas. Esses comentários podem fornecer comentários valiosos para ajudar o projeto ou equipes de gerenciamento de serviço entender os ajustes necessários para fornecer uma qualidade de serviço.

Para fornecer pesquisas NPS à sua organização, você pode aproveitar a ferramenta de pesquisa online favorito.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Diariamente/semanalmente/mensal/conforme necessidade tarefas

| Atividade              | Descrição                                                                                                                                                                         | Cadência   | Equipe atribuído |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Avaliar sentimento de usuário | Capturar e avaliar sentimento de usuário usando pesquisas ou entrevistas, ou por meio de um canal de comentários em equipes ou Yammer.                                                                 | Conforme necessário |               |
| Atualizar os planos de adoção | Alteração de unidade em sua organização com base nos comentários do usuário; Isso pode incluir alterações em seus planos de comunicação, programas de treinamento ou da maneira que você ofereça suporte aos seus usuários. | Conforme necessário |               |

### <a name="references"></a>Referências 

[Pontuação Promotores NET](https://en.wikipedia.org/wiki/Net_Promoter)

[Usando o Yammer para coletar comentários](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Práticas recomendadas para comentários do usuário](https://docs.microsoft.com/microsoftteams/best-practices-feedback)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gerenciar a qualidade da rede

Muitos elementos de planejamento de núcleo entram na otimização de dimensionamento à direita e correção de sua infraestrutura de rede para garantir um caminho de alta qualidade e eficiente para o serviço Microsoft Teams. As tarefas de planejamento e requisitos são abordados em nossa orientação de [Preparação da rede](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) anterior. Redes frequentemente evoluem ao longo do tempo devido às atualizações, expansão ou outros requisitos de negócios. É importante considerar para seus requisitos para equipes em sua rede atividades de planejamento.

Embora o planejamento da rede é um aspecto crítico de uma implantação de equipes, é igualmente importante garantir que a rede permanece íntegra e permanece atual, com base na alteração requisitos técnicos e comerciais.

Para garantir a integridade da sua rede, um número de atividades de operações precisa ser executadas em intervalos regulares.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diariamente/semanalmente/mensal/conforme necessário

| Atividade                                                       | Descrição                                                                                                                                                                                                                                                                                                                                                                 | Cadência                | Equipe atribuído |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Monitorar o Office 365 IPs e URLs                                | Monitorar quaisquer alterações para o [Office 365 URLs e intervalos de endereços IP](https://aka.ms/o365ips) usando o [RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) de fornecido e inicia uma solicitação de alteração para grupos de redes aplicáveis.                                                                                                                                | Diariamente                  |               |
| Atualizar a rede com base nas alterações para o Office 365 IPs e URLs | Faça atualizações para os componentes de rede aplicáveis (firewalls, servidores proxy, VPNs, firewalls do lado do cliente e assim por diante) para refletir as alterações do [Office 365 URLs e intervalos de endereços IP](https://aka.ms/o365ips).                                                                                                                                                              | Conforme necessário              |               |
| Fornecer dados de construção                                          | Fornecem informações de sub-rede atualizado ao campeão de qualidade (ou participantes relevantes) para garantir que a [criação de definições no CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) são mantidos atualizados. | Conforme necessário              |               |
| Implementar uma alteração                                               | Implementar alterações na rede para requisitos técnicos e comerciais em constante mudança equipes suporte. Elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Com fio e redes Wi-Fi</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul>     | Conforme necessário              |               |
| Rede de monitoramento e emissão de relatórios                               | Monitore a ponta a ponta para disponibilidade, tendências de capacidade e utilização de rede usando suas ferramentas de gerenciamento de rede de terceiros existentes e recursos disponíveis a partir de seus provedores de rede de relatórios. Use as tendências de dados para planejamento de capacidade de rede.                                                                                                            | Diariamente, semanalmente, mensalmente |               |
| Planejamento de capacidade                                              | Colabore com os proprietários de serviço de equipes para entender os requisitos de negócios e técnicos que talvez mudanças de capacidade adicional de unidade de alteração. Aproveite os resultados a partir do [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) para assegurar que largura de banda suficiente está disponível for Microsoft Teams.                               | Conforme necessário              |               |
| Solução de problemas de rede e remediação                        | Ajudá-los o equipes, os proprietários de serviços e os principais participantes para solucionar problemas e remediar problemas para relacionado a qualidade, confiabilidade ou conectividade equipes. Elementos de rede podem incluir:<ul><li>Firewalls</li><li>VPNs</li><li>Com fio e redes Wi-Fi</li><li>Conectividade com a Internet e ExpressRoute</li><li>DNS</li></ul>    | Conforme necessário              |               |
| Teste de alta disponibilidade e recuperação de desastres                | Execute regular alta disponibilidade e recuperação de desastres Testando a infra-estrutura de rede para garantir que ele atenda os objetivos de nível de serviço indicado (SLOs) ou contratos de nível de serviço (SLAs) para o serviço de equipes.                                                                                                                                                  | Mensal                |               |


### <a name="references"></a>Referências 

[Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips)

[Esquema de dados de construção](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Avaliar e garantir a qualidade 

Todas as empresas precisam de um grupo ou indivíduo para ser responsável qualidade. Essa é a função mais importante no gerenciamento de serviço. A função de qualidade campeão é atribuída a uma pessoa ou grupo que esteja entusiasmados pela sobre a experiência dos seus usuários.
Essa função requer habilidades a identificar tendências no ambiente e o patrocínio para trabalhar com outras equipes para conduzir a correção. O melhor candidato para o posto de defensor da qualidade costuma ser o proprietário do serviço do cliente. Dependendo do tamanho e complexidade da organização, isso poderia ser qualquer pessoa ou grupo com entusiasmo para garantir uma experiência de usuário de alta qualidade.

O campeão de qualidade aproveita as ferramentas existentes e processos documentados, como o painel de controle de qualidade de chamada (CQD) e o guia de revisão qualidade de experiência, para monitorar a experiência do usuário, identificam tendências de qualidade e remediação de unidade onde for necessário.
O campeão de qualidade deve trabalhar com as respectivas equipes às ações de remediação de unidade e relatório para um comitê de orientação sobre o progresso e quaisquer problemas em aberto.

A [Qualidade da experiência Revise o guia](https://aka.ms/qerguide) inclui atividades que avaliam e oferecem orientação de remediação em áreas principais que têm o maior impacto sobre como melhorar a experiência do usuário. As diretrizes fornecidas no guia de revisão de experiência de qualidade enfoca usando CQD Online como a ferramenta principal para relatar e investigar cada área, com foco para maximizar a adoção e o impacto de áudio. Otimizações de feitas à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.

É altamente recomendável que você designar desde o início do campeão de qualidade. Depois que está sendo indicado, eles devem iniciar podem se familiarizar com o conteúdo no Revise o guia de qualidade de experiência e materiais de treinamento associado.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diariamente/semanalmente/mensal/conforme necessário

| Atividade                               | Descrição                                                                                                                                                                                                                                                                                                 | Cadência                             | Equipe atribuído |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nomear e treinar champion(s) de qualidade | Nomear e treinar um champion(s) de qualidade.                                                                                                                                                                                                                                                                   | Conforme necessário                           |               |
| Executar as revisões de experiência de qualidade     | Execute uma revisão de experiência de qualidade (QER) para identificar tendências de qualidade e confiabilidade, examine contra as metas definidas e relatá-out para os principais participantes na organização.                                                                                                                            | Mensalmente (semanalmente durante implantações) |               |
| Correção de unidade                      | Coordene os esforços de remediação em toda a organização baseada na descobertas e avaliações de QER.                                                                                                                                                                                                           | Conforme necessário                           |               |
| Atualizar dados de construção em CQD            | Atualizar ou adicionar novas definições de construção em CQD quando são feitas alterações à rede (veja [informações de construção de carregamento](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Conforme necessário                           |               |
| Preencher a função Champion(s) de qualidade      | Responsabilidade de ponta a ponta da qualidade na organização. Isso inclui:<ul><li>Certifique-se de que o QER está sendo conduzido regularmente.</li><li>Relatar o check-out para os principais participantes no status de qualidade.</li><li>Verifique se os dados de construção definições são até a data.</li><li>Coordene os esforços de remediação em toda a organização para garantir que os usuários tenham uma experiência de alta qualidade com equipes.</li></ul>          | Diariamente                               |               |



### <a name="references"></a>Referências 

[Saiba CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[Informações de construção de carregamento](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Qualidade da experiência Revise o guia](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gerenciar pontos de extremidade

Pontos de extremidade do Microsoft Teams podem ser definidos como qualquer PC, Mac, tablet ou dispositivo móvel (ou qualquer outro) executando o cliente de equipes. O *ponto de extremidade* do termo abrange não apenas o dispositivo em si, mas como um usuário se conecta ao dispositivo — por exemplo, usando o alto-falante ou microfone de internas do dispositivo, fones de ouvido com ou um headset otimizada. Depois que eles estiver implantados, os pontos de extremidade não devem ser esquecidos. Os pontos de extremidade de equipes exigem manutenção e atendimento médico em andamento. As seções a seguir descrevem as áreas específicas para focalizar em.

### <a name="endpoint-requirements"></a>Requisitos de ponto de extremidade

Um dos principais benefícios de equipes é que o cliente sejam mantido atualizado automaticamente. Os clientes no PC e Mac são atualizados usando um processo de plano de fundo que verifica se há novas compilações e baixa o novo cliente quando o aplicativo estiver ocioso. As equipes de aplicativos móveis são mantidos atualizados através de lojas seus respectivos app.

O cliente de equipes tem requisitos mínimos em termos da plataforma de software subjacente. Esses requisitos podem mudar ao longo do tempo e, portanto, é importante monitorá-los para que as alterações. Por exemplo, o cliente de equipes tem uma versão mínima iOS. Se o cliente usa um navegador da internet, o navegador deve ser mantido atualizado também. Uma lista das plataformas com suporte pode ser encontrada nos [Clientes obter para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

### <a name="endpoint-firewalls"></a>Firewalls do ponto de extremidade

Firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário.
Firewalls do lado do cliente podem afetar a qualidade da chamada e até mesmo impedir que uma chamada de sendo estabelecida. Depois que as exclusões apropriadas no firewall cliente tiverem sido configuradas, eles precisam ser mantidos atualizados com base nas informações em [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips). O fornecedor terceirizado terão específico orientação sobre como atualizar as exclusões.

### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Drivers de Wi-Fi podem ser problemáticos. Por exemplo, um driver pode ter muito agressivos comportamentos roaming entre os pontos de acesso que podem provocar desnecessário-ponto de acesso alternando, levando a qualidade de chamadas ruins. Um driver de Wi-Fi com desempenho insatisfatório pode ser descoberto por meio de uma análise de experiência de qualidade (consulte o [Guia de revisão do Quality of Experience](https://aka.ms/qerguide) para obter mais detalhes). Ele é essencial para implementar um processo orientado a qualidade que monitora novos drivers Wi-Fi e garante que eles estiver testados antes de serem implantadas à população geral do usuário.

### <a name="endpoint-management"></a>Gerenciamento de ponto de extremidade

Um catálogo de pontos de extremidade com suporte e dispositivos de interface (por exemplo, headsets) deve estar disponível e mantida. Esse catálogo incluirá uma lista de dispositivos aprovados que foram selecionados e validado como parte das fases envisioning e inclusão. Normalmente, os dispositivos específicos são selecionados para cada tipo de pessoa em sua organização e atenda às necessidades dos atributos dessa pessoa. Todos os pontos de extremidade tem um ciclo de vida e não há necessidade de gerenciar os contratos de fornecedor garantia, substituição, políticas de distribuição e reparar associadas a esses dispositivos.

### <a name="endpoint-troubleshooting"></a>Solução de problemas do ponto de extremidade

Mesmo que ter seguido as diretrizes anteriores, usuários em sua organização ainda podem encontrar problemas com equipes. Embora o problema pode não estar com o ponto de extremidade em si, os sintomas do problema são geralmente exibidos por meio do cliente para o usuário. As orientações a seguir é destinada a fornecer etapas gerais que pode ser executadas para resolver o problema; ele não tem deve ser um guia abrangente sobre solução de problemas. As etapas são fornecidas em uma ordem específica, mas eles não precisam ser seguidas explicitamente e talvez não sejam aplicáveis, dependendo da natureza do problema.

1.  **Validar a integridade do serviço:** O problema que um usuário pode estar apresentando pode estar relacionado a um evento que afeta negativamente o serviço de equipes ou seus serviços dependentes. Como uma primeira etapa, recomendamos que você confirme que não existem problemas serviço ativo. Consulte [como verificar a integridade do serviço Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    Lembre-se de verificar o status dos serviços dependentes (exemplos; Exchange, SharePoint, OneDrive for Business). Monitoramento de integridade do serviço é abordada em mais detalhes na seção **monitoramento de integridade do serviço.**

2.  **Validar a conectividade do cliente:** Problemas de conectividade causam funcionalidade ou problemas de login em equipes. É recomendável (especialmente para novos sites ou locais) validar a conectividade com o serviço. Certifique-se de que a seguinte diretriz de [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips) é seguida para cada site. Você pode aproveitar a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para executar um teste de conectividade para validar que as portas de mídia foram abertas corretamente para os recursos de voz de nuvem. Etapas detalhadas sobre como executar os testes de conectividade são fornecidas no guia de [Preparação da rede](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) .

3.  **Verifique a lista de problemas conhecidos:** Consulte a [lista de problemas conhecidos para equipes](https://docs.microsoft.com/MicrosoftTeams/known-issues) para determinar se o usuário foi afetado negativamente por um desses problemas. Siga a solução alternativa fornecida (se houver algum) para resolver o problema.

4.  **Visite a comunidade Microsoft Tech:** [Comunidade do Microsoft equipes Tech](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) oferece espaços dedicados para equipes. A comunidade de equipes fornece uma lista de discussão, postagens de blog e centralizados em torno de equipes de comunicados. Você pode postar uma pergunta ou discussões anteriores para soluções de pesquisa ao seu problema.

5.  **Entre em contato com o suporte da Microsoft:** Você pode contatar o Microsoft Support para problemas com equipes online ou por telefone. Para obter informações, consulte [suporte para as equipes da Microsoft do contato](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    Para Premier clientes, suporte a solicitações podem ser iniciadas seguindo as orientações em [Contatar o suporte para as equipes da Microsoft (clientes Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diariamente/semanalmente/mensal/conforme necessário

| Atividade                 | Descrição                                                                                                                                                                                                                                                                                                                                                                     | Cadência   | Equipe atribuído |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Requisitos de ponto de extremidade    | Certifique-se de que o ponto de extremidade das equipes continua a atender a todos os requisitos de software para equipes [obter clientes para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).                                                                                                                                                                                       | Mensal   |               |
| Firewalls do ponto de extremidade       | Manter as exclusões apropriadas no ponto de extremidade firewall com base nas informações no artigo [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips) . O fornecedor terceirizado terão orientação específica para como manter as exclusões. Assine o [RSS feed](https://support.office.com/en-us/o365ip/rss) para ser notificado automaticamente das alterações. | Conforme necessário |               |
| Drivers de Wi-Fi            | Testar e atualizar os drivers de Wi-Fi no PC. Valide os resultados usando CQD ([Guia de revisão do Quality of Experience](https://aka.ms/qerguide)).                                                                                                                                                                                                                                                                   | Conforme necessário |               |
| Gerenciamento de ponto de extremidade      | Manter o catálogo de pontos de extremidade com suporte e dispositivos de interface (por exemplo, headsets). Gerenciar contratos de fornecedores, garantia, distribuição, substituição e reparar políticas.                                                                                                                                                                                                        | Mensal   |               |
| Solução de problemas do ponto de extremidade | Tarefas de solução de problemas pode incluir; Verificando a conectividade, a lista de problemas conhecidos, log de coleta, análise e escalonamento para o Microsoft Support ou fornecedores terceirizados de consultoria.                                                                                                                                                                                               | Conforme necessário |               |

### <a name="references"></a>Referências 

[URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips)

[Obter clientes para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients)

[Comunidade de tecnologia do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Problemas conhecidos para equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/known-issues)

[Verificar a integridade do serviço para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/service-health)

[Contatar o suporte do Office 365 para empresas - Ajuda para Administradores](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&rs=en-US&ad=US)

[Contato Premier](https://support.microsoft.com/premier/contacts)

[Vídeo de equipes de solução de problemas](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gerenciar equipes

Depois que o serviço Microsoft Teams tiver sido implantado, você precisará executar várias atividades relacionadas a sua administração. O intervalo de atividades de administrando o serviço e a usuários individuais para o planejamento de capacidade e o provisionamento de licenciamento e números de telefone. As seções a seguir abordam algumas dessas tarefas comuns de administração.

### <a name="service-administration"></a>Administração do serviço

O serviço de equipes tem várias configurações que podem ser configuradas todo o inquilino.
Alterações feitas nas configurações de locatário afetam todos os usuários que tiverem sido habilitados para equipes. Para obter uma lista detalhada dessas configurações, consulte [ativar os recursos de equipes da Microsoft em sua organização do Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365).

### <a name="user-administration"></a>Administração do usuário

Para suportar usuários, uma organização pode exigir qualquer número de tarefas relacionadas — as tarefas específicas variam de uma organização para a próxima. Por fim, essas tarefas precisam ser gerenciados por uma equipe de suporte que tenha sido atribuída a essas tarefas operacionais. As seguintes tarefas comumente são necessárias para oferecer suporte a usuários em equipes.

#### <a name="general-tasks"></a>Tarefas gerais

[Gerenciar o acesso do usuário aos Teams da Microsoft](https://docs.microsoft.com/microsoftteams/user-access)

#### <a name="common-tasks-for-phone-system"></a>Tarefas comuns para o sistema telefônico

[Atribuir, alterar ou remover o número de telefone de um usuário](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user)

[Atribuir ou alterar o endereço de emergência de um usuário](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Adicionar, alterar ou remover um local de emergência para sua organização](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Criar e gerenciar planos de discagem](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)

#### <a name="common-tasks-for-audio-conferencing"></a>Tarefas comuns para conferência de áudio

[Alterar as configurações de uma ponte de audioconferência](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge)

[Alterar os números de telefone de sua ponte de audioconferência](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge)

[Gerenciar as configurações de audioconferência de um usuário](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/manage-the-audio-conferencing-settings-for-a-user)

[Redefinir o PIN de audioconferência de um usuário](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/reset-the-audio-conferencing-pin-for-a-user)

### <a name="license-management"></a>Gerenciamento de licença

Que sua organização cresce ou contrai, é importante que você planeje licenciamento para necessidades atuais e futuras. Não há uma licença de equipes base, além de licenciamento para recursos de voz de nuvem ([Sistema de telefonia](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system?ui=en-US&rs=en-US&ad=US) e [Conferência de áudio](https://products.office.com/skype-for-business/audio-conferencing)).

Para equipes, as licenças de sistema telefônico exigem licenças [Chamar planejar](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365) associadas. Chamar o plano de licenciamento permite fazer e receber chamadas de telefone internacionais e/ou domésticas. Esses planos são baseados em uso e tem pools minutos associados a eles. Provisionamento [Communications créditos](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) garantirá que você nunca executar fora de serviço.

Serviços de audioconferência permite a conferência discada tolled e serviços de conferência de discagem domésticas. Conferência discada gratuita ou não-doméstico cenários de discagem podem causar a incorrer em encargos adicionais para os quais [Comunicações créditos](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) são necessários.

Comunicações créditos podem suplementar licenças chamar planejar e conferência de áudio. Chamar planejar licenças e a comunicação créditos são baseados em uso e, portanto, devem ser monitorados e provisionado para adequadamente.

Você pode aproveitar o [relatório de uso do PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) para ajudá-lo a monitorar o uso de chamar planejar minutos e créditos de comunicações. Com base nos resultados dessa atividade, você pode ajustar seu licenciamento de acordo. Em breve, podemos oferecerá um relatório de [pool minuto do PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) para ajudá-lo com mais eficiência com esta tarefa.

### <a name="telephone-number-management"></a>Gerenciamento de número de telefone

Há dois métodos para adquirir números em equipes: porta de números de telefone do outro provedor, ou você pode provisionar os números diretamente do inventário de número da Microsoft. Esses dois métodos são descritos na [Getting números de telefone para seus usuários](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).

Não há um limite para a quantidade de números de telefone, que você pode provisionar do estoque de número da Microsoft. Os limites são determinados por um número de fatores detalhados nos [números de telefone de quantos você pode obter](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get).
Os limites dependem do tipo de números — gratuito números de serviço, números de serviço tarifados e números de telefone do assinante (usuário). Cada uma tem seus próprios limites e deve ser gerenciada de forma independente. Se você está se aproximando do limite (ou se você tiver atingido o limite), você pode aplicar um incremento ao limite. Esse processo é descrito no artigo acima.

Pode haver momentos quando um número não está disponível para ser provisionado em uma região onde o serviço está disponível. Para obter informações sobre o processo para números solicitantes, consulte [gerenciar números de telefone para sua organização](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Criação de equipe (opcional)

Por padrão, todos os usuários com uma caixa de correio no Exchange Online tem permissões para criar grupos de Office 365 e, portanto, uma equipe no Microsoft Teams. Se você quiser ter controle rigoroso e [restringir a criação de novas equipes](https://docs.microsoft.com/MicrosoftTeams/assign-roles-permissions#permissions-to-create-teams) (e, portanto, a criação de novos grupos do Office 365), você pode delegar a criação de grupos e direitos de gerenciamento para um conjunto de administradores. Se sua organização deseja buscar a essa opção, consulte o processo descrito neste artigo para permitir que os usuários enviem solicitações são processadas por uma equipe atribuída.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tarefas diariamente/semanalmente/mensal/conforme necessário

| Atividade                    | Descrição                                                                                                                                                                                                                                                                                                                                                                                                             | Cadência   | Equipe atribuído |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Administração do serviço      | Administração de configurações de equipes de todo o inquilino.                                                                                                                                                                                                                                                                                                                                                                           | Conforme necessário |               |
| Administração do usuário         | Administração de configurações do usuário e as equipes de licenciamento.                                                                                                                                                                                                                                                                                                                                                           | Conforme necessário |               |
| Gerenciamento de licença          | Planejar as necessidades atuais e futuras para o usuário e o licenciamento baseado em consumo (chamar planos e créditos de comunicação) utilizando o relatório de [relatório de uso PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) e [pool minuto do PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Por semana    |               |
| Gerenciamento de número de telefone | Gerenciar os números de telefone disponíveis para o crescimento futuro e ajustar os níveis de inventário para atender às suas necessidades organizacionais.                                                                                                                                                                                                                                                                                                | Por semana    |               |
| Criação de equipe (opcional)    | Solicitações de revisão e processo para criação de equipe.                                                                                                                                                                                                                                                                                                                                                                          | Conforme necessário |               |

<!--ENDOFSECTION-->

## <a name="quality-of-experience-review-guide"></a>Qualidade da experiência Revise o guia
A qualidade de experiência Revise o guia tem um conjunto de atividades que avaliar e oferecem orientação de remediação em áreas principais que têm um impacto maior para melhorar a experiência do usuário, conforme mostrado na figura a seguir.

![As principais áreas para examinar durante uma qualidade de experiência revisão: áudio, a confiabilidade e resultados de pesquisa do usuário.] (media/plan-my-service-management-image2.png "As principais áreas para examinar durante uma qualidade de experiência revisão: áudio, a confiabilidade e resultados de pesquisa do usuário.")

Continuamente avaliando e correção as áreas descritas neste documento, você pode reduzir seu potencial para afetar negativamente a experiência do usuário. A maioria dos problemas de experiência do usuário encontrados em uma implantação podem ser agrupados nas seguintes categorias:

-   Configuração de firewall ou proxy incompleta

-   Baixa cobertura de Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Uso de dispositivos de áudio não otimizados ou internos

-   Sub-redes problemáticos ou dispositivos de rede

As diretrizes fornecidas no guia de revisão de experiência de qualidade enfoca usando Online do painel de controle de qualidade de chamada (CQD) como a ferramenta principal para relatar e investigar cada área descrita, com foco para maximizar a adoção e o impacto de áudio. Otimizações de feitas à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.

É altamente recomendável que você designar desde o início do campeão de qualidade. Depois que está sendo indicado, eles devem iniciar podem se familiarizar com o conteúdo no [Revise o guia de qualidade da experiência](https://aka.ms/qerguide).

<!--ENDOFSECTION-->