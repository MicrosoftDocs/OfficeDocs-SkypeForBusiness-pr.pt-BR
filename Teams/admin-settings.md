---
title: Configurações de administração para aplicativos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: Saiba como permitir e habilitar aplicativos no Microsoft Teams, incluindo o carregamento lateral de aplicativos externos.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d2e00e7e8608f78ef2e7ed87bd225596aec6c3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464152"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Configurações de administração para aplicativos no Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Aplicativos são guias, conectores, bots ou qualquer combinação destas três, fornecido pelo equipes (apps primários e também conhecido como aplicativos padrão) ou por um terceiro (também conhecido como aplicativos externos). No Centro de administração do Microsoft 365, você pode habilitar e desabilitar aplicativos padrão e definir configurações para controlar aplicativos externos. Essas configurações permitem especificar quais aplicativos externos são permitidos e não permitidos, novo comportamento de aplicativo externo, e se os aplicativos do lado do carregamento é permitido.

 Para gerenciar as configurações de administração para aplicativos em equipes, vá para o Centro de administração do Microsoft 365 e escolha **configurações** > **Serviços & complementos** > **Equipes da Microsoft**. Se você tiver entrado como administrador do Office 365, esse link deverá levá-lo corretamente ao local correto:

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Para saber mais sobre as configurações do administrador de aplicativos, veja este vídeo: 
 
|  |  |
|---------|---------|
| Gerenciando a experiência de aplicativos no Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Permitir aplicativos externos no Teams

Por padrão, a **permissão de aplicativos externos no Microsoft Teams** está habilitada para todos os aplicativos.  Se você desativar essa configuração, todos os aplicativos de terceiros externos serão desabilitados. 

## <a name="enable-new-external-apps-by-default"></a>Habilitar novos aplicativos externos por padrão

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: Prática recomendada: Gerenciar aplicativos externos individualmente 
 
Para ativar alguns aplicativos (e desativar outros), desative **Allow sideloading of external apps** (Permitir o sideload de aplicativos externos). Em seguida, desative os aplicativos que você não quer que os usuários utilizem. Opcional: desative a opção **Enable new external apps by default** (Habilitar novos aplicativos externos por padrão) (se quiser controlar os novos aplicativos). 

> [!NOTE]
> Aplicativos padrão, como as criadas pela Microsoft, não são afetados pela definição **habilitar novos aplicativos externos por padrão** . Novos aplicativos estão habilitados por padrão quando lançada pela Microsoft.

Quando essa configuração é ativada, os usuários podem ativar novos aplicativos assim que são adicionados ao catálogo de aplicativos de equipes. Para abrir o catálogo de aplicativos do Teams, clique em **Loja** na parte inferior do Teams e clique em **Aplicativos**. Se você quiser controlar quais aplicativos estão disponíveis, desative esta configuração. Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas. 

O sideload é a forma de adicionar um aplicativo ao Teams carregando um arquivo zip diretamente para uma equipe. O sideload permite testar um aplicativo durante seu desenvolvimento. E também possibilita a criação de um aplicativo somente para uso interno, compartilhando-o com a sua equipe sem enviá-lo para o catálogo de aplicativos do Teams na Office Store. 

Apenas os proprietários de equipes ou os membros aos quais foram concedidas permissões podem fazer sideload de aplicativos no Teams.  

![Captura de tela da seção de aplicativos externos expandida.] (media/teams-tenant-wide-settings-external-apps.png "Captura de tela da seção aplicativos externos expandida mostrando aplicativos externos")

## <a name="creating-and-uploading-app-packages"></a>Criação e upload de pacotes de aplicativos 

Para saber mais sobre os aplicativos, consulte [desenvolver aplicativos para equipes](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



