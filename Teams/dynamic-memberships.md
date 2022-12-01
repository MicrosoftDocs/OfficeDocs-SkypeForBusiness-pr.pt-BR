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
description: Saiba como Microsoft Teams dá suporte a equipes associadas a Microsoft 365 grupos usando associação dinâmica.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c747fea2b33f2fd18b004e9a16a2302702ec59
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198723"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Visão geral da associação dinâmica de equipes

Microsoft Teams dá suporte a equipes associadas a Microsoft 365 grupos usando *associação dinâmica*. A associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam determinados atributos de usuário no Azure Active Directory (Azure AD). Os usuários são adicionados ou removidos automaticamente às equipes corretas à medida que os atributos de usuário mudam ou os usuários se juntam e saem do locatário.

Com a associação dinâmica, você pode configurar equipes para determinadas coortes de usuários em sua organização. Os cenários possíveis incluem:
- Um hospital pode criar equipes distintas para enfermeiros, médicos e cirurgiões transmitirem comunicações. Isso é especialmente importante se o hospital depende de funcionários temporários.
- Uma universidade pode criar uma equipe para todos os professores em uma determinada faculdade, incluindo um corpo docente adjunto que muda com frequência.
- Uma companhia aérea quer criar uma equipe para cada voo (como uma terça-feira à tarde sem parar de Chicago para Atlanta) e ter uma tripulação de voo com mudanças frequentes automaticamente atribuída ou removida conforme necessário.

Usando esse recurso, os membros de uma determinada equipe são atualizados automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação. Fazer isso requer Azure AD Premium P1 licenças e associação de equipe podem ser [atribuídas por um administrador de locatário](/azure/active-directory/users-groups-roles/groups-dynamic-membership) às propriedades Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.

Microsoft o Teams pode levar de alguns minutos a até 2 horas para refletir as alterações dinâmicas de associação depois que entrarem em vigor no grupo Microsoft 365 para uma equipe.

Ao usar equipes com grupos dinâmicos:

- As regras podem definir quem é um membro da equipe, mas não quem é um proprietário da equipe.
- Os proprietários não poderão adicionar ou remover usuários como membros da equipe, uma vez que os membros são definidos por regras dinâmicas de grupo.
- Os clientes do Teams não permitem o gerenciamento de membros para a equipe. As opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estão ocultas.

Para criar uma equipe que usa associação dinâmica, comece [criando um grupo dinâmico Microsoft 365](/azure/active-directory/users-groups-roles/groups-create-rule) e [crie uma equipe desse grupo](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

Você pode alterar uma equipe existente para ter uma associação dinâmica. Consulte [Alterar a associação de grupo estático para dinâmica no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) para obter informações.

## <a name="related-topics"></a>Tópicos relacionados

[Limites e especificações do Microsoft Teams](limits-specifications-teams.md)

[Regras de associação dinâmica para grupos no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
