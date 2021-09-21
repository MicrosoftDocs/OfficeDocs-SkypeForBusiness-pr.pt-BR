---
title: Planejar o gerenciamento do ciclo de vida
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Neste artigo, você aprenderá como planejar a implementação dos recursos de gerenciamento do ciclo de vida no Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fa4d2cfa493ae6bec4429db9c3d01319d889288e
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456371"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Planejar o gerenciamento de ciclo de vida no Teams

O Teams fornece um conjunto avançado de ferramentas para implementar processos de gerenciamento de ciclo de vida de colaboração para sua organização. Este artigo orienta os profissionais de TI por meio das perguntas certas para determinar seus requisitos de gerenciamento de ciclo de vida e as ferramentas a serem usadas para atendê-los. 

É importante planejar o gerenciamento de ciclo de vida, pois isso significa que você está criando um plano para realizar o trabalho com eficiência. A maioria dos projetos consiste em início, meio e fim. Isso também se aplica às equipes, mas elas podem ser criadas e usadas de várias maneiras. Por isso, nem sempre é óbvio em qual estágio do ciclo de vida elas estão. Ter um plano para o gerenciamento do ciclo de vida ajudará você a acompanhar os projetos de sua organização enquanto eles percorrem esses estágios.

> [!Tip]
> Assista à seguinte sessão para saber mais sobre o ciclo de vida no Microsoft Teams: [Governança, gerenciamento e ciclo de vida no Microsoft Teams](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>Conceitos de ciclo de vida

Os conceitos e as definições a seguir afetam as decisões que você toma para o gerenciamento de ciclo de vida.

**Microsoft Teams**

Uma _equipe_ é um conjunto de pessoas, conteúdo e ferramentas que possibilitam a colaboração. Uma equipe define quem são seus membros e as permissões e as políticas que se aplicam a eles. As equipes são criadas com o Microsoft 365 Groups e as alterações feitas na assinatura de grupo do Microsoft 365 devem ser sincronizadas com a equipe. Assim como outros Grupos do Microsoft 365, o Teams é provisionado automaticamente com uma caixa de correio do Exchange, um site do SharePoint, um bloco de anotações do OneNote e outros ativos do Microsoft 365 ou Office 365. Saiba mais sobre os [Grupos do Microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Canais**

Canais são os espaços de colaboração em uma equipe nos quais o trabalho real é feito. Cada canal representa um tópico ou fluxo de trabalho diferente na equipe geral. Para cada canal, uma pasta é criada automaticamente no site do SharePoint para armazenar todos os arquivos compartilhados do canal. Assim, os usuários podem localizar e trabalhar mais facilmente com os documentos mais importantes. Os canais também podem ser ampliados com aplicativos que são relevantes para um fluxo de trabalho específico. Por exemplo, você pode adicionar um painel do Power BI a um canal para acompanhar o êxito de um aspecto do projeto.

**Tipos de acesso de equipe**

Determinam quem pode ingressar na equipe:

-   As equipes _privadas_ estão restritas aos membros da equipe aprovados pelo(s) proprietário(s) dela. Essa é uma configuração típica para equipes de projeto e equipes virtuais em uma grande organização.
-   As equipes _públicas_ são abertas para que qualquer pessoa na organização ingresse nelas diretamente. Isso é útil para colaboração em tópicos de interesse geral para pessoas de vários departamentos que trabalham em diferentes projetos. Essa é uma boa configuração padrão para organizações menores.

**Tipos de usuários de equipes e funções administrativas** 

Os tipos de usuários da equipe determinam o grau de controle que cada membro da equipe tem:

-   O *criador da equipe* tem permissões para criar um grupo ou uma equipe no diretório. O administrador pode restringir esse tipo de usuário a um subconjunto de administradores ou usuários. Para obter mais informações, confira [Gerenciar quem pode criar Grupos do Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). Os criadores da equipe tornam-se automaticamente proprietários da equipe.
-   O *Proprietário da equipe* gerencia a afiliação e as configurações da equipe. Pode haver até 100 proprietários de equipe por equipe.
-   Um *membro da equipe* é um membro de sua organização que participa de uma equipe.
-   Um *convidado* é um usuário que é externo à sua organização. Qualquer pessoa com um endereço de email poderá ser convidada se a organização tiver habilitado o [acesso de convidado](guest-access.md).

> [!Note]
> Saiba mais sobre os recursos de proprietário de equipe e de membro de equipe no artigo [Atribuir função e permissões no Microsoft Teams](assign-roles-permissions.md).

As funções de administrador de equipe determinam quais recursos cada detentor da função de administrador tem. Estes são descritos no artigo a seguir: [Use funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md).

## <a name="it-decisions-to-make-before-getting-started"></a>Decisões de TI a serem tomadas antes de começar

Antes de distribuir o Teams a sua organização, implemente as políticas de governança que a organização considerou necessárias. Elas podem incluir convenções de nomenclatura, políticas de expiração, políticas de retenção e muito mais. De modo geral, é muito mais fácil implementar esses requisitos antes de realizar a implantação em toda a organização.

Para obter mais informações, confira [Planejar a governança no Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Etapas do ciclo de vida das equipes

De modo geral, uma equipe possui uma finalidade que está alinhada a um projeto ou para atingir um objetivo. Mesmo que uma equipe tenha sido formada com base em um interesse compartilhado, a associação com a equipe provavelmente mudará ao longo do tempo e a discussão poderá ficar obsoleta, apenas para aparecer novamente de uma maneira um pouco diferente em uma equipe diferente.

Cada equipe tem um começo, quando ela é criada e os canais são configurados; um meio, quando a equipe é usada e a colaboração ocorre para corresponder ao ritmo do fluxo de trabalho; e, às vezes, um fim, quando a equipe conclui seu propósito e chega ao fim da vida útil. 

Para obter mais informações, confira [Gerenciar equipes no Centro de administração do Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Etapa 1: início

#### <a name="create-the-team"></a>Criar a equipe

A primeira etapa é definir o objetivo da equipe. Ele pode consistir em processos de negócios, na estrutura organizacional de projetos ou apenas na criação de um hub de colaboração aberto e não estruturado. A definição do objetivo da equipe está vinculada à identificação das pessoas certas. Na medida do possível, é recomendável promover a colaboração aberta, buscando uma associação ampla. 

Os proprietários da equipe convidam membros, definem a imagem e a descrição da equipe e podem definir permissões para membros individuais. 

> [!Tip]
>  O ideal é selecionar pelo menos dois proprietários para a equipe. Assim, ela estará coberta em caso de ausência ou reatribuição.

#### <a name="team-origins"></a>Origens da equipe

As equipes podem ser criadas por meio de diversos métodos:

-   Crie a equipe do zero. Adicione membros usando pseudônimos de e-mail ou nomes de usuário individuais, ou expanda uma lista de distribuição.
-   Crie a equipe com base em uma equipe existente e use sua configuração de canal e qualquer configuração de aplicativo como modelo. Opcionalmente, você também pode usar sua lista de associação.
-   Adicione uma equipe a um grupo existente do Microsoft 365, o qual também fornece à equipe acesso à sua caixa de correio e ao site do SharePoint.
-   Use as APIs do Microsoft Graph Teams ou os cmdlets do PowerShell para criar equipes. As APIs podem criar equipes de forma programática com base nos atributos do Livro de Endereços Global (como região ou departamento) ou processos de negócios (compromissos de cliente ou lista de participação em sala de aula, por exemplo).

Use estes links para obter mais informações sobre como organizar as equipes:

-   [Práticas recomendadas para organizar equipes no Teams](best-practices-organizing.md)
-   [Implantar chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Implantar reuniões e conferências](deploy-meetings-microsoft-teams-landing-page.md)
-   [Implantar o Cloud Voice](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão.](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Qual é o objetivo da equipe?</li><li>Quem pertence à equipe?</li><li>A equipe será privada ou pública?</li><li>Os novos membros podem adicionar a si mesmos ou os proprietários da equipe devem adicioná-los?</li><li>Quem terá permissões para criar canais ou adicionar guias, bots e conectores?</li></ul> |
| ![Um ícone representando os próximos passos.](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Crie a equipe.</li><li>Planeje canais.</li></ul>|


#### <a name="set-up-channels"></a>Configure canais

Qualquer proprietário ou membro de equipe com permissões apropriadas pode criar canais em uma equipe. É importante considerar o objetivo de cada canal. As opções incluem colaboração em torno a projetos, discussões de tópicos ou áreas de interesse comum. Por padrão, todas as equipes incluem um canal Geral. A maioria das equipes precisa de mais do que isso, e os membros criarão canais adicionais. É provável que o conjunto de canais cresça organicamente à medida que novos tópicos ou projetos surjam, e as discussões possam superar o canal em que começaram.

Para despertar interesse, o proprietário do canal pode postar uma mensagem de boas-vindas, carregar documentos relevantes na guia **Arquivos** ou adicionar guias ou conectores ao canal. O proprietário também define a descrição do canal e pode "marcar automaticamente" canais importantes para que sejam listados por padrão para todos os membros da equipe.

Considere os nomes dos canais antes de criá-los, pois renomear um canal na equipe não renomeia a pasta correspondente na biblioteca de documentos do Microsoft Office SharePoint Online, o que pode causar confusão para o usuário final. 

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão.](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Que canais iniciais serão adicionados à equipe?</li><li>Que diretrizes, se houver, serão fornecidas para a adição de novos canais? (Eles serão configurados por projeto, por tópico ou...?)</li></ul> |
| ![Um ícone representando os próximos passos.](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Crie canais iniciais.</li><li>Poste uma mensagem de boas-vindas.</li><li>Comece a colaborar.</li></ul>|

### <a name="stage-2-middle"></a>Estágio 2: meio

À medida que o trabalho em equipe começa, a associação à equipe provavelmente começa a evoluir, juntamente com a hierarquia de canais. A menos que a equipe precise ser estritamente controlada e bloqueada, é recomendável incentivar a exploração, mesmo que isso leve a impasses. À medida que os usuários se sentirem mais à vontade, poderão experimentar menções de \@equipe, marcar canais como favoritos e usar o canal Geral para se familiarizarem com as postagens. Cada equipe é diferente. Deixe que o uso oriente a evolução do design. Monitore o uso e a integridade da equipe por meio dos recursos de relatórios do Teams.

A confiança, a tolerância e o espírito de colaboração aumentarão gradativamente, à medida que as comunicações dos grupos-chave forem iniciadas e mantidas no Teams. Os membros da equipe veem a utilidade das conversas em grupo, em comparação com os chats entre duas pessoas. Equipes individuais tendem a desenvolver sua própria personalidade, auxiliadas por recursos divertidos, como Giphys e figurinhas. Ao mesmo tempo, é importante que o comportamento nocivo ou rude seja desencorajado sempre que ocorrer.

Como as equipes são em forma de vida, ocasionalmente, elas precisam de verificação e de cuidado. Essas são algumas práticas recomendadas:

- Use defensores para manter o uso, se ele começar a diminuir, e também para descobrir e propagar novos comportamentos criativos. 
- Gerencie os convidados criteriosamente, garantindo que o acesso deles seja encerrado quando a necessidade de negócios terminar.
- Incentive os membros a usar conversas encadeadas com linhas de assunto para melhorar a visibilidade e atenção ao rolar por um canal.
- Permita que os canais evoluam junto com as necessidades de negócios. Adicione novos canais conforme necessário e deixe que os antigos desapareçam (ou considere arquivá-los ou excluí-los, se eles contiverem dados confidenciais ou efêmeros, com base em seus requisitos de retenção).
- Crie novas equipes à medida que surgirem grupos ou áreas de interesse maiores.
- Experimente diferentes colaborações de canal, como reuniões de canal ou conversas de guias referentes a documentos.
- Use o aplicativo móvel Microsoft Teams para aumentar o engajamento.

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão.](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Quem monitorará o uso para identificar problemas?</li><li>Que métricas serão usadas para determinar a integridade de uma equipe?</li><li>Identifique equipes que chegaram ao fim de sua vida útil.</li><li>Identifique equipes não íntegras que ainda servem a um propósito, mas precisam ser revigoradas.</li></ul> |
| ![Um ícone representando o passo seguinte.](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Implemente um processo para monitorar a integridade de equipes individuais.</li></ul>|

### <a name="stage-3-end"></a>Etapa 3: fim

Quando o trabalho de uma equipe chega ao fim, é importante reconhecer formalmente que terminou. Assim, os membros da equipe são informados do encerramento. Além disso, é impedido o acesso a informações desatualizadas e obsoletas. Você pode usar a própria equipe para realizar tarefas de encerramento, como post-mortem e resumos executivos.

Você pode excluir equipes que você sabe que não precisa (por exemplo, uma equipe criada exclusivamente para testes ou uma equipe que contenha dados confidenciais). Na verdade, as equipes são excluídas com uma "exclusão temporária" que a TI pode reverter por até 30 dias. A exclusão de equipes não afeta os chats nem o conteúdo retidos de acordo com as políticas de conformidade. Os canais também têm uma "exclusão reversível" e podem ser revertidos por até 21 dias após a exclusão. Excluir um canal não excluirá a pasta ou seu conteúdo da biblioteca de documentos do Microsoft Office SharePoint Online.

Você também pode usar as políticas de expiração e retenção, além de recursos de arquivamento, para reduzir a exposição de equipes que não estão mais ativas ou cujos proprietários deixaram a organização.

As políticas de retenção aplicadas a equipes ou serviços associados, como o Microsoft Office SharePoint Online, podem proibir a exclusão de equipes. Além disso, considere que o conteúdo de uma equipe geralmente é mais do que apenas arquivos na biblioteca de documentos do Microsoft Office SharePoint Online; são conversas, painéis do Microsoft Planner, wikis, resultados de formulários, reuniões gravadas, blocos de anotações do Microsoft OneNote e vários outros.

Para obter informações sobre como configurar políticas de expiração e retenção, confira [Visão geral de segurança e conformidade no Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão.](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Defina como é o fim da vida útil de uma equipe.</li><li>Decida se deseja manter o conteúdo de uma equipe disponível e por quanto tempo.</li></ul> |
| ![Um ícone representando os próximos passos.](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documente as práticas recomendadas e as lições aprendidas.</li><li>Arquive os dados, se necessário.</li></ul>|

## <a name="related-topics"></a>Tópicos relacionados

[Início rápido de governança para Teams](teams-adoption-governance-quick-start.md)
