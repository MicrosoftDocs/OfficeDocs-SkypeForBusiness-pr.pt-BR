---
title: Pacotes de política do Teams para assistência médica
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
description: Saiba como usar e gerenciar pacotes de política do Teams para sua organização de saúde.
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812851"
---
# <a name="teams-policy-packages-for-healthcare"></a>Pacotes de política do Teams para assistência médica

## <a name="overview"></a>Visão Geral

Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários que têm funções semelhantes em sua organização. Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas. Você pode personalizar as configurações das políticas no pacote para atender às necessidades dos usuários. Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obterão as configurações atualizadas. Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

Pacotes de política pré-definem políticas para o seguinte, dependendo do pacote:

- Mensagens
- Reuniões
- Chamadas
- Configuração do aplicativo
- Eventos ao vivo

Atualmente, o Teams inclui os seguintes pacotes de política de saúde.

|Nome do pacote no centro de administração do Microsoft Teams|Melhor usado para|Descrição |
|---------|---------|---------|
|Profissional da assistência médica  |Funcionários médicos em sua organização de saúde  |Cria um conjunto de políticas e configurações de política que dão aos funcionários médicos, como residentes registrados, oficiais de carga, funcionários sociais, acesso total a chats, chamada, gerenciamento de turnos e reuniões. |
|Profissional de informações de saúde  |Profissionais de informações em sua organização de saúde |Cria um conjunto de políticas e configurações de política que dão aos profissionais de informações, como funcionários de INFORMAÇÕES, equipe de informações, funcionários financeiros e responsáveis pela conformidade, acesso total a chats, chamada e reuniões.|
|Sala do paciente de saúde  |Dispositivos de sala de pacientes|Cria um conjunto de políticas e configurações de política que se aplicam a salas de pacientes em sua organização de saúde.|

![Captura de tela de pacotes de políticas de saúde](media/policy-packages-healthcare.png)

Cada política individual recebe o nome do pacote de política para que você possa identificar facilmente as políticas vinculadas a um pacote de política. Por exemplo, quando você atribui o pacote de política de trabalhador médicos médicos aos trabalhadores em sua organização, uma política chamada Healthcare_ClinicalWorker é criada para cada política no pacote.

![Captura de tela de políticas no pacote de trabalho médicos médicos](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>Começar a trabalhar com pacotes de política

Para começar a trabalhar com pacotes de política de saúde, no hub de integração do Centro de Administração da Microsoft, selecione **Assistência** Médica e, em seguida, selecione Atribuir configurações de **política por função.** Quando estiver pronto para começar, decida a quais pacotes de política você gostaria de atribuir indivíduos em sua organização.

Selecione **Exibir detalhes da política** para saber mais sobre as políticas específicas em um pacote e suas respectivas configurações. Eles [podem ser personalizados após](manage-policy-packages.md#customize-policies-in-a-policy-package) a atribuição no Centro de Administração do Teams.

Escolha um ou vários pacotes para atribuir e clique em **Next**. Você pode pesquisar e adicionar pessoas ao pacote de política mais adequado para sua função. Um indivíduo não pode ser atribuído a mais de um pacote de política ao mesmo tempo.

Depois de adicionar pessoas ao pacote de política correto, **Concluir** finaliza suas seleções. Você pode continuar a personalizar e gerenciar pacotes de política no centro de administração do Microsoft Teams.

## <a name="manage-policy-packages"></a>Gerenciar pacotes de política

### <a name="view"></a>Exibir

Exibir as configurações de cada política em um pacote de política antes de atribuir um pacote. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para pacotes de **política,** selecione o nome do pacote e selecione o nome da política.

Decida se os valores predefinidos são apropriados para a sua organização ou se você precisa personalizá-los para serem mais restritivos ou leniente com base nas necessidades da sua organização.

### <a name="customize"></a>Personalizar

Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização. As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote. Para editar as configurações de uma política em um pacote de política, na navegação à esquerda do centro de administração do Microsoft Teams, vá para pacotes de **política,** selecione o pacote de política, selecione o nome da política que você deseja editar e selecione **Editar**.

Lembre-se de que você também pode alterar as configurações das políticas em um pacote após atribuir o pacote de política. Para saber mais, confira [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package).

### <a name="assign"></a>Atribuir

Atribua o pacote de política aos usuários. Se um usuário tiver uma política atribuída e, em seguida, você atribuir uma política diferente, a atribuição mais recente terá prioridade.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Atribuir um pacote de política a um ou vários usuários

Para atribuir um pacote de política a um ou vários usuários, na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Pacotes de política** e, em seguida, selecione **Gerenciar usuários**.  

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

Para saber mais, confira [Atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).

Se um usuário tiver uma política atribuída e, em seguida, você atribuir uma política diferente, a atribuição mais recente terá prioridade.

#### <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

**Este recurso está na visualização particular**

As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas. Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Para saber mais, confira [Atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Atribuir um pacote de política a um conjunto grande (lote) de usuários

Use a tarefa de pacote de política de lote para atribuir um pacote de política a grandes conjuntos de usuários por vez. Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.

Um lote pode conter até 5.000 usuários. Você pode especificar os usuários por ID do objeto, UPN, endereço SIP ou endereço de email. Para saber mais, confira [Atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar pacotes de política em equipes](manage-policy-packages.md)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)
