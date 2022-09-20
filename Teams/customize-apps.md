---
title: Usar a personalização de aplicativos para marcar os aplicativos de acordo com as necessidades da sua organização
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como alterar os metadados e a aparência de um aplicativo para renomeá-lo para melhor adoção em sua organização.
ms.openlocfilehash: 6903d6bcd190869046c6f2e1a134c43cde3a1f07
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837691"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Usar a personalização de aplicativos para atualizar a identidade visual de aplicativos na loja do Teams da sua organização

Os administradores do Microsoft Teams podem modificar a aparência de alguns aplicativos do Teams para fornecer uma experiência personalizada com a marca aos usuários finais da organização. Essas modificações podem aprimorar a experiência de armazenamento do Teams para os usuários finais e ajudar a aderir à identidade visual da organização. Por exemplo, os administradores podem modificar a descrição e o ícone de um aplicativo. A personalização facilita para os usuários finais identificarem o aplicativo como ferramentas internas, entenderem seu caso de uso específico da organização e usá-lo com confiança. Os administradores fazem essas atualizações alterando alguns metadados ou propriedades de um aplicativo. As alterações estão disponíveis apenas em sua organização. Essa funcionalidade é chamada de personalização de aplicativo.

Os administradores só poderão personalizar aplicativos se o desenvolvedor do aplicativo permitir que seu aplicativo seja personalizado. Embora o Teams forneça uma opção para personalizar as propriedades a seguir, os desenvolvedores de aplicativos controlam quais propriedades podem realmente ser personalizadas por qualquer administrador.

* Nome abreviado
* Descrição breve
* Descrição completa
* URL da política de privacidade
* URL do site
* URL dos termos de uso
* Ícone do aplicativo
* Cor da estrutura de tópicos do ícone
* Cor de ênfase

Para obter informações detalhadas sobre cada uma dessas propriedades, consulte o esquema de manifesto [do Teams](/microsoftteams/platform/resources/schema/manifest-schema) na documentação do desenvolvedor do Teams.

> [!NOTE]
> Você deve ter uma licença de cliente do Teams para personalizar as informações do aplicativo.

## <a name="verify-if-an-app-is-customizable"></a>Verificar se um aplicativo é personalizável

Todos os aplicativos não são personalizáveis. Se um desenvolvedor de aplicativos permitir a personalização de seu aplicativo, somente você poderá modificar a aparência do aplicativo. Para verificar se o aplicativo de sua escolha é personalizável ou não, siga estas etapas:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Opcionalmente, se a **coluna Personalizável** não estiver visível, selecione Editar Colunas :::image type="icon" source="media/settings-icon-16px.svg"::: e alterne a **opção Personalizável** para **Ativado**.

1. Pesquise o aplicativo que você deseja personalizar usando o nome do aplicativo. Verifique na coluna **Personalizável** se o desenvolvedor do aplicativo permite que o aplicativo seja personalizado ou não.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="A captura de tela mostra que a coluna personalizável no centro de administração ajuda você a verificar se um aplicativo é personalizável ou não.":::

Para descobrir todos os aplicativos personalizáveis na loja do Teams, classifique a **coluna Personalizável** .

## <a name="customize-an-app"></a>Personalizar um aplicativo

