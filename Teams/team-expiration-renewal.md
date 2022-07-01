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
ms.collection:
- M365-collaboration
description: Saiba mais sobre a expiração e a renovação da equipe e como usar a política de expiração de grupo do Microsoft 365 para limpar automaticamente as equipes não utilizadas no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1a322e07df81727c75c05ebb16c4cdabc0916a4
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564169"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiração e renovação da equipe no Microsoft Teams

Organizações com um grande número de equipes geralmente têm equipes que nunca são realmente usadas. Isso pode acontecer devido a vários motivos, incluindo experimentação de produtos, colaboração em equipe de curto prazo ou proprietários de equipe que estão saindo da organização. Ao longo do tempo, essas equipes podem se acumular e criar uma carga nos recursos do locatário.  

Para reduzir o número de equipes não utilizadas, como administrador, você pode usar a política de expiração de grupo do [Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para limpar automaticamente as equipes não utilizadas. Como as equipes são apoiadas por grupos, as políticas de expiração de grupo também se aplicam automaticamente às equipes.

Quando você aplica uma política de expiração a uma equipe, um proprietário da equipe recebe uma notificação para renovação da equipe 30 dias, 15 dias e 1 dia antes da data de expiração da equipe. Quando o proprietário da equipe recebe a notificação, ele pode clicar em **Renovar agora** nas configurações da equipe para renovar a equipe.

![Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe.](media/team-expiration.png "Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe")

Se o proprietário da equipe não renovar a equipe e não houver nenhuma atividade adicional na equipe até o final da política de expiração, a equipe será colocada em um estado de "exclusão reversível", o que significa que ela poderá ser restaurada dentro dos próximos 30 dias.

## <a name="team-auto-renewal"></a>Renovação automática da equipe

Pode haver ocasiões em que um proprietário da equipe não consegue renovar a equipe, talvez porque se esqueceu de renovar ou estava ausente quando a renovação era devido. Nesses cenários, uma equipe em uso ativo pode ser excluída devido a políticas de expiração que se aplicam à equipe.  

Para evitar a exclusão acidental, a renovação automática é habilitada automaticamente para uma equipe na política de expiração de grupo. Quando a política de expiração do grupo é configurada, qualquer equipe que tenha pelo menos uma visita de canal de qualquer membro da equipe antes de sua data de expiração é renovada automaticamente sem nenhuma intervenção manual do proprietário da equipe.

## <a name="known-issues"></a>Problemas conhecidos

**A data de validade da equipe e do grupo subjacente não corresponde**

Antes que uma equipe seja renovada, o grupo que faz backup da equipe é renovado primeiro. Como parte da renovação, uma nova data de expiração é definida no grupo para uma data futura. Essa nova data pode não estar imediatamente visível no Teams. A sincronização pode levar até 24 horas. Se você vir uma discrepância entre a data de expiração de uma equipe e seu grupo subjacente, aguarde 24 horas antes de buscar mais suporte.