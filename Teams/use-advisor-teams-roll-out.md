---
title: Use o Assistente do Teams (visualização pública) para ajudar a implantar o Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ''
description: Use o Assistente do Teams (visualização pública) para ajudar a planejar e concluir a implantação do Microsoft Teams.
ms.openlocfilehash: 006ecf1563da153660902ac4c580253e50632867
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780800"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Use o Assistente do Teams para ajudá-lo na implantação do Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

O Assistente do Teams (visualização pública) orienta você na implantação do Microsoft Teams. Ele avalia o ambiente da organização do Office 365 e identifica as configurações mais comuns que talvez seja necessário atualizar ou modificar antes de poder implantar o Teams com êxito. Em seguida, o Assistente do Teams cria uma Equipe de implantação (no Teams), com canais para cada carga de trabalho que você deseja implantar. Cada carga de trabalho da Equipe de implantação vem com um plano abrangente do Planner que inclui todas as tarefas de implantação para cada carga de trabalho.  Usando esse plano do Planner, você atribuirá tarefas às pessoas responsáveis por cada fase da implantação, incluindo o gerente de projeto, os administradores do Teams e do Office 365, o pessoal do suporte e a equipe de adoção e preparação do usuário. Cada tarefa de implantação contém todas as orientações e recursos necessários para concluir a tarefa com êxito.

