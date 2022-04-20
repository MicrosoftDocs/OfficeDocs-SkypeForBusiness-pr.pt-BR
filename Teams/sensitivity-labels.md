---
title: Rótulos de confidencialidade para Microsoft Teams
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar rótulos de confidencialidade para proteger suas equipes Microsoft Teams.
ms.openlocfilehash: fab5ad4e3be3da5afc6ee373aa6bebe2afae819e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922692"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Rótulos de confidencialidade para Microsoft Teams

[Os rótulos de](/microsoft-365/compliance/sensitivity-labels) confidencialidade Teams administradores para proteger e regular o acesso a conteúdo organizacional confidencial criado durante a colaboração nas equipes. Depois de configurar rótulos de confidencialidade com suas políticas associadas no portal de conformidade do [Microsoft Purview](/microsoft-365/compliance/go-to-the-securitycompliance-center), esses rótulos podem ser aplicados às equipes em sua organização.

Atualmente, não há suporte para rótulos de confidencialidade em equipes de classe para clientes que usam SKUs Teams Education. Para saber mais sobre licenciamento, confira [Microsoft Teams descrição do serviço](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>Qual é a diferença entre rótulos de confidencialidade e Teams classificação?

Os rótulos de confidencialidade são diferentes Teams classificação, também conhecida como classificação de grupo do Azure AD. As classificações são cadeias de caracteres de texto que podem ser associadas a um grupo Microsoft 365, mas não têm nenhuma política real associada a elas. Você usa a classificação como metadados e, em seguida, deve usar outros métodos, como ferramentas internas e scripts, para impor políticas.

O benefício de usar rótulos de confidencialidade é que suas políticas são impostas automaticamente de ponta a ponta por meio de uma combinação da plataforma Grupos do Microsoft 365, do centro de conformidade e Teams serviços. Os rótulos de confidencialidade fornecem suporte avançado à infraestrutura para proteger os dados confidenciais da sua organização e garantir a conformidade com suas políticas ou regulamentos internos.

Se você usa a classificação Teams, consulte a seguinte documentação para obter mais informações e instruções sobre como converter esses valores em rótulos de confidencialidade: classificação de grupo clássico do [Azure AD](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Cenários de exemplo para rótulos de confidencialidade

Cenários de exemplo de como você pode usar rótulos de confidencialidade com Teams em sua organização:

- [Definir o nível de privacidade (público ou privado) para equipes](#set-the-privacy-level-for-teams)
- [Controlar o acesso de convidados às equipes](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Definir o nível de privacidade das equipes

Você pode criar e configurar um rótulo de confidencialidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração de privacidade específica (pública ou privada).

Por exemplo, você cria e publica um rótulo de confidencialidade chamado "Confidencial" que tem a opção de privacidade de rótulo configurada como **Privada**. Como resultado, qualquer equipe criada com esse rótulo deve ser uma equipe privada. 

Quando um usuário cria uma nova equipe e seleciona o rótulo  Confidencial, a única opção de privacidade disponível para o usuário é **Privada**. Outras opções de privacidade, como Pública e em toda a organização, não estão disponíveis para o usuário selecionar:

![Captura de tela do rótulo confidencial de confidencialidade.](media/sensitivity-labels-confidential-example.png)

Da mesma forma, você cria e publica um rótulo de confidencialidade chamado "Geral" que tem a opção de privacidade de rótulo configurada como **Pública**. Quando um usuário cria uma nova equipe, ele só pode criar equipes públicas ou de toda a organização ao selecionar esse rótulo:

![Captura de tela do rótulo de confidencialidade geral.](media/sensitivity-labels-general-example.png)

Quando a equipe é criada, o rótulo de confidencialidade fica visível para os usuários no canto superior direito dos canais da equipe. 

![Captura de tela do rótulo de confidencialidade no canal da equipe.](media/sensitivity-labels-channel.png)

Um proprietário da equipe pode alterar o rótulo de confidencialidade e a configuração de privacidade da equipe a qualquer momento, indo para a equipe e, em seguida, clique **em Editar equipe**.

![Captura de tela do rótulo de confidencialidade nas propriedades da equipe.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controlar o acesso de convidados às equipes

Você pode usar rótulos de confidencialidade para controlar o acesso de convidados às suas equipes. Teams criado com um rótulo que não permite o acesso de convidados só estão disponíveis para usuários em sua organização. Pessoas de fora da sua organização não podem ser adicionadas à equipe.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams de administração

Você pode aplicar rótulos de confidencialidade ao criar ou editar uma equipe no Microsoft Teams de administração. 

Os rótulos de confidencialidade também são visíveis nas propriedades  da equipe e na  coluna Classificação na página Gerenciar equipes do Microsoft Teams de administração.

## <a name="limitations"></a>Limitações

Antes de usar rótulos de confidencialidade para Teams, lembre-se das seguintes limitações:

- **Não há suporte para rótulos de confidencialidade Teams Graph APIs e cmdlets do PowerShell**
    
    Os usuários não poderão especificar rótulos de confidencialidade ao criar equipes diretamente por meio de APIs Teams Graph ou cmdlets Teams PowerShell. No entanto, grupos modernos Graph APIs e cmdlets do PowerShell permitem a criação de grupos com rótulos de confidencialidade. Isso significa que você pode criar grupos com rótulos de confidencialidade usando esses métodos e, em seguida, converter esses grupos em equipes.

- **Suporte para canais privados**
    
    Os canais privados criados em uma equipe herdam o rótulo de confidencialidade aplicado em uma equipe. O mesmo rótulo é aplicado automaticamente no conjunto SharePoint site para o canal privado.
    
    No entanto, se um usuário alterar diretamente o rótulo de confidencialidade em um site SharePoint para um canal privado, essa alteração de rótulo não será refletida no Teams cliente. Nesse cenário, os usuários continuam a ver o rótulo de confidencialidade original aplicado à equipe no cabeçalho do canal privado.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Como criar e configurar rótulos de confidencialidade para Teams

Use as instruções da documentação Microsoft 365 para criar e configurar rótulos de confidencialidade para Teams: 

- [Use rótulos de confidencialidade para proteger o conteúdo Microsoft Teams, Microsoft 365 grupos e SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
