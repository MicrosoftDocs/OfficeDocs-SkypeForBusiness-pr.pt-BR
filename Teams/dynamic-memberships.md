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
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583920"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Visão geral da associação dinâmica de equipes

O Microsoft Teams dá suporte a equipes associadas a grupos do Microsoft 365 usando *associação dinâmica.* A associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam determinados atributos do usuário no Azure Active Directory (Azure AD). Os usuários são adicionados ou removidos automaticamente às equipes corretas à medida que os atributos do usuário mudam ou os usuários ingressam e saem do locatário.

Com a associação dinâmica, você pode configurar equipes para determinados tipos de usuários em sua organização. Os cenários possíveis incluem:
- Um hospital pode criar equipes distintas para médicos, médicos e médicos para transmitir comunicações. Isso é especialmente importante se o hospital depende de funcionários temporários.
- Uma universidade pode criar uma equipe para todos os docentes em uma faculdade específica, incluindo um corpo docente adjunta que muda com frequência.
- Uma companhia aérea quer criar uma equipe para cada voo (como uma terça-feira à tarde sem parar de Chicago para Atlanta) e ter uma equipe de voos de mudança frequente atribuída ou removida automaticamente, conforme necessário.

Usando esse recurso, os membros de uma determinada equipe são atualizados automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação. Isso requer licenças do Azure AD Premium [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) P1 e a associação à equipe pode ser atribuída por um administrador de locatário às propriedades do Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.

O Microsoft Teams pode levar de alguns minutos a até duas horas para refletir as alterações dinâmicas de associação depois que elas entrarem em vigor no grupo do Microsoft 365 para uma equipe.

> [!NOTE]
> - As regras podem definir quem é um membro da equipe, mas não quem é o proprietário da equipe.
> - Consulte [Limites e especificações do Microsoft Teams para](limits-specifications-teams.md) ver os limites atuais de tamanhos de equipe e canal.
> - Os proprietários não poderão adicionar ou remover usuários como membros da equipe, uma vez que os membros são definidos por regras dinâmicas de grupo.
> -    Os membros não poderão sair das equipes com o apoio de grupos dinâmicos.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Criar e gerenciar um grupo do Microsoft 365 com associação dinâmica

Enquanto estiver conectado como administrador do locatário, siga as instruções em Criar um [grupo dinâmico e verificar o status.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) Conforme necessário, consulte [as regras de associação dinâmicas para grupos no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Criar uma nova equipe com seu grupo do Microsoft 365

Agora, permita que as alterações de associação entre em vigor e crie uma nova equipe conforme descrito em Criar uma equipe a partir de [um grupo existente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar associação dinâmica a uma equipe existente

Você também pode assumir uma equipe existente e alterá-la para ter uma associação dinâmica, conforme descrito em Alterar associação de grupo estático para dinâmica [no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>Alterações no comportamento do cliente

Depois que a associação dinâmica for habilitada para uma equipe, os clientes do Teams não permitirão mais o gerenciamento de membros para a equipe. As opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estão ocultas.
