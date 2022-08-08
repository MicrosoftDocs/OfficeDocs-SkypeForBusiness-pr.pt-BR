---
title: Comprar aplicativos de terceiros para o Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Saiba como comprar aplicativos de terceiros na loja do Teams usando um cartão de crédito, um cartão de débito ou por meio de cobrança de fatura.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 9da0b39582238f10fc3d76d7299afd0b004048fd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270826"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicativos de terceiros para o Teams

Os aplicativos do Teams estão disponíveis para instalação e alguns podem exigir assinaturas de serviço de compra para experimentar a funcionalidade e o escopo completos do aplicativo. Essas assinaturas de serviço são chamadas de ofertas de SaaS (software como serviço), que estão disponíveis para compra por meio do [AppSource](https://appsource.microsoft.com/) e agora por meio do [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com).

A página [Gerenciar aplicativos](manage-apps.md), no Centro de administração do Microsoft Teams, é onde você pode exibir e gerenciar todos os aplicativos do Teams da sua organização. Você pode ver o status e as propriedades de aplicativos no nível da organização, carregar novos aplicativos personalizados na loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização e gerenciar configurações de aplicativos em toda a organização.

Aqui, você também pode comprar licenças para serviços oferecidos por aplicativos de terceiros para usuários em sua organização. A coluna **Licenças** na tabela indica se um aplicativo oferece uma assinatura de SaaS para compra.

![Captura de tela da página gerenciar aplicativos de licenças de compra.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicativos no Centro de administração do Teams

> [!IMPORTANT]
> Ao habilitar a compra de aplicativos, isso também ativa a compra no aplicativo. Os usuários podem ver ofertas de compra no aplicativo que são controladas pelo ISV para seu aplicativo. Se você quiser impedir que os usuários adquiram um aplicativo, será necessário bloquear o aplicativo. Para obter mais informações sobre como bloquear um aplicativo, confira [Gerenciar políticas de aplicativo](app-policies.md) ou [saiba como bloquear um aplicativo no nível da organização](manage-apps.md#allow-and-block-apps).

1. No painel à esquerda do Centro de administração do Microsoft Teams, acesse **Aplicativos do Teams** > **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**. Você deve ser um administrador global ou administrador de serviços do Teams para acessar a página.

1. Pesquise o aplicativo desejado pelo nome. Para identificar aplicativos que têm uma assinatura de SaaS paga, examine a coluna **Licenças**. Cada aplicativo tem um dos seguintes valores:
    * **Comprar**: o aplicativo oferece uma assinatura de SaaS e está disponível para compra.  
    * **Comprado**: O aplicativo oferece uma assinatura de SaaS e você comprou licenças para ele.
    * **- -**: O aplicativo não oferece uma assinatura de SaaS.

1. Quando você encontrar o aplicativo, selecione **Comprar** para ir para a guia **Planos e preços** da página de detalhes do aplicativo. Examine os planos e as informações de preços da oferta de SaaS para o aplicativo. Se precisar de mais informações, selecione **Saiba mais** para acessar a página do aplicativo no [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > Os planos privados também podem ser listados para compra, que incluem preços especiais que sua organização negociou anteriormente com um ISV. Esses planos terão o rótulo **Plano privado** abaixo do nome do plano.

1. Para assinar um aplicativo, escolha o plano desejado e selecione **Comprar**. O fluxo de check-out é aberto diretamente no Centro de administração do Teams.

1. Selecione o número de licenças de usuário que você deseja comprar.

1. Verifique se a conta de cobrança e o endereço vendido estão corretos. Se você ainda não tiver um, selecione **Adicionar**. Para obter mais informações sobre contas de cobrança, confira [Noções básicas sobre contas de cobrança](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Somente um administrador global pode adicionar uma nova conta de cobrança.

1. Verifique se o perfil de cobrança correto está selecionado. Se você ainda não tiver um, selecione **Adicionar novo**. Você tem a opção de pagar com cartão de crédito, cartão de débito ou com [cobrança de fatura](#invoice-billing). O perfil de cobrança também permite adicionar um número de pedido de compra para identificar seu pedido mais tarde. Para obter mais informações sobre perfis de cobrança, confira [Noções básicas sobre perfis de cobrança](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. Selecione **Fazer pedido**.

1. Selecione **Configurar** para ativar sua assinatura no site do publicador. Se você não configurar sua assinatura após a compra, poderá fazer isso mais tarde selecionando **Gerenciar licenças**.

Depois de comprar a oferta de SaaS associada ao aplicativo do Teams, você poderá exibir os seguintes detalhes de compra na guia **Planos e preços** da página de detalhes do aplicativo.

* **Data de ativação da licença**: data em que sua licença foi ativada. Se sua conta ainda não estiver configurada, isso será exibido como **Ativação pendente da assinatura**.
* **Licenças**: número de licenças compradas.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de tela da guia Planos e preços na página de detalhes do aplicativo no Centro de administração do Teams.":::

Para exibir e gerenciar as licenças adquiridas, selecione **Gerenciar licenças** para acessar o Centro de administração do Microsoft 365.

Os administradores globais podem adicionar mais licenças, remover licenças e cancelar assinaturas para compras feitas por qualquer pessoa na organização. Os administradores de serviços do Teams podem executar as mesmas ações para compras feitas por si mesmos. No entanto, se um administrador de serviços do Teams também tiver a função de administrador de cobrança, ele poderá gerenciar compras feitas por qualquer pessoa na organização.

> [!NOTE]
> Se um administrador global quiser gerenciar uma assinatura adquirida por outro administrador global, ele precisará estar na mesma conta de cobrança. Você pode dar a outro administrador global acesso a uma assinatura adquirida selecionando o aplicativo no [Centro de administração do Microsoft 365](https://admin.microsoft.com). A partir daí, acesse **Exibir perfil de cobrança** > **Selecionar conta de cobrança** > **Atribuir funções** > **Adicionar outros administradores globais**.

### <a name="invoice-billing"></a>Cobrança de fatura

* A cobrança de fatura está disponível como uma opção de pagamento para algumas transações.
* Uma revisão de crédito é necessária na primeira vez que você usa a cobrança de fatura, o que pode levar de 24 a 48 horas para aprovação. A cobrança de fatura não estará disponível até que a verificação de crédito seja concluída. Você pode fazer seu pedido com um cartão de crédito ou tentar novamente mais tarde depois que sua revisão de crédito for aprovada.
* A cobrança de fatura só está disponível para administradores globais ou um administrador com permissões de administrador de serviço e de cobrança do Teams.
* A cobrança de fatura não está disponível ao comprar um plano com uma avaliação gratuita de 30 dias.

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Listar e vender uma oferta de SaaS para um aplicativo do Teams

Os desenvolvedores podem criar ofertas de SaaS associadas aos aplicativos do Teams. Essas ofertas são publicadas por meio do [Partner Center](https://partner.microsoft.com) e estão disponíveis para as organizações comprarem por meio do [AppSource](https://appsource.microsoft.com/) e do Centro de administração do Microsoft Teams.

Para obter mais informações para desenvolvedores de aplicativos de terceiros, confira [Criar uma oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer).

## <a name="related-articles"></a>Artigos relacionados

* [Gerenciar seus aplicativos no Centro de Administração do Microsoft Teams](manage-apps.md)
* [Criar uma oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Funções internas do Azure Active Directory](/azure/active-directory/roles/permissions-reference)
* [Funções de administrador do Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)
