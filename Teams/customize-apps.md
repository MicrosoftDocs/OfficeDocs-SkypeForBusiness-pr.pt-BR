---
title: Personalizar aplicativos no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como personalizar aplicativos em Microsoft Teams.
ms.openlocfilehash: cac5bc4e5d2748b8e4a9143d50e40dbf96ae80a0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410614"
---
# <a name="customize-apps-in-microsoft-teams"></a>Personalizar aplicativos no Microsoft Teams

 Microsoft Teams oferece personalização de aplicativo para aprimorar a experiência Teams aplicativo. Alguns desenvolvedores de aplicativos permitem que um aplicativo seja personalizado pelo Teams administrador. O administrador pode personalizar ou renomear as propriedades do aplicativo com base nas necessidades organizacionais usando o centro de administração Teams **página Gerenciar** aplicativos. Os detalhes que você pode personalizar são:

- Nome curto
- Descrição curta
- Descrição completa
- URL da política de privacidade
- URL do site
- URL de termos de uso
- Ícone de cor
- Ícone de outline
- Cor do destaque

Consulte o [Teams de manifesto para](/microsoftteams/platform/resources/schema/manifest-schema) obter detalhes sobre os campos que você pode personalizar.

> [!NOTE]
> Não há suporte para personalização de aplicativos Nuvem da Comunidade Governamental High (GCCH) ou Departamento de Defesa (DoD) neste momento.
> Atualmente, esse recurso não está disponível para aplicativos Microsoft Teams sideload.

## <a name="customize-the-apps-details"></a>Personalizar os detalhes do aplicativo

Para começar a personalizar um aplicativo, conclua as seguintes etapas:

1. Entre no Centro de administração do Teams.

2. **Expanda Teams Aplicativos e** selecione **Gerenciar aplicativos**.

3. Verifique a **coluna Personalizável** da lista de aplicativos e classificar por aplicativos personalizáveis.

   ![A coluna personalizar que está ordenada.](media/customize-column.png)

   Há três pontos de entrada para acessar o recurso personalizar:

   - Selecione ao lado do aplicativo que você deseja personalizar e selecione **Personalizar**.

     ![A opção personalizar seleção 1.](media/select-app-to-customize1.png)

   - Selecione o nome do aplicativo e **personalizável**.

     ![A opção personalizar seleção 2.](media/app-details-customizable.png)

   - Selecione o nome do aplicativo e selecione **Personalizar** no menu suspenso **Ações** .

     ![A opção personalizar seleção 3.](media/customize-action-menu.png)

4. Expanda **a seção Detalhes** e personalize os seguintes campos:

    - Nome curto
    - Descrição curta
    - Descrição completa
    - Site
    - URL da política de privacidade
    - URL de termos de uso

   ![As configurações de personalização.](media/customize-settings.png)

> [!Note]
> Somente os campos atribuídos pelo desenvolvedor de aplicativos como personalizáveis estarão visíveis.

5. Expanda **a seção Ícone** .

   1. Upload um ícone. Use um ícone de cor completa (192 x 192) pixel no formato PNG.

   1. Escolha uma cor de contorno de ícone. Use um pixel de contorno transparente (32x32) no formato PNG.

   1. Selecione uma cor de destaque do aplicativo que corresponde ao ícone.

    ![Personalize as opções de cores do painel de ícones.](media/customize-app-colors.png)

6. Depois que seu aplicativo tiver sido personalizado, selecione **Aplicar**.

7. Selecione **Publicar** para publicar o aplicativo personalizado.

   O aplicativo personalizado agora está listado na página **Gerenciar aplicativos** . Você terá apenas uma versão do aplicativo, já que a personalização dos recursos do aplicativo não cria uma cópia do aplicativo.

