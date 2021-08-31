---
title: Teams de política para o governo
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de Teams de política para sua organização governamental.
ms.openlocfilehash: 8f0b998540121e05f4113b298446dffefc832cb5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731980"
---
# <a name="teams-policy-packages-for-government"></a>Teams de política para o governo

> [!NOTE]
> No momento, os pacotes de política não estão disponíveis Microsoft 365 implantações GCC Alta ou DoD.

## <a name="overview"></a>Visão Geral

Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários com funções semelhantes em sua organização. Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas. Você pode personalizar as configurações das políticas no pacote para atender às necessidades dos usuários. Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote têm as configurações atualizadas. Você pode gerenciar pacotes de política usando o Centro de Administração do Microsoft Teams ou o Windows PowerShell.

Pacotes de política pré-definem políticas para o seguinte, dependendo do pacote:

- Mensagens
- Reuniões
- Chamadas
- Configuração do aplicativo
- Eventos ao vivo

Teams atualmente inclui os seguintes pacotes de política para o governo.

|Nome do pacote listado no Centro de Administração do Microsoft Teams|Melhor usado para|Descrição |
|---------|---------|---------|
|Oficial de segurança pública  |Agentes de segurança pública em sua organização governamental  |Cria um conjunto de políticas e configurações de política que se aplicam aos agentes de segurança pública em sua organização. |
|Gerenciador de frontline  |Gerentes de linha de frente em sua organização governamental |Cria um conjunto de políticas e aplica essas configurações aos Gerentes de Linha de Frente em sua organização.|
|Trabalhador de linha de frente  |Trabalhadores de linha de frente em sua organização governamental |Cria um conjunto de políticas e aplica essas configurações aos Trabalhadores de Linha de Frente em sua organização.|

![Captura de tela de pacotes de política de saúde.](media/policy-packages-gov.png)

Cada política individual recebe o nome do pacote de políticas, para que você possa identificar facilmente políticas vinculadas a um pacote de políticas. Por exemplo, quando você atribui o pacote de política de agente de segurança pública aos usuários em sua organização, uma política chamada PublicSafety_Officer é criada para cada política no pacote.

![Captura de tela de políticas no pacote de trabalho da assistência médica.](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Gerenciar pacotes de política

### <a name="view"></a>Exibir

Exibir as configurações de cada política em um pacote de política antes de atribuir um pacote. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, selecione **Pacotes de Política**, selecione o nome do pacote e, em seguida, selecione o nome da política.

Decida se os valores predefinidos são apropriados para a sua organização ou se você precisa personalizá-los para serem mais restritivos ou leniente com base nas necessidades da sua organização.

### <a name="customize"></a>Personalizar

Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização. As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote. Para editar as configurações de uma política em um pacote de política, no centro de administração do Microsoft Teams, selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.

Lembre-se de que você também pode alterar as configurações das políticas em um pacote após atribuir o pacote de política. Para saber mais, confira [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Atribuir

Atribua o pacote de política aos usuários. Se um usuário tiver uma política atribuída e, mais tarde, você atribuir uma política diferente, a atribuição mais recente terá prioridade.

> [!NOTE]
> Cada usuário exigirá o complemento de Comunicações Avançadas para receber uma atribuição de pacote de políticas personalizadas. Para obter mais informações, consulte [Complemento de Comunicações Avançadas para o Microsoft Teams ](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Atribuir um pacote de política a um ou vários usuários

Para atribuir um pacote de política a um ou vários usuários, na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Pacotes de política** e, em seguida, selecione **Gerenciar usuários**.  

![Captura de tela de como atribuir um pacote de política no centro de administração.](media/policy-packages-healthcare-assign.png)

Para saber mais, confira [Atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).

Se um usuário tiver uma política atribuída e, em seguida, você atribuir uma política diferente, a atribuição mais recente terá prioridade.

#### <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

**Este recurso está na visualização particular**

As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas. Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Para saber mais, confira [Atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Atribuir um pacote de política a um conjunto grande (lote) de usuários

Use a tarefa de pacote de política de lote para atribuir um pacote de política a grandes conjuntos de usuários por vez. Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.

Um lote pode conter até 5.000 usuários. Você pode especificar os usuários por ID do objeto, UPN, endereço SIP ou endereço de email. Para saber mais, confira [Atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar pacotes de política em equipes](manage-policy-packages.md)

[Atribuir pacotes de política a usuários e grupos](assign-policy-packages.md)
