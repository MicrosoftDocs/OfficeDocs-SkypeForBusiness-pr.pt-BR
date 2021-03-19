---
title: Rótulos de sensibilidade para o Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
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
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar rótulos de sensibilidade para proteger suas equipes no Microsoft Teams.
ms.openlocfilehash: 6929e9c51f35cb4483c81323048b2a1f9ec6243a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875101"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Rótulos de sensibilidade para o Microsoft Teams

[Os rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores do Teams protejam e regularem o acesso a conteúdo organizacional sensível criado durante a colaboração dentro das equipes. Depois de configurar rótulos de sensibilidade com suas políticas associadas no centro de conformidade da [Microsoft,](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)esses rótulos podem ser aplicados às equipes em sua organização.

Atualmente, os rótulos de sensibilidade não têm suporte para clientes que usam SKUs do Teams Education. Para saber mais sobre licenciamento, consulte a descrição [do serviço do Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação do Teams?

Os rótulos de sensibilidade são diferentes dos rótulos de classificação, também conhecidos como classificação de grupo do Azure AD. Rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo do Microsoft 365, mas não têm políticas reais associadas a elas. Você usa rótulos de classificação como metadados e, em seguida, deve usar outros métodos, como ferramentas internas e scripts, para impor políticas.

O benefício de usar rótulos de sensibilidade é que suas políticas são impostas automaticamente de ponta a ponta por meio de uma combinação da plataforma grupos do Microsoft 365, do centro de conformidade e dos serviços do Teams. Os rótulos de sensibilidade oferecem suporte de infraestrutura eficiente para proteger os dados confidenciais da sua organização e garantir a conformidade com suas políticas ou regulamentos internos.

Se você usa rótulos de classificação no momento, consulte a documentação a seguir para obter mais informações e instruções sobre como migrar para rótulos de sensibilidade: Classificação de grupo clássica do [Azure AD](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Cenários de exemplo para rótulos de sensibilidade

Exemplos de cenários de como você pode usar rótulos de sensibilidade com o Teams em sua organização:

- [Definir o nível de privacidade (público ou privado) para equipes](#set-the-privacy-level-for-teams)
- [Controlar o acesso de convidados às equipes](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Definir o nível de privacidade para equipes

Você pode criar e configurar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração de privacidade específica (pública ou privada).

Por exemplo, você cria e publica um rótulo de confidencialidade chamado "Confidencial" que tem a opção de privacidade de rótulo configurada como **Private**. Como resultado, qualquer equipe criada com esse rótulo deve ser uma equipe privada. 

Quando um usuário cria uma nova equipe e seleciona o rótulo **Confidencial,** a única opção de privacidade disponível para o usuário é **Private**. Outras opções de privacidade, como Público e toda a organização, não estão disponíveis para o usuário selecionar:

![Captura de tela do rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

Da mesma forma, você cria e publica um rótulo de sensibilidade chamado "Geral" que tem a opção de privacidade de rótulo configurada como **Pública**. Quando um usuário cria uma nova equipe, ele só pode criar equipes públicas ou em toda a organização quando seleciona esse rótulo:

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

Quando a equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais na equipe. Observe que, se você estiver usando rótulos filho pai hierárquicos, como "Confidencial\Finanças", somente o rótulo pai será showin the channel header.


![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, indo para a equipe e clique em **Editar equipe**.

![Captura de tela do rótulo de sensibilidade nas propriedades da equipe](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controlar o acesso de convidados às equipes

Você pode usar rótulos de sensibilidade para controlar o acesso de convidados às suas equipes. As equipes criadas com um rótulo que não permite o acesso de convidados estão disponíveis apenas para usuários em sua organização. Pessoas de fora da sua organização não podem ser adicionadas à equipe.

## <a name="microsoft-teams-admin-center"></a>Centro de administração do Microsoft Teams

Você pode aplicar rótulos de sensibilidade ao criar ou editar uma equipe no centro de administração do Microsoft Teams. 

Os rótulos de sensibilidade também são  visíveis  nas propriedades da equipe e na coluna Classificação na página Gerenciar equipes do centro de administração do Microsoft Teams.

## <a name="limitations"></a>Limitações

Antes de usar rótulos de sensibilidade para o Teams, esteja ciente das seguintes limitações:

- **Os nomes de rótulo pai não são exibidos para sub-rótulos**
    
    O Teams dá suporte a sub-rótulos, mas não exibe o nome do rótulo pai. Por exemplo, **Confidencial** \\ **Todos os Funcionários** é exibido como **Todos os Funcionários.**

- **Rótulos de sensibilidade não são suportados por APIs do Teams Graph, cmdlets do PowerShell e modelos**
    
    Os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio de APIs do Teams Graph, cmdlets do Teams PowerShell e modelos do Teams.

- **Suporte para canais privados**
    
    Canais privados criados em uma equipe herdam o rótulo de sensibilidade aplicado em uma equipe. O mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.
    
    No entanto, se um usuário alterar diretamente o rótulo de sensibilidade em um site do SharePoint para um canal privado, essa alteração de rótulo não será refletida no cliente do Teams. Nesse cenário, os usuários continuam a ver o rótulo de sensibilidade original aplicado à equipe no header de canal privado.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Como criar e configurar rótulos de sensibilidade para o Teams

Use as instruções da documentação do Microsoft 365 para criar e configurar rótulos de sensibilidade para o Teams: 

- [Use rótulos de sensibilidade para proteger conteúdo no Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
