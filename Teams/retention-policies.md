---
title: Gerenciar políticas de retenção para o Microsoft Teams.
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Use políticas de retenção do Microsoft Teams para manter as mensagens de que sua organização precisa para estar em conformidade com políticas internas, regulamentos do setor ou requisitos legais e excluir mensagens que são consideradas uma vulnerabilidade ou que não têm valor comercial legal.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 508f10c07a25bb2dc3cef7af84d7dacc62989f28
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023682"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Gerenciar políticas de retenção para o Microsoft Teams.

> [!NOTE]
> Se você estiver vendo uma mensagem no Teams informando que os seus chats ou mensagens foram excluídos por uma política de retenção, consulte [Mensagens do Teams sobre políticas de retenção](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> As informações nesta página são para administradores de TI que gerenciam essas políticas de retenção.

As políticas de retenção e os rótulos Microsoft 365 ajudam você a gerenciar com mais eficiência as informações em sua organização. Você pode definir as configurações de retenção para manter os dados necessários para estar em conformidade com as políticas internas, os regulamentos do setor ou os requisitos legais da sua organização. Você também pode definir configurações de retenção para excluir dados que são considerados uma vulnerabilidade, que você não precisa mais manter ou que não têm valor legal ou comercial.

O Teams dá suporte a políticas de retenção para chat e mensagens de canal para que, como administrador, você possa decidir proativamente se deseja reter esses dados, excluí-los ou retê-los por um período específico de tempo e, em seguida, excluí-los. O início do período de retenção para essas ações é sempre baseado em quando uma mensagem é criada. Você pode aplicar uma política de retenção do Teams para toda a organização ou para usuários e equipes específicas. Não há suporte para rótulos de retenção no Teams.

> [!NOTE]
> [Os canais compartilhados](shared-channels.md) são compatíveis com políticas de retenção.

Para saber mais sobre soluções de retenção no Microsoft 365, consulte [Saiba mais sobre políticas de retenção e rótulos de retenção](/microsoft-365/compliance/retention).

Os usuários que estão sujeitos a uma política de retenção do Teams devem ter uma licença apropriada, como o Office 365 E3 ou o Office 365 A3. Para obter outras opções de licenciamento para essas políticas de retenção, consulte a seção [Governança de Informações](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) de [Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). Para saber mais sobre o licenciamento do Teams, confira a [Descrição do serviço do Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Como as políticas de retenção do Teams dão suporte a ações de retenção e exclusão

Se você configurar uma política de retenção do Teams para reter chats ou mensagens de canal, os usuários ainda poderão editar e excluir suas mensagens no aplicativo Teams. Embora os usuários não vejam mais suas mensagens pré-editadas ou excluídas no Teams, os dados dessas mensagens são armazenados em um local seguro projetado para pesquisas de Descoberta Eletrônica por administradores de conformidade. A exclusão permanente desses dados não ocorre antes do final do período de retenção configurado, ou se outra política de retenção estiver configurada para reter esses dados ou sujeita a uma [retenção de Descoberta Eletrônica](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).

Quando uma política de retenção é configurada para excluir chats e mensagens de canal, essas mensagens se tornam elegíveis para exclusão automática. Se as mensagens ainda forem exibidas no aplicativo do Teams, elas desaparecerão de lá e [os usuários serão informados de que uma política de retenção excluiu essas mensagens](#end-user-experience). Se as mensagens anteriormente estavam sujeitas a uma ação de retenção e foram editadas ou excluídas por usuários, essas mensagens agora serão excluídas do local seguro e não serão mais retornadas em pesquisas de Descoberta Eletrônica.

Para obter informações detalhadas sobre como essas políticas funcionam dependendo da configuração da política e das ações do usuário e quais dados de mensagem são incluídos e excluídos das políticas de retenção do Teams, consulte [Saiba mais sobre a retenção do Microsoft Teams](/microsoft-365/compliance/retention-policies-teams). Essa página também explica por que às vezes você pode ter atrasos quando as políticas de retenção excluem mensagens. Por exemplo, as mensagens podem ficar visíveis para os usuários no aplicativo do Teams até sete dias após o período de expiração que você configurou na política de retenção.

Se você configurar várias políticas de retenção do Teams com configurações de retenção diferentes, os princípios de retenção resolverão os conflitos. Por exemplo:

- Se houver um conflito entre reter ou excluir o mesmo conteúdo, o conteúdo sempre será mantido no local seguro para que ele permaneça pesquisável com a Descoberta Eletrônica para administradores de conformidade.
    
    Esse princípio também se aplica a mensagens que estão sob retenções de Descoberta Eletrônica por motivos legais ou de investigação.

- Se houver um conflito sobre quanto tempo manter o mesmo conteúdo, ele será mantido no local seguro pelo período de retenção mais longo.

Esses dois princípios de retenção abordam a maioria dos conflitos que podem surgir quando você tem várias políticas de retenção para o Teams, mas para obter mais informações, consulte [Os princípios de retenção ou o que tem precedência?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando usar as políticas de retenção para o Teams.

Em muitos casos, as organizações consideram os dados de chat privados como um número mais passivo do que as mensagens de canal, que geralmente são conversas mais relacionadas ao projeto.

Você pode configurar com muita eficiência uma única política de retenção para todas as mensagens do Teams. Ou, para um controle mais refinado, você pode:

- Ter políticas de retenção separadas para chats privados (chats 1:1 ou 1:muitos), mensagens de canais padrão ou mensagens de canais privados.

- Aplique as políticas somente a usuários ou equipes específicas em sua organização. Para chats do Teams e canais privados, você pode selecionar a quais usuários a política se aplica. Para mensagens de canal do Teams, você pode selecionar a quais equipes a política será aplicada.

Por exemplo, para mensagens de canal padrão: crie uma política de retenção para equipes específicas em sua organização e configure essa política com uma ação de exclusão após 1 ano. Em seguida, crie outra política de retenção para mensagens de canal padrão para todas as outras equipes e configure essa política com uma ação de exclusão após 3 anos.

## <a name="create-and-manage-retention-policies-for-teams"></a>Criar e gerenciar políticas de retenção para o Teams

Para criar ou editar uma política de retenção para mensagens do Teams, use as instruções da [política de retenção para locais do Teams](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).

Essa página tem informações adicionais sobre como criar e gerenciar políticas de retenção para outras cargas de trabalho no Microsoft 365. Por exemplo, talvez você também queira criar uma política de retenção para Grupos do Microsoft 365 para reter e excluir arquivos que são acessados no Teams e armazenados no OneDrive ou no Microsoft Office SharePoint Online.  

## <a name="end-user-experience"></a>Experiência do usuário final

Para chats privados (chats individuais) ou chats em grupo, os usuários verão que chats mais antigos do que a configuração de política de retenção são excluídos e uma mensagem gerada automaticamente informa que "Excluímos mensagens mais antigas devido à política de retenção da sua organização" é exibida acima de mensagens ainda não excluídas. Por exemplo:

:::image type="content" source="media/retention-policies-image1.png" alt-text="O usuário informou no Teams que a mensagem de chat foi excluída devido a uma política de retenção do Teams.":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="O usuário do Teams explicando que as mensagens são excluídas como resultado de uma política de retenção do Teams.":::

Para mensagens do Canal, os usuários (membros do canal) verão as mensagens excluídas desaparecerem da exibição depois que as mensagens expirarem. Se a mensagem excluída era uma mensagem pai de uma conversa encadeada, então, no lugar da mensagem pai, será exibida uma mensagem dizendo "Esta mensagem foi excluída por causa de uma Política de Retenção". Por exemplo:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Captura de tela do canal antes da retenção.":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Captura de tela do canal após a retenção.":::

> [!NOTE]
> As mensagens exibidas que os usuários veem como resultado de mensagens excluídas não são configuráveis no momento.

Os links nessas mensagens exibidas vão para [Mensagens do Teams sobre políticas de retenção](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b). Esta documentação para usuários finais ajuda a responder perguntas básicas sobre por que suas mensagens foram excluídas. No entanto, como parte da implantação da política de retenção, certifique-se de se comunicar com os usuários e o suporte técnico sobre o impacto das configurações definidas.

## <a name="related-topics"></a>Tópicos relacionados

- [Introdução às políticas de retenção e rótulos de retenção](/microsoft-365/compliance/get-started-with-retention)
- [Saiba mais sobre retenção para o Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Criar e configurar políticas de retenção](/microsoft-365/compliance/create-retention-policies)
- Solução de problemas: [as mensagens nos aplicativos do Teams e do Yammer são excluídas inesperadamente pelas políticas de retenção](/microsoftteams/troubleshoot/teams-im-presence/messages-unexpectedly-deleted-retention-policy)
