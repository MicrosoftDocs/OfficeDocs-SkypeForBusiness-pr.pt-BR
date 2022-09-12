---
title: Usar a personalização de aplicativos para marcar os aplicativos de acordo com as necessidades da sua organização
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como alterar os metadados e a aparência de um aplicativo para renomeá-lo para melhor adoção em sua organização.
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647475"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Usar a personalização de aplicativos para atualizar a identidade visual de aplicativos na loja do Teams da sua organização

Os administradores do Microsoft Teams podem modificar a aparência de alguns aplicativos do Teams para fornecer uma experiência personalizada com a marca aos usuários finais da organização. Essas modificações podem aprimorar a experiência de armazenamento do Teams para os usuários finais e ajudar a aderir à identidade visual da organização. Por exemplo, os administradores podem modificar a descrição e o ícone de um aplicativo que torna mais fácil para os usuários finais de suas organizações identificarem o aplicativo, entenderem seu uso e para maior destaque. Os administradores fazem essas alterações alterando alguns metadados ou propriedades de um aplicativo. As alterações estão disponíveis apenas em sua organização. Essa funcionalidade é chamada de personalização de aplicativo.

Os administradores só poderão personalizar aplicativos se o desenvolvedor do aplicativo permitir que seu aplicativo seja personalizado. Embora o Teams forneça uma opção para personalizar algumas propriedades, os desenvolvedores de aplicativos controlam as propriedades que podem ser personalizadas por qualquer administrador.

Como administrador, você pode personalizar as propriedades a seguir.

* Nome abreviado
* Descrição breve
* Descrição completa
* URL da política de privacidade
* URL do site
* URL dos termos de uso
* Ícone do aplicativo
* Cor da estrutura de tópicos do ícone
* Cor de ênfase

Para obter informações detalhadas sobre cada um desses campos de metadados, consulte o esquema de manifesto do [Teams](/microsoftteams/platform/resources/schema/manifest-schema) na documentação do desenvolvedor do Teams.

> [!NOTE]
> A funcionalidade de personalização de aplicativos não está disponível para aplicativos personalizados. Os administradores não podem personalizar nenhum aplicativo nos ambientes GCCH (Government Community Cloud High) e DoD (Departamento de Defesa).

## <a name="verify-if-an-app-is-customizable"></a>Verificar se um aplicativo é personalizável

Todos os aplicativos não são personalizáveis. Se um desenvolvedor de aplicativos permitir que você personalize seu aplicativo, somente você poderá usar a funcionalidade de personalização do aplicativo para modificar a aparência do aplicativo. Para verificar se o aplicativo de sua escolha é personalizável ou não, siga estas etapas:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pesquise o aplicativo que você deseja personalizar usando o nome do aplicativo. Verifique na coluna **Personalizável** se o desenvolvedor do aplicativo permite que o aplicativo seja personalizado ou não. Se a coluna não estiver visível, selecione Editar Colunas :::image type="icon" source="media/settings-icon-16px.svg"::: e alterne **a opção Personalizável** para **Ativado**.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="A captura de tela mostra que a coluna personalizável no centro de administração ajuda você a verificar se um aplicativo é personalizável ou não.":::

Para descobrir todos os aplicativos personalizáveis na loja do Teams, classifique a coluna Personalizável.

## <a name="customize-the-details-of-an-app"></a>Personalizar os detalhes de um aplicativo

Para alterar a aparência de um aplicativo como ele aparece na loja do Teams da sua organização, siga estas etapas:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pesquise o aplicativo que você deseja personalizar usando o nome do aplicativo e verifique se ele pode ser personalizado.

1. Para abrir a interface do usuário para personalizar campos de metadados individuais, siga uma destas etapas:

   * Selecione a linha de um aplicativo e, em seguida, selecione **Personalizar** :::image type="icon" source="media/edit-pen-icon.png"::: na barra de ferramentas na página Gerenciar aplicativos.

   * Selecione o nome do aplicativo para abrir a página de detalhes do aplicativo e, em seguida, selecione o ícone de edição :::image type="icon" source="media/edit-pen-icon.png"::: **em Personalizável**.

   * Selecione o nome do aplicativo, selecione **Ações** e selecione **Personalizar**.

     :::image type="content" source="media/customize-action-menu.png" alt-text="A captura de tela mostra uma opção para personalizar um aplicativo abrindo o menu Ações e selecionando Personalizar na página de detalhes do aplicativo." lightbox="media/customize-action-menu-expanded.png":::

