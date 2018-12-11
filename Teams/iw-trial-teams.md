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
localization_priority: Normal
description: Os usuários do Office 365 que não estejam licenciados for Microsoft Teams podem iniciar uma versão de avaliação das equipes 1 ano.
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc0b62ce0be0606ad4c31d3cee04347729fbbe32
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27214577"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Gerenciar a oferta de avaliação na nuvem comercial do Microsoft Teams
=======================================================

Teams da Microsoft é uma ótima ferramenta colaborativa para sua organização. Ele capacita pessoas e equipes para discutir, inovem e compartilhem ideias usando o poder do Office 365. O Microsoft equipes comerciais nuvem avaliação oferece usuários existentes do Office 365 em sua organização que não são licenciados for Microsoft Teams iniciar uma versão de avaliação do produto 1 ano. Os administradores podem alternar esse recurso ativada ou desativada para usuários em suas organizações.

## <a name="whats-in-the-offer"></a>Novidades da oferta de

Os planos de serviço incluídos nesta oferta são:

- Exchange Foundation
- Fluxo de plano 1 do Office 365
- Planejador da Microsoft
- Equipes da Microsoft (Teams1, equipes IW)
- Office Online
- PowerApps para o Office 365 plano 1
- SharePoint Online quiosque
- Sway
- O Yammer Enterprise

A versão de avaliação concede uma assinatura de avaliação de um ano em toda sua organização. A versão de avaliação torna 500.000 licenças disponíveis para atribuição. Para cada licença foi atribuída, a versão de avaliação aloca 2 GB de armazenamento do SharePoint Online. 

## <a name="who-is-eligible"></a>Quem pode participar

Os usuários devem ser habilitados se inscrever para aplicativos e avaliações (no Centro de administração do Office 365). Para obter mais informações, consulte [Manage a avaliação](#manage-the-trial) neste artigo. 

Os usuários que não têm uma licença do Office 365 que inclui as equipes podem iniciar a oferta de avaliação de nuvem comercial do Microsoft equipes. Por exemplo, se um usuário tiver o Office 365 Business (que não inclui as equipes), eles estarão elegíveis para a versão de avaliação.

## <a name="who-is-not-eligible"></a>Quem não é qualificado

Sua organização não é qualificada para a avaliação se: 

- Você é um cliente de parceiro agregação
- Você é um cliente de parceiro do revendedor
- Você é um cliente do governo ou EDU

Se sua organização for não qualificada para a oferta de avaliação de comercial nuvem Microsoft equipes, você não verá a opção **Permitir que os usuários a instalar os serviços e aplicativos de avaliação** .

## <a name="how-users-sign-up-for-the-trial"></a>Como os usuários Inscreva-se para a versão de avaliação

Usuários qualificados podem Inscreva-se para a oferta de avaliação por log em equipes ([teams.microsoft.com](https://teams.microsoft.com)). Eles verão a tela a seguir para iniciar a versão de avaliação. 

![Captura de tela da página inicial para a versão de avaliação do operador de informações de equipes.](media/iw-trial-start-screen.png)

Todas as tentativas dentro da sua organização compartilham o mesmo datas de início e fim, que é a data em que o primeiro usuário se inscreveu para a versão de avaliação. Por exemplo, se o usuário inicia a versão de avaliação primeiro em 25 de janeiro de 2019 e o usuário B inicia uma avaliação de 3 de junho de 2019, avaliação de ambos os usuários expirará em 25 de janeiro de 2020.

## <a name="manage-the-trial"></a>Gerenciar a versão de avaliação

Os administradores podem gerenciar as licenças para usuários que se inscreveu. 

Além disso, os administradores podem desabilitar a capacidade para os usuários finais a declaração avaliação aplicativos e serviços dentro de sua organização. Atualmente, a versão de avaliação descrito neste artigo é apenas avaliação nesta categoria, mas ele pode ser aplicadas a outros programas semelhantes no futuro. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Impedir que os usuários instalem os serviços e aplicativos de avaliação

Você pode desativar a capacidade de um usuário para instalar os serviços e aplicativos de avaliação.

1. Desde o [Centro de administração do Microsoft 365](https://portal.office.com/adminportal/home), vá para **configurações** > **Serviços & suplementos** > **usuário pertencentes a aplicativos e serviços**.

    ![Captura de tela da página Serviços & suplementos no Centro de administração do Office 365.](media/iw-trial-enable-1.png)

2. Desative o **permitem que os usuários a instalar os serviços e aplicativos de avaliação**.

    ![Captura de tela do usuário pertencentes a página de aplicativos e serviços no Centro de administração do Office 365.](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Gerenciar a disponibilidade de avaliação para um usuário com uma licença que inclui as equipes

Um usuário que é atribuído a uma licença que inclui as equipes não é qualificado para a versão de avaliação. Quando o plano de serviço de equipes estiver habilitado, o usuário pode fazer logon e usar equipes. Se o plano de serviço estiver desabilitado, o usuário não pode fazer logon e não é apresentado com a opção de avaliação ou.

Para desativar o acesso às equipes:

1. No Centro de administração do Microsoft 365, selecione **usuários** > **usuários ativos**.

2. Marque a caixa ao lado do nome do usuário.

3. À direita, na linha **licenças do produto** , escolha **Editar**.

4. No painel de **licenças do produto** , alterne a alternância para **desativado**.

    ![Captura de tela da página de licenças do produto no Centro de administração do Office 365.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Gerenciar a disponibilidade de equipes para usuários que já tinha solicitado a versão de avaliação

Se um usuário tenha solicitado uma licença de avaliação de equipes, você poderá ser removido, removendo o plano de licença ou serviço.

Para desativar a licença de avaliação:

1. No Centro de administração do Microsoft 365, selecione **usuários** > **usuários ativos**.

2. Marque a caixa ao lado do nome do usuário.

3. À direita, na linha **licenças do produto** , escolha **Editar**.

4. No painel de **licenças do produto** , alterne a alternância para **desativado**.

    ![Captura de tela da configuração de licença de avaliação de equipes, no painel de licenças de produto](media/iW-trial-enable-4.png)

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Gerenciar equipes para usuários que possuem a licença de avaliação

Você pode gerenciar usuários que têm uma licença de avaliação, assim como você gerencia os usuários que têm uma licença paga regular. Para obter mais informações, consulte [os recursos de gerenciar equipes da Microsoft em sua organização do Office 365](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Atualizar os usuários a partir da licença de avaliação

Para atualizar os usuários a licença de avaliação, faça o seguinte:

1. Compre uma assinatura que inclui as equipes.

2. Remova a inscrição de avaliação de equipes do usuário.

3. Atribua a licença adquirida recentemente.

Para mais informações, consulte [Licenciamento do Office 365 para o Microsoft Teams](Office-365-licensing.md).