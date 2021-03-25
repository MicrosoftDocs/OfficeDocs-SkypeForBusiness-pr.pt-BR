---
title: Gerenciar políticas de retenção para o Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Use políticas de retenção para o Microsoft Teams para manter mensagens necessárias para estar em conformidade com políticas internas, regulamentos do setor ou necessidades legais e excluir mensagens que são consideradas uma responsabilidade ou que não têm valor comercial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d7d998afb47480fa59ce936a93e20af9ac4b2a12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117599"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Gerenciar políticas de retenção para o Microsoft Teams

> [!NOTE]
> Se você estiver vendo uma mensagem no Teams de que seus chats ou mensagens foram excluídos por uma política de retenção, consulte Mensagens do [Teams sobre políticas de retenção](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> As informações nesta página são para administradores de IT que gerenciam essas políticas de retenção.

As políticas de retenção e os rótulos de retenção do Microsoft 365 ajudam você a gerenciar com mais eficiência as informações em sua organização. Você pode definir configurações de retenção para manter os dados necessários para estar em conformidade com as políticas internas da sua organização, os regulamentos do setor ou as necessidades legais. Você também pode definir configurações de retenção para excluir dados considerados uma responsabilidade, que você não precisa mais manter, ou que não tem valor legal ou comercial.

O Teams dá suporte a políticas de retenção para mensagens de chat e canal para que, como administrador, você possa decidir proativamente se deve reter esses dados, excluí-los ou retê-los por um período específico de tempo e excluí-los. Você pode aplicar uma política de retenção do Teams para toda a organização ou para usuários e equipes específicas. Não há suporte para rótulos de retenção para o Teams.

Para saber mais sobre retenção e como você pode aplicar configurações de retenção usando políticas de retenção ou rótulos de retenção para outras cargas de trabalho no Microsoft 365, consulte [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).

O requisito mínimo de licenciamento para políticas de retenção para o Teams é o Microsoft 365 E3. Para saber mais sobre licenciamento, consulte a descrição [do serviço do Microsoft Teams.](/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retentiondeletion-policies-work"></a>Como funcionam as políticas de retenção/exclusão do Teams

As mensagens de chat do Teams são armazenadas em dois locais. A cópia primária é armazenada no Azure, uma cópia secundária, usada para políticas de compilação, é armazenada em uma pasta oculta na caixa de correio do Exchange online de cada usuário incluído no chat, e as mensagens de canal do Teams são armazenadas em uma pasta oculta semelhante na caixa de correio do grupo para a equipe. Quando uma política de exclusão de mensagem de chat é aplicada a um usuário ou Equipe, a cópia secundária é excluída primeiro, seguido pela cópia primária. A descoberta digital ou a pesquisa do Teams é baseada em mensagens armazenadas em cópia secundária e, portanto, as mensagens se tornam não descobertas quando a cópia secundária é excluída. 

Quando uma poilcy de retenção de mensagem de chat é aplicada a um usuário ou Equipe e se as mensagens são excluídas (devido a outra política de exclusão ou pelo próprio usuário), a cópia primária é excluída, portanto, o cliente do Teams verá a mensagem desaparecer, mas a cópia secundária é movida automaticamente para uma pasta oculta chamada **SubstrateHolds** , que é como uma subpasta na pasta Itens **Recuperáveis** do Exchange. Até que essas mensagens sejam excluídas permanentemente da pasta SubstrateHolds, elas permanecerão pesquisáveis por ferramentas de Descoberta e.

Para obter informações detalhadas sobre o que está incluído e excluído para políticas de retenção do Teams e como essas políticas funcionam dependendo da configuração da política, consulte Saiba mais sobre retenção [para o Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).

> [!NOTE]
> Essa página explica por que às vezes você pode ver atrasos quando as políticas de retenção excluem mensagens. Por exemplo, as mensagens podem ficar visíveis até 7 dias após o período de expiração que você configurou na política de retenção.

Se você configurar várias políticas de retenção do Teams com configurações de retenção diferentes, os princípios de retenção resolverão quaisquer conflitos. Por exemplo:
- Se houver um conflito entre reter ou excluir o mesmo conteúdo, o conteúdo sempre será mantido.
- Se houver um conflito em quanto tempo manter o mesmo conteúdo, ele será mantido pelo período de retenção mais longo.

Esses dois princípios de retenção abordam a maioria dos conflitos que podem surgir quando você tem várias políticas de retenção para o Teams, mas para obter mais informações, consulte Os princípios de retenção ou o que tem [precedência?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando usar as políticas de retenção para o Teams.

Em muitos casos, as organizações consideram os dados de chat privados como um número mais passivo do que as mensagens de canal, que geralmente são conversas mais relacionadas ao projeto.

Você pode configurar uma política de retenção separada para chats privados (1:1 ou 1: muitos chats) e mensagens de canal. Você também pode configurar políticas exclusivas que se aplicam a usuários ou equipes específicas em sua organização. Nos chats do Teams, você pode selecionar a quais usuários a política será aplicada. Para mensagens de canal do Teams, você pode selecionar a quais equipes a política será aplicada.

Por exemplo, para mensagens de canal, você pode aplicar uma política de exclusão de um ano a equipes específicas em sua organização e aplicar uma política de exclusão de três anos a todas as outras equipes.

## <a name="create-and-manage-retention-policies-for-teams"></a>Criar e gerenciar políticas de retenção para o Teams

Para criar uma política de retenção para chats e mensagens de canal do Teams, use as instruções da [política de retenção para locais do Teams.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Essa página tem informações adicionais sobre como criar e gerenciar políticas de retenção para outras cargas de trabalho no Microsoft 365. Por exemplo, talvez você também queira criar uma política de retenção para grupos do Microsoft 365 para reter e excluir arquivos acessados no Teams e armazenados no OneDrive ou no SharePoint.  

## <a name="end-user-experience"></a>Experiência do usuário final

Para chats privados (chats 1:1) ou chats em grupo, os usuários verão que os chats mais antigos que a configuração da política de retenção são excluídos e uma mensagem gerada automaticamente informando "Excluímos mensagens mais antigas devido à política de retenção da sua organização" é mostrada em cima de mensagens ainda não elevadas. Por exemplo:

:::image type="content" source="media/retention-policies-image1.png" alt-text="Usuário informado no Teams de que a mensagem de chat é excluída por causa de uma política de retenção do Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="O usuário no Teams explicando mensagens são excluídos como resultado de uma política de retenção do Teams":::

Para mensagens do Canal, os usuários (membros do canal) verão as mensagens excluídas desaparecerem da exibição depois que as mensagens expirarem. Se a mensagem excluída fosse uma mensagem pai de uma conversa encadeada, então, no lugar da mensagem pai, uma mensagem informando "Essa mensagem foi excluída por causa de uma Política de Retenção" será exibida. Por exemplo:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de tela do canal antes da retenção":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de tela do canal após a retenção":::

> [!NOTE]
> As mensagens exibidas pelos usuários como resultado de mensagens excluídas não são configuráveis no momento.

Os links nessas mensagens exibidas vão para mensagens [do Teams sobre políticas de retenção.](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) Essa documentação para usuários finais ajuda a responder a perguntas básicas sobre por que suas mensagens foram excluídas. No entanto, como parte da implantação da política de retenção, certifique-se de se comunicar com os usuários e com o seu help desk o impacto das configurações configuradas.

## <a name="related-topics"></a>Tópicos relacionados

- [Começar com políticas de retenção e rótulos de retenção](/microsoft-365/compliance/get-started-with-retention)
- [Saiba mais sobre retenção para o Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Criar e configurar políticas de retenção](/microsoft-365/compliance/create-retention-policies)