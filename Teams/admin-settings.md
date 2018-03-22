---
title: Configurações de administração para aplicativos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Saiba como permitir e habilitar aplicativos no Microsoft Teams, incluindo o carregamento lateral de aplicativos externos.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58fb8598f8e63aa3e8abc943dcffde64452da462
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Configurações de administração para aplicativos no Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Os aplicativos consistem em guias, conectores, bots ou qualquer combinação dos três, fornecidos por um serviço de terceiros. Existem políticas de administração do Teams que podem ser configuradas no Centro de administração do Office 365 para controlar quais aplicativos externos de terceiros são permitidos. Essas políticas permitem especificar quais aplicativos são permitidos ou não, o comportamento do novo aplicativo externo e se o sideload de aplicativos é permitido.

> [!NOTE]
> Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o Centro de administração do Office 365 e abra **Configurações** > **Serviços e complementos** e escolha **Microsoft Teams**. Se você tiver entrado como administrador do Office 365, este link deverá direcioná-lo corretamente:
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Para saber mais sobre as configurações do administrador de aplicativos, veja este vídeo: 
 
|  |  |
|---------|---------|
| Gerenciando a experiência de aplicativos no Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Permitir aplicativos externos no Teams

Por padrão, a **permissão de aplicativos externos no Microsoft Teams** está habilitada para todos os aplicativos.  Se você desativar essa opção, todos os aplicativos externos de terceiros serão desabilitados. 

## <a name="enable-new-external-apps-by-default"></a>Habilitar novos aplicativos externos por padrão

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: Prática recomendada: Gerenciar aplicativos externos individualmente 
 
Para ativar alguns aplicativos (e desativar outros), desative **Allow sideloading of external apps** (Permitir o sideload de aplicativos externos). Em seguida, desative os aplicativos que você não quer que os usuários utilizem. Opcional: desative a opção **Enable new external apps by default** (Habilitar novos aplicativos externos por padrão) (se quiser controlar os novos aplicativos). 

Quando essa opção está ativada, os usuários podem ativar novos aplicativos assim que eles são adicionados ao catálogo de aplicativos do Teams. Para abrir o catálogo de aplicativos do Teams, clique em **Loja** na parte inferior do Teams e clique em **Aplicativos**. Para controlar os aplicativos que estão disponíveis, desative essa opção. Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas. 

O sideload é a forma de adicionar um aplicativo ao Teams carregando um arquivo zip diretamente para uma equipe. O sideload permite testar um aplicativo durante seu desenvolvimento. E também possibilita a criação de um aplicativo somente para uso interno, compartilhando-o com a sua equipe sem enviá-lo para o catálogo de aplicativos do Teams na Office Store. 

Apenas os proprietários de equipes ou os membros aos quais foram concedidas permissões podem fazer sideload de aplicativos no Teams.  

![Captura de tela da seção Apps expandida nas configurações de todo o inquilino.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)


## <a name="creating-and-uploading-app-packages"></a>Criação e upload de pacotes de aplicativos 

Para saber mais sobre aplicativos, leia [Desenvolver aplicativos para o Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



