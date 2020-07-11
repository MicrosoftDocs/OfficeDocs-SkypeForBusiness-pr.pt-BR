---
title: Criar um 'aplicativo Portal da Intranet' do Teams a partir de um site ou página do SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Use um site ou uma página existente do SharePoint Online e crie uma guia estática independente que possa ser usada como um portal da Intranet para a sua organização.
localization_priority: Priority
ms.openlocfilehash: 09ff3fd57eee23c5eec9dfac118b68938c1c9f36
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083161"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Criar um 'aplicativo Portal da Intranet' do Teams a partir de um site ou página do SharePoint Online

Use as etapas deste artigo para criar um aplicativo autônomo e estático dentro do Teams vinculado ao site da intranet da sua organização.

Um *Aplicativo pessoal do Teams* do seu site da intranet do SharePoint é criado e aparecerá como uma guia dentro do Teams. Esta guia pode conter informações importantes para todos os usuários do Teams. É uma maneira rápida e conveniente para que os usuários do Teams acessem atualizações com apenas um clique.

Lembre-se de que o processo mostrado **deve usar** um site ou página do SharePoint *moderno* para funcionar. Este processo não está disponível para sites ou páginas *clássicos*.

> [!IMPORTANT]
> Verifique se o carregamento lateral dos aplicativos do Teams está ativado para o locatário. Dependendo de onde você estiver no processo de migração do portal de administração do Teams, talvez seja necessário habilitá-lo em Teams > Administrador, ou em Administrador > Configurações > Serviços e suplementos > Microsoft Teams > Aplicativos > Aplicativos externos, na versão anterior do portal!

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Use o App Studio para criar seu aplicativo autônomo do SharePoint Online

Antes de começar:

1. Você precisará saber a URL de um site ou página moderna de Comunicação ou de Equipe do SharePoint Online.
    - Esses sites sempre terão */teams/* ou */sites/* em seus caminhos.

2. Você precisará conhecer o subdomínio de seu locatário, que será usado no espaço reservado **{{subdomínio}}**.

3. Este artigo usará **{{siteUrl}}** como um espaço reservado para a *URL* do site ou da página que você escolheu.
    - *URLs* de exemplo:   https://contoso.sharepoint.com/teams/Contoso   *ou* https://contoso.sharepoint.com/sites/Contoso
4. Além disso, o **{{sitePath}}** será usado para indicar o *caminho* da URL (ex:/teams/Contoso).
    - Exemplos de *caminhos*: /teams/Contoso *ou* /sites/Contoso

Comece seguindo as etapas abaixo:

1. Vá para a Teams Store.

2. Instale ou abra o App Studio.

3. Clique em **Abrir**, ao lado da opção Aplicativo.

4. Com o App Studio aberto, clique em **Editor de manifesto**.

5. **Criar um novo aplicativo**.

6. Preencha todos os **Detalhes do aplicativo**.

7. Clique nas **guias** em Recursos.

8. Clique em **Adicionar** na guia Pessoal.

9. Preencha o **Nome** e escolha **uma nova ID de Entidade exclusiva**.

10. Preencha a **contentURL e URL do site**.

- **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **websiteUrl**: {{siteUrl}}

    Exemplo de **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub

11. Navegue para **Domínios e permissões**. Verifique se a seção de domínios válidos contém o nome do seu domínio do SharePoint Online.

    Exemplo: contoso.sharepoint.com

12. Adicione as seguintes propriedades de **logon único** do aplicativo Web:

     Exemplo:  **ID de aplicativo AAD**: 00000003-0000-0ff1-ce00-000000000000  **URL do recurso**: {{subdomain}}.sharepoint.com

    ![Logon único de aplicativo Web, com ID e URL.](media/personal-app.png)

13. **Salve** essas propriedades e navegue para **Testar e distribuir**.

14. Instale o aplicativo para testá-lo pessoalmente.

> [!IMPORTANT]
> Se você não estiver usando o Teams App Studio, será necessário compactar o arquivo manifest.JSON que você acabou de criar, navegar até a App Store no Teams e clicar no link **carregar aplicativo personalizado** (na parte inferior direita da App Store). Isso tornará o aplicativo disponível para você.

15. Agora o aplicativo está disponível como uma guia estática para você carregar e visualizar no Teams.

## <a name="test-and-view-your-new-static-tab"></a>Testar e exibir sua nova guia estática

Para exibir a nova guia no Teams para área de trabalho, navegue até as reticências (**…**) no lado esquerdo da barra de aplicativos. Encontre seu novo aplicativo, carregue-o e teste seu aplicativo autônomo no Teams.

Se você deseja disponibilizar o novo aplicativo no menu esquerdo em uma posição superior, você deve usar uma configuração de política de aplicativo. Essa configuração pode ser encontrada na seção Administrador da equipe > Política do aplicativo > Adicionar um aplicativo afixado. Quando você atribui a política a um usuário para teste, a alteração será exibida algumas horas depois. Com isso em mente, decida onde o aplicativo deve aparecer o quanto antes para evitar atrasos.

Para exibir e testar o novo aplicativo em um dispositivo móvel, abra a gaveta de aplicativos tocando na divisa (**^**) acima da barra de guias, na parte inferior da tela. Encontre seu aplicativo e navegue até ele no seu dispositivo móvel.

> [!CAUTION]
> No momento, o suporte para dispositivos móveis está em Visualização de desenvolvedor. Para habilitar a Visualização de desenvolvedor, navegue até Configurações > Sobre e habilite o modo de Visualização de desenvolvedor.

## <a name="a-sample-manifestjson-file"></a>Um arquivo Manifest.JSON de amostra

O arquivo JSON que você gerar se parecerá com o mostrado abaixo.

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

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
