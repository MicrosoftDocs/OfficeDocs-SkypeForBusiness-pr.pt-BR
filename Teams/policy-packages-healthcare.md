---
title: Pacotes de política de equipe para assistência médica
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Saiba como usar e gerenciar pacotes de política de equipe para sua organização de assistência médica.
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908510"
---
# <a name="teams-policy-packages-for-healthcare"></a>Pacotes de política de equipe para assistência médica

## <a name="overview"></a>Visão geral

Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização. Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas. Você pode personalizar as configurações das políticas do pacote para atender às necessidades dos seus usuários. Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas. Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Pacotes de política pré-defina políticas para o seguinte, dependendo do pacote:

- Mensagens
- Reuniões
- Chamadas
- Configuração do aplicativo
- Eventos ao vivo

Atualmente, o Microsoft Teams inclui os seguintes pacotes de política de assistência médica.

|Nome do pacote no centro de administração do Microsoft Teams|Melhor usado para|Descrição |
|---------|---------|---------|
|Trabalhador clínico da assistência médica  |Trabalhadores clínicos na sua organização de assistência médica  |Cria um conjunto de políticas e configurações de política que dão a funcionários clínicos, como as mensagens de mão registradas, recarga de mão, médicos e funcionários sociais acesso total a chats, chamadas, gerenciamento de turnos e reuniões. |
|Operador de informações da assistência médica  |Operadores de informações em sua organização de assistência médica |Cria um conjunto de políticas e configurações de política que fornecem aos operadores de informações, como pessoal de ti, pessoal de informática, pessoal de finanças e órgãos de conformidade, acesso total a chats, chamadas e reuniões.|
|Sala de pacientes de assistência médica  |Dispositivos da sala de pacientes|Cria um conjunto de políticas e configurações de política que se aplicam a salas de pacientes em sua organização de assistência médica.|

![Captura de tela dos pacotes de política da assistência médica](media/policy-packages-healthcare.png)

Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política. Por exemplo, quando você atribui o pacote de política do funcionário clínico à assistência médica a clínicos em sua organização, uma política chamada Healthcare_ClinicalWorker é criada para cada política do pacote.

![Captura de tela de políticas no pacote de trabalho clínico da assistência médica](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Introdução aos pacotes de política

Para começar a usar os pacotes de política da assistência médica, no Hub de integração do centro de administração do Microsoft, selecione **assistência médica** e escolha **atribuir configurações de política por função**. Quando estiver pronto para começar, decida de quais pacotes de política você gostaria de atribuir indivíduos à sua organização.

Selecione **Exibir detalhes da política** para saber mais sobre as políticas específicas em um pacote e suas respectivas configurações. Eles [podem ser personalizados](manage-policy-packages.md#customize-policies-in-a-policy-package) após a atribuição no centro de administração do teams.

Escolha um ou vários pacotes para atribuir e clique em **Avançar**. Você pode procurar e adicionar pessoas ao pacote de políticas mais adequado para sua função. Um indivíduo não pode ser atribuído a mais de um pacote de política ao mesmo tempo.

Depois de adicionar pessoas ao pacote de política correto, **concluir** finalizará suas seleções. Você pode continuar Personalizando e gerenciando pacotes de política no centro de administração do Microsoft Teams.

## <a name="manage-policy-packages"></a>Gerenciar pacotes de política

### <a name="view"></a>View

Exiba as configurações de cada política em um pacote de política antes de atribuir um pacote. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **pacotes de política** , selecione o nome do pacote e, em seguida, selecione o nome da política.

Decida se os valores predefinidos são adequados para sua organização ou se você precisa personalizá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.

### <a name="customize"></a>Personalizar

Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização. Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote. Para editar as configurações de uma política em um pacote de política, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **pacotes de política** , selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.

Lembre-se de que você também pode alterar as configurações de políticas em um pacote após atribuir o pacote de política. Para saber mais, consulte [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Atribuição

Atribua o pacote de política aos usuários. Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Atribuir um pacote de política a um ou vários usuários

Para atribuir um pacote de política a um ou vários usuários, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **pacotes de política** e selecione **gerenciar usuários**.  

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

Para saber mais, consulte [atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).

Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.

#### <a name="assign-a-policy-package-to-a-group"></a>Atribuir um pacote de política a um grupo

**Este recurso está em visualização particular**

A atribuição de pacote de política para grupos permite que você atribua várias políticas a um grupo de usuários, como um grupo de segurança ou lista de distribuição. A atribuição de política é propagada para os membros do grupo de acordo com as regras de precedência. Conforme os membros são adicionados ou removidos de um grupo, suas atribuições de política herdadas são atualizadas de acordo. Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Para saber mais, consulte [atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Atribuir um pacote de política a um grande conjunto (lote) de usuários

Use a atribuição de pacote de política em lotes para atribuir um pacote de política a grandes conjuntos de usuários por vez. Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação em segundo plano e uma ID de operação é gerada para cada lote.

Um lote pode conter até 5.000 usuários. Você pode especificar os usuários por sua ID de objeto, UPN, endereço SIP ou endereço de email. Para saber mais, consulte [atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar pacotes de política em equipes](manage-policy-packages.md)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)
