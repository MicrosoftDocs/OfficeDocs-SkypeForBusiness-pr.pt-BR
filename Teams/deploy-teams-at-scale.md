---
title: Implantar equipes em escala para trabalhadores da linha de frente Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como implantar equipes em escala para os trabalhadores da linha de frente em sua organização.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 561eaf310201b99ada9cce4dde49746d58d77088
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046020"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Implantar equipes em escala para trabalhadores da linha de frente Microsoft Teams

> [!NOTE]
> Esse recurso está atualmente em versão prévia privada. Se você quiser participar da versão prévia privada, entre em contato [conosco em dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Visão Geral
 
Sua organização pode ter muitas equipes que você usa para impulsionar a comunicação e a colaboração entre sua força de trabalho de linha de frente, que estão distribuídas em diferentes lojas, locais e funções. Atualmente, não há uma solução fácil para implantar, configurar e gerenciar essas equipes e usuários em escala.

Estamos criando uma solução para permitir que os administradores implantem e gerenciem equipes em escala.

Aqui está uma visão geral dos recursos disponíveis hoje para criar e gerenciar um grande número de equipes por vez e o que estamos planejando para o futuro próximo.

||Disponível hoje |Posteriormente em 2022  |
|---------|---------|---------|
|**Número de equipes que você pode criar por lote**|Até 100 |Até 500|
|**Número de usuários que você pode adicionar por equipe**|Até 25|Até 25|

A implantação de equipes em escala permite que você:

- Crie equipes usando modelos pré-criados ou seus próprios modelos personalizados.
- Adicione usuários às equipes como proprietários ou membros.
- Gerencie equipes em escala adicionando ou removendo usuários de equipes existentes.
- Mantenha-se notificado por email, incluindo conclusão, status e erros (se houver). Você pode optar por notificar até cinco pessoas sobre o status de cada lote de equipes implantadas. Os proprietários e membros da equipe são notificados automaticamente quando são adicionados a uma equipe.

## <a name="how-to-deploy-teams-at-scale"></a>Como implantar equipes em escala

> [!NOTE]
> Antes de implantar suas equipes, verifique se todos os proprietários de equipes têm uma Teams licença.

Siga estas etapas para implantar um grande número de equipes por vez.

### <a name="step-1-prepare-your-csv-files"></a>Etapa 1: Preparar seus arquivos CSV

Você precisará criar dois arquivos CSV para cada lote de equipes que implantar:

- **Um arquivo CSV que define as equipes que você está criando**. Esse arquivo deve conter essas colunas necessárias, na seguinte ordem, começando com a primeira coluna:

    |Nome da coluna  |Descrição  |
    |---------|---------|
    |**Nome da equipe**|O nome da equipe.|
    |**ID da equipe existente**|Se você estiver adicionando ou removendo usuários de uma equipe existente, especifique a ID da equipe.|
    |**Visibilidade**|Se a equipe é pública (qualquer pessoa em sua organização pode ingressar) ou privada (os usuários precisam de aprovação dos proprietários da equipe para ingressar). As opções são **Pública** e **Privada**.|
    |**ID do Modelo de Equipe**|Se você estiver criando uma equipe com base em um modelo predefinido ou personalizado, especifique a ID do modelo de equipe. Consulte [Introdução modelos de](get-started-with-teams-templates-in-the-admin-console.md) equipe no centro de administração do Teams para obter uma lista de IDs e modelos de equipe pré-criados. Se você quiser usar o modelo de equipe padrão padrão, deixe isso em branco.|

- **Um arquivo CSV que mapeia os usuários que você está adicionando a cada equipe**. Esse arquivo deve conter essas colunas necessárias, na seguinte ordem, começando com a primeira coluna:

    |Nome da coluna  |Descrição  |
    |---------|---------|
    |**Nome Completo do Usuário**|O nome de exibição do usuário.|
    |**UPN ou ID do usuário**|O NOME UPN ou a ID do usuário. Por exemplo, averyh@contoso.com.|
    |**Nome da equipe**|O nome da equipe.|
    |**ActionType**|Se você está adicionando ou removendo o usuário da equipe. As opções **são AddMember** **e RemoveMember**.|
    |**Proprietário ou Membro**|Se o usuário é um proprietário da equipe ou membro da equipe. As opções são **Proprietário** e **Membro**.|

#### <a name="examples"></a>Exemplos

Use os exemplos a seguir para ajudá-lo a criar seus arquivos CSV. Aqui, nomeemos os arquivos, Teams.csv e Users.csv.

**Teams.csv**

|Nome da equipe|ID da equipe existente|Visibilidade|ID do Modelo de Equipe|
|---------|---------|---------|---------|
|Contoso Store 1||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 2||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 3||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 4||Público|com.microsoft.teams.template.retailStore|
|Contoso Store 5||Público|com.microsoft.teams.template.ManageAProject|
|Contoso Store 6||Público|com.microsoft.teams.template.ManageAProject|
|Contoso Store 7||Público||
|Contoso Store 8||Privada|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 9||Privada|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 10||Privada|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|Nome Completo do Usuário |UPN ou ID do usuário|Nome da equipe|ActionType|Proprietário ou Membro|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Contoso Store 1|AddMember|Proprietário|
|Casey Jensen|caseyj@contoso.com|Contoso Store 2|AddMember|Proprietário|
|Jessie Mateus|jessiei@contoso.com|Contoso Store 3|AddMember|Proprietário|
|Manjeet Bhatia|manjeetb@contoso.com|Contoso Store 4|AddMember|Proprietário|
|Brasa Lee|mikaelal@contoso.com|Contoso Store 5|AddMember|Proprietário|
|Morgan Connors|morganc@contoso.com|Contoso Store 6|AddMember|Membro|
|Oscar Ward|oscarw@contoso.com|Contoso Store 7|AddMember|Membro|
|Rene Pelletier|renep@contoso.com|Contoso Store 8|AddMember|Membro|
|Sydney Mattos|sydneym@contoso.com|Contoso Store 9|AddMember|Membro|
|Violet Martinez|violetm@contoso.com|Contoso Store 10|AddMember|Membro|

### <a name="step-2-deploy-your-teams"></a>Etapa 2: Implantar suas equipes

Agora que você criou seus arquivos CSV, está pronto para configurar seu ambiente e implantar suas equipes.

Use o ```New-CsBatchTeamsDeployment``` cmdlet para enviar um lote de equipes a serem criados. Uma ID de orquestração é gerada para cada lote. Em seguida, você pode usar o ```Get-CsBatchTeamsDeployment``` cmdlet para acompanhar o progresso e o status de cada lote.

1. Instale o PowerShell versão 7 ou posterior. Para obter diretrizes passo a passo, consulte [Instalar o PowerShell no Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Execute o PowerShell no modo de administrador.
1. Execute o seguinte para desinstalar todos os módulos Teams PowerShell instalados anteriormente.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Se você receber uma mensagem de erro, já estará definido. Vá para a próxima etapa.
1. Baixe e instale a [versão mais recente do módulo Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Execute o seguinte para se conectar ao Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Quando for solicitado, entre usando suas credenciais de administrador.

1. Execute o seguinte para obter uma lista dos comandos no módulo Teams PowerShell.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Verifique se e ```New-CsBatchTeamsDeployment``` estão ```Get-CsBatchTeamsDeployment``` listados.

1. Execute o seguinte para implantar um lote de equipes. Neste comando, você especifica o caminho para seus arquivos CSV e os endereços de email de até cinco destinatários para notificar sobre essa implantação.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Por exemplo:

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    Os destinatários receberão notificações por email sobre o status da implantação. O email contém a ID de orquestração do lote enviado e quaisquer erros que possam ter ocorrido.

1. Execute o seguinte para verificar o status do lote enviado.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Nos envie seus comentários

Nós damos valor aos seus comentários. Usabilidade, confiabilidade, desempenho,&mdash;demos as boas-vindas a tudo!

Envie [dscale@microsoft.com](mailto:dscale@microsoft.com) email e inclua sua ID de orquestração e o arquivo de erro, se você tiver.

## <a name="related-articles"></a>Artigos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
