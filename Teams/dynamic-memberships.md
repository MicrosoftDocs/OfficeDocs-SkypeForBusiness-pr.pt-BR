---
title: Visão geral da associação dinâmica de equipes
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como o Microsoft Teams dá suporte a equipes associadas a grupos do Microsoft 365 usando associação dinâmica.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff6a71978873d723f39a534f876696a0def2f756
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562570"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Visão geral da associação dinâmica de equipes

O Microsoft Teams dá suporte a equipes associadas a grupos do Microsoft 365 usando *associação dinâmica*. A associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam determinados atributos de usuário no Azure Active Directory (Azure AD). Os usuários são adicionados ou removidos automaticamente às equipes corretas à medida que os atributos de usuário mudam ou os usuários ingressam e saem do locatário.

Com a associação dinâmica, você pode configurar equipes para determinadas coortes de usuários em sua organização. Os cenários possíveis incluem:
- Um hospital pode criar equipes distintas para enfermeiras, médicos e cirurgiões transmitirem comunicações. Isso é especialmente importante se o hospital depende de funcionários temporários.
- Uma universidade pode criar uma equipe para todos os docentes em uma faculdade específica, incluindo um corpo docente associado que muda com frequência.
- Uma companhia aérea deseja criar uma equipe para cada voo (como uma tarde de terça-feira sem interrupção de Chicago para Atlanta) e ter uma tripulação de voo com alteração frequente atribuída ou removida automaticamente, conforme necessário.

Usando esse recurso, os membros de uma determinada equipe são atualizados automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação. Isso requer que Azure AD Premium P1 licenças e associação de equipe possam ser atribuídas [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) por um administrador de locatários às propriedades de Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.

O Microsoft Teams pode levar de alguns minutos a até duas horas para refletir as alterações de associação dinâmicas depois que elas entrarem em vigor no grupo do Microsoft 365 para uma equipe.

Ao usar equipes com grupos dinâmicos:

- As regras podem definir quem é um membro da equipe, mas não quem é o proprietário da equipe.
- Os proprietários não poderão adicionar ou remover usuários como membros da equipe, pois os membros são definidos por regras de grupo dinâmico.
- Os clientes do Teams não permitem o gerenciamento de membros para a equipe. As opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estão ocultas.

Para criar uma equipe que usa associação dinâmica, comece criando um grupo dinâmico do [Microsoft 365](/azure/active-directory/users-groups-roles/groups-create-rule) e, em seguida, crie [uma equipe desse grupo](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

Você pode alterar uma equipe existente para ter uma associação dinâmica. Consulte [Alterar a associação de grupo estático para dinâmico no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) para obter informações.

## <a name="related-topics"></a>Tópicos relacionados

[Limites e especificações do Microsoft Teams](limits-specifications-teams.md)

[Regras de associação dinâmica para grupos no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