Agora, Teams usuários finais podem abrir o cliente Teams para ver o aplicativo personalizado.

   ![Aplicativo personalizado no Teams cliente.](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a>Considerações especiais para personalizar um aplicativo

A observação a seguir inclui detalhes importantes sobre como personalizar um aplicativo.

> [!Note]
> - Ao personalizar aplicativos e qualquer descrição relacionada a um aplicativo, certifique-se de seguir quaisquer diretrizes de personalização, se fornecidos pelo editor de aplicativos em sua documentação ou termos de uso. Você também é responsável por respeitar os direitos de outras pessoas em relação a quaisquer imagens de terceiros que você possa usar.
> - Os dados de personalização fornecidos pelo administrador são armazenados na região mais próxima.
> - Você é responsável por garantir que os links para termos de uso ou política de privacidade sejam válidos.
> - Caso o editor de aplicativos não permita mais que um campo seja personalizável, uma mensagem será exibida na página de detalhes do aplicativo notificando o administrador sobre os campos que não podem mais ser personalizados. Todas as alterações feitas nesse campo serão revertidas para os valores originais.
> - Recomendamos testar as alterações de personalização do aplicativo em um Teams de teste antes de fazer essas alterações em seu ambiente de produção.
> - As alterações na identidade visual podem exigir até 24 horas para os usuários verem as alterações.

## <a name="review-app-details"></a>Revisar detalhes do aplicativo

Talvez você queira ver os detalhes do aplicativo para revisar as informações.

1. Entre no Centro de administração do Teams.

2. Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.

3. Selecione o nome do aplicativo.

4. Exibir os detalhes do aplicativo, incluindo o nome do aplicativo original **Nome curto do editor**.

   ![Personalizar o nome do aplicativo do painel de ícones.](media/original-app-version.png)

   O **nome curto do campo editor** só será visível se você tiver alterado o nome curto do aplicativo.

## <a name="reset-app-details-to-default"></a>Redefinir os detalhes do aplicativo como padrão

A qualquer momento, você pode redefinir os detalhes do aplicativo para as configurações originais.

1. Entre no Centro de administração do Teams.

2. **Expanda Teams Aplicativos e** selecione **Gerenciar aplicativos**.

3. Selecione o nome do aplicativo.

4. Selecione **Redefinir como padrão** no menu suspenso **Ações** .

   ![Selecione redefinir para o padrão realçado.](media/select-reset.png)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quanto tempo levará para meus usuários verem o aplicativo personalizado?**

Embora o administrador possa ver imediatamente as alterações no Teams Admin Center, pode levar até 24 horas para os usuários finais verem as alterações.  

**O provedor de aplicativos pode personalizar o aplicativo para seus clientes?**

 Não, o administrador de um locatário precisa personalizar o aplicativo para seu locatário usando o Teams Admin Center.

**O aplicativo personalizado será implantado automaticamente para substituir meu aplicativo personalizado atual em um locatário?**

Não, os administradores de locatários terão que remover manualmente qualquer aplicativo personalizado e publicar a versão personalizada do aplicativo. Se você tiver personalizado um aplicativo e publicado como um aplicativo personalizado, o novo aplicativo personalizado usando o recurso de personalização do aplicativo não substituirá o aplicativo personalizado atual.  

**O relatório de uso do aplicativo também mostrará os valores personalizados, como nome curto personalizado?**

 Não, o relatório de uso do aplicativo ainda mostrará o nome original do aplicativo enviado do editor.

**Quais aplicativos posso personalizar usando o recurso de personalização do aplicativo?**

Você só pode personalizar aplicativos que tenham permissão para serem personalizáveis pelo editor de aplicativos. O editor de aplicativos precisará optar por permitir que seus clientes personalizem o aplicativo.

**As propriedades personalizadas aparecerão na tela de consentimento de permissão do gráfico?**

Não, a tela de consentimento de permissão ainda mostrará o valor original enviado pelo editor.

## <a name="related-article"></a>Artigo relacionado

- [Gerenciar aplicativos](manage-apps.md)
- [Personalizar sua loja de aplicativos](customize-your-app-store.md)
- [Renomear seus aplicativos](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
