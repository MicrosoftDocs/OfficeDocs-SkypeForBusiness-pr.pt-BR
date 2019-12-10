---
title: Use o Assistente do Teams (versão prévia) para ajudá-lo na implantação do Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Use o Assistente do Teams (versão prévia) para ajudá-lo a planejar e concluir a implantação do Microsoft Teams.
ms.openlocfilehash: 63a3ae01dbe47323fd9227e65fa8c38a2d725ddf
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909467"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Use o Assistente do Teams para ajudá-lo na implantação do Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

O Assistente do Teams (versão prévia) o orienta na implantação do Microsoft Teams. Ele avalia o ambiente de locatário do Office 365 e identifica as configurações mais comuns que talvez seja necessário atualizar ou modificar antes de poder implantar o Teams com êxito. Em seguida, o Assistente do Teams cria uma Equipe de implantação (no Teams), com canais para cada carga de trabalho que você deseja implantar. Cada carga de trabalho da Equipe de implantação vem com um plano abrangente do Planner que inclui todas as tarefas de implantação para cada carga de trabalho.  Usando esse plano do Planner, você atribuirá tarefas às pessoas responsáveis por cada fase da implantação, incluindo o gerente de projeto, os administradores do Teams e do Office 365, o pessoal do suporte e a equipe de adoção e preparação do usuário. Cada tarefa de implantação contém todas as orientações e recursos necessários para concluir a tarefa com êxito.

O Assistente do Teams faz parte do [centro de administração do Teams](https://admin.teams.microsoft.com). Para usar o Assistente do Teams pela primeira vez, clique no botão **Iniciar** no widget de **Implantação da carga de trabalho do Teams** no Painel.  Ou vá para **Planejamento** > **Assistente**.

> [!IMPORTANT]
> O Assistente do Teams não está disponível para implantações do Office 365 U.S. Government DoD ou GCC High.

Consulte nosso Assistente do Teams nesse vídeo de [Introdução à Implantação e Configuração do Teams](https://youtu.be/o2mlsUubIO4?t=44) (Assistente do Teams está entre 0:50 – 3:15 minutos)  

## <a name="using-advisor-for-teams-preview"></a>Usando o Assistente do Teams (versão prévia)

Você não precisa ser um administrador do Teams para usar o Assistente do Teams, qualquer pessoa em sua organização pode usá-lo. Configuramos permissões especiais para que usuários não administradores possam acessar o Assistente do Teams, mesmo que seja no centro de administração do Teams. Você PRECISA ser um administrador do Teams, Administrador de Serviços do Teams ou Administrador Global para abrir as avaliações de prontidão do locatário.

Na primeira vez em que você usar o Assistente do Teams, ele criará uma Equipe de implantação no Teams. Ele adiciona canais para cada carga de trabalho que você deseja implantar. 


## <a name="available-advisor-for-teams-plans"></a>Planos de Assistente do Teams Disponíveis

Enquanto o Assistente do Teams está em versão prévia, estamos fornecendo esses dois planos:

1. Chat, equipes, canais e aplicativos
    - Avaliação do locatário
    - Plano do Planner, incluindo tarefas de adoção
    - Pesquisa de usuário do Forms
1. Reuniões e conferências
    - Avaliação do locatário
    - Plano do Planner, incluindo tarefas de adoção
    - Pesquisa de usuário do Forms

Recomendamos que você comece com o plano de Chat, equipes, canais e aplicativos. Quando terminar de implantar a carga de trabalho, volte ao Assistente e clique em **Adicionar canal** para iniciar a próxima carga de trabalho. 

## <a name="tenant-assessment"></a>Avaliação do locatário
Cada plano inclui uma avaliação de prontidão do locatário que você pode usar para identificar e corrigir as deficiências em seu ambiente antes de implantar o Teams. Veja o que cada avaliação verifica:

### <a name="chat-teams-channels-and-apps"></a>Chat, equipes, canais e aplicativos


|Avaliação  |O que ele informa  |
|---------|---------|
|Licenças do Teams     |Se você tiver uma assinatura ativa com licenças disponíveis do Teams |
|Licenças do Exchange     |Se você tiver uma assinatura ativa com licenças disponíveis do Exchange Online. Embora o Exchange não seja necessário para a funcionalidade básica do Teams, a integração com o Exchange fornece uma experiência ideal para o Teams.         |
|Licenças do SharePoint Online     | Se você tiver uma assinatura ativa com licenças disponíveis do SharePoint Online. Você precisa de uma licença do SharePoint Online por usuário para armazenamento de arquivos, colaboração de canal e chat. 
|Acesso para convidado habilitado     |Se o acesso para convidado estiver ativado no Teams. As configurações do Azure Active Directory de acesso para convidado não estão revisadas.   |
|Domínio personalizado configurado     |Se houver um domínio que não seja @onmicrosoft.com configurado para o locatário  |
|Padrão de nomeação do Grupo do Office 365 configurado     | Se os padrões de nomeação foram configurados para Grupos do Office 365        |
|Expiração de Grupo do Office 365 configurado     |  Se uma política de expiração de Grupo foi definida para Grupos do Office 365. Caso contrário, o valor será definido como nunca.        |
|Acesso externo configurado     |Se o acesso externo estiver ativado para que você possa se comunicar com organizações externas no Teams.          |

### <a name="meetings-and-conferencing"></a>Reuniões e conferências


|Avaliação  |O que ele informa  |
|---------|---------|
|Licenças do Teams     |Se você tiver uma assinatura ativa com licenças disponíveis do Teams |
|Licenças do Exchange     |Se você tiver uma assinatura ativa com licenças disponíveis do Exchange Online. Embora o Exchange não seja necessário para a funcionalidade básica do Teams, a integração com o Exchange fornece uma experiência ideal para o Teams. |
|Licenças de Audioconferência    |Se você tiver uma assinatura ativa com licenças de Audioconferência |
|Licenças de Stream     |Se você tiver uma assinatura ativa com licenças de Stream, ela pode ser usada para fazer Gravação de Reunião. |
|Acesso para convidado     |Se o acesso para convidado estiver ativado no Teams. As configurações do Azure Active Directory de acesso para convidado não estão revisadas.|
|Domínio personalizado     |Se houver um domínio que não seja @onmicrosoft.com configurado para o locatário.  |
|Acesso externo     |Se o acesso externo estiver ativado para que você possa se comunicar com organizações externas no Teams. |


### <a name="advisor-bot"></a>Bot do Assistente
Depois que o Assistente cria a Equipe de implantação, o bot do Assistente fornece a seguinte mensagem.

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
> O Bot do Assistente do Teams está habilitado por padrão. Não desabilite-o se você usar ou planeja usar o Assistente do Teams.


## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Quais são os requisitos de licenciamento para o Assistente do Teams?
Não há requisitos de licenciamento adicionais além de ser licenciado para o Teams.

### <a name="can-i-delete-the-deployment-team"></a>Posso excluir a Equipe de implantação?
Depois que o Assistente do Teams tiver criado a Equipe de implantação, gerencie-a como qualquer outra equipe, incluindo a capacidade de excluí-la. Lembre-se de que, se você não excluir a equipe usando o centro de administração do Teams, será relatado que a equipe existe.

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
