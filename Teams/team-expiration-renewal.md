---
title: Expiração e renovação da equipe no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
description: Saiba mais sobre expiração e renovação de equipe e como usar Microsoft política de expiração de grupo 365 para limpar automaticamente equipes não utilizadas no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4f56c8cbb2d25b05d6c87fa2862e56244d6b9c8
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198793"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiração e renovação da equipe no Microsoft Teams

Organizações com um grande número de equipes geralmente têm equipes que nunca são realmente usadas. Isso pode acontecer devido a vários motivos, incluindo experimentação de produtos, colaboração de equipe de curto prazo ou proprietários de equipe deixando a organização. Com o tempo, essas equipes podem acumular e criar um fardo sobre os recursos de locatário.  

Para reduzir o número de equipes não utilizadas, como administrador, você pode usar [Microsoft política de expiração de grupo 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para limpar automaticamente equipes não utilizadas. Como as equipes são apoiadas por grupos, as políticas de expiração de grupo também se aplicam automaticamente às equipes.

Quando você aplica uma política de expiração a uma equipe, um proprietário da equipe recebe uma notificação para renovação da equipe 30 dias, 15 dias e um dia antes da data de validade da equipe. Quando o proprietário da equipe recebe a notificação, ele pode clicar em **Renovar agora** nas configurações da equipe para renovar a equipe.

![Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe.](media/team-expiration.png "Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe")

Se o proprietário da equipe não renovar a equipe e não houver mais atividades na equipe até o final da política de expiração, a equipe será colocada em um estado "excluído suavemente", o que significa que ele pode ser restaurado nos próximos 30 dias.

## <a name="team-auto-renewal"></a>Renovação automática da equipe

Pode haver momentos em que um dono de equipe não consegue renovar a equipe talvez porque esqueceu de renovar ou estava fora quando a renovação estava prevista. Nesses cenários, uma equipe em uso ativo pode ser excluída devido a políticas de expiração que se aplicam à equipe.  

Para evitar a exclusão acidental, a renovação automática é habilitada automaticamente para uma equipe na política de expiração do grupo. Quando a política de expiração de grupo é configurada, qualquer equipe que tenha pelo menos uma visita de canal de qualquer membro da equipe antes de sua data de validade é renovada automaticamente sem qualquer intervenção manual do proprietário da equipe.

## <a name="known-issues"></a>Problemas conhecidos

**A data de validade da equipe e do grupo subjacente não correspondem**

Antes de uma equipe ser renovada, o grupo que apoia a equipe é renovado primeiro. Como parte da renovação, uma nova data de validade é definida no grupo para uma data futura. Essa nova data pode não estar imediatamente visível no Teams. Pode levar até 24 horas para sincronizar. Se você vir uma discrepância entre a data de validade de uma equipe e seu grupo subjacente, aguarde 24 horas antes de buscar mais suporte.