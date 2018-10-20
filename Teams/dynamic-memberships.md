---
title: Visão geral da participação dinâmica para equipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 10/10/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre a associação de equipe dinâmica com base em AAD.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a98009237d6575e97705ae7a8eea4b444ac77a0
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25682362"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Visão geral da participação dinâmica para equipes

Microsoft Teams suporta as equipes associadas a grupos de Office 365 usando a participação dinâmica. Participação dinâmica permite a associação de uma equipe sejam definidos por uma ou mais regras que verificam para alguns atributos de usuário no Windows Azure Active Directory (AAD). Automaticamente, a usuários forem adicionados ou removidos para as equipes corretas como alterar os atributos de usuário ou usuários entram e saem de locatário.

Com associação dinâmica, que você pode a instalação para determinadas equipes colaboradores de usuários em sua organização. Os possíveis cenários incluem:
- Um hospital pode criar equipes distintas para enfermeiros, os médicos e cirurgiões difusão de comunicações. Isso é especialmente importante se hospital depende de funcionários temporários.
- Uma universidade pode criar uma equipe para todo o Corpo Docente dentro de uma faculdade específico, incluindo um corpo docente prestado que muda com frequência.
- Uma companhias quer criar uma equipe para cada aéreas (como uma terça-feira tarde contínuas de Chicago para Atlanta) e ter um crew aéreas muda com frequência automaticamente atribuídos ou removidos conforme necessário.

Usar esse recurso, a atualização de membros da equipe de um determinado automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação. Esse procedimento exige o Windows Azure AD Premium P1 licenças e participação na equipe pode ser [atribuído por um administrador proprietário](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) para as propriedades do usuário, qualquer AAD fornecido a que você tem uma conta de administrador e de um inquilino.

Microsoft Teams pode levar alguns minutos até 2 horas para refletir as alterações de associação dinâmica depois que eles entrem em vigor no grupo Office 365 para uma equipe.

> [!NOTE]
> Regras podem definir os membros da equipe, mas não os proprietários de equipe.

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Criando e gerenciando um grupo do Office 365 com participação dinâmica
Enquanto logado como o administrador de locatário, siga as instruções em [um grupo dinâmico de criar e verificar o status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule). Conforme necessário, consulte [regras de participação dinâmicas para grupos do Active Directory do Windows Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Criar uma nova equipe com seu grupo de O365

Agora, reserve um tempo para as alterações de associação entre em vigor e crie uma nova equipe, conforme descrito em [grupos de aprimorar existente Office 365 com as equipes da Microsoft](enhance-office-365-groups.md).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar a participação dinâmica para uma equipe existente

Você também pode levar uma equipe existente e alterá-lo para ter uma associação dinâmica, conforme descrito em [alterar a associação de grupo estático para dinâmico no Windows Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Alterações no comportamento dos clientes

Depois que a associação dinâmica estiver habilitada para uma equipe, os clientes de equipes não são mais permitirá que o gerenciamento de membros da equipe. Opções para adicionar membros, edite as funções de membro, enviar e aprovar solicitações de ingresso e deixar a equipe todos estão ocultas.