Para alterar a aparência de um aplicativo na loja do Teams da sua organização, siga estas etapas:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pesquise o aplicativo que você deseja personalizar usando o nome do aplicativo e [verifique se ele pode ser personalizado](#verify-if-an-app-is-customizable).

1. Para abrir a interface do usuário para personalizar campos de metadados individuais, siga uma destas etapas:

   * Selecione a linha de um aplicativo e, em seguida, selecione **Personalizar** :::image type="icon" source="media/edit-pen-icon.png"::: na barra de ferramentas na página Gerenciar aplicativos.

   * Selecione o nome do aplicativo para abrir a página de detalhes do aplicativo e, em seguida, selecione o ícone de edição :::image type="icon" source="media/edit-pen-icon.png"::: **em Personalizável**.

   * Selecione o nome do aplicativo para abrir a página de detalhes do aplicativo e, em seguida, **selecione Personalizar Ações** > .

     :::image type="content" source="media/customize-action-menu.png" alt-text="A captura de tela mostra uma opção para personalizar um aplicativo abrindo o menu Ações e selecionando Personalizar na página de detalhes do aplicativo." lightbox="media/customize-action-menu-expanded.png":::

1. Personalize um ou mais dos campos disponíveis. Somente esses campos de metadados são exibidos e são personalizáveis que o desenvolvedor do aplicativo permitiu. Para obter as limitações em alguns dos campos, consulte [considerações e limitações de campos personalizáveis](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="A captura de tela exibe o nome e a descrição na interface do usuário personalizada.":::

1. Depois de personalizar o aplicativo, selecione **Aplicar**. Para verificar as alterações feitas, consulte os detalhes [do aplicativo de visualização](#preview-app-customizations). Para desfazer as alterações, consulte [redefinir detalhes do aplicativo para valores padrão](#reset-app-details-to-default-values).

1. Selecione **Publicar** para publicar o aplicativo personalizado na loja da sua organização.

O aplicativo está listado na página  Gerenciar aplicativos e na loja e no cliente do Teams (disponível por meio do cliente Web, móvel ou da área de trabalho) com os detalhes atualizados. A modificação pode levar algumas horas para ser exibida.

## <a name="preview-app-customizations"></a>Visualizar personalizações de aplicativo

Para exibir as alterações depois de salvar as personalizações, exiba a página de detalhes do aplicativo.

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir a página de detalhes do aplicativo, selecione o nome do aplicativo.

1. Exiba os detalhes do aplicativo, incluindo o nome do aplicativo original no campo **Nome curto do editor**. O campo só estará visível se você tiver alterado o nome curto do aplicativo.

   :::image type="content" source="media/original-app-version.png" alt-text="A captura de tela mostra o nome curto modificado de um aplicativo.":::

Após algumas horas, os usuários do Teams poderão ver o aplicativo personalizado na loja do Teams em seu cliente (Web, móvel e área de trabalho).

   :::image type="content" source="media/contoso-app.png" alt-text="A captura de tela mostra um aplicativo personalizado no cliente do Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Considerações e limitações da personalização do aplicativo

Considere os seguintes detalhes sobre a funcionalidade de personalização do aplicativo:

* Você só pode personalizar [aplicativos de terceiros e](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-validated-by-microsoft) não [aplicativos personalizados](deploy-apps-microsoft-teams-landing-page.md#custom-apps).

* Você não pode personalizar nenhum aplicativo nos ambientes GCCH (Government Community Cloud High) e DoD (Departamento de Defesa).

* Um aplicativo só poderá ser personalizado se o desenvolvedor do aplicativo permitir.

* As modificações em todos os aplicativos estão disponíveis somente em sua organização.

* Você terá apenas uma versão do aplicativo, pois a personalização dos detalhes do aplicativo não cria uma cópia do aplicativo.

* Ao personalizar aplicativos e qualquer descrição relacionada a um aplicativo, certifique-se de seguir as diretrizes que o desenvolvedor de aplicativos fornece em sua documentação ou termos de uso. Siga as leis de direitos autorais ao usar imagens de terceiros.

* Administração dados de personalização fornecidos são armazenados na região de armazenamento de dados mais próxima.

* Você é responsável por garantir que os links para termos de uso ou política de privacidade sejam válidos.

* Caso o desenvolvedor do aplicativo não permita mais que um campo seja personalizável, uma mensagem será exibida na página de detalhes do aplicativo notificando o administrador sobre esse campo. Todas as alterações feitas no campo são revertidas para o valor original.

* Recomendamos testar as alterações de personalização do aplicativo em um locatário de teste do Teams antes de fazer essas alterações em seu ambiente de produção. Para obter um locatário de teste, siga as instruções em [criar seu locatário de teste](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* Atualizações levar até 24 horas para aparecer no cliente para todos os usuários e contas de administrador.

* Para que um aplicativo existente se torne personalizável, o desenvolvedor pode fornecer uma nova versão do aplicativo na loja do Teams.

* O [relatório de uso](teams-analytics-and-reports/app-usage-report.md) do aplicativo exibe o nome original do aplicativo fornecido pelo editor, mesmo que o aplicativo personalizado seja usado pelos usuários finais.

* A caixa de diálogo de consentimento de permissão do Microsoft Graph exibe o nome original do aplicativo fornecido pelo editor. Ela ajuda você a identificar com precisão um aplicativo enquanto fornece permissões para ele.

* A personalização de um aplicativo não altera nenhuma funcionalidade do aplicativo.

As limitações em alguns dos campos personalizáveis estão abaixo:

| Campo personalizável | Consideração |
|:---|:---|
| Quaisquer campos de URL | Garantir URLs válidas e seguras usando `https`. |
| Descrição breve | A descrição curta deve ter menos de 80 caracteres. Não repita o que está na descrição completa. |
| Ícone | Ícone de estrutura de tópicos transparente no formato PNG que tem 32 x 32 pixels de resolução. |
| Ícone de cor | Ícone de cor inteira no formato PNG que tem 192 x 192 pixels de resolução. |
| Cor de ênfase | A cor deve corresponder à tela de fundo do ícone. |

## <a name="troubleshoot-app-customization"></a>Solucionar problemas de personalização de aplicativo

| Erros e problemas | Possível correção ou compreensão do problema |
| --- | --- |
| Minhas atualizações não estão disponíveis para meus usuários finais. | Aguarde algumas horas para que as alterações se propaguem. |
| Não consigo personalizar um aplicativo. | Verifique se o aplicativo [é personalizável ou não](#verify-if-an-app-is-customizable).|
| Comecei a personalizar um aplicativo, mas não consigo salvar nem aplicar minhas alterações. | Adera às limitações dos campos. Procurar erros na interface do usuário e as [limitações da personalização do aplicativo](#considerations-and-limitations-of-app-customization) |
| Página Gerenciar aplicativos que não estão sendo carregadas corretamente. A lista de aplicativos não é exibida. | Administração conta em uso deve ter a licença do Teams atribuída. |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>Redefinir detalhes do aplicativo para valores padrão

Você pode redefinir os detalhes do aplicativo para os valores originais fornecidos pelo desenvolvedor do aplicativo. A opção só está disponível para o aplicativo que você personalizar.

1. No Centro de administração do Teams, selecione **Aplicativos do Teams** > **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir a página de detalhes do aplicativo, selecione o nome do aplicativo.

1. No menu **Ações** , selecione **Redefinir como padrão**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="A captura de tela mostra a opção redefinir para padrão para um aplicativo personalizado.":::

## <a name="related-articles"></a>Artigos relacionados

* [Personalizar a loja de aplicativos da sua organização](customize-your-app-store.md)
* [Renomear sua postagem da comunidade de aplicativos](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
