---
title: Expiração e renovação da equipe no Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
ms.openlocfilehash: 697e36085169e0666e6a821a66c763be39cf9425
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868518"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiração e renovação da equipe no Microsoft Teams

Organizações com um grande número de equipes muitas vezes têm equipes que nunca são usadas de fato. Isso pode acontecer devido a vários motivos, incluindo a experimentação do produto, a colaboração da equipe de curto prazo ou os proprietários da equipe que deixam a organização. Ao longo do tempo, tais equipes podem acumular e criar uma sobrecarga nos recursos do locatário.  

Para restringir o número de equipes não usadas, como administrador, você pode usar a [política de expiração de grupo do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para limpar automaticamente as equipes não usadas. Como as equipes são apoiadas por grupos, as políticas de expiração de grupo também se aplicam automaticamente às equipes.

Quando você aplica uma política de expiração a uma equipe, um proprietário da equipe recebe uma notificação para a renovação da equipe 30 dias, 15 dias e 1 dia antes da data de expiração da equipe. Quando o proprietário da equipe receber a notificação, poderá clicar em **renovar agora** em configurações da equipe para renovar a equipe.

![Captura de tela do botão Renovar agora para renovar uma equipe nas configurações da equipe](media/team-expiration.png "Captura de tela do botão Renovar agora para renovar uma equipe nas configurações da equipe")

Se o proprietário da equipe não renovar a equipe, a equipe será colocada em um estado "excluído sem disco", o que significa que ela pode ser restaurada dentro dos próximos 30 dias.

## <a name="team-auto-renewal"></a>Renovação automática da equipe

Pode haver ocasiões em que um proprietário de equipe não consiga renovar a equipe, talvez porque ela se esqueceu de ser renovada ou ficou ausente quando a renovação foi concluída. Nesses cenários, uma equipe em uso ativo pode ser excluída devido às políticas de expiração que se aplicam à equipe.  

Para evitar exclusão acidental, a renovação automática é habilitada automaticamente para uma equipe na política de expiração do grupo. Quando a política de expiração de grupo é configurada, qualquer equipe que tenha pelo menos um canal acessado de qualquer membro da equipe antes da data de expiração seja automaticamente renovada sem nenhuma intervenção manual do proprietário da equipe.

## <a name="known-issues"></a>Problemas conhecidos

**A data de expiração da equipe e do grupo subjacente não correspondem**

Antes que uma equipe seja renovada, o grupo que faz o backup da equipe é renovado primeiro. Como parte da renovação, uma nova data de vencimento é definida no grupo para uma data futura. Esta nova data pode não ser imediatamente visível no Microsoft Teams. Pode levar até 24 horas para sincronizar. Se você vir uma discrepância entre a data de vencimento de uma equipe e seu grupo subjacente, Aguarde 24 horas antes de buscar mais suporte.
