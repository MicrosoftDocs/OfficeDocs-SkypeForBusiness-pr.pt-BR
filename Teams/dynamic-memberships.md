---
title: Visão geral da associação dinâmica de equipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre associações dinâmicas a equipes com base no AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: beb93d1bd369d98743ad54b9f5753278dea36ed8
ms.sourcegitcommit: 21a5550e3c0feafaa57dbcdc428ed13eedd276b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2019
ms.locfileid: "34748431"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Visão geral da associação dinâmica de equipes

O Microsoft Teams dá suporte a equipes associadas a grupos do Office 365 usando associação dinâmica. Associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam certos atributos de usuário no Azure Active Directory (AAD). Os usuários são automaticamente adicionados ou removidos às equipes corretas à medida que os atributos do usuário mudam ou fazem o usuário ingressar e deixar o locatário.

Com associação dinâmica, você pode configurar equipes para determinados cohorts de usuários em sua organização. Os cenários possíveis incluem:
- Um hospital pode criar equipes distintas para surgeonss, médicos e para transmitir comunicações. Isso é especialmente importante se o hospital depende de funcionários temporários.
- Uma universidade pode criar uma equipe para todos os professores dentro de uma faculdade específica, incluindo um docente Adjunct que muda com frequência.
- Uma companhia aérea quer criar uma equipe para cada voo (como uma tarde de terça-feira de terça-feira de Chicago para Atlanta) e ter uma equipe de voo que muda com frequência automaticamente atribuída ou removida conforme necessário.

Usando esse recurso, uma determinada atualização dos membros da equipe com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação. Isso exige que as licenças do Azure AD Premium e a associação da equipe possam ser [atribuídas por um administrador locatário](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) às propriedades AAD de qualquer usuário, contanto que você tenha um locatário e uma conta de administrador. 

O Microsoft Teams pode levar alguns minutos de até 2 horas para refletir as alterações de associação dinâmica quando entrarem em vigor no grupo do Office 365 para uma equipe. 

> [!NOTE]
> - As regras podem definir quem é um membro da equipe, mas não quem é o proprietário da equipe.
> - Consulte [limites e especificações do Microsoft Teams](limits-specifications-teams.md) para obter os limites atuais sobre tamanhos de canal e equipe.
> - Os proprietários não poderão adicionar ou remover usuários como membros da equipe, pois os membros são definidos por regras de grupo dinâmico.
> - Os membros não poderão deixar a equipe apoiada por grupos dinâmicos.


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Criando e gerenciando um grupo do Office 365 com associação dinâmica
Enquanto estiver conectado como administrador de locatários, siga as instruções em [criar um grupo dinâmico e verificar o status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule). Conforme necessário, consulte [regras de associação dinâmica para grupos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Criar uma nova equipe com seu grupo do O365

Agora, aguarde o tempo para as alterações de associação entrarem em vigor e crie uma nova equipe, conforme descrito em aprimorar os [grupos existentes do Office 365 com o Microsoft Teams](enhance-office-365-groups.md).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar associação dinâmica a uma equipe existente

Você também pode pegar uma equipe existente e alterá-la para ter uma associação dinâmica, conforme descrito em [Alterar Associação de grupo estático para dinâmico no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Alterações no comportamento do cliente

Depois que a associação dinâmica estiver habilitada para uma equipe, os clientes do Teams não permitirão mais o gerenciamento de membros da equipe. Opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estar oculta.
