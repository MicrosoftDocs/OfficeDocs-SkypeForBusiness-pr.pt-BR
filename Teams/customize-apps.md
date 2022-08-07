---
title: Modificar a aparência dos aplicativos na loja do Teams da sua organização
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Saiba como alterar a aparência do aplicativo e renomear um aplicativo editando detalhes e metadados do aplicativo.
ms.openlocfilehash: 32c526e2cbbb4ef464e0daa777228e0a17dd391b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269076"
---
# <a name="customize-appearance-of-apps-in-your-organizations-teams-store"></a>Personalize a aparência dos aplicativos na loja do Teams da sua organização

O Microsoft Teams permite que os administradores personalizem o aplicativo Teams para aprimorar a experiência da loja e aderir à identidade visual da organização. Um desenvolvedor de aplicativos pode permitir que seu aplicativo seja personalizado por um administrador do Teams. Em seguida, você pode atualizar as propriedades do aplicativo com base nas necessidades organizacionais, na página Gerenciar aplicativos no Centro de administração do Teams. Os detalhes que você pode personalizar são:

* Nome abreviado
* Descrição breve
* Descrição completa
* URL da política de privacidade
* URL do site
* URL dos termos de uso
* Ícone do aplicativo
* Cor da estrutura de tópicos do ícone
* Cor de ênfase

Para obter informações sobre os vários campos de metadados do aplicativo, consulte [Esquema do manifesto do Teams](/microsoftteams/platform/resources/schema/manifest-schema) na documentação do desenvolvedor.

> [!NOTE]
> Você não pode personalizar aplicativos com sideload em nenhuma organização. Você não pode personalizar nenhum aplicativo na Nuvem da Comunidade Governamental - Alta (GCCH) ou nas nuvens do DoD (Departamento de Defesa).

## <a name="customize-details-of-an-app"></a>Personalizar detalhes de um aplicativo

Para personalizar um aplicativo, conclua as seguintes etapas:

1. Entre no Centro de administração do Teams.

1. Expanda **aplicativos Teams** e selecione **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Verifique a coluna **Personalizável** da lista de aplicativos e classifique por aplicativos personalizáveis.

   ![A coluna de personalização no centro de administração ajuda você a ver os aplicativos que são personalizáveis.](media/customizable-apps-in-tac.png)

   Há três pontos de entrada para acessar o recurso de personalização:

   * Selecione ao lado do aplicativo que você deseja personalizar e selecione **Personalizar**.

     ![A opção de seleção de personalização 1.](media/select-app-to-customize1.png)

   * Selecione o nome do aplicativo e, em seguida, selecione o ícone de edição em **Personalizável**.

     ![A opção de seleção de personalização 2.](media/communities-microsoft.png)

   * Selecione o nome do aplicativo, clique no **menu estouro** passe o mouse sobre **Ações** e selecione personalizar.

     ![A opção de seleção de personalização 3.](media/customize-action-menu.png)

1. Expanda a seção **Detalhes** e personalize um ou mais dos campos a seguir. Os campos atribuídos como personalizáveis pelo desenvolvedor estão visíveis.

    * Nome abreviado
    * Descrição breve
    * Descrição completa
    * Site
    * URL da política de privacidade
    * URL dos termos de uso

   ![As configurações de personalização.](media/customize-settings.png)

1. Expanda a seção **Ícone**.

1. Carregar um item. Use um ícone (192 x 192) pixel no formato PNG.

1. Escolher uma cor da estrutura de tópicos do ícone. Use um pixel de contorno transparente (32x32) no formato PNG.

1. Selecione uma cor de destaque do aplicativo que corresponda ao ícone.

   ![Personalize as opções de cor do painel de ícones.](media/customize-app-colors.png)

1. Depois de personalizar o aplicativo, selecione **Aplicar**.

1. Selecione **Publicar** para publicar o aplicativo personalizado.

   O aplicativo personalizado agora está listado na página **Gerenciar aplicativos**. Você terá apenas uma versão do aplicativo, pois a personalização dos recursos do aplicativo não cria uma cópia do aplicativo.

Agora, os usuários finais do Teams podem ver o aplicativo personalizado no cliente.

   ![Aplicativo personalizado no cliente do Teams.](media/contoso-app.png)

Observe os seguintes detalhes sobre a personalização de um aplicativo:

* Ao personalizar aplicativos e qualquer descrição relacionada a ele, certifique-se de seguir as diretrizes de personalização, se fornecidas pelo editor do aplicativo em sua documentação ou termos de uso. Você também é responsável por respeitar os direitos de outras pessoas em relação a quaisquer imagens de terceiros que você possa usar.

* Os dados de personalização fornecidos pelo administrador são armazenados na região mais próxima.

* Você é responsável por garantir que os links para os termos de uso ou a política de privacidade sejam válidos.

* Caso o editor do aplicativo não permita mais que um campo seja personalizável, uma mensagem será exibida na página de detalhes do aplicativo notificando o administrador sobre os campos que não podem mais ser personalizados. Todas as alterações feitas nesse campo serão revertidas para os valores originais.

* Recomendamos testar as alterações de personalização do aplicativo em um locatário de teste do Teams antes de fazer essas alterações em seu ambiente de produção.

* As alterações na identidade visual podem exigir até 24 horas para serem propagadas para todos os usuários.

* Para que um aplicativo se torne personalizável, os desenvolvedores podem fornecer uma nova versão do aplicativo. Carregue a nova versão e remova a versão anterior do aplicativo. Se você personalizou um aplicativo e o publicou, o novo aplicativo personalizado usando o recurso de personalização do aplicativo não substituirá o aplicativo atual.

* O [relatório de uso do aplicativo](teams-analytics-and-reports/app-usage-report.md) exibe o nome original do aplicativo fornecido pelo editor.

* A caixa de diálogo de consentimento de permissão do Microsoft Graph exibe o nome original do aplicativo fornecido pelo editor. Ela ajuda você a identificar com precisão um aplicativo enquanto fornece permissões para ele.

## <a name="review-app-details"></a>Examinar detalhes do aplicativo

Talvez você queira ver os detalhes do aplicativo para examinar as informações.

1. Entre no Centro de administração do Teams.

1. Expanda **aplicativos Teams** e selecione **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Selecione o nome do aplicativo.

1. Exiba os detalhes do aplicativo, incluindo o nome do aplicativo original **Nome curto do editor**.

   ![Personalize o nome do aplicativo do painel de ícones.](media/original-app-version.png)

   O campo **Nome curto do editor** só estará visível se você tiver alterado o nome curto do aplicativo.

## <a name="reset-app-details-to-default-values"></a>Redefinir detalhes do aplicativo para valores padrão

Você pode redefinir os detalhes do aplicativo para os valores originais fornecidos pelo desenvolvedor do aplicativo. A opção só está disponível para o aplicativo que você personalizar.

1. No Centro de administração do Teams, selecione **Aplicativos do Teams** > **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Selecione o nome do aplicativo.

1. Selecione **Redefinir para padrão** no menu **Ações**.

   ![Selecione redefinir para o padrão realçado.](media/select-reset.png)

## <a name="related-article"></a>Artigo relacionado

* [Gerenciar aplicativos](manage-apps.md)
* [Personalizar a loja de aplicativos da sua organização](customize-your-app-store.md)
* [Rebatize seus aplicativos](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
