---
title: Rótulos de sensibilidade do Microsoft Teams
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
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937523"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Rótulos de sensibilidade do Microsoft Teams

Os [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores de equipe protejam e regulassem o acesso a conteúdos organizacionais confidenciais criados durante a colaboração no Microsoft Teams. Depois de configurar os rótulos de sensibilidade com suas políticas associadas no [centro de conformidade da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), esses rótulos podem ser aplicados às equipes em sua organização.

No momento, os rótulos de sensibilidade não são aceitos para clientes que usam SKUs de educação do teams. Para saber mais sobre licenciamento, consulte [Descrição do serviço Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação de equipes?

Rótulos de sensibilidade são diferentes dos rótulos de classificação, também conhecidos como classificação do Azure AD Group. Os rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo do Microsoft 365, mas não têm políticas reais associadas a eles. Você usa rótulos de classificação como metadados e deve usar outros métodos, como ferramentas internas e scripts, para impor políticas.

A vantagem de usar rótulos de sensibilidade é que suas políticas sejam automaticamente impostas de ponta a ponta por meio de uma combinação da plataforma de grupos do Microsoft 365, do centro de conformidade e dos serviços do teams. Os rótulos de sensibilidade fornecem suporte avançado à infra-estrutura para proteger os dados confidenciais da sua organização e garantir a conformidade com suas políticas internas ou normas.

Se você usa rótulos de classificação no momento, confira a documentação a seguir para obter mais informações e instruções sobre como migrá-los para rótulos de sensibilidade: [classificação clássica do Azure ad Group](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Cenários de exemplo para rótulos de sensibilidade

Exemplos de cenários sobre como você pode usar rótulos de sensibilidade com o Teams em sua organização:

- [Definir o nível de privacidade (público ou particular) para o Teams](#set-the-privacy-level-for-teams)
- [Controlar o acesso de convidados às equipes](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Definir o nível de privacidade para Teams

Você pode criar e configurar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite aos usuários criar equipes com uma configuração específica de privacidade (pública ou particular).

Por exemplo, você cria e publica um rótulo de sensibilidade chamado "confidencial" que tem a opção de privacidade de rótulo configurada como **particular**. Como resultado, qualquer equipe criada com esse rótulo deve ser uma equipe privada. 

Quando um usuário cria uma nova equipe e seleciona o rótulo **confidencial** , a única opção de privacidade que está disponível para o usuário é **particular**. Outras opções de privacidade, como público e de toda a organização, não estão disponíveis para que o usuário selecione:

![Captura de tela de rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

Da mesma forma, você cria e publica um rótulo de sensibilidade chamado "geral" com a opção de privacidade de rótulo configurada como **público**. Quando um usuário cria uma nova equipe, ele só pode criar equipes públicas ou de toda a organização quando eles selecionam este rótulo:

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

Quando uma equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, acessando a equipe e, em seguida, clique em **Editar equipe**.

![Captura de tela do rótulo de sensibilidade nas propriedades da equipe](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controlar o acesso de convidados às equipes

Você pode usar rótulos de sensibilidade para controlar o acesso de convidados às suas equipes. As equipes criadas com um rótulo que não permite acesso de convidado só estão disponíveis para os usuários da sua organização. Pessoas de fora da sua organização não podem ser adicionadas à equipe.

## <a name="microsoft-teams-admin-center"></a>Centro de administração do Microsoft Teams

Você pode aplicar rótulos de sensibilidade ao criar ou editar uma equipe no centro de administração do Microsoft Teams. 

Os rótulos de sensibilidade também são visíveis nas propriedades da equipe e na coluna **classificação** na página **gerenciar equipes** do centro de administração do Microsoft Teams.

## <a name="limitations"></a>Relacionadas

Antes de usar rótulos de sensibilidade para o Teams, lembre-se das seguintes limitações:

- **Nomes de rótulos pai não são exibidos para subrótulos**
    
    O Teams dá suporte a subrótulos, mas não exibe o nome do rótulo pai. Por exemplo, **confidencial** \\ **todos os funcionários** são exibidos como **todos os funcionários**.

- **Rótulos de sensibilidade não são compatíveis com APIs do teams Graph, cmdlets e modelos do PowerShell**
    
    Os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio das APIs do teams Graph, cmdlets do PowerShell do Teams e modelos do teams.

- **Suporte a canais privados**
    
    Os canais privados criados em uma equipe herdam o rótulo de sensibilidade aplicado a uma equipe. O mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.
    
    No entanto, se um usuário alterar diretamente o rótulo de sensibilidade em um site do SharePoint para um canal privado, essa alteração de rótulo não será refletida no cliente do teams. Nesse cenário, os usuários continuam a ver o rótulo de sensibilidade original aplicado na equipe no cabeçalho do canal privado.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Como criar e configurar rótulos de sensibilidade para equipes

Use as instruções da documentação do Microsoft 365 para criar e configurar rótulos de sensibilidade para equipes: 

- [Use rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos do microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
