---
title: Pacotes de política de equipe para o governo
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
description: Saiba como usar e gerenciar pacotes de política de equipe para sua organização governamental.
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804003"
---
# <a name="teams-policy-packages-for-government"></a>Pacotes de política de equipe para o governo

> [!NOTE]
> Atualmente, os pacotes de política não estão disponíveis nas implantações do Microsoft 365 governo GCC High ou DoD.

## <a name="overview"></a>Visão geral

Um [pacote de política](manage-policy-packages.md) no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização. Os pacotes de políticas simplificam, otimizam e ajudam a fornecer consistência ao gerenciar políticas. Você pode personalizar as configurações das políticas do pacote para atender às necessidades dos seus usuários. Quando você altera as configurações de políticas em um pacote de política, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas. Você pode gerenciar pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.

Pacotes de política pré-defina políticas para o seguinte, dependendo do pacote:

- Mensagens
- Reuniões
- Chamadas
- Configuração do aplicativo
- Eventos ao vivo

Atualmente, o Teams inclui os seguintes pacotes de política para o governo.

|Nome do pacote no centro de administração do Microsoft Teams|Melhor usado para|Descrição |
|---------|---------|---------|
|Diretor de segurança pública  |Diretores de segurança públicos em sua organização governamental  |Cria um conjunto de políticas e configurações de política que se aplicam a órgãos públicos de segurança em sua organização. |
|Gerente da primeira mão  |Gerentes de primeira mão em sua organização governamental |Cria um conjunto de políticas e aplica essas configurações aos gerentes de primeira empresa.|
|Trabalho da primeira  |Trabalhadores de primeira mão em sua organização governamental |Cria um conjunto de políticas e aplica essas configurações aos trabalhos iniciais em sua organização.|

![Captura de tela dos pacotes de política da assistência médica](media/policy-packages-gov.png)

Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas que estão vinculadas a um pacote de política. Por exemplo, quando você atribui o pacote de política do diretor de segurança pública aos usuários em sua organização, uma política chamada PublicSafety_Officer é criada para cada política no pacote.

![Captura de tela de políticas no pacote de trabalho clínico da assistência médica](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>Gerenciar pacotes de política

### <a name="view"></a>View

Exiba as configurações de cada política em um pacote de política antes de atribuir um pacote. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **pacotes de política**, selecione o nome do pacote e, em seguida, selecione o nome da política.

Decida se os valores predefinidos são adequados para sua organização ou se você precisa personalizá-los para serem mais restritivos ou lenient com base nas necessidades da sua organização.

### <a name="customize"></a>Personalizar

Personalize as configurações das políticas no pacote de política, conforme necessário, para atender às necessidades da sua organização. Todas as alterações feitas nas configurações de política são automaticamente aplicadas a usuários atribuídos ao pacote. Para editar as configurações de uma política em um pacote de política, no centro de administração do Microsoft Teams, selecione o pacote de política, selecione o nome da política que você deseja editar e, em seguida, selecione **Editar**.

Lembre-se de que você também pode alterar as configurações de políticas em um pacote após atribuir o pacote de política. Para saber mais, consulte [Personalizar políticas em um pacote de política](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Atribuição

Atribua o pacote de política aos usuários. Para atribuir um pacote de política a um ou vários usuários, clique em **gerenciar usuários**. Você também pode [usar o PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para atribuir um pacote de política a lotes grandes de usuários. 

Para ver as etapas sobre como atribuir um pacote de política usando o centro de administração do Microsoft Teams ou o PowerShell, consulte [atribuir um pacote de política](manage-policy-packages.md#assign-a-policy-package).

![Captura de tela de como atribuir um pacote de política no centro de administração](media/policy-packages-gov-assign.png)

Se um usuário tiver uma política atribuída e depois você atribuir uma política diferente, a atribuição mais recente terá prioridade.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar pacotes de política em equipes](manage-policy-packages.md)

[Atribuir políticas a seus usuários no Teams](assign-policies.md) 