1. Personalize um ou mais dos campos disponíveis. Um desenvolvedor de aplicativos pode permitir que apenas alguns dos campos de metadados sejam personalizados. Consulte [considerações e limitações de campos personalizáveis](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="A captura de tela exibe o nome e a descrição na interface do usuário personalizada.":::

1. Depois de personalizar o aplicativo, selecione **Aplicar**. Para verificar as alterações feitas, consulte os detalhes [do aplicativo de visualização](#preview-app-details). Para desfazer as alterações, consulte [redefinir detalhes do aplicativo para valores padrão](#reset-app-details-to-default-values).

1. Selecione **Publicar** para publicar o aplicativo personalizado e veja-o listado na página **Gerenciar aplicativos** .

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>Visualizar detalhes do aplicativo

Para exibir as alterações depois de salvar a personalização, exiba a página de detalhes do aplicativo.

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir a página de detalhes do aplicativo, selecione o nome do aplicativo.

1. Exiba os detalhes do aplicativo, incluindo o nome do aplicativo original no campo **Nome curto do editor**. O campo só estará visível se você tiver alterado o nome curto do aplicativo.

   :::image type="content" source="media/original-app-version.png" alt-text="A captura de tela mostra o nome curto modificado de um aplicativo.":::

Os usuários do Teams podem ver o aplicativo personalizado na loja do Teams em seu cliente.

   :::image type="content" source="media/contoso-app.png" alt-text="A captura de tela mostra um aplicativo personalizado no cliente do Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Considerações e limitações da personalização do aplicativo

Considere os seguintes detalhes sobre a funcionalidade de personalização do aplicativo:

* Você terá apenas uma versão do aplicativo, pois a personalização dos recursos do aplicativo não cria uma cópia do aplicativo.

* Ao personalizar aplicativos e qualquer descrição relacionada a um aplicativo, certifique-se de seguir as diretrizes que o desenvolvedor do aplicativo fornece em sua documentação ou termos de uso. Siga as leis de direitos autorais ao usar imagens de terceiros.

* Os dados de personalização fornecidos pelo administrador são armazenados na região mais próxima.

* Você é responsável por garantir que os links para termos de uso ou política de privacidade sejam válidos.

* Caso o desenvolvedor do aplicativo não permita mais que um campo seja personalizável, uma mensagem aparecerá na página de detalhes do aplicativo notificando o administrador sobre os campos que não podem mais ser personalizados. Todas as alterações feitas nesse campo serão revertidas para os valores originais.

* Recomendamos testar as alterações de personalização do aplicativo em um locatário de teste do Teams antes de fazer essas alterações em seu ambiente de produção. Para obter um locatário de teste, siga as instruções em [criar seu locatário de teste](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* As alterações levam até 24 horas para serem propagadas para todos os usuários.

* Para que um aplicativo se torne personalizável, os desenvolvedores podem fornecer uma nova versão do aplicativo. Carregue a nova versão e remova a versão anterior do aplicativo. Se você personalizou um aplicativo e o publicou, o novo aplicativo personalizado usando o recurso de personalização do aplicativo não substituirá o aplicativo atual.

* O [relatório de uso do aplicativo](teams-analytics-and-reports/app-usage-report.md) exibe o nome original do aplicativo fornecido pelo editor.

* A caixa de diálogo de consentimento de permissão do Microsoft Graph exibe o nome original do aplicativo fornecido pelo editor. Ela ajuda você a identificar com precisão um aplicativo enquanto fornece permissões para ele.

As limitações nos campos personalizáveis estão abaixo:

| Campo personalizável | Consideração |
|:---|:---|
| Quaisquer campos de URL | Garantir URLs válidas e seguras usando `https`. |
| Descrição breve | A descrição curta deve ter menos de 80 caracteres e não repetir o que está na descrição completa. |
| Ícone | Ícone de estrutura de tópicos transparente no formato PNG que tem 32 x 32 pixels de resolução. |
| Ícone de cor | Ícone de cor inteira no formato PNG que tem 192 x 192 pixels de resolução. |
| Cor de ênfase | A cor deve corresponder à tela de fundo do ícone. |

## <a name="reset-app-details-to-default-values"></a>Redefinir detalhes do aplicativo para valores padrão

Você pode redefinir os detalhes do aplicativo para os valores originais fornecidos pelo desenvolvedor do aplicativo. A opção só está disponível para o aplicativo que você personalizar.

1. No Centro de administração do Teams, selecione **Aplicativos do Teams** > **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Para abrir a página de detalhes do aplicativo, selecione o nome do aplicativo.

1. No menu **Ações** , selecione **Redefinir como padrão**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="A captura de tela mostra a opção redefinir para padrão para um aplicativo personalizado.":::

## <a name="related-articles"></a>Artigos relacionados

* [Personalizar a loja de aplicativos da sua organização](customize-your-app-store.md)
* [Rebatize seus aplicativos](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
