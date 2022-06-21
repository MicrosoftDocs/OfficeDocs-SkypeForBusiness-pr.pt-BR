---
title: Comprar aplicativos de terceiros para Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: Saiba como comprar aplicativos de terceiros da Teams usando um cartão de crédito, um cartão de débito ou por meio da cobrança da fatura.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 33d5faec0694c666b2f392713d235cb52ef8b0e8
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190321"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicativos de terceiros para Teams

Teams aplicativos são gratuitos para instalação e alguns podem exigir assinaturas de serviço de compra para experimentar a funcionalidade e o escopo completos do aplicativo. Essas assinaturas de serviço são chamadas de ofertas de SaaS (software como serviço), que estão disponíveis para compra por meio do [AppSource](https://appsource.microsoft.com/) e agora por meio do Microsoft Teams de administração.

A [página Gerenciar aplicativos](manage-apps.md) no Microsoft Teams de administração é onde você exibe e gerencia todos os Teams aplicativos para sua organização. Por exemplo, você pode ver o status e as propriedades de aplicativos no nível da organização, carregar novos aplicativos personalizados na loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização e gerenciar configurações de aplicativos em toda a organização.

Aqui, você também pode comprar licenças para serviços oferecidos por aplicativos de terceiros para usuários em sua organização. A **coluna Licenças** na tabela indica se um aplicativo oferece uma assinatura de SaaS para compra.

![Captura de tela da página gerenciar aplicativos de licenças de compra.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicativos no Teams de administração

> [!IMPORTANT]
> Quando você habilita a compra de aplicativos, ele também ativa a compra no aplicativo. Os usuários podem ver ofertas de compra no aplicativo que são controladas pelo ISV para seu aplicativo. Se você quiser impedir que os usuários adquiram um aplicativo, será necessário bloquear o aplicativo. Para obter mais informações sobre como bloquear um aplicativo, consulte [Gerenciar](app-policies.md) políticas de aplicativo ou saiba como bloquear um aplicativo [no nível da organização](manage-apps.md#allow-and-block-apps).

1. No painel esquerdo do centro de administração do Microsoft Teams, acesse Teams **Aplicativos** > **Gerenciados**. Você deve ser um administrador global ou Teams de serviço para acessar a página.
1. Pesquise o aplicativo desejado. Para identificar aplicativos que têm uma assinatura de SaaS paga, examine a coluna **Licenças** . Cada aplicativo terá um dos seguintes valores:
    - **Compra**: o aplicativo oferece uma assinatura de SaaS e está disponível para compra.  
    - **Comprado**: o aplicativo oferece uma assinatura de SaaS e você comprou licenças para ele.
    - **- -**: o aplicativo não oferece uma assinatura de SaaS.
1. Quando você encontrar o aplicativo, selecione **Comprar** para ir para a guia Planos e **preços** da página de detalhes do aplicativo. Examine os planos e as informações de preços da oferta de SaaS para o aplicativo. Se precisar de mais informações, selecione **Saiba mais** para acessar a página do aplicativo no [AppSource](https://appsource.microsoft.com/).

   > [!NOTE]
   > Os planos privados também podem ser listados para compra, que incluem preços especiais que sua organização negociou anteriormente com um ISV. Esses planos terão o rótulo **Plano privado sob** o nome do plano.

1. Para assinar um aplicativo, escolha o plano desejado e selecione **Comprar**. O fluxo de check-out é aberto diretamente no Teams de administração.

1. Selecione o número de licenças de usuário que você deseja comprar.
1. Verifique se a conta de cobrança e o endereço vendido estão corretos. Se você ainda não tiver um, adicione um novo selecionando **Adicionar**. Para obter mais informações sobre contas de cobrança, consulte [Noções básicas sobre contas de cobrança](/microsoft-365/commerce/manage-billing-accounts).

   > [!NOTE]
   > Você precisa ser um administrador global para adicionar uma nova conta de cobrança.

1. Verifique se o perfil de cobrança correto está selecionado. Se você ainda não tiver um, adicione um novo selecionando **Adicionar novo**. Você tem a opção de pagar com um cartão de crédito, cartão de débito ou com cobrança [de fatura](#invoice-billing). O perfil de cobrança também permite adicionar um número de pedido de compra para identificar seu pedido mais tarde. Para obter mais informações sobre perfis de cobrança, consulte [Noções básicas sobre perfis de cobrança](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).
1. Selecione **Fazer pedido**.
1. Selecione **Configurar para** ativar sua assinatura no site do editor. Se você não configurar sua assinatura após a compra, poderá fazer isso mais tarde selecionando **Gerenciar licenças**.

Depois de comprar a oferta de SaaS associada ao aplicativo Teams, você poderá exibir os seguintes detalhes de compra na guia Planos e preços da página  de detalhes do aplicativo.

- **Data de ativação da** licença: data em que sua licença foi ativada. Se sua conta ainda não estiver configurada, isso será exibido como ativação **pendente da assinatura**.
- **Licenças**: número de licenças adquiridas.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de tela da guia Planos e preços da página de detalhes do aplicativo.":::

Selecione **Gerenciar licenças** para acessar o Centro de administração do Microsoft 365 para exibir e gerenciar as licenças adquiridas.

Os administradores globais podem adicionar mais licenças, remover licenças e cancelar assinaturas para compras feitas por qualquer pessoa na organização. Teams administradores de serviço podem executar as mesmas ações para compras feitas por si mesmos. No entanto, se um Teams administrador de serviços também tiver a função de administrador de Cobrança, ele poderá gerenciar compras feitas por qualquer pessoa na organização.

> [!NOTE]
> Se um administrador global quiser gerenciar uma assinatura adquirida por outro administrador global, ele precisará estar na mesma conta de cobrança. Você pode dar a outro administrador global acesso a uma assinatura adquirida selecionando o aplicativo no Centro de administração do Microsoft 365. A partir daí, vá para **Exibir perfil de cobrança** > **Selecionar conta de cobrança Atribuir** > **funções** > **Adicionar outros administradores globais**.

### <a name="invoice-billing"></a>Cobrança da fatura

- A cobrança da fatura está disponível como uma opção de pagamento para algumas transações.
- Uma revisão de crédito é necessária na primeira vez que você usa a cobrança da fatura, o que pode levar de 24 a 48 horas para aprovação. A cobrança da fatura não estará disponível até que a verificação de crédito seja concluída. Você pode fazer seu pedido com um cartão de crédito ou tentar novamente mais tarde depois que sua revisão de crédito for aprovada.
- A cobrança da fatura só está disponível para administradores globais ou um administrador com permissões de administrador Teams de serviço e de cobrança.
- A cobrança da fatura não está disponível ao comprar um plano com uma avaliação gratuita de 30 dias.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Tem uma oferta de SaaS para um Teams que você deseja listar e vender no centro de administração do Microsoft Teams e no AppSource?

Os desenvolvedores podem criar ofertas de SaaS associadas a seus Teams aplicativos. Essas ofertas são publicadas por meio [do Partner Center](https://partner.microsoft.com) e estão disponíveis para que as organizações comprem por meio do [AppSource](https://appsource.microsoft.com/) e do Microsoft Teams de administração.

Os desenvolvedores de aplicativos de terceiros podem acessar [Criar uma oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) para obter mais informações.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar seus aplicativos no Microsoft Teams de administração](manage-apps.md)
- [Criar uma oferta de SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD funções internas](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 de administrador](/microsoft-365/admin/add-users/about-admin-roles)
