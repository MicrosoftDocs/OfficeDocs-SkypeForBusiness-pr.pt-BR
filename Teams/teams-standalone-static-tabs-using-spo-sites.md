---
title: Criar um aplicativo de portal de intranet do teams ' a partir de um site ou página do SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Pegue um site ou uma página existente do SharePoint Online e crie uma guia estática autônoma que pode ser usada como um portal da intranet para a sua organização.
localization_priority: Normal
ms.openlocfilehash: 772063a7444e9c31d2740ac48635dc0f2e367435
ms.sourcegitcommit: aaae9df142ebb844a1fea27d3ae3b95130903d6a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43100350"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Criar um aplicativo de portal de intranet do teams ' a partir de um site ou página do SharePoint Online

Use as etapas neste artigo para criar um aplicativo autônomo e estático dentro do teams que está vinculado ao site de intranet da sua organização.

Um *aplicativo pessoal do teams* do seu site de intranet do SharePoint é criado e será exibido como uma guia dentro do teams. Esta guia pode conter informações importantes para todos os usuários do Microsoft Teams. É uma maneira rápida e conveniente para os usuários do teams acessarem atualizações apenas em uma guia clique em ausente.

Lembre-se de que o processo mostrado **deve usar** um site *moderno* do SharePoint ou uma página para funcionar. Este processo não está disponível para sites ou páginas *clássicas* .

> [!IMPORTANT]
> Certifique-se de que o carregamento lado a lado dos aplicativos da equipe esteja habilitado para seu locatário. Dependendo de onde você estiver no processo de migração do portal de administração do Teams, talvez seja necessário habilitá-lo em Teams > administrador ou em configurações do administrador > > serviços e suplementos > Microsoft Teams > aplicativos > aplicativos externos, na versão anterior do portal! 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Usar o app Studio para criar seu aplicativo autônomo do SharePoint Online

Antes de começar:
1. Você precisará saber a URL de um site de equipe ou de comunicação moderna do SharePoint Online ou uma página.
    - Esses sites sempre terão o */Teams/* ou o */sites/* em seus caminhos.

2. Você precisará saber o subdomínio do seu locatário, que será usado no espaço reservado **{{subdomain}}**.

3. Este artigo usará o espaço reservado **{{SiteUrl}}** para você que seja a *URL* do site ou da página que você escolheu.
    - Exemplos de *URLs*: https://contoso.sharepoint.com/teams/Contoso *ou*   https://contoso.sharepoint.com/sites/Contoso 
4. Além disso, **{{sitePath}}** será usado para denotar o *caminho* da URL (ex:/Teams/contoso).
    - *Caminhos*de exemplo:/Teams/Contoso *ou* /sites/contoso 

Comece seguindo as etapas abaixo:

1. Acesse a loja do teams.

2. Instalar ou abrir o app Studio.

3. Clique em **abrir**, ao lado da opção do aplicativo.

4. Com o app Studio aberto, clique em **Editor de manifestos**.

5. **Crie um novo aplicativo**.

6. Preencha todos os **detalhes do aplicativo**.

7. Clique nas **guias** em recursos.

8. Clique em **Adicionar** na guia pessoal.

9. Preencha o **nome** e escolha **uma nova ID de entidade exclusiva**.

10. Preencha o **contentURL e a URL do site**. 

- **contentUrl**: {{siteurl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}  
- **websiteUrl**: {{SiteUrl}} 

    Exemplo **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. Navegue até **domínios e permissões**. Verifique se a seção Domains válidos contém seu nome de domínio do SharePoint Online.

    Exemplo: contoso.sharepoint.com

12. Adicione as seguintes propriedades de **logon único** do aplicativo Web: 
     
     Exemplo: **ID do aplicativo AAD**: **URL do recurso**00000003-0000-0ff1-ce00-000000000000: {{subdomain}}. SharePoint. com

    ![Logon único do aplicativo Web, com ID e URL.](media/personal-app.png)

13. **Salve** essas propriedades e navegue para **testar e distribuir**. 

14. Instale o aplicativo para testar o aplicativo pessoalmente.

> [!IMPORTANT]
> Se você não estiver usando o Teams app Studio, será necessário. zip no manifesto. Arquivo JSON que você acabou de criar, navegue até a App Store no Teams e clique em carregar link do **aplicativo personalizado** (no canto inferior direito da App Store). Isso fará com que o aplicativo seja disponibilizado para você.

15. Agora o aplicativo está disponível como uma guia estática para você carregar e exibir no Teams.

## <a name="test-and-view-your-new-static-tab"></a>Testar e exibir sua nova guia estática

Para exibir a nova guia na área de trabalho do Teams, navegue até as reticências (**...**) no lado esquerdo da barra de aplicativos. Encontre o novo aplicativo, carregue-o e teste o aplicativo autônomo no Microsoft Teams.

Se você quiser disponibilizar o novo aplicativo no menu à esquerda em uma posição mais alta, você deve usar uma configuração de política de aplicativo para isso. Essa configuração pode ser encontrada na seção administrador da equipe > política do aplicativo > adicionar um aplicativo fixo. Quando você atribuir a política a um usuário para teste, a alteração será exibida em 24 horas depois. Com isso em mente, decida onde o aplicativo deve ser exibido da sua conveniência mais antiga para ajudar a evitar atrasos.

Para exibir e testar o novo aplicativo em um dispositivo móvel, abra a gaveta do aplicativo tocando na divisa (**^**) acima da barra de guias próxima à parte inferior da tela. Localize seu aplicativo e navegue para ele em seu dispositivo móvel.

> [!CAUTION]
> O suporte móvel está atualmente na visualização do desenvolvedor. Para habilitar a visualização de desenvolvedor, navegue até configurações > e, em seguida, habilite o modo de visualização do desenvolvedor.

## <a name="a-sample-manifestjson-file"></a>Um arquivo manifest. JSON de exemplo

O arquivo JSON que você gerar irá se parecer com o nome abaixo.

```JSON
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", 

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", 

        "full": "Intranet Portal for Contoso" 

    }, 

    "description": { 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 

    "staticTabs": [ 

        { 

            "entityId": "communicationSiteTab", 

            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```