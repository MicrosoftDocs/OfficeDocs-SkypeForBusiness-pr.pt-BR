---
title: Conformidade de comunicação do Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre conformidade de comunicação, parte do conjunto de soluções de risco do Insider, da perspectiva do Microsoft Teams (isso faz parte da funcionalidade de conformidade de comunicação do M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077686"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Conformidade de comunicação do Microsoft Teams

A conformidade com comunicações faz parte da nova solução de risco do insider definida no Microsoft 365, que ajuda a minimizar os riscos de comunicação, ajudando você a detectar, capturar e fazer ações de correção para mensagens inadequadas em sua organização. Isso ajuda a identificar uma linguagem ofensiva e um antiassédio em canais de equipe ou 1:1 e chats em grupo. Você também pode definir políticas para ver se as informações confidenciais estão sendo compartilhadas como parte dos canais da equipe ou 1:1 e chats em grupo. Para obter mais informações sobre diferentes tipos de políticas e como configurar, consulte o [artigo M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-teams"></a>Como usar a conformidade com comunicações no Microsoft Teams

### <a name="identify-inappropriate-messages"></a>Identificar mensagens inadequadas

Se você deseja identificar as mensagens que são enviadas no Microsoft Teams (1:1, chats em grupo ou conversas de canal) contenham idiomas ofensivos ou antiassédio, você pode habilitar políticas para identificar isso, e o revisor pode examinar as mensagens e tomar as medidas necessárias, como enviar material de treinamento ou encaminhar para as autoridades certas.

### <a name="identify-sensitive-or-regulatory-information"></a>Identificar informações confidenciais ou normativas

Se você quiser verificar mensagens enviadas no Microsoft Teams (1:1, chats em grupo ou conversas de canal) para obter informações confidenciais ou tipos regulatórios, poderá escolher políticas que ofereçam suporte a tipos confidenciais ou regulatórios predefinidos.

> [!NOTE]
> Os canais privados não são compatíveis com a conformidade de comunicação.

### <a name="custom-policy"></a>Política personalizada

Use este modelo para configurar canais de comunicação específicos, condições individuais de detecção e o volume de conteúdo a ser monitorado e revisado em sua organização.

### <a name="custom-trainable-classifier"></a>Classificador treinado personalizado

Use classificadores ferroviárias quando um dos classificadores prontos para atender às suas necessidades. Um classificador do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando a ele exemplos para ver. O treinamento do classificador envolve primeiro dar a ele exemplos que sejam separados à sua categoria humana e positiva. Depois disso, após processar esses exemplos, você testará as previsões dando a ele uma mistura de exemplos positivos e negativos. Para obter mais informações sobre isso, consulte o [artigo M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) para obter mais informações sobre este tópico.

> [!NOTE]
> A conformidade com comunicações agora oferece suporte a implantações híbridas do Exchange.

Conformidade de comunicação compatível com o histórico de conversas para qualquer mensagem que corresponda às políticas. Isso fornece contexto para o administrador de investigação.

:::image type="content" source="media/communication-compliance-1.png" alt-text="Uma tela para conformidade de comunicação no Microsoft Teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>Onde as políticas de comunicação podem ser aplicadas no Teams

As políticas de conformidade de comunicação podem ser configuradas para mensagens enviadas no Microsoft Teams nos seguintes níveis:

- Nível do usuário: um administrador pode configurar políticas em um nível de usuário individual ou aplicá-las a todos os usuários no locatário. Isso inclui apenas as mensagens que um usuário enviou no 1:1 ou chats em grupo.
- Nível da equipe: um administrador também pode configurar políticas em uma equipe. Isso abrange todas as mensagens enviadas no canal da equipe (mensagens de canal privado não são suportadas).
