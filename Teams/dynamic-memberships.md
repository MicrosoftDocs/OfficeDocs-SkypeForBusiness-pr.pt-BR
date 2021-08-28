---
title: Visão geral da associação dinâmica de equipes
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como Microsoft Teams dá suporte a equipes associadas Microsoft 365 grupos usando associação dinâmica.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a18e2cbe1a34fe78f5e84b4df4ae9a95c46fd9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613630"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Visão geral da associação dinâmica de equipes

Microsoft Teams dá suporte a equipes associadas Microsoft 365 grupos usando *a associação dinâmica*. A associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam determinados atributos de usuário no Azure Active Directory (Azure AD). Os usuários são adicionados ou removidos automaticamente às equipes corretas à medida que os atributos do usuário mudam ou os usuários ingressam e saem do locatário.

Com a associação dinâmica, você pode configurar equipes para determinados grupos de usuários em sua organização. Cenários possíveis incluem:
- Um hospital pode criar equipes distintas para profissionais de saúde, médicos e médicos transmitirem comunicações. Isso é especialmente importante se o hospital depende de funcionários temporários.
- Uma universidade pode criar uma equipe para todos os professores em uma determinada universidade, incluindo um corpo docente adjunta que muda com frequência.
- Uma companhia aérea deseja criar uma equipe para cada voo (como uma tarde de terça-feira sem parar de Chicago para Atlanta) e ter uma equipe de voo com frequência mudando automaticamente atribuída ou removida conforme necessário.

Usando esse recurso, os membros de uma determinada equipe são atualizados automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação. Isso requer Azure AD Premium P1 licenças e associação de [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) equipe podem ser atribuídas por um administrador de locatários às propriedades do Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.

Microsoft Teams pode levar de alguns minutos a até duas horas para refletir as alterações dinâmicas de associação depois que elas entrarem em vigor no grupo Microsoft 365 para uma equipe.

Ao usar equipes com grupos dinâmicos:

- As regras podem definir quem é membro da equipe, mas não quem é o proprietário da equipe.
- Os proprietários não poderão adicionar ou remover usuários como membros da equipe, já que os membros são definidos por regras dinâmicas de grupo.
- Teams clientes não permitem o gerenciamento de membros para a equipe. Opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estão ocultas.

Para criar uma equipe que use [](/azure/active-directory/users-groups-roles/groups-create-rule) associação dinâmica, comece criando um grupo Microsoft 365 dinâmico e crie uma [equipe desse grupo.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

Você pode alterar uma equipe existente para ter uma associação dinâmica. Consulte [Alterar a associação do grupo estático para dinâmica Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) informações.

## <a name="related-topics"></a>Tópicos relacionados

[Limites e especificações do Microsoft Teams](limits-specifications-teams.md)

[Regras de associação dinâmicas para grupos Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
