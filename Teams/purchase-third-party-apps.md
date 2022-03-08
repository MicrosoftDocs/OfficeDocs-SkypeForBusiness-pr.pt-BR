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
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: Saiba como comprar aplicativos de terceiros para Teams no Microsoft Teams de administração.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 0ce9458bbec59eb80d399a78e5d3bce1611ca381
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070200"
---
# <a name="purchase-third-party-apps-for-teams"></a>Comprar aplicativos de terceiros para Teams

Teams aplicativos são gratuitos para instalar e alguns podem exigir assinaturas de serviço de compra para experimentar a funcionalidade e o escopo completos do aplicativo. Essas assinaturas de serviço são chamadas de ofertas de Software como Serviço (SaaS), que estão disponíveis para compra por meio do [AppSource](https://appsource.microsoft.com/) e agora por meio do centro de administração do Microsoft Teams.

A [página Gerenciar aplicativos](manage-apps.md) no centro de administração Microsoft Teams é onde você visualiza e gerencia todos os Teams aplicativos para sua organização. Por exemplo, você pode ver o status e as propriedades de aplicativos no nível da organização, carregar novos aplicativos personalizados na loja de aplicativos da sua organização, bloquear ou permitir aplicativos no nível da organização e gerenciar configurações de aplicativos em toda a organização.

Aqui, você também pode comprar licenças para serviços oferecidos por aplicativos de terceiros para usuários em sua organização. A **coluna Licenças** na tabela indica se um aplicativo oferece uma assinatura SaaS para compra.

![Captura de tela das licenças de compra gerenciam a página aplicativos.](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Comprar aplicativos no Teams de administração

> [!IMPORTANT]
> Se você quiser impedir que os usuários adqueiem um aplicativo por meio da Teams de aplicativos, você deve bloquear o aplicativo. Para obter mais informações sobre como bloquear um aplicativo, consulte [Manage app policies](app-policies.md) or [learn how to block an app at the org-level](manage-apps.md#allow-and-block-apps).

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**. Você deve ser um administrador global ou Teams de serviço para acessar a página.
2. Pesquise o aplicativo que você deseja. Para identificar aplicativos que tenham uma assinatura saaS paga, procure na coluna **Licenças** . Cada aplicativo terá um dos seguintes valores:
    - **Compra**: o aplicativo oferece uma assinatura SaaS e está disponível para compra.  
    - **Comprado**: o aplicativo oferece uma assinatura SaaS e você comprou licenças para ele.
    - **- -**: O aplicativo não oferece uma assinatura SaaS.
3. Quando você encontrar o aplicativo, clique em **Comprar** para acessar a guia **Planos** e preços da página de detalhes do aplicativo. Revise os planos e informações de preços da oferta SaaS para o aplicativo. Se você precisar de mais informações, selecione **Saiba mais** para ir para a página do aplicativo no [AppSource](https://appsource.microsoft.com/).

> [!NOTE]
> Planos privados também podem ser listados para compra, que incluem preços especiais que sua organização já negociou com um ISV. Esses planos terão o rótulo **Plano particular** sob o nome do plano.

4. Para assinar um aplicativo, escolha o plano que você deseja e selecione **Comprar**. O fluxo de check-out será aberto diretamente no Teams de administração.
5. Selecione o número de licenças de usuário que você deseja comprar.
6. Verifique se a conta de cobrança e o endereço vendido estão corretos. Se você ainda não tiver um, adicione um novo selecionando **Adicionar**. Para obter mais informações sobre contas de cobrança, consulte [Understand billing accounts](/microsoft-365/commerce/manage-billing-accounts).

> [!NOTE]
> Você precisa ser um administrador global para adicionar uma nova conta de cobrança.

7. Verifique se o perfil de cobrança correto está selecionado. Se você ainda não tiver um, adicione um novo selecionando **Adicionar novo**. Você tem a opção de pagar com um cartão de crédito, cartão de débito ou com cobrança [de fatura](#invoice-billing). O perfil de cobrança também permite adicionar um número de pedido de compra para identificar seu pedido posteriormente. Para obter mais informações sobre perfis de cobrança, consulte [Understand billing profiles](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).
8. Selecione **Colocar ordem**.
9. Selecione **Configurar para** ativar sua assinatura no site do editor. Se você não configurar sua assinatura após a compra, poderá fazer isso mais tarde selecionando **Gerenciar licenças**.

Depois de comprar a oferta SaaS associada ao aplicativo Teams, você poderá exibir os seguintes detalhes de compra na guia Planos e preços da página de  detalhes do aplicativo.

- **Data de ativação da** licença: Data em que sua licença foi ativada. Se sua conta ainda não estiver configurada, isso será ativação **pendente de assinatura**.
- **Licenças**: número de licenças que você comprou.

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Captura de tela de Planos e guia de preços da página de detalhes do aplicativo.":::

Selecione **Gerenciar licenças** para ir para o Centro de administração do Microsoft 365 para exibir e gerenciar as licenças adquiridas.

Os administradores globais podem adicionar mais licenças, remover licenças e cancelar assinaturas para compras feitas por qualquer pessoa na organização. Teams administradores de serviço podem executar as mesmas ações para compras feitas por si mesmos. No entanto, se um Teams de serviço também tiver a função de administrador de Cobrança, ele poderá gerenciar compras feitas por qualquer pessoa na organização.

> [!NOTE]
> Se um administrador global quiser gerenciar uma assinatura comprada por outro administrador global, ele precisará estar na mesma conta de cobrança. Você pode dar a outro administrador global acesso a uma assinatura que você comprou selecionando o aplicativo no Centro de administração do Microsoft 365. A partir daí, vá para **Exibir perfil de** **cobrançaSelecione** >  conta  >  de **cobrançaAssign rolesAdd** >  **outros administradores globais**.

### <a name="invoice-billing"></a>Cobrança de faturas

- A cobrança de faturas está disponível como uma opção de pagamento para algumas transações.
- Uma revisão de crédito é necessária na primeira vez que você usa cobrança de fatura, que pode levar de 24 a 48 horas para aprovação. A cobrança de faturas não estará disponível até que a verificação de crédito seja concluída. Você pode fazer seu pedido com um cartão de crédito ou tentar novamente mais tarde depois que sua revisão de crédito for aprovada.
- A cobrança de faturas só está disponível para administradores globais ou administradores com Teams de serviço e permissões de administrador de cobrança.
- A cobrança de faturas não está disponível ao comprar um plano com uma avaliação gratuita de 30 dias.

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Tem uma oferta saaS para um aplicativo Teams que você deseja listar e vender no centro de administração Microsoft Teams e AppSource?

Os desenvolvedores podem criar ofertas saaS associadas aos seus Teams aplicativos. Essas ofertas são publicadas [por meio do Partner Center](https://partner.microsoft.com) e estão disponíveis para as organizações comprarem por meio do [AppSource](https://appsource.microsoft.com/) e do Microsoft Teams de administração.

Desenvolvedores de aplicativos de terceiros podem ir [até Criar uma oferta saaS](/azure/marketplace/partner-center-portal/create-new-saas-offer) para obter mais informações.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar seus aplicativos no Microsoft Teams de administração](manage-apps.md)
- [Criar uma oferta SaaS](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Funções integrados do Azure AD](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365 de administrador](/microsoft-365/admin/add-users/about-admin-roles)