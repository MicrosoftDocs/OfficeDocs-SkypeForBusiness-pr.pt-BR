---
title: Comprar aplicativos de terceiros para o Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Saiba como comprar aplicativos de terceiros na loja do Teams usando um cartão de crédito, um cartão de débito ou por meio de cobrança de fatura.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 20abb80fed79995bd8496a04936737265503e67e
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377189"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicativos de terceiros para o Teams

Os aplicativos do Teams estão disponíveis para instalação e alguns podem exigir assinaturas de serviço de compra para experimentar a funcionalidade e o escopo completos do aplicativo. Essas assinaturas de serviço são chamadas de ofertas de SaaS (software como serviço), que estão disponíveis para compra por meio do [AppSource](https://appsource.microsoft.com/) e agora por meio do [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com).

A página [Gerenciar aplicativos](manage-apps.md), no Centro de administração do Microsoft Teams, é onde você pode exibir e gerenciar todos os aplicativos do Teams da sua organização. Você pode ver o status e as propriedades de aplicativos no nível da organização, carregar novos aplicativos personalizados na loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização e gerenciar configurações de aplicativos em toda a organização.

Aqui, você também pode comprar licenças para serviços oferecidos por aplicativos de terceiros para usuários em sua organização. A coluna **Licenças** na tabela indica se um aplicativo oferece uma assinatura de SaaS para compra. Os usuários finais podem comprar aplicativos usando um cartão de crédito, cartão de débito ou com cobrança de fatura.

:::image type="content" source="media/manage-apps-new-page.png" alt-text="Captura de tela mostrando a página de gerenciamento de licenças de compra de aplicativos.":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicativos no Centro de administração do Teams

Para comprar aplicativos no Centro de administração do Teams, siga estas etapas:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**. Você deve ser um administrador global ou administrador de serviços do Teams para acessar a página.

1. Pesquise o aplicativo desejado pelo nome. Para identificar aplicativos que têm uma assinatura de SaaS paga, examine a coluna **Licenças**. Cada aplicativo tem um dos seguintes valores:
    * **Comprar**: o aplicativo oferece uma assinatura de SaaS e está disponível para compra.
    * **Comprado**: O aplicativo oferece uma assinatura de SaaS e você comprou licenças para ele.
    * **- -**: O aplicativo não oferece uma assinatura de SaaS.

1. Quando você encontrar o aplicativo, selecione **Comprar** para ir para a guia Planos e **assinaturas** da página de detalhes do aplicativo. Examine os planos e as informações de preços da oferta de SaaS para o aplicativo. Se precisar de mais informações, selecione **Saiba mais** para acessar a página do aplicativo no [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > Planos privados também podem ser listados para compra, que incluem preços especiais que sua organização pode negociar separadamente com um desenvolvedor de aplicativos. Esses planos têm o rótulo **Plano privado** sob o nome do plano.

1. Para assinar um aplicativo, escolha o plano desejado e selecione **Comprar**. O fluxo de check-out é aberto diretamente no Centro de administração do Teams.

1. Selecione o número de licenças de usuário que você deseja comprar.

1. Verifique se a conta de cobrança e o endereço vendido estão corretos. Se você ainda não tiver um, selecione **Adicionar**. Para obter mais informações sobre contas de cobrança, confira [Noções básicas sobre contas de cobrança](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Somente um administrador global pode adicionar uma nova conta de cobrança.

1. Verifique se o perfil de cobrança correto está selecionado. Se você ainda não tiver um, selecione **Adicionar novo**. Você pode pagar com um cartão de crédito, cartão de débito ou com cobrança [de fatura](#invoice-billing). O perfil de cobrança também permite adicionar um número de pedido de compra para identificar seu pedido mais tarde. Para obter mais informações sobre perfis de cobrança, confira [Noções básicas sobre perfis de cobrança](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Selecione **Fazer pedido**.

1. Selecione **Configurar** para ativar sua assinatura no site do desenvolvedor do aplicativo. Se você não configurar sua assinatura após a compra, poderá fazer isso mais tarde selecionando **Gerenciar assinaturas**.

Depois de comprar a oferta de SaaS associada ao aplicativo Teams, você poderá exibir os seguintes detalhes de compra na guia Planos e **assinaturas** da página de detalhes do aplicativo.

* **Data de ativação da licença**: data em que sua licença foi ativada.
* **Licenças**: número de licenças adquiridas.

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text="Captura de tela da guia Planos e preços na página de detalhes do aplicativo no Centro de administração do Teams." lightbox="media/purchase-third-party-apps-details-page.png":::

Selecione **Gerenciar assinaturas** para exibir e gerenciar as licenças adquiridas.

Os administradores globais podem exibir as assinaturas adquiridas por qualquer pessoa na organização, mas só podem adicionar mais licenças, remover licenças e cancelar assinaturas para compras feitas por qualquer pessoa em sua conta de cobrança. Os administradores de serviços do Teams podem executar as mesmas ações para compras feitas por si mesmos.

> [!NOTE]
> Se um administrador global quiser gerenciar uma assinatura adquirida por outro administrador global, ele precisará estar na mesma conta de cobrança. Você pode dar a outro administrador global acesso a uma assinatura adquirida selecionando o aplicativo no [Centro de administração do Microsoft 365](https://admin.microsoft.com). No centro de administração, acesse **Exibir perfil de cobrança** > **Selecionar conta de cobrança** > **Atribuir funções** > **Adicionar outros Administradores globais**.

> [!IMPORTANT]
> Quando você habilita a compra de aplicativos, também ativa a compra no aplicativo. Os usuários podem ver ofertas de compra no aplicativo que são controladas pelo desenvolvedor do aplicativo para seus aplicativos. Para impedir que os usuários comprem um aplicativo, é necessário bloquear o aplicativo.

### <a name="invoice-billing"></a>Cobrança de fatura

* A cobrança de fatura está disponível como uma opção de pagamento para algumas transações.
* Uma revisão de crédito é necessária na primeira vez que você usa a cobrança de fatura, o que pode levar de 24 a 48 horas para aprovação. A cobrança de fatura não estará disponível até que a verificação de crédito seja concluída. Você pode fazer seu pedido com um cartão de crédito ou tentar novamente mais tarde depois que sua revisão de crédito for aprovada.
* A cobrança de fatura só está disponível para administradores globais ou um administrador com permissões de administrador de serviço e de cobrança do Teams.
* A cobrança de fatura não está disponível ao comprar um plano com uma avaliação gratuita de 30 dias.

## <a name="manage-subscriptions-in-teams-admin-center"></a>Gerenciar assinaturas no Centro de administração do Teams

No Centro de administração do Teams, você pode gerenciar as assinaturas de aplicativo e as licenças adquiridas. Você pode exibir a lista de assinaturas de aplicativo e seus detalhes e executar as seguintes ações:

* Alterar um plano
* Comprar ou remover licença
* Atualizar uma forma de pagamento
* Cancelar uma assinatura
* Exibir sua fatura

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="Captura de tela dos detalhes da assinatura de um aplicativo." lightbox="media/manage-existing-subscriptions-all.png":::

Para gerenciar assinaturas, siga estas etapas:

1. Entre no centro de administração do Teams e acesse os aplicativos **do Teams Gerenciar** > [**aplicativos**](https://admin.teams.microsoft.com/policies/manage-apps) .

1. Selecione a **guia Assinaturas** para exibir as assinaturas que você comprou.

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="Captura de tela da opção de assinatura para um aplicativo na página gerenciar aplicativos." lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> No Centro de administração do Teams, você pode gerenciar as assinaturas de aplicativo adquiridas por você ou por outros administradores que fazem parte da mesma conta de cobrança. Para exibir todas as assinaturas de aplicativo adquiridas para o mesmo locatário por outros administradores ou adquiridas usando contas de cobrança diferentes, visite o [Centro de administração do Microsoft 365](https://admin.microsoft.com/adminportal/home#/homepage).

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Listar e vender uma oferta de SaaS para um aplicativo do Teams

Os desenvolvedores podem criar ofertas de SaaS associadas aos aplicativos do Teams. Essas ofertas são publicadas por meio do [Partner Center](https://partner.microsoft.com) e estão disponíveis para as organizações comprarem por meio do [AppSource](https://appsource.microsoft.com/) e do Centro de administração do Microsoft Teams.

Para obter mais informações para desenvolvedores de aplicativos de terceiros, confira [Criar uma oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Artigos relacionados

* [Gerenciar seus aplicativos no Centro de Administração do Microsoft Teams](manage-apps.md)
* [Criar uma oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Funções internas do Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Funções de administrador do Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
