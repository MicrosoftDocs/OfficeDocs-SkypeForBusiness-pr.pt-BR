---
title: Pacotes de políticas do Teams para funcionários da linha de frente
ms.author: v-lanachin
author: LanaChin
manager: samanro
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
f1.keywords: ''
ms.custom: ''
ms.localizationpriority: high
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft 365 for frontline workers
description: Saiba como usar e gerenciar pacotes de políticas do Teams para funcionários da linha de frente em sua organização.
ms.openlocfilehash: 20f0f926a50a56140bab8d20c9c663e0020ac3c0
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819567"
---
# <a name="teams-policy-packages-for-frontline-workers"></a>Pacotes de políticas do Teams para funcionários da linha de frente

## <a name="overview"></a>Visão Geral

Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários com funções semelhantes em sua organização. Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas.

Você pode personalizar as configurações das políticas no pacote para atender às necessidades dos usuários. Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote têm as configurações atualizadas. Você pode gerenciar pacotes de política usando o Centro de Administração do Microsoft Teams ou o Windows PowerShell.

Pacotes de política pré-definem políticas para o seguinte, dependendo do pacote:

- Mensagens
- Reuniões
- Chamadas
- Configuração do aplicativo
- Eventos ao vivo

O Teams inclui os pacotes de políticas **Gerente de linha de frente** e **Trabalhador de linha de frente**.

|Nome do pacote listado no Centro de Administração do Microsoft Teams|Descrição |
|---------|---------|
|**Gerente de linha de frente** |Cria um conjunto de políticas e aplica essas configurações aos gerentes da linha de frente em sua organização. |
|**Trabalhador de linha de frente**  |Cria um conjunto de políticas e aplica essas configurações aos funcionários da linha de frente em sua organização.|

:::image type="content" source="media/policy-packages-flw.png" alt-text="Captura de tela dos pacotes de políticas da linha de frente." lightbox="media/policy-packages-flw.png":::

Cada política individual recebe o nome do pacote de políticas, para que você possa identificar facilmente políticas vinculadas a um pacote de políticas. Por exemplo, quando você atribui o pacote de políticas Gerente de linha de frente a gerentes de loja em sua organização, uma política chamada Frontline_Manager é criada para cada política no pacote.

:::image type="content" source="media/policy-packages-flw-frontline-manager.png" alt-text="Captura de tela de políticas no pacote de políticas do Gerente de linha de frente." lightbox="media/policy-packages-flw-frontline-manager.png":::

## <a name="manage-policy-packages"></a>Gerenciar pacotes de política

### <a name="view"></a>Exibir

Exibir as configurações de cada política em um pacote de política antes de atribuir um pacote. Na navegação à esquerda do Centro de Administração do Microsoft Teams, selecione **Pacotes de Política**, selecione o nome do pacote e, em seguida, selecione o nome da política.

Decida se os valores predefinidos são apropriados para a sua organização ou se você precisa personalizá-los para serem mais restritivos ou leniente com base nas necessidades da sua organização.

### <a name="customize"></a>Personalizar

Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização. As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote. Para editar as configurações de uma política em um pacote de política, na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Pacotes de política**, selecione o pacote de política, selecione o nome da política que você deseja editar e selecione **Editar**.

Lembre-se de que você também pode alterar as configurações das políticas em um pacote após atribuir o pacote de política. Para saber mais, confira [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Atribuir

Atribua o pacote de política aos usuários. Se um usuário tiver uma política atribuída e, mais tarde, você atribuir uma política diferente, a atribuição mais recente terá prioridade.

> [!NOTE]
> Cada usuário exigirá o complemento de Comunicações Avançadas para receber uma atribuição de pacote de políticas personalizadas. Para obter mais informações, consulte [Complemento de Comunicações Avançadas para o Microsoft Teams ](/microsoftteams/teams-add-on-licensing/advanced-communications).

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Atribuir um pacote de política a um ou vários usuários

Para atribuir um pacote de política a um ou vários usuários, na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Pacotes de política** e, em seguida, selecione **Gerenciar usuários**.  

:::image type="content" source="media/policy-packages-flw-frontline-manager-assign.png" alt-text="Captura de tela de como atribuir um pacote de políticas a um usuário no centro de administração do Teams." lightbox="media/policy-packages-flw-frontline-manager-assign.png":::

Para saber mais, consulte [Atribuir pacotes de políticas a usuários](assign-policy-packages.md#assign-a-policy-package-to-users).

#### <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

A atribuição de pacote de política a grupos permite atribuir várias políticas a um grupo de usuários, como um grupo de segurança ou uma lista de distribuição. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas. Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Para saber mais, confira [Atribuir um pacote de política a um grupo](assign-policy-packages.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Atribuir um pacote de política a um conjunto grande (lote) de usuários

Use a tarefa de pacote de política de lote para atribuir um pacote de política a grandes conjuntos de usuários por vez. Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.

Um lote pode conter até 5.000 usuários. Você pode especificar usuários por seu ID de objeto ou endereço SIP (Protocolo SIP). Para saber mais, confira [Atribuir um pacote de política a um lote de usuários](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar pacotes de política em equipes](manage-policy-packages.md)
- [Atribuir pacotes de políticas a usuários e grupos](assign-policy-packages.md)
