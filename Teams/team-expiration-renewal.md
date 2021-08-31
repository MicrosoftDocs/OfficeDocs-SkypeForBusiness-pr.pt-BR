---
title: Expiração e renovação de equipe no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba mais sobre a expiração e renovação da equipe e como usar Microsoft 365 política de expiração de grupo para limpar automaticamente as equipes não usadas no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14c76bd56fa7e6e9392550fa61385539415e52eb
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733550"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiração e renovação de equipe no Microsoft Teams

Organizações com um grande número de equipes geralmente têm equipes que nunca são realmente usadas. Isso pode acontecer devido a vários motivos, incluindo experimentação de produto, colaboração de equipe de curto prazo ou proprietários de equipe deixando a organização. Com o tempo, essas equipes podem se acumular e criar uma sobrecarga nos recursos do locatário.  

Para reduzir o número de equipes não usadas, como administrador, você pode usar Microsoft 365 política de expiração de grupo para limpar automaticamente as equipes não usadas. [](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) Como as equipes têm o suporte de grupos, as políticas de expiração de grupo também se aplicam automaticamente às equipes.

Quando você aplica uma política de expiração a uma equipe, um proprietário da equipe recebe uma notificação para renovação de equipe 30 dias, 15 dias e 1 dia antes da data de expiração da equipe. Quando o proprietário da equipe recebe a notificação, ele pode clicar em **Renovar agora** nas configurações da equipe para renovar a equipe.

![Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe.](media/team-expiration.png "Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe")

Se o proprietário da equipe não renovar a equipe e não houver mais atividades na equipe até o final da política de expiração, a equipe será colocada em um estado "excluído de forma suave", o que significa que ela poderá ser restaurada dentro dos próximos 30 dias.

## <a name="team-auto-renewal"></a>Renovação automática da equipe

Pode haver momentos em que um proprietário da equipe não consegue renovar a equipe, talvez porque esqueceu de renovar ou estava fora quando a renovação era devido. Nesses cenários, uma equipe em uso ativo pode ser excluída devido às políticas de expiração que se aplicam à equipe.  

Para evitar a exclusão acidental, a renovação automática é automaticamente habilitada para uma equipe na política de expiração de grupo. Quando a política de expiração de grupo é configurada, qualquer equipe que tenha pelo menos uma visita de canal de qualquer membro da equipe antes de sua data de expiração é renovada automaticamente sem qualquer intervenção manual do proprietário da equipe.

## <a name="known-issues"></a>Problemas conhecidos

**A data de expiração da equipe e do grupo subjacente não é igual**

Antes que uma equipe seja renovada, o grupo que faz o backs da equipe é renovado primeiro. Como parte da renovação, uma nova data de expiração é definida no grupo para uma data futura. Essa nova data pode não estar imediatamente visível Teams. Pode levar até 24 horas para sincronizar. Se você vir uma discrepância entre a data de expiração de uma equipe e seu grupo subjacente, aguarde 24 horas antes de procurar mais suporte.