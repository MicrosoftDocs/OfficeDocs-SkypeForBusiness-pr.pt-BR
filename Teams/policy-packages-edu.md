---
title: Pacotes de política do Microsoft Teams para administradores EDU
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de política no Microsoft Teams.
ms.openlocfilehash: a49ab725ff0042b75afca9b1f9b4d7d9655c34b7
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676249"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>Pacotes de política do Microsoft Teams para administradores EDU

Um pacote de política no Microsoft Teams coleta políticas predefinidas e configurações de política que você pode atribuir a usuários com funções semelhantes em sua instituição. Os pacotes de política simplificam, simplificam e ajudam a fornecer consistência ao gerenciar políticas. Na prática normal, você atribui a cada um dos seus usuários um pacote de política e, conforme necessário, redefina as políticas em cada pacote para atender às necessidades desse grupo de usuários. Quando você atualiza as configurações em um pacote, todos os usuários atribuídos a esse pacote são alterados como uma atualização em massa.

As instituições educacionais em geral têm muitos tipos de usuários com necessidades exclusivas, dependendo parte da idade e do vencimento dos alunos. Por exemplo, talvez você queira conceder acesso total aos educadores e à equipe ao Microsoft Teams, mas deseja limitar os recursos do Microsoft Teams para que os alunos possam incentivar um ambiente de aprendizagem seguro e focado. Você pode usar pacotes de política para personalizar as configurações com base nas necessidades de diferentes cohorts na sua comunidade escolar.

## <a name="what-is-a-policy-package"></a>O que é um pacote de política?

Os pacotes de política permitem que você controle os recursos do Microsoft Teams que permitem ou restringir o uso do Microsoft Teams para conjuntos específicos de pessoas em sua organização. Cada pacote de política é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte a atividades típicas para essa função.

Políticas de predefinição de pacotes de política para:
- Mensagens
- Reuniões
- Configuração do aplicativo
- Chamadas
- Eventos ao vivo

Atualmente, o Microsoft Teams inclui os seguintes pacotes de política:

|Nome do pacote listado no centro de administração do Microsoft Teams |Melhor usado para  |Descrição |
|:--- |:--- |:--- |
|Education_Teacher| Professores e funcionários| Use este conjunto de políticas e configurações de política para conceder aos professores e à equipe dentro da sua organização acesso total a chats, chamadas e reuniões pelo Microsoft Teams. |
|Education_PrimaryStudent | Principais alunos da escola  | Os alunos de ensino mais jovem, de ensino mais antigo dentro da sua instituição podem precisar de mais limites no Microsoft Teams. Use este conjunto de políticas e configurações de política para limitar recursos como criação e gerenciamento de reuniões, gerenciamento de chat e chamadas privadas. |
|Education_SecondaryStudent| Estudantes secundários de ensino antigo | Ensino secundário os alunos antigos dentro da sua instituição podem precisar de mais limites no Microsoft Teams. Use este conjunto de políticas e configurações de política para limitar recursos como criação e gerenciamento de reuniões, gerenciamento de chat e chamadas privadas. |
|Education_HigherEducationStudent | Alunos de ensino mais alto | Os alunos de educação mais alta dentro da sua própria intuição podem precisar de menos limites do que os estudantes mais recentes, mas algumas limitações podem ser recomendadas. Você pode usar esse conjunto de políticas e configurações de política para dar acesso a chats, chamadas e reuniões em sua organização, mas limitar como os alunos usam o Microsoft Teams com participantes externos. |
|||

Cada política individual recebe o nome do pacote de política para que você possa facilmente identificar as políticas vinculadas a um pacote de política. Por exemplo, quando você atribui o pacote de política de Education_Teacher a professores em sua escola, uma política chamada Education_Teacher é criada para cada política do pacote.

![Captura de tela do pacote de política de Education_Teacher](media/policy-packages-education_teacher.png)

> [!NOTE]
> Se você decidir que a equipe de suporte administrativo ou professores precisa de políticas diferentes, você pode redefinir um pacote existente: identifique um pacote que não está usando atualmente e altere as configurações para que sejam apropriados para esse grupo. Talvez seja necessário fazer uma anotação para você mesmo qual grupo tem qual pacote, mas esse é o único obstáculo para redefinir o redirecionamento de um pacote.

## <a name="why-use-policy-packages"></a>Por que usar pacotes de política

Se a sua instituição tem centenas ou até milhares de usuários, você pode estar se perguntando: "por que levar tempo para atribuir um pacote ou outro a todos esses usuários?"

Atribuir pacotes a centenas de usuários é um investimento no período administrativo, sem dúvida. Uma coisa importante sobre os investimentos é que eles pagam ao longo do tempo, em vez de imediatamente.

Em um ambiente educacional, há muitos usuários com funções iguais ou semelhantes. Você gasta menos esforço ao gerenciar a experiência do usuário da mesma maneira. Grupo de pacotes um conjunto de políticas específicas para as várias funções na instituição. Os usuários com a mesma licença, mas funções diferentes, podem ter políticas relevantes atribuídas com base em suas funções, o que é mais eficiente do que ajustar políticas para usuários individuais.

Depois que todos os usuários da instituição estiverem classificados em grupos e os pacotes forem aplicados, o gerenciamento deles a partir de então, é uma questão de alterar as configurações do pacote uma vez para todos os usuários atribuídos ao pacote. Você pode optar por ajustar as políticas em um pacote antes ou depois de atribuir usuários ao pacote.

Consulte [gerenciar pacotes de política no Microsoft Teams](manage-policy-packages.md) para obter orientação passo a passo sobre como atribuir um pacote a um único usuário, atribuir pacotes em massa a até 20 usuários e gerenciar e atualizar as políticas vinculadas a cada pacote.
