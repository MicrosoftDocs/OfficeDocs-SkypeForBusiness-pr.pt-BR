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
description: Use políticas de retenção para o Microsoft Teams para manter mensagens de que sua organização precisa estar em conformidade com políticas internas, regulamentos do setor ou requisitos legais e excluir mensagens que são consideradas uma responsabilidade ou que não têm valor comercial legal.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617753"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Gerenciar políticas de retenção para o Microsoft Teams

> [!NOTE]
> Se você estiver vendo uma mensagem no Teams de que seus chats ou mensagens foram excluídos por uma política de retenção, consulte Mensagens do [Teams sobre políticas de retenção](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> As informações nesta página são para administradores de IT que gerenciam essas políticas de retenção.

As políticas de retenção e os rótulos de retenção do Microsoft 365 ajudam você a gerenciar com mais eficiência as informações em sua organização. Você pode definir configurações de retenção para manter os dados necessários para estar em conformidade com as políticas internas da sua organização, os regulamentos do setor ou os requisitos legais. Você também pode definir configurações de retenção para excluir dados considerados uma responsabilidade, que você não precisa mais manter, ou que não tem valor legal ou comercial.

O Teams dá suporte a políticas de retenção para mensagens de chat e canal para que, como administrador, você possa decidir proativamente se deve reter esses dados, excluí-los ou retê-los por um período específico de tempo e excluí-los. O início do período de retenção dessas ações é sempre baseado em quando uma mensagem é criada. Você pode aplicar uma política de retenção do Teams para toda a organização ou para usuários e equipes específicas. Não há suporte para rótulos de retenção para o Teams.

Para saber mais sobre soluções de retenção no Microsoft 365, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](/microsoft-365/compliance/retention)

Os usuários que estão sujeitos a uma política de retenção para o Teams devem ter uma licença apropriada, como o Office 365 E3 ou o Office 365 A3. Para obter outras opções de licenciamento para essas políticas de retenção, consulte a seção [Governança](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) de Informações do [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). Para saber mais sobre licenciamento para o Teams, consulte [a descrição do serviço do Microsoft Teams.](/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Como as políticas de retenção do Teams suportam ações de retenção e exclusão

Se você configurar uma política de retenção do Teams para reter chats ou mensagens de canal, os usuários ainda poderão editar e excluir suas mensagens em seu aplicativo do Teams. Embora os usuários não vejam mais suas mensagens pré-editadas ou excluídas no Teams, os dados dessas mensagens são armazenados em um local seguro projetado para pesquisas de Descobertas EDiscovery por administradores de conformidade. A exclusão permanente desses dados não acontece antes do final do período de retenção configurado ou se outra política de retenção está configurada para reter esses dados ou está sujeita a uma retenção de [Descoberta](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)e.

Quando uma política de retenção é configurada para excluir chats e mensagens de canal, essas mensagens se tornam qualificadas para exclusão automática. Se as mensagens ainda são exibidas no aplicativo do Teams, elas desaparecerão de lá e os usuários serão informados de que uma política de retenção [excluiu essas mensagens.](#end-user-experience) Se as mensagens anteriormente estavam sujeitas a uma ação de retenção e foram editadas ou excluídas pelos usuários, essas mensagens agora serão excluídas do local protegido e não serão mais retornadas nas pesquisas de DescobertaSede.

Para obter informações detalhadas sobre como essas políticas funcionam dependendo da configuração da política e das ações do usuário e quais dados de mensagem são incluídos e excluídos para políticas de retenção do Teams, consulte Saiba mais sobre retenção para [o Microsoft Teams](/microsoft-365/compliance/retention-policies-teams). Essa página também explica por que, às vezes, você pode ter atrasos quando as políticas de retenção excluem mensagens. Por exemplo, as mensagens podem ficar visíveis para os usuários no aplicativo do Teams até 7 dias após o período de expiração que você configurou na política de retenção.

Se você configurar várias políticas de retenção do Teams com configurações de retenção diferentes, os princípios de retenção resolverão quaisquer conflitos. Por exemplo:

- Se houver um conflito entre reter ou excluir o mesmo conteúdo, o conteúdo sempre será retido no local protegido para que ele permaneça pesquisável com a Descoberta eDiscovery para administradores de conformidade.
    
    Esse princípio também se aplica a mensagens que estão em ressarções de Descoberta e Por motivos legais ou investigativos.

- Se houver um conflito em quanto tempo manter o mesmo conteúdo, ele será mantido no local protegido pelo período de retenção mais longo.

Esses dois princípios de retenção abordam a maioria dos conflitos que podem surgir quando você tem várias políticas de retenção para o Teams, mas para obter mais informações, consulte Os princípios de retenção ou o que tem [precedência?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando usar as políticas de retenção para o Teams.

Em muitos casos, as organizações consideram os dados de chat privados como um número mais passivo do que as mensagens de canal, que geralmente são conversas mais relacionadas ao projeto.

Você pode configurar uma política de retenção separada para chats privados (1:1 ou 1: muitos chats) e mensagens de canal. Você também pode configurar políticas exclusivas que se aplicam a usuários ou equipes específicas em sua organização. Nos chats do Teams, você pode selecionar a quais usuários a política será aplicada. Para mensagens de canal do Teams, você pode selecionar a quais equipes a política será aplicada.

Por exemplo, para mensagens de canal, você pode aplicar uma política de retenção a equipes específicas em sua organização e essa política é configurada com uma ação de exclusão após 1 ano. Em seguida, aplique outra política de retenção a todas as outras equipes e essa política é configurada com uma ação de exclusão após três anos.

## <a name="create-and-manage-retention-policies-for-teams"></a>Criar e gerenciar políticas de retenção para o Teams

Para criar ou editar uma política de retenção para chats e mensagens de canal do Teams, use as instruções da política de [retenção para locais do Teams.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

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