O Assistente do Teams faz parte do [centro de administração do Teams](https://admin.teams.microsoft.com). No mínimo, você precisará de uma licença do Microsoft 365 Business Basic para poder aproveitar o Assistente do Teams para integração com os Formulários e o Planner. Para usar o Assistente do Teams, clique no botão **Iniciar** no widget de **Implantação da Carga de Trabalho do Teams** no Painel. Ou vá para **Planejamento** > **Teams Advisor**.

> [!IMPORTANT]
> O Assistente do Teams não está disponível para implantações do Office 365 U.S. Government DoD ou GCC High.

Para obter uma visão geral dirigida da experiência do Assistente do Teams, confira o vídeo do Microsoft Mechanics [Implantar & Configurar o Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50).

## <a name="using-advisor-for-teams-public-preview"></a>Usando o Assistente do Teams (visualização pública)

**As licenças do Teams, Forms e Planner são necessárias para usar o Assistente do Teams.** No entanto, não é necessário ser um administrador do Teams para usar o Assistente do Teams, qualquer pessoa em sua organização pode usá-lo. Configuramos permissões especiais para que usuários não administradores possam acessar o Assistente do Teams, mesmo que seja no centro de administração do Teams. Você TEM que ser um administrador do Teams, Administrador de Serviços do Teams ou Administrador Global para abrir as avaliações de prontidão dos locatários (isso ocorre porque as funções especiais não administrativas não têm acesso às APIs do Microsoft Graph, subjacentes às avaliações).

> [!IMPORTANT]
> Se o **Teams Advisor** estiver ausente em **Planejamento** no centro de administração do Teams, isso significa que o usuário não está licenciado para o Teams. Esse comportamento será alterado no futuro.

Na primeira vez em que você usar o Assistente do Teams, ele criará uma equipe de Implantação no Teams. Ele adiciona um canal para cada carga de trabalho selecionada.

> [!IMPORTANT]
> Se uma equipe de Implantação já tiver sido criada e outro usuário tentar criá-la, receberá um erro pedindo que ele entre em contato com a equipe de suporte. Isso impede que o Teams, involuntariamente, divulgue informações sobre a equipe existente e seus membros. Peça ajuda ao proprietário da equipe de Implantação para adicioná-lo, ou entre em contato com o suporte para obter ajuda.

## <a name="available-advisor-for-teams-plans"></a>Planos de Assistente do Teams Disponíveis

Enquanto o Assistente do Teams está na visualização pública, fornecemos os dois planos a seguir:

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

Recomendamos que você comece com o plano de Chat, equipes, canais e aplicativos. Quando terminar de implantar a carga de trabalho, volte ao Assistente do Teams e clique em **Adicionar canal** para iniciar a próxima carga de trabalho.

## <a name="tenant-assessment"></a>Avaliação do locatário
Cada plano inclui uma avaliação de prontidão do locatário, que você pode usar para identificar rapidamente os aspectos do seu ambiente que talvez precisem ser remediados antes de implantar o Teams. As avaliações incluem pré-requisitos e práticas recomendadas. Todos os testes de avaliação terão uma marca de seleção verde ou um triângulo de aviso laranja. 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Uma marca de seleção verde significa que o locatário passou por um teste específico. 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Um triângulo de aviso laranja significa que sugerimos que você faça um acompanhamento para determinar se alguma ação é necessária (por exemplo, uma política de expiração do Grupo do Office 365 é recomendada, mas não obrigatória).

> [!IMPORTANT]
> Quando um usuário com uma função Administrativa inicia o Assistente do Teams, todas as avaliações são executadas em segundo plano. Se você atualizar ou corrigir algo, isso pode não ser refletido em suas avaliações por até 24 horas. Isso é temporário, assim que o Assistente do Teams deixar a visualização pública e estiver geralmente disponível, as avaliações serão atualizadas quase em tempo real.

As seções a seguir descrevem cada avaliação, incluindo se algo é um pré-requisito ou prática recomendada, o que cada verificação de avaliação está fazendo e por que e as diretrizes para a correção, conforme necessário.

### <a name="assessment-tests-for-all-workloads"></a>Testes de avaliação de todas as cargas de trabalho

|Teste de avaliação  |O que ele informa  |
|---------|---------|
|Domínio personalizado configurado     |Se houver um domínio que não seja @onmicrosoft.com configurado para o locatário (por exemplo, @contoso.onmicrosoft.com). Você pode usar o domínio @onmicrosoft. com, é claro, ou - pode configurar um domínio personalizados, sua escolha. Para obter mais informações, leia [Adicionar um domínio ao Office 365.](https://docs.microsoft.com/office365/admin/setup/add-domain) |
|Licenças do Teams     |Esse é um pré-requisito - você **deve ter** licenças do Teams para implantar o Teams. Consulte o Microsoft Graph para ver se você tem licenças do Teams (com pelo menos uma licença disponível para atribuir). Para obter mais informações, leia [Licenças do Office 365 do Microsoft Teams](https://docs.microsoft.com/microsoftteams/office-365-licensing).    |
|Licenças do Exchange Online     |Se você tiver uma assinatura ativa com licenças disponíveis do Exchange Online. Embora o Exchange não seja necessário para a funcionalidade básica do Teams, a integração com o Exchange fornece uma experiência ideal para o Teams. Consulte o Microsoft Graph para analisar as assinaturas associadas ao seu locatário e valide se você tiver assinaturas com uma licença qualificada do Exchange Online (com pelo menos uma licença disponível para atribuir). Para obter mais informações, leia [Como o Exchange e o Teams interagem](exchange-teams-interact.md).    |
|Licenças do SharePoint Online     |Se você tiver uma assinatura ativa com licenças disponíveis do SharePoint Online. Recomendamos licenças do SharePoint Online por usuário para fornecer o OneDrive for Business para armazenamento de arquivos em chats. Consulte o Microsoft Graph para ver se você tem licenças do SharePoint Online (com pelo menos uma licença disponível para atribuir). Para obter mais informações, leia [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact).    |
|Acesso para convidado habilitado     |Se o [acesso para convidado](guest-access.md) estiver habilitado. O acesso de convidados permite convidar usuários externos para suas equipes. Use a lista de [Verificação de acesso de convidado ao Teams](guest-access-checklist.md) para ativar o acesso de convidados no Teams. a lista de verificação inclui as configurações necessárias do Azure AD. |
|Acesso externo configurado     |Se o [acesso externo](manage-external-access.md) está habilitado. Por padrão, ele está habilitado, com Federação aberta. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Avaliações para chat, equipes, canais e aplicativos

Além dos [Testes de avaliação de todas as cargas de trabalho](#assessment-tests-for-all-workloads), as avaliações adicionais a seguir são executadas para o chat, as equipes, os canais e as cargas de trabalho de aplicativos:

|Teste de avaliação  |O que ele informa  |
|---------|---------|
|Política de nomenclatura do Grupo do Office 365 configurada     |Se os padrões de nomeação foram configurados para Grupos do Microsoft 365. A política de nomenclatura de grupos do Microsoft 365 permite que sua organização aplique uma estratégia de nomenclatura consistente para equipes criadas pelo usuário e se aplica também a outras cargas de trabalho de grupos (incluindo o Outlook, o SharePoint, o Planner e o Yammer). Esse teste consulta o Azure AD por meio do Microsoft Graph para verificar a existência de políticas de nomenclatura que se aplicam aos grupos do Microsoft 365. Para obter mais informações, confira [Política de Nomenclatura dos Grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy).    |
|Política de Expiração de Grupo do Office 365 configurada     |Se uma Política de Expiração de Grupo foi definida para Grupos do Microsoft 365. Isso permite que sua organização remova automaticamente as Equipes inativas. Ela está desativada por padrão. Este teste consulta o Azure AD por meio do Microsoft Graph e relata se o valor foi modificado no padrão. Para obter mais informações, leia [Política de Expiração dos Grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Avaliações de reuniões e conferências

Além dos [Testes de avaliação de todas as cargas de trabalho](#assessment-tests-for-all-workloads), as avaliações adicionais a seguir são executadas para as reuniões e as cargas de trabalho de conferências:

|Teste de avaliação  |O que ele informa  |
|---------|---------|
|Licenças de Audioconferência    |Se você tiver uma assinatura ativa com licenças de Audioconferência. Esse é um pré-requisito se você estiver implantando pontes de Audioconferência. Consulta o Microsoft Graph para ver se você tem licenças de audioconferência (com pelo menos uma licença disponível para atribuir). Para obter mais informações, leia [Licenciamento do complemento do Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Licenças de Stream     |Se você tiver uma assinatura ativa com licenças do Microsoft Stream disponíveis. Esse é um pré-requisito se deseja habilitar a Gravação da Reunião. Consulte o Microsoft Graph para ver se você tem licenças do Microsoft Stream (com pelo menos uma licença disponível para atribuir). Para obter mais informações sobre o Stream e sobre como habilitá-lo, leia [Gravação de reuniões na nuvem do Teams](cloud-recording.md).

### <a name="advisor-for-teams-bot"></a>Assistente para o bot do Teams

Depois que o Assistente do Teams a criar a equipe de Implantação, o bot do Assistente fornece a seguinte mensagem no canal Geral:

>**Bem-vindo à Equipe de implantação do Microsoft Teams!**
>  
>A finalidade dessa equipe é orientá-lo na implantação do Teams da organização, fornecendo todos os recursos necessários e fornecendo um espaço de colaboração para a equipe do projeto. Cada canal criado usando o Assistente do Teams inclui um passo a passo do plano do Planner e outros recursos, como uma pesquisa de usuários do Forms que pode ser usada durante a implantação. A qualquer momento, você pode voltar e revisar a avaliação de prontidão do locatário ou adicionar planos de carga de trabalho adicionais usando o Centro de administração do Teams.
> 
>**Chamada para ação** 
>- Se você não estiver familiarizado com o Teams ou o Planner, confira nosso [Passo a passo do Teams.](https://teamsdemo.office.com/) e assista aos [Vídeos de início rápido do Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 
>- Vá para a Equipe de implantação no Teams. Escolha seu canal de carga de trabalho (por exemplo, Chat, equipes, canais e aplicativos) e selecione a guia **Planner** para começar.
> 
>Para saber mais sobre o Assistente do Teams, leia [Usar o Assistente do Teams para implantar o Microsoft Teams](use-advisor-teams-roll-out.md).
>

> [!IMPORTANT]
> O Bot do Assistente do Teams é usado apenas para enviar uma mensagem de boas-vindas à sua Equipe de implantação. Nenhum dado adicional é coletado.

> [!IMPORTANT]
> O bot do Assistente do Teams está habilitado por padrão. Não desabilite-o se você usa ou planeja usar o Assistente do Teams.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quais são os requisitos de licenciamento para o Assistente do Teams?
No mínimo, você precisará do Microsoft 365 Business Basic para poder aproveitar o Assistente do Teams para integração com os Formulários e o Planner.

### <a name="can-i-delete-the-deployment-team"></a>Posso excluir a Equipe de implantação?
Depois que o Assistente do Teams tiver criado a Equipe de implantação, gerencie-a como qualquer outra equipe, incluindo a capacidade de excluí-la. Lembre-se de que, se você não excluir a equipe usando o centro de administração do Teams, o centro de administração do Teams relatará que a equipe ainda existe. Esse é um recurso temporário e será corrigido quando o Assistente do Teams deixar o período de visualização pública e ficar geralmente disponível.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>Posso adicionar ou remover canais da Equipe de implantação?
Sim, uma vez que a Equipe de implantação foi criada, você gerenciará os canais da mesma maneira que em qualquer outra equipe.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>Posso adicionar ou remover membros na Equipe de implantação?
Sim, uma vez que a Equipe de implantação foi criada, você gerenciará da mesma maneira que em qualquer outra equipe.

### <a name="can-i-modify-the-planner-plans"></a>Posso modificar os planos do Planner?
Sim, depois que o Assistente do Teams tiver criado a Equipe de implantação, você deverá atualizar o plano do Planner para que ele dê um melhor suporte na implantação do Teams. Você pode modificar qualquer item (buckets, tarefas, detalhes da tarefa), como qualquer outro plano do Planner.

### <a name="can-i-modify-the-forms-survey"></a>Posso modificar a pesquisa do Forms?
Sim, depois que o Assistente do Teams tiver criado a Equipe de implantação, você poderá modificar a pesquisa do Forms, conforme necessário.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Quais informações o Assistente do Teams está coletando sobre minha organização?
O Assistente do Teams solicita o seu contrato para coletar informações não fazem parte da informações de identificação do usuário final (EUII). As informações coletadas estão na forma de telemetria que fornece comentários à Microsoft sobre a forma como o Assistente do Teams está impulsionando os resultados bem-sucedidos e onde talvez seja necessário melhorar o desempenho. Esses mesmos dados são usados para identificar oportunidades para a Microsoft se envolver proativamente com sua organização, podendo assim ajudar na implantação.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Posso usar o Assistente do Teams com o FastTrack?
Sim, o FastTrack usa o Assistente do Teams para todos os clientes que desejam implantar o Teams. Eles podem ajudar na configuração inicial da Equipe de implantação usando o Assistente do Teams (se necessário) e também fornecer o suporte necessário sobre tópicos específicos durante a implantação do Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Posso usar o Assistente do Teams com um parceiro?
Sim, você pode usar o Assistente do Teams e, ao mesmo tempo, usar um parceiro de implantação para a implantação do Teams. Se o seu parceiro é um CSP e gerencia o locatário em seu nome, ele poderá usar o Assistente do Teams para criar a Equipe de implantação e ajudá-lo na execução geral do projeto. Além disso, você pode trabalhar com qualquer parceiro, adicionando-os como convidados na Equipe de implantação, para permitir que eles participem como membro da equipe geral do projeto.

### <a name="how-do-i-use-planner"></a>Como usar o Planner?
Confira a [Ajuda do Microsoft Planner](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) e os [Vídeos de início rápido do Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 

### <a name="how-do-i-use-forms"></a>Como posso usar o Forms?
Vá para [Central de Ajuda do Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Tópicos relacionados

[Como implantar o Teams](How-to-roll-out-teams.md)

[Práticas recomendadas para organizar equipes no Teams](best-practices-organizing.md)

[Nomes de produtos e identificadores de plano de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference
) 
