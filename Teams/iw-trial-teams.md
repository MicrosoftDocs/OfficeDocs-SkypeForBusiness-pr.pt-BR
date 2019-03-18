---
title: Gerenciar a oferta de avaliação na nuvem comercial do Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/10/2018
ms.topic: article
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Usuários do Office 365 que não possuem licenças para o Microsoft Teams podem iniciar uma avaliação de 1 ano do Teams.
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4fdeba0e4540d64e98eb2853b73e6d1edb5110e
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569611"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Gerenciar a oferta de avaliação na nuvem comercial do Microsoft Teams
=======================================================

O Microsoft Teams é uma ótima ferramenta de colaboração para sua organização. Ele permite que colaboradores e equipes discutam, inovem e compartilhem ideias usando o poder do Office 365. A avaliação do Microsoft Teams Commercial Cloud oferece 1 ano de avaliação do produto para usuários que já possuem o Office 365 em sua organização e não possuem licenças do Microsoft Teams.. Os administradores podem mudar ou desativar esse recurso para os usuários de sua organização.

## <a name="whats-in-the-offer"></a>O que está incluso na oferta?

Os planos de serviço dessa oferta estão:

- Exchange Foundation
- Flow para Office 365 Plano 1
- Microsoft Planner
- Microsoft Teams (Teams1, equipes IW)
- Office Online
- PowerApps para Office 365 Plano 1
- SharePoint Online Kiosk
- Sway
- Yammer Enterprise

A versão de avaliação concede uma assinatura de avaliação de um ano para toda a sua organização. A versão de avaliação tem 500.000 licenças disponíveis para atribuição. Para cada licença, a versão de avaliação aloca 2 GB de armazenamento do SharePoint Online. 

## <a name="who-is-eligible"></a>Quem se qualifica?

Habilite os usuários para usar avaliações e aplicativos (no Centro de administração do Office 365). Para obter informações, consulte [Gerenciar avaliação](#manage-the-trial) posteriormente neste artigo. 

Os usuários que não têm uma licença do Office 365 que inclui o Teams podem iniciar a oferta de avaliação do Microsoft Teams Commercial Cloud. Por exemplo, se um usuário tiver o Office 365 Business (que não inclui o Teams), eles estará qualificado para a versão de avaliação.

## <a name="who-is-not-eligible"></a>Quem não está qualificado

Sua organização não está qualificada para avaliação se: 

- Você for um Cliente Parceiro de Distribuição
- Você for um Cliente Parceiro Revendedor
- Você for um cliente EDU ou Governamental

Se sua organização não estiver qualificada para a oferta da avaliação do Microsoft Teams Commercial Cloud, você não verá a mudança **Permitir que os usuários instalem aplicativos e serviços de avaliação**.

## <a name="how-users-sign-up-for-the-trial"></a>Como os usuários podem se inscrever para a versão de avaliação

Usuários qualificados podem se inscrever para o oferta de avaliação entrando no Teams ([teams.microsoft.com](https://teams.microsoft.com)). Eles verão a seguinte tela para iniciar a avaliação. 

![Captura de tela da página inicial da avaliação do Teams IW.](media/iw-trial-start-screen.png)

Todas as avaliações em sua organização compartilham as mesmas datas de início e fim, que é a data em que o primeiro usuário se inscreveu na versão de avaliação. Por exemplo, se um usuário começa a primeira versão de avaliação em 25 de janeiro de 2019 e usuário B iniciar uma avaliação em 3 de junho de 2019, a avaliação de ambos expirará em 25 de janeiro de 2020.

## <a name="manage-the-trial"></a>Gerenciar a versão de avaliação

Os administradores podem gerenciar licenças de usuários que se inscreveram. 

Além disso, os administradores podem desabilitar a capacidade de os usuários finais solicitarem aplicativos e serviços de avaliação na organização.  Atualmente, a avaliação descrita neste artigo é a única avaliação nessa categoria, mas pode se aplicar a outros programas semelhante no futuro. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Impeça que os usuários instalem serviços e aplicativos de avaliação

Você pode desativar a capacidade de um usuário de instalar serviços e aplicativos de avaliação.

1. No [Centro de administração do Microsoft 365](https://portal.office.com/adminportal/home), vá até **Configurações** > **Serviços e suplementos** > ** Aplicativos e serviços de propriedade do usuário**.

    ![Captura de tela da página Serviços e complementos do Centro de administração do Office 365.](media/iw-trial-enable-1.png)

2. Desative **Permitir que os usuários instalem aplicativos e serviços de avaliação**.

    ![Captura de tela da página Aplicativos e serviços de propriedade do usuário no Centro de administração do Office 365.](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Gerencie a disponibilidade de avaliação de um usuário com uma licença que inclua o Teams

Um usuário que possui uma licença que inclui o Teams não está qualificado para a versão de avaliação. Quando o plano de serviço do Teams estiver habilitado, ele poderá entrar e usar o Teams. Se o plano de serviço estiver desativado, o usuário não poderá entrar e não receberá a opção de avaliação.

Para desativar o acesso ao Teams:

1. No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.

2. Marque a caixa ao lado do nome do usuário.

3. À direita, na linha **Licenças de produto**, escolha **Editar**.

4. No painel **Licenças de produto**, troque o botão para **Desativar**.

    ![Captura de tela da página de licenças do produto do Centro de administração do Office 365.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Gerencie a disponibilidade do Teams para usuários que já haviam solicitado a versão de avaliação

Se um usuário solicitou uma licença de avaliação do Teams, você pode removê-lo ao remover o plano de serviço ou a licença.

Para desativar a licença de avaliação:

1. No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.

2. Marque a caixa ao lado do nome do usuário.

3. À direita, na linha **Licenças de produto**, escolha **Editar**.

4. No painel **Licenças de produto**, troque o botão para **Desativar**.

    ![Captura de tela da configuração de licença de avaliação do Teams no painel de licenças de produto](media/iW-trial-enable-4.png)
    
>[!Note]
>A opção de alternância da avaliação do Microsoft Teams será exibida assim que o primeiro usuário se inscrever para a avaliação na organização.

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Gerenciamento do Teams para usuários que possuem a licença de avaliação

Você pode gerenciar os usuários que têm uma licença de avaliação da mesma forma que gerencia os usuários que têm uma licença paga normal. Para obter mais informações, consulte [Gerenciar os recursos do Microsoft Teams na sua organização do Office 365](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Atualize os usuários da licença de avaliação

Para atualizar os usuários da licença de avaliação, faça o seguinte:

1. Compre uma assinatura que inclua o Teams.

2. Remova a assinatura de avaliação do Teams do usuário.

3. Atribua as licenças adquiridas recentemente.

Para saber mais, confira [Licenças do Office 365 do Microsoft Teams](Office-365-licensing.md).
