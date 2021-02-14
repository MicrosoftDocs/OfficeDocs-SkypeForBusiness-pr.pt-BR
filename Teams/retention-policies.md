---
title: Políticas de retenção no Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Use políticas de retenção do Microsoft Teams para manter mensagens necessárias para cumprir políticas internas, regulamentos do setor ou necessidades legais e excluir mensagens que são consideradas uma responsabilidade ou que não têm valor comercial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786823"
---
# <a name="retention-policies-in-microsoft-teams"></a>Políticas de retenção no Microsoft Teams

As políticas de retenção e os rótulos de retenção do Microsoft 365 ajudam você a gerenciar com mais eficiência as informações em sua organização. Você pode definir configurações de retenção para manter os dados necessários para atender às políticas internas, aos regulamentos do setor ou às necessidades legais da sua organização. Você também pode definir configurações de retenção para excluir dados que são considerados uma responsabilidade, que você não precisa mais manter ou que não tem nenhum valor legal ou comercial.

O Teams dá suporte a políticas de retenção para mensagens de chat e canal para que, como administrador, você possa decidir proativamente se deve reter esses dados, excluí-los ou retê-los por um período específico e depois excluí-los. Você pode aplicar uma política de retenção do Teams para toda a organização ou para usuários e equipes específicas. Não há suporte para rótulos de retenção no Teams.

Para saber mais sobre retenção e como você pode aplicar configurações de retenção usando políticas de retenção ou rótulos de retenção para outras cargas de trabalho no Microsoft 365, consulte Saiba mais sobre políticas de retenção e rótulos de [retenção.](https://docs.microsoft.com/microsoft-365/compliance/retention)

O requisito mínimo de licenciamento para políticas de retenção para o Teams é o Microsoft 365 E3. Para saber mais sobre licenciamento, consulte a descrição [do serviço microsoft teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-work"></a>Como funcionam as políticas de retenção do Teams

As mensagens de chat do Teams são armazenadas em uma pasta oculta na caixa de correio de cada usuário incluído no chat, e as mensagens do canal do Teams são armazenadas em uma pasta oculta semelhante na caixa de correio do grupo da equipe. Para reter mensagens sujeitas a uma política de retenção, uma cópia do conteúdo é mantida automaticamente em uma pasta oculta **chamadaHolds como** uma subpasta na pasta Itens **Recuperáveis** do Exchange. Até que essas mensagens sejam permanentemente excluídas da pastaHolds, elas permanecerão pesquisáveis por ferramentas de Descobertas Digitais.

Para obter informações detalhadas sobre o que está incluído e excluído para políticas de retenção do Teams e como essas políticas funcionam dependendo da configuração da política, consulte Saiba mais sobre retenção para o [Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> Essa página explica por que, às vezes, você pode ver atrasos quando as políticas de retenção excluem mensagens. Por exemplo, as mensagens podem ficar visíveis até 7 dias após o período de expiração que você configurou na política de retenção.

Se você configurar várias políticas de retenção do Teams com configurações de retenção diferentes, os princípios de retenção resolverão quaisquer conflitos. Por exemplo:
- Se houver um conflito entre reter ou excluir o mesmo conteúdo, o conteúdo sempre será retido.
- Se houver um conflito em quanto tempo manter o mesmo conteúdo, ele será mantido pelo período de retenção mais longo.

Esses dois princípios de retenção abordam a maioria dos conflitos que podem surgir quando você tem várias políticas de retenção para o Teams, mas para obter mais informações, consulte Os princípios de retenção ou o que [tem precedência?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando usar as políticas de retenção para o Teams.

Em muitos casos, as organizações consideram os dados de chat privados como um número mais passivo do que as mensagens de canal, que geralmente são conversas mais relacionadas ao projeto.

Você pode configurar uma política de retenção separada para chats privados (1:1 ou 1: muitos chats) e mensagens de canal. Você também pode configurar políticas exclusivas que se aplicam a usuários ou equipes específicas em sua organização. Nos chats do Teams, você pode selecionar a quais usuários a política será aplicada. Para mensagens de canal do Teams, você pode selecionar a quais equipes a política será aplicada.

Por exemplo, para mensagens de canal, você pode aplicar uma política de exclusão de um ano a equipes específicas em sua organização e aplicar uma política de exclusão de três anos a todas as outras equipes.

## <a name="create-and-manage-retention-policies-for-teams"></a>Criar e gerenciar políticas de retenção para o Teams

Para criar uma política de retenção para chats e mensagens de canal do Teams, use as instruções da [política de retenção para locais do Teams.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Essa página tem informações adicionais sobre como criar e gerenciar políticas de retenção para outras cargas de trabalho no Microsoft 365. Por exemplo, talvez você também queira criar uma política de retenção para grupos do Microsoft 365 para reter e excluir arquivos acessados no Teams e armazenados no OneDrive ou no SharePoint.  

## <a name="end-user-experience"></a>Experiência do usuário final

Para chats privados (chats 1:1) ou chats em grupo, os usuários finais verão que os chats mais antigos que a configuração da política de retenção são excluídos e uma mensagem de controle informando que "Excluímos mensagens mais antigas devido à política de retenção da sua organização" é mostrada em cima de mensagens ainda não excluídas.

:::image type="content" source="media/retention-policies-image1.png" alt-text="Usuário informado no Teams de que a mensagem de chat é excluída devido a uma política de retenção do Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="O usuário no Teams explicando que mensagens são excluídas como resultado de uma política de retenção do Teams":::

Para mensagens do Canal, os usuários finais (membros do canal) verão as mensagens excluídas desaparecerem da exibição após a expiração das mensagens. Se a mensagem excluída era uma mensagem pai de uma conversa encadeada, então, no lugar da mensagem pai, será exibida uma mensagem informando "Esta mensagem foi excluída devido a uma Política de Retenção".

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de tela do canal antes da retenção":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de tela do canal após a retenção":::

> [!NOTE]
> As mensagens exibidas que os usuários finais veem como resultado de mensagens excluídas não são configuráveis no momento.


## <a name="related-topics"></a>Tópicos relacionados

- [Começar a trabalhar com políticas de retenção e rótulos de retenção](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [Saiba mais sobre retenção para o Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [Criar e configurar políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)