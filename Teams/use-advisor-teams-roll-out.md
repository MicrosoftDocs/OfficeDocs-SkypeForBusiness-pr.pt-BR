---
title: Use o Assistente do Teams para ajudá-lo na implantação do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: pkrebs
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
- m365initiative-deployteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
description: Utilize o Advisor for Teams para ajudá-lo a planejar e concluir a implementação do Microsoft Teams.
ms.openlocfilehash: b05567eb17d878d297be1900425e51760341389a
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045590"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Use o Assistente do Teams para ajudá-lo na implantação do Microsoft Teams

O Advisor for Teams orienta você durante a implementação do Microsoft Teams.. Ele avalia o ambiente da organização do Microsoft 365 e identifica as configurações mais comuns que você pode precisar atualizar ou modificar antes de implementar o Teams com êxito. Em seguida, o Assistente do Teams cria uma Equipe de implantação (no Teams), com canais para cada carga de trabalho que você deseja implantar. Cada carga de trabalho da Equipe de implantação vem com um plano abrangente do Planner que inclui todas as tarefas de implantação para cada carga de trabalho.  Ao usar o plano do Planner, você atribuirá tarefas às pessoas responsáveis por cada fase da implementação, incluindo o gerente de projeto, administradores de serviço do Teams, pessoas de suporte e sua equipe de adoção e prontidão do usuário. Cada tarefa de implantação contém todas as orientações e recursos necessários para concluir a tarefa com êxito.

O Assistente do Teams faz parte do [centro de administração do Teams](https://admin.teams.microsoft.com). No mínimo, você precisará de uma licença do Microsoft 365 Business Basic para que possa aproveitar as vantagens da integração do Advisor for Teams com o Forms e o Planner. Para usar o Assistente do Teams, clique no botão **Iniciar** no widget de **Implantação da Carga de Trabalho do Teams** no Painel. Ou vá para **Planejamento** > **Teams Advisor**.

> [!IMPORTANT]
> O Advisor for Teams não está disponível para a implementação do Microsoft 365 Government (GCC High ou DoD).

Para obter uma visão geral dirigida da experiência do Assistente do Teams, confira o vídeo do Microsoft Mechanics [Implantar & Configurar o Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50).

## <a name="using-advisor-for-teams"></a>Utilizando o Advisor for Teams

**As licenças do Teams, Forms e Planner são necessárias para usar o Assistente do Teams.** No entanto, não é necessário ser um administrador do Teams para usar o Assistente do Teams, qualquer pessoa em sua organização pode usá-lo. Configuramos permissões especiais para que usuários não administradores possam acessar o Assistente do Teams, mesmo que seja no centro de administração do Teams. Você PRECISA ser Administrador do Teams, Administrador de Serviços do Teams ou Administrador Global para abrir as avaliações de prontidão dos locatários (isso ocorre porque as funções especiais não administrativas não possuem acesso às APIs do Microsoft Graph, subjacentes às avaliações).

> [!IMPORTANT]
> Se o **Teams Advisor** estiver ausente em **Planejamento** no centro de administração do Teams, isso significa que o usuário não está licenciado para o Teams.

Na primeira vez em que você usar o Assistente do Teams, ele criará uma equipe de Implantação no Teams. Ele adiciona um canal para cada carga de trabalho selecionada.

> [!IMPORTANT]
> Se uma equipe de implementação já tiver sido criada e um usuário diferente tentar criá-la, ele receberá um erro solicitando que entre em contato com a equipe de suporte. Isso impede que o Teams, involuntariamente, divulgue informações sobre a equipe existente e seus membros. Peça ajuda ao proprietário da equipe de Implantação para adicioná-lo, ou entre em contato com o suporte para obter ajuda.

## <a name="available-advisor-for-teams-plans"></a>Planos de Assistente do Teams Disponíveis

O Advisor for Teams oferece atualmente os seguintes planos:

1. Bate-papo, equipes, canais e aplicativos
    - Avaliação do locatário
    - Plano do Planner, incluindo tarefas de adoção
    - Pesquisa de usuário do Forms
    - Assistente para o bot do Teams
1. Reuniões e conferências
    - Avaliação do locatário
    - Plano do Planner, incluindo tarefas de adoção
    - Pesquisa de usuário do Forms
    - Assistente para o bot do Teams
1. Atualização do Skype for Business
    - Avaliação do locatário
    - Plano do Planner, incluindo tarefas de adoção
    - Pesquisa de usuário do Forms
    - Assistente para o bot do Teams
    - Projetado para clientes que estão usando o Skype for Business Online ou o Skype for Business local, o plano de atualização do Skype for Business ajudará você a entender melhor sua jornada de atualização. Aproveitando uma estrutura comprovada de sucesso para implementar mudanças, o plano orientará você no processo passo a passo, esteja você começando a usar o Teams, já usando o Teams com o Skype for Business, ou estando pronto para a atualização.  O plano também conectará você às [diretrizes online e práticas recomendadas](./upgrade-start-here.md), [ativos para download](https://aka.ms/UpgradeSuccessKit), [live 1: muitos workshops de planejamento](./upgrade-workshops-landing-page.yml)e recursos adicionais para dar suporte ao seu sucesso.
1. Educação (visível apenas para Organizações Educacionais)
    - Avaliação do locatário
    - Plano do Planner, incluindo tarefas de adoção
    - Pesquisa de usuário do Forms
    - Assistente para o bot do Teams
    - Projetado para organizações educacionais, o Plano de Educação ajudará você a implantar, adotar e gerenciar o Teams em sua instituição de educacional.

Para organizações comerciais, recomendamos que você comece com o plano de Chat, equipes, canais e aplicativos. Para organizações educacionais, recomendamos que você comece com o Plano de Educação. Quando terminar de implantar a carga de trabalho, volte ao Assistente do Teams e selecione **Adicionar canal** para iniciar a próxima carga de trabalho.



## <a name="tenant-assessment"></a>Avaliação do locatário

Cada plano inclui uma avaliação de prontidão do locatário, que você pode usar para identificar rapidamente os aspectos do seu ambiente que talvez precisem ser remediados antes de implantar o Teams. As avaliações incluem pré-requisitos e práticas recomendadas. Todos os testes de avaliação terão uma marca de seleção verde ou um triângulo de aviso laranja.

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Uma marca de seleção verde significa que o locatário passou por um teste específico.
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Um triângulo de aviso laranja significa que sugerimos que você faça um acompanhamento para determinar se alguma ação é necessária (por exemplo, uma política de expiração do Grupo do Microsoft 365 é recomendada, mas não obrigatória).

> [!IMPORTANT]
> Quando um usuário com uma função Administrativa inicia o Assistente do Teams, todas as avaliações são executadas em segundo plano. Se você atualizar ou corrigir algo, isso pode não ser refletido em suas avaliações por até 24 horas.

As seções a seguir descrevem cada avaliação, incluindo se algo é um pré-requisito ou prática recomendada, o que cada verificação de avaliação está fazendo e por que e as diretrizes para a correção, conforme necessário.

### <a name="assessment-tests-for-all-workloads"></a>Testes de avaliação de todas as cargas de trabalho

|Teste de avaliação  |O que ele informa  |
|---------|---------|
|Domínio personalizado configurado     |Se houver um domínio que não seja @onmicrosoft.com configurado para o locatário (por exemplo, @contoso.onmicrosoft.com). Você pode usar o domínio @onmicrosoft. com, é claro, ou - pode configurar um domínio personalizados, sua escolha. Para obter mais informações, leia [Adicionar um domínio ao Microsoft 365.](/microsoft-365/admin/setup/add-domain) |
|Licenças do Teams     |Esse é um pré-requisito - você **deve ter** licenças do Teams para implantar o Teams. Consulte o Microsoft Graph para ver se você tem licenças do Teams (com pelo menos uma licença disponível para atribuir). Para saber mais, leia a [descrição do serviço do Microsoft Teams](/office365/servicedescriptions/teams-service-description).    |
|Licenças do Exchange Online     |Se você tiver uma assinatura ativa com licenças disponíveis do Exchange Online. Embora o Exchange não seja necessário para a funcionalidade básica do Teams, a integração com o Exchange fornece uma experiência ideal para o Teams. Consulte o Microsoft Graph para analisar as assinaturas associadas ao seu locatário e valide se você tiver assinaturas com uma licença qualificada do Exchange Online (com pelo menos uma licença disponível para atribuir). Para obter mais informações, leia [Como o Exchange e o Teams interagem](exchange-teams-interact.md).    |
|Licenças do SharePoint Online     |Se você tiver uma assinatura ativa com licenças disponíveis do SharePoint Online. Recomendamos licenças do SharePoint Online por usuário para fornecer o OneDrive for Business para armazenamento de arquivos em chats. Consulte o Microsoft Graph para ver se você tem licenças do SharePoint Online (com pelo menos uma licença disponível para atribuir). Para obter mais informações, leia [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](./sharepoint-onedrive-interact.md).    |
|Acesso para convidado habilitado     |Se o [acesso para convidado](guest-access.md) estiver habilitado. O acesso de convidados permite convidar usuários externos para suas equipes. Confira [Colaborar com convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team) para um tutorial de como ativar o acesso de convidados no Teams; a lista de verificação inclui as configurações necessárias do Azure AD. |
|Acesso externo configurado     |Se o [acesso externo](manage-external-access.md) está habilitado. Por padrão, ele está habilitado, com Federação aberta. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Avaliações para chat, equipes, canais e aplicativos

Além dos [Testes de avaliação de todas as cargas de trabalho](#assessment-tests-for-all-workloads), as avaliações adicionais a seguir são executadas para o chat, as equipes, os canais e as cargas de trabalho de aplicativos:

|Teste de avaliação  |O que ele informa  |
|---------|---------|
|Política de nome de grupo do Microsoft 365 configurada     |Se os padrões de nomeação foram configurados para Grupos do Microsoft 365. A política de nomenclatura de grupos do Microsoft 365 permite que sua organização aplique uma estratégia de nomenclatura consistente para equipes criadas pelo usuário e se aplica também a outras cargas de trabalho de grupos (incluindo o Outlook, o SharePoint, o Planner e o Yammer). Esse teste consulta o Azure AD por meio do Microsoft Graph para verificar a existência de políticas de nomenclatura que se aplicam aos grupos do Microsoft 365. Para obter mais informações, leia [Política de nomenclatura dos grupos](/microsoft-365/admin/create-groups/groups-naming-policy).    |
|Política de Expiração de grupo do Microsoft 365 configurada     |Se uma Política de Expiração de Grupo foi definida para Grupos do Microsoft 365. Isso permite que sua organização remova automaticamente as Equipes inativas. Ela está desativada por padrão. Este teste consulta o Azure AD por meio do Microsoft Graph e relata se o valor foi modificado no padrão. Para obter mais informações, leia [Política de expiração de grupo do Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Avaliações de reuniões e conferências

Além dos [Testes de avaliação de todas as cargas de trabalho](#assessment-tests-for-all-workloads), as avaliações adicionais a seguir são executadas para as reuniões e as cargas de trabalho de conferências:

|Teste de avaliação  |O que ele informa  |
|---------|---------|
|Licenças de Audioconferência    |Se você tiver uma assinatura ativa com licenças de Audioconferência. Esse é um pré-requisito se você estiver implantando pontes de Audioconferência. Consulta o Microsoft Graph para ver se você tem licenças de audioconferência (com pelo menos uma licença disponível para atribuir). Para obter mais informações, leia [Licenciamento do complemento do Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Licenças de Stream     |Se você tiver uma assinatura ativa com licenças do Microsoft Stream disponíveis. Esse é um pré-requisito se deseja habilitar a Gravação da Reunião. Consulte o Microsoft Graph para ver se você tem licenças do Microsoft Stream (com pelo menos uma licença disponível para atribuir). Para obter mais informações sobre o Stream e sobre como habilitá-lo, leia [Gravação de reuniões na nuvem do Teams](cloud-recording.md).

### <a name="assessments-for-skype-for-business-upgrade"></a>Avaliações da atualização do Skype for Business

Além de [Testes de avaliação de todas as cargas de trabalho](#assessment-tests-for-all-workloads), a atualização do Skype for Business também inclui avaliações usadas no plano de reuniões e conferências.

### <a name="advisor-for-teams-bot"></a>Assistente para o bot do Teams

Depois que o Assistente do Teams a criar a equipe de Implantação, o bot do Assistente fornece a seguinte mensagem no canal Geral:

>**Bem-vindo à Equipe de implantação do Microsoft Teams!**
>  
>A finalidade dessa equipe é orientá-lo na implantação do Teams da organização, fornecendo todos os recursos necessários e fornecendo um espaço de colaboração para a equipe do projeto. Cada canal criado usando o Assistente do Teams inclui um passo a passo do plano do Planner e outros recursos, como uma pesquisa de usuários do Forms que pode ser usada durante a implantação. A qualquer momento, você pode voltar e revisar a avaliação de prontidão do locatário ou adicionar planos de carga de trabalho adicionais usando o Centro de administração do Teams.
>
>**Chamada para ação**
>
>- Se você não estiver familiarizado com o Teams ou o Planner, confira nosso [Passo a passo do Teams.](https://teamsdemo.office.com/) e assista aos [Vídeos de início rápido do Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).
>- Vá para a Equipe de implantação no Teams. Escolha seu canal de carga de trabalho (por exemplo, Chat, equipes, canais e aplicativos) e selecione a guia **Planner** para começar.
>
>Para saber mais sobre o Assistente do Teams, leia [Usar o Assistente do Teams para implantar o Microsoft Teams](use-advisor-teams-roll-out.md).
>

> [!IMPORTANT]
> O Bot do Supervisor para Teams é usado apenas para enviar uma mensagem de boas-vindas para sua equipe de Implementação. Nenhum dado adicional é coletado.

> [!IMPORTANT]
> O bot do Assistente do Teams está habilitado por padrão. Não desabilite-o se você usa ou planeja usar o Assistente do Teams.

## <a name="advisor-for-teams-and-microsoft-365-learning-pathways"></a>O Assistente do Teams e os roteiros de aprendizagem do Microsoft 365

[Os roteiros de aprendizagem do Microsoft 365](/office365/customlearning/) são uma solução de aprendizado sob demanda que você pode personalizar para treinar seus usuários e aumentar o uso e a adoção do Teams em sua organização. Use os roteiros de aprendizagem junto com o Assistente do Teams para fazer com que os usuários trabalhem rapidamente e aumentem a adoção.

Os roteiros de aprendizagem fornecem a você um modelo de site do SharePoint Online e a habilidade para criar facilmente um site de aprendizagem para os seus usuários. Você pode personalizar o portal de treinamento dos roteiros de aprendizagem para incluir conteúdo de suporte e treinamento específico às necessidades dos usuários. Use as playlists do Teams do catálogo online da Microsoft e adicione a sua.

Você pode criar um site de aprendizagem em roteiros de aprendizagem e, em seguida, adicioná-lo como uma guia do canal no Teams para acesso rápido e fácil pelos usuários.

Por exemplo, use o Assistente do Teams junto com os roteiros de aprendizagem para treinar o suporte técnico e os Campeões, e, em seguida, permita que os roteiros de aprendizagem deem suporte de treinamento aos usuários finais. Crie um site de aprendizagem para ajudar a integrar seu suporte técnico e Campeões no Teams, e, em seguida, adicione-o como uma guia para cada canal de carga de trabalho você está implementando. Seu suporte técnico e Campeões podem criar uma página de suporte no portal de treinamento de roteiros de aprendizagem com links e playlists personalizadas para oferecer suporte aos seus usuários no Teams. Esta página de suporte pode ser adicionada a um canal em qualquer equipe para ajudar a treinar seus usuários finais.

Esta é uma visão geral de como você pode usar o Assistente do Teams junto com os roteiros de aprendizagem.

### <a name="get-started-in-learning-pathways"></a>Introdução dos roteiros de aprendizagem

Para começar com os roteiros de aprendizagem, confira [Introdução aos roteiros de aprendizagem](/office365/customlearning/).

Para configurar uma nova solução de roteiros de aprendizagem em seu ambiente, consulte [Provisionar uma nova solução de roteiros de aprendizagem](/office365/customlearning/custom_provision).

### <a name="create-a-learning-plan"></a>Criar um plano de aprendizagem

#### <a name="plan-your-learning-content"></a>Planejar o conteúdo de aprendizagem

Antes de criar seu site em roteiros de aprendizagem, reserve algum tempo para revisar e coletar os recursos e capacidades de aprendizagem disponíveis para você. Com os roteiros de aprendizagem, você pode usar o conteúdo da página de treinamento do Microsoft 365 e adicionar o conteúdo que você cria para adaptar o site às suas necessidades exclusivas.

Para saber mais, consulte [Planejar o conteúdo dos roteiros de aprendizagem](/office365/customlearning/custom_plancontent) e [Recursos para dar suporte à sua força de trabalho remota](/office365/customlearning/custom_plancontent_remoteresources).

#### <a name="explore-teams-content-in-learning-pathways"></a>Explore o conteúdo do Teams em roteiros de aprendizagem

Os roteiros de aprendizagem fornecem a um site do SharePoint uma Web part que está conectada a um catálogo online. A página de treinamento do Microsoft 365, que hospeda a Web part, mostra todos os treinamentos disponíveis nos roteiros de aprendizagem. Dê uma olhada para se familiarizar com o que está disponível e como o conteúdo é organizado.

[Acesse o site de roteiros de aprendizagem](/office365/customlearning/custom_goto), selecione **Treinamento do Microsoft 365**, e, então, selecione **Microsoft Teams** para ver todas as playlists de treinamento do Teams no catálogo online. Selecione uma playlist e, em seguida, selecione os botões **Próximo** e **Anterior** para navegar por ela. Você também pode clicar na seta para baixo para exibir os conteúdos da playlist e ir para um tópico específico.

#### <a name="take-an-inventory-of-teams-learning-resources-in-your-organization"></a>Faça um inventário dos recursos de aprendizagem do Teams em sua organização

Revise o conteúdo de aprendizagem do Teams que já está disponível em sua organização. Por exemplo, você pode já ter desenvolvido treinamento personalizado de integração ou conteúdo de suporte do Teams. Seus ativos existentes do SharePoint podem ser misturados com o conteúdo da Microsoft em uma playlist para construir uma playlist direcionada para sua organização.

#### <a name="build-your-site-in-learning-pathways"></a>Crie seu site em roteiros de aprendizagem

O [Administrador do Centro de Recursos para o Sucesso](/office365/customlearning/custom_successcenter) em roteiros de aprendizagem fornece orientação e recursos para ajudá-lo a planejar e personalizar roteiros de aprendizagem em sua organização. Aprenda como [personalizar o site](/office365/customlearning/custom_overview), mostrar e ocultar conteúdo, criar playlists personalizadas e muito mais.

Para acessar o Administrador do Centro de Recursos para o Sucesso, na página Inicial dos recursos de aprendizagem, selecione **Administrador do Centro de Recursos para o Sucesso**.

#### <a name="add-your-site-to-teams"></a>Adicionar o seu site ao Teams

Quando seu site estiver pronto, adicione-o a um canal de qualquer equipe para acesso rápido e fácil.

1. No Teams, vá para a equipe e selecione um canal.
2. No topo da página do canal, selecione **+** (**Adicionar uma guia**).
3. Selecione **Páginas do SharePoint**, e, em seguida, selecione **Adicionar uma página de qualquer site do SharePoint**.
4. Cole a URL do site do seus roteiros de aprendizagem e, em seguida, selecione **Salvar**.

Para saber mais, consulte [Adicionar uma página do SharePoint ou lista para um canal do Teams](https://support.microsoft.com/office/add-a-sharepoint-page-or-list-to-a-channel-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).

### <a name="train-your-support-team"></a>Treine sua equipe de suporte

Use os recursos em seu site de roteiros de aprendizagem para integrar seu suporte técnico e Campeões ao Teams. Prepare-os com as ferramentas e informações de que precisam para oferecer suporte aos usuários no Teams.

Para obter orientação e recursos sobre como preparar seu suporte técnico e Campeões no Teams, consulte [Treinar sua organização](https://adoption.microsoft.com/microsoft-teams/#train-your-org) e [Construir Campeões](https://adoption.microsoft.com/microsoft-teams/#build-champions).

Como o contato principal para seus usuários para perguntas “como fazer”, seu suporte técnico e Campeões podem usar o site de roteiros de aprendizagem para treinar usuários e como uma alternativa para a criação de tíquetes de suporte. Incentive o suporte técnico e Campeões para [personalizar seu site de roteiros de aprendizagem](/office365/customlearning/) criando uma página de treinamento e suporte, e, em seguida, [adicione-a como uma guia a um canal ](#add-your-site-to-teams) em uma equipe de usuários para autoatendimento.

### <a name="drive-adoption"></a>Aumentar a adoção

Depois de personalizar o site e reunir seus planos de aprendizagem, considere como você aumentará a conscientização de seus usuários para incentivá-los a usar roteiros de aprendizagem para o aprendizado contínuo.

Use seus canais de comunicação para promover o site e gerar conscientização. Por exemplo, inclua um tipo de marcação padrão, como "Consulte nosso site de treinamento e suporte para saber como ser produtivo com o Teams" nas comunicações com os usuários.

Envolva os usuários destacando as maneiras como eles podem colaborar no Teams e, em seguida, direcione-os ao site de roteiros de aprendizagem para aprender como.

Confira esses recursos, que incluem orientações, kits de adoção, práticas recomendadas e muito mais, para ajudá-lo a implementar um plano de implantação e adoção bem-sucedido.  

- [Impulsione a adoção de roteiros de aprendizagem](/office365/customlearning/driveadoption)
- [Adotar o Microsoft Teams](adopt-microsoft-teams-landing-page.md)
- [Adotar recursos para o Teams](https://adoption.microsoft.com/microsoft-teams/)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quais são os requisitos de licenciamento para o Assistente do Teams?

No mínimo, você precisará do Microsoft 365 Business Basic para poder aproveitar o Assistente do Teams para integração com os Formulários e o Planner.

### <a name="can-i-delete-the-deployment-team"></a>Posso excluir a Equipe de implantação?

Depois que o Assistente do Teams tiver criado a Equipe de implantação, gerencie-a como qualquer outra equipe, incluindo a capacidade de excluí-la. Lembre-se de que, se você não excluir a equipe usando o centro de administração do Teams, o centro de administração do Teams relatará que a equipe ainda existe.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>Posso adicionar ou remover canais da Equipe de implantação?

Sim, uma vez que a Equipe de implantação foi criada, você gerenciará os canais da mesma maneira que em qualquer outra equipe.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>Posso adicionar ou remover membros na equipe do projeto na Equipe de implantação?

Sim, uma vez que a Equipe de implantação foi criada, você gerenciará da mesma maneira que em qualquer outra equipe.

### <a name="can-i-modify-the-planner-plans"></a>Posso modificar os planos do Planner?

Sim, depois que o Assistente do Teams tiver criado a Equipe de implantação, você deverá atualizar o plano do Planner para que ele dê um melhor suporte na implantação do Teams. Você pode modificar qualquer item (buckets, tarefas, detalhes da tarefa), como qualquer outro plano do Planner.

### <a name="can-i-modify-the-forms-survey"></a>Posso modificar a pesquisa do Forms?

Sim, depois que o Assistente do Teams tiver criado a Equipe de implantação, você poderá modificar a pesquisa do Forms, conforme necessário.

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>Existem diferenças entre o Assistente do Teams no GCC?

Sim, os Formulários de pesquisa do usuário são criados, mas não são fixados nos canais do plano, pois o aplicativo Teams Forms não está disponível no momento.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Quais informações o Assistente do Teams está coletando sobre minha organização?

O Assistente do Teams solicita o seu contrato para coletar informações não fazem parte da informações de identificação do usuário final (EUII). As informações coletadas estão na forma de telemetria que fornece comentários à Microsoft sobre a forma como o Assistente do Teams está impulsionando os resultados bem-sucedidos e onde talvez seja necessário melhorar o desempenho. Esses mesmos dados são usados para identificar oportunidades para a Microsoft se envolver proativamente com sua organização, podendo assim ajudar na implantação.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Posso usar o Assistente do Teams com o FastTrack?

Sim, o FastTrack aproveita o Supervisor para Teams de todos os clientes que procuram implementar o Teams. Eles podem ajudar com a configuração inicial da sua equipe de Implementação usando o Supervisor para Teams (se necessário) e também fornecer o suporte necessário para tópicos específicos durante a implementação do Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Posso usar o Assistente do Teams com um parceiro?

Sim, você pode usar o Assistente do Teams e, ao mesmo tempo, usar um parceiro de implantação para a implantação do Teams. Se o seu parceiro é um CSP e gerencia o locatário em seu nome, ele poderá usar o Assistente do Teams para criar a Equipe de implantação e ajudá-lo na execução geral do projeto. Além disso, você pode trabalhar com qualquer parceiro, adicionando-os como convidados na Equipe de implantação, para permitir que eles participem como membro da equipe geral do projeto.

### <a name="how-do-i-use-planner"></a>Como usar o Planner?

Confira a [Ajuda do Microsoft Planner](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) e os [Vídeos de início rápido do Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).

### <a name="how-do-i-use-forms"></a>Como posso usar o Forms

Vá para [Central de Ajuda do Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Tópicos relacionados

[Personalizar o supervisor do Teams](/office365/customlearning/custom_teamsadvisor)

[Como implantar o Teams](./deploy-overview.md)

[Práticas recomendadas para organizar equipes no Teams](best-practices-organizing.md)

[Nomes de produtos e identificadores de plano de serviço para licenciamento](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
