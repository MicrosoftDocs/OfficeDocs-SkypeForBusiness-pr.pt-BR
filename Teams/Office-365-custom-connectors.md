---
title: Gerenciar o Microsoft 365 e conectores personalizados
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como os Conectores mantêm sua equipe atualizada fornecendo frequentemente conteúdo e atualizações diretamente em um canal do Teams para os serviços que você usa.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb056cbee4dc1d56a6cd967d3f46c3f0680e9b73
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880225"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Gerenciar o Microsoft 365 e conectores personalizados

Para manter sua equipe atualizada, os conectores fornecem atualizações de conteúdo e serviço usadas com frequência diretamente em um canal do Teams. Com conectores, os usuários do Teams podem receber atualizações de serviços populares, como Trello, Wunderlist, GitHub e Azure DevOps Services. As atualizações são postadas diretamente no fluxo de chat em sua equipe.

Os conectores do Microsoft 365 são usados com grupos do Microsoft Teams e do Microsoft 365, facilitando a sincronização de todos os membros e o recebimento rápido de informações relevantes. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas. No entanto, se você desabilitar os conectores configurados para um grupo do Microsoft 365, ele também desabilitará a capacidade do grupo do Microsoft 365 de criar conectores.

Qualquer membro de uma equipe poderá conectar sua equipe a serviços de nuvem populares com os conectores se as permissões da equipe permitirem, e todos os membros da equipe serão notificados sobre atividades desse serviço. Os conectores continuam a funcionar depois que o membro que inicialmente configurou o conector sai. Qualquer membro da equipe com as permissões para adicionar ou remover pode modificar a configuração de conectores por outros membros.

## <a name="enable-or-disable-connectors-in-teams"></a>Habilitar ou desabilitar conectores no Teams

O Exchange Online powershell V2 usa autenticação moderna e funciona com a autenticação multifator, chamada MFA para se conectar a todos os ambientes do PowerShell relacionados ao Exchange no Microsoft 365. Os administradores podem usar Exchange Online PowerShell para desabilitar conectores para um locatário inteiro ou uma caixa de correio de grupo específica, afetando todos os usuários nesse locatário ou caixa de correio. Não é possível desabilitar para poucos usuários específicos. Além disso, os conectores são desabilitados por padrão para o Government Community Cloud, chamado de locatários GCC.

A configuração de locatário substitui a configuração de grupo. Por exemplo, se um administrador habilitar conectores para o grupo e desabilitá-los no locatário, os conectores do grupo serão desabilitados. Para habilitar um conector no Teams, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) usando autenticação moderna com ou sem MFA.

Para habilitar ou desabilitar um conector, execute os seguintes comandos Exchange Online PowerShell:

* Para desabilitar conectores para o locatário: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Para desabilitar mensagens acionáveis para o locatário: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Para habilitar conectores para o Teams, execute os seguintes comandos:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Para obter mais informações sobre a troca de módulos do PowerShell, consulte [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Para habilitar ou desabilitar conectores do Outlook, [conecte aplicativos aos seus grupos no Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>Publicar conectores para sua organização

Se quiser que um conector personalizado esteja disponível apenas para os usuários em sua organização, você pode carregar um aplicativo conector personalizado no catálogo de aplicativos da sua organização. Depois de carregar o pacote do aplicativo, os usuários finais podem instalar o conector do catálogo de aplicativos da organização e podem configurar e usar o conector em uma equipe.

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> Os conectores personalizados não estão disponíveis na GCC (Nuvem da Comunidade Governamental), no GCCH (Government Community Cloud-High) e no DoD (Departamento de Defesa).

Para usar conectores em uma equipe ou canal, abra o menu Mais Opções no canto superior direito de um canal. No menu, selecione **Conectores** e localize ou pesquise o conector necessário. Configure o conector selecionado, se necessário.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Adicione conectores ao canal no Teams nas opções Mais no canto superior direito do canal.":::

## <a name="update-url-of-a-connector"></a>Atualizar a URL de um conector

Os conectores do Teams estão fazendo a transição para uma nova URL para aprimorar a segurança. Durante a transição, você receberá uma notificação para atualizar o conector configurado. Atualize o conector o mais cedo possível para evitar qualquer interrupção nos serviços do conector. Para atualizar o conector:

1. Na página de configuração de conectores, verifique se há **uma mensagem de** Atenção Necessária ao lado do conector configurado.

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="Captura de tela da mensagem Atenção Necessária.":::

1. Para recriar a conexão para conectores de webhook de entrada, selecione Atualizar **URL** e use a URL de webhook gerada.

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="Captura de tela do botão Atualizar URL.":::

1. Para outros tipos de conector, remova o conector e recrie a configuração do conector. Uma **URL é exibida com uma mensagem** atualizada.

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="A captura de tela da URL está atualizada.":::

## <a name="related-articles"></a>Artigos relacionados

* [Visão geral de conectores e webhooks personalizados](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Criar Office 365 conectores](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
