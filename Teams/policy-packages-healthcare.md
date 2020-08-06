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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de política de equipe para sua organização de assistência médica.
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578182"
---
# <a name="teams-policy-packages-for-healthcare"></a>Pacotes de política de equipe para assistência médica

## <a name="overview"></a>Visão geral

Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização. Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas. Você pode personalizar as configurações das políticas do pacote para atender às necessidades dos seus usuários. Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas. Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.

Pacotes de política pré-defina políticas para o seguinte, dependendo do pacote:

- Reuniões
- Eventos ao vivo
- Chamadas
- Mensagens
- Teams
- Configuração do aplicativo

Atualmente, o Microsoft Teams inclui os seguintes pacotes de política de assistência médica.

|Nome do pacote no centro de administração do Microsoft Teams|Melhor usado para|Descrição |
|---------|---------|---------|
|Trabalhador clínico da assistência médica  |Trabalhadores clínicos na sua organização de assistência médica  |Cria um conjunto de políticas e configurações de política que dão a funcionários clínicos, como as mensagens de mão registradas, recarga de mão, médicos e funcionários sociais acesso total a chats, chamadas, gerenciamento de turnos e reuniões. |
|Operador de informações da assistência médica  |Operadores de informações em sua organização de assistência médica |Cria um conjunto de políticas e configurações de política que fornecem aos operadores de informações, como pessoal de ti, pessoal de informática, pessoal de finanças e órgãos de conformidade, acesso total a chats, chamadas e reuniões.|
|Sala de pacientes de assistência médica  |Dispositivos da sala de pacientes|Cria um conjunto de políticas e configurações de política que se aplicam a salas de pacientes em sua organização de assistência médica.|

![Captura de tela dos pacotes de política da assistência médica](media/policy-packages-healthcare.png)

Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política. Por exemplo, quando você atribui o pacote de política do funcionário clínico à assistência médica a clínicos em sua organização, uma política chamada Healthcare_ClinicalWorker é criada para cada política do pacote.

![Captura de tela de políticas no pacote de trabalho clínico da assistência médica](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a>Gerenciar pacotes de política

### <a name="view"></a>View

Exiba as configurações de cada política em um pacote de política antes de atribuir um pacote. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **pacotes de política**, selecione o nome do pacote e, em seguida, selecione o nome da política.

Decida se os valores predefinidos são adequados para sua organização ou se você precisa personalizá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.

### <a name="customize"></a>Personalizar

Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização. Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote. Para editar as configurações de uma política em um pacote de política, no centro de administração do Microsoft Teams, selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.

Lembre-se de que você também pode alterar as configurações de políticas em um pacote após atribuir o pacote de política. Para saber mais, consulte [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Atribuição

Atribua o pacote de política aos usuários. Para atribuir um pacote de política a um ou vários usuários, clique em **gerenciar usuários**. Você também pode usar o PowerShell para atribuir um pacote de política a lotes grandes de usuários. Para ver as etapas sobre como atribuir um pacote de política, consulte [atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-healthcare-assign.png)

Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar pacotes de política em equipes](manage-policy-packages.md)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)
