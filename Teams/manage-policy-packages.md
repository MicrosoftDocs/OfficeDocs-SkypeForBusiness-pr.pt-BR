---
title: Gerenciar pacotes de política em Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar pacotes de política Microsoft Teams simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários.
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341777"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gerenciar pacotes de política em Microsoft Teams

Um pacote de política no Microsoft Teams é uma coleção de políticas predefinidas e configurações de política que você pode atribuir aos usuários que têm funções semelhantes em sua organização. Construímos pacotes de política para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários em toda a sua organização.  

Você pode usar os pacotes [de política incluídos no Teams](#policy-packages-included-in-teams) ou criar seus próprios pacotes de política [personalizados.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de tela da página Pacotes de política no centro de administração":::

Você pode personalizar as configurações das políticas em um pacote de política para atender às necessidades de seus usuários. Quando você altera as configurações de políticas em um pacote, todos os usuários atribuídos a esse pacote obterão as configurações atualizadas. Você gerencia pacotes de política usando o centro de administração Microsoft Teams ou o PowerShell.

> [!NOTE]
> Cada usuário exigirá o complemento Comunicações Avançadas para receber uma atribuição de pacote de política personalizada. Para obter mais informações, consulte [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>O que é um pacote de políticas?

Os pacotes de política permitem que Teams recursos que você deseja permitir ou restringir para conjuntos específicos de pessoas em toda a sua organização. Cada pacote de política no Teams é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que suportam as atividades de colaboração e comunicação típicas para essa função.

Os pacotes de política suportam os seguintes tipos Teams de política:

- Política de mensagens
- Política de reunião
- Política de configuração de aplicativo
- Políticas de chamada
- Política de eventos ao vivo

## <a name="policy-packages-included-in-teams"></a>Pacotes de política incluídos no Teams

Teams atualmente inclui os seguintes pacotes de política.

| Nome do pacote | Descrição |
|---------|---------|
|Education (estudante de ensino superior)    |Cria um conjunto de políticas e configurações de política que se aplicam aos alunos do ensino superior.|
|Educação (aluno primário)   |Cria um conjunto de políticas e configurações de política que se aplicam aos alunos primários.|
|Educação (estudante do ensino médio)    |Cria um conjunto de políticas e configurações de política que se aplicam a alunos secundários.         |
|Educação (Professor)    |Cria um conjunto de políticas e configurações de política que se aplicam aos professores.      |
|Educação (professor primário usando aprendizagem remota)    |Cria um conjunto de políticas que se aplicam aos professores primários para maximizar a segurança e a colaboração dos alunos ao usar o aprendizado remoto.      |
|Educação (aluno do ensino fundamental usando o aprendizado remoto)    |Cria um conjunto de políticas que se aplicam aos alunos primários para maximizar a segurança e a colaboração dos alunos ao usar o aprendizado remoto.      |
|Gerenciador de frontline |Cria um conjunto de políticas e aplica essas configurações aos gerentes de Linha de Frente em sua organização. |
|Trabalhador de linha de frente |Cria um conjunto de políticas e aplica essas configurações aos trabalhadores frontline em sua organização. |
|Trabalhador médico-médico  |Cria um conjunto de políticas e configurações de política que dão aos funcionários médicos, como os funcionários registrados, os técnicos de carga, os médicos e os assistentes sociais, acesso total ao chat, chamada, gerenciamento de turnos e reuniões. |
|Trabalhador de informações de saúde  |Cria um conjunto de políticas e configurações de política que dão aos funcionários de informações, como funcionários de IT, equipe de informática, funcionários financeiros e agentes de conformidade, acesso total a chat, chamada e reuniões.|
|Sala de pacientes de saúde  |Cria um conjunto de políticas e configurações de política que se aplicam às salas de pacientes em sua organização de saúde.|
|Usuário de pequenas e médias empresas (Business Voice) |Cria uma política de configuração de aplicativo que inclui os aplicativos para uma experiência de voz comercial.|
|Usuário de pequenas e médias empresas (sem o Business Voice) |Cria uma política de configuração de aplicativo relevante para uma empresa de pequeno e médio porte Teams usuários (experiência que não é do Business Voice).
|Oficial de segurança pública   |Cria um conjunto de políticas e configurações de política que se aplicam aos agentes de segurança pública em sua organização.|

> [!NOTE]
> Vamos adicionar mais pacotes de política em versões futuras do Teams, portanto, verifique novamente as informações mais atualizadas.  

Cada política individual recebe o nome do pacote de política para que você possa identificar facilmente as políticas vinculadas a um pacote de política.
Por exemplo, quando você atribui o pacote de política de Educação (Professor) aos professores em sua escola, uma política chamada Education_Teacher é criada para cada política no pacote.

![Captura de tela do pacote de política educação (professor)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacotes de política personalizados

**Pacotes de política personalizados ainda não estão disponíveis para o Nuvem da Comunidade Governamental (GCC)**

Pacotes de política personalizados permitem que você empacote seu próprio conjunto de políticas para usuários com funções semelhantes em sua organização. Crie seus próprios pacotes de política adicionando os tipos de política e as políticas de que você precisa.

Para criar um novo pacote de política personalizado:

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Pacotes** de política e clique em **Adicionar**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de tela do botão Adicionar na página Pacotes de política no centro de administração":::

2. Insira um nome e uma descrição para o pacote.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de tela da adição de um novo pacote de política personalizado":::

3. Selecione os tipos de política e os nomes de política a incluir no pacote.

4. Clique em **Salvar**.

## <a name="how-to-use-policy-packages"></a>Como usar pacotes de política

As estruturas a seguir explicam como usar pacotes de política em sua organização.

![Visão geral de como usar pacotes de política](media/manage-policy-packages-overview.png)

- **[Exibir](#view-the-settings-of-a-policy-in-a-policy-package)**: Exibir as políticas em um pacote de política. Em seguida, exibir as configurações de cada política em um pacote antes de atribuir o pacote. Certifique-se de entender cada configuração. Decida se os valores predefinidos são apropriados para sua organização ou se você precisa alterá-los para ser mais restritivo ou tolerante com base nas necessidades da sua organização.

    Se uma política for excluída, você ainda poderá exibir as configurações, mas não poderá alterar nenhuma configuração. Uma política excluída é re-criada com as configurações predefinida quando você atribui o pacote de política.

- **[Personalizar](#customize-policies-in-a-policy-package)**: personalize as configurações de políticas no pacote de política para se ajustar às necessidades da sua organização.

- **[Atribuir](#assign-a-policy-package)**: atribuir o pacote de política aos usuários.  

> [!NOTE]
> Você também pode alterar as configurações de políticas em um pacote de política depois de atribuir um pacote. Todas as alterações feitas nas configurações de política são aplicadas automaticamente aos usuários atribuídos ao pacote.

Aqui estão as etapas de como exibir, atribuir e personalizar pacotes de política no Microsoft Teams de administração.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Exibir as configurações de uma política em um pacote de política

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione Pacotes de política **e** selecione um pacote de política clicando à esquerda do nome do pacote.

2. Clique na política que você deseja exibir.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar políticas em um pacote de política

Você pode editar as configurações  de uma política por meio da página Pacotes de Política ou indo diretamente para a página de política no Microsoft Teams de administração.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, siga um destes procedimentos:
    - Clique **em Pacotes de** Política e selecione o pacote de política clicando à esquerda do nome do pacote.
    - Clique no tipo de política.  Por exemplo, clique em **Políticas de mensagens.**

2. Selecione a política que deseja editar. As políticas vinculadas a um pacote de políticas têm o mesmo nome do pacote de políticas.

3. Faça as alterações que você deseja e clique em **Salvar**.

### <a name="assign-a-policy-package"></a>Atribuir o pacote de política

Você pode atribuir um pacote de política a um usuário individual, a um grupo ou a um lote de usuários. Para obter mais informações sobre como atribuir pacotes de política, consulte Atribuir pacotes [de política a usuários e grupos.](assign-policy-packages.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir pacotes de políticas](assign-policy-packages.md)
- [Teams de política para administradores EDU](policy-packages-edu.md)
- [Teams de política para assistência médica](policy-packages-healthcare.md)
- [Teams de política para o governo](policy-packages-gov.md)
