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
description: Saiba como o Microsoft Teams dá suporte a equipes associadas a grupos do Microsoft 365 usando associação dinâmica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120763"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Visão geral da associação dinâmica de equipes

O Microsoft Teams dá suporte a equipes associadas a grupos do Microsoft 365 usando *associação dinâmica.* A associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam determinados atributos de usuário no Azure Active Directory (Azure AD). Os usuários são adicionados ou removidos automaticamente às equipes corretas à medida que os atributos do usuário mudam ou os usuários ingressam e saem do locatário.

Com a associação dinâmica, você pode configurar equipes para determinados grupos de usuários em sua organização. Cenários possíveis incluem:
- Um hospital pode criar equipes distintas para profissionais de saúde, médicos e médicos transmitirem comunicações. Isso é especialmente importante se o hospital depende de funcionários temporários.
- Uma universidade pode criar uma equipe para todos os professores em uma determinada universidade, incluindo um corpo docente adjunta que muda com frequência.
- Uma companhia aérea deseja criar uma equipe para cada voo (como uma tarde de terça-feira sem parar de Chicago para Atlanta) e ter uma equipe de voo com frequência mudando automaticamente atribuída ou removida conforme necessário.

Usando esse recurso, os membros de uma determinada equipe são atualizados automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação. Isso requer licenças do Azure AD Premium [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) P1 e a associação à equipe pode ser atribuída por um administrador de locatário às propriedades do Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.

O Microsoft Teams pode levar de alguns minutos a até duas horas para refletir as alterações dinâmicas de associação depois que entrar em vigor no grupo do Microsoft 365 para uma equipe.

> [!NOTE]
> - As regras podem definir quem é membro da equipe, mas não quem é o proprietário da equipe.
> - Consulte [Limites e especificações do Microsoft Teams](limits-specifications-teams.md) para os limites atuais em tamanhos de equipe e canal.
> - Os proprietários não poderão adicionar ou remover usuários como membros da equipe, já que os membros são definidos por regras dinâmicas de grupo.
> -    Os membros não poderão deixar as equipes com o suporte de grupos dinâmicos.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Criar e gerenciar um grupo do Microsoft 365 com associação dinâmica

Enquanto estiver conectado como o administrador do locatário, siga as instruções em [Criar um grupo dinâmico e verificar o status](/azure/active-directory/users-groups-roles/groups-create-rule). Conforme necessário, consulte [Regras de associação dinâmicas para grupos no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Criar uma nova equipe com seu grupo do Microsoft 365

Agora, permita que as alterações de associação entre em vigor e criem uma nova equipe conforme descrito em [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar associação dinâmica a uma equipe existente

Você também pode usar uma equipe existente e alterá-la para ter uma associação dinâmica, conforme descrito em Alterar associação de grupo estático para [dinâmica no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Alterações no comportamento do cliente

Depois que a associação dinâmica for habilitada para uma equipe, os clientes do Teams não permitirão mais o gerenciamento de membros para a equipe. Opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estão ocultas.