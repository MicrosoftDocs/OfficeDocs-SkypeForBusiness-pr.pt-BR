---
title: Expiração e renovação da equipe no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba mais sobre a expiração e a renovação da equipe e como usar a política de expiração de grupo do Microsoft 365 para limpar automaticamente as equipes não usadas no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809401"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiração e renovação da equipe no Microsoft Teams

Organizações com um grande número de equipes geralmente têm equipes que nunca são realmente usadas. Isso pode acontecer devido a vários motivos, incluindo experimentação de produto, colaboração em equipe de curto prazo ou proprietários de equipe deixando a organização. Com o tempo, essas equipes podem se acumular e criar uma carga nos recursos do locatário.  

Para reduzir o número de equipes não usadas, como administrador, você pode usar a política de expiração de grupo do [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para limpar automaticamente as equipes não usadas. Como as equipes são respaldadas por grupos, as políticas de expiração de grupo também se aplicam automaticamente às equipes.

Quando você aplica uma política de expiração a uma equipe, um proprietário da equipe recebe uma notificação para renovação da equipe por 30 dias, 15 dias e 1 dia antes da data de expiração da equipe. Quando o proprietário da equipe recebe a notificação, ele pode clicar em **Renovar agora** nas configurações da equipe para renovar a equipe.

![Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe](media/team-expiration.png "Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe")

Se o proprietário da equipe não renovar a equipe e não houver mais atividades na equipe até o final da política de expiração, a equipe será colocada em um estado "excluído de forma suave", o que significa que ela poderá ser restaurada dentro dos próximos 30 dias.

## <a name="team-auto-renewal"></a>Renovação automática da equipe

Pode haver momentos em que um proprietário da equipe não consegue renovar a equipe, talvez porque ele esqueceu de renovar ou estava fora quando a renovação estava em vencimento. Nesses cenários, uma equipe em uso ativo pode ser excluída devido a políticas de expiração que se aplicam à equipe.  

Para evitar a exclusão acidental, a renovação automática é habilitada automaticamente para uma equipe na política de expiração de grupo. Quando a política de expiração de grupo é configurada, qualquer equipe que tenha pelo menos uma visita de canal de qualquer membro da equipe antes de sua data de expiração é renovada automaticamente sem qualquer intervenção manual do proprietário da equipe.

## <a name="known-issues"></a>Problemas conhecidos

**A data de expiração da equipe e do grupo subjacente não é igual**

Antes da renovação de uma equipe, o grupo que faz o back-back da equipe é renovado primeiro. Como parte da renovação, uma nova data de vencimento é definida no grupo para uma data futura. Essa nova data pode não estar imediatamente visível no Teams. Pode levar até 24 horas para sincronizar. Se você vir uma discrepância entre a data de expiração de uma equipe e seu grupo subjacente, aguarde 24 horas antes de procurar mais suporte.
