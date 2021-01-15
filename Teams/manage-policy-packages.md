---
title: Gerenciar pacotes de política no Microsoft Teams
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
description: Saiba como usar e gerenciar pacotes de política no Microsoft Teams para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários.
ms.openlocfilehash: 9718751ea1d34692718b63cbe90ee6e694577c21
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49862584"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gerenciar pacotes de política no Microsoft Teams

> [!NOTE]
> Um dos recursos discutidos neste artigo, pacotes [de](#custom-policy-packages)política personalizados, está atualmente em visualização privada.

Um pacote de política no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários que têm funções semelhantes em sua organização. Nós construímos pacotes de política para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários em toda a organização.  

Você pode usar os pacotes [de política incluídos no Teams](#policy-packages-included-in-teams) ou criar seus próprios pacotes de política [personalizados](#custom-policy-packages) (em visualização privada).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de tela da página Pacotes de política no centro de administração":::

Você pode personalizar as configurações das políticas em um pacote de política para atender às necessidades dos usuários. Quando você altera as configurações de políticas em um pacote, todos os usuários atribuídos a esse pacote obterão as configurações atualizadas. Você gerencia pacotes de política usando o Centro de administração do Microsoft Teams ou o PowerShell.

## <a name="what-is-a-policy-package"></a>O que é um pacote de política?

Os pacotes de política permitem controlar os recursos do Teams que você deseja permitir ou restringir para conjuntos específicos de pessoas em toda a organização. Cada pacote de política no Teams é projetado em torno de uma função de usuário e inclui políticas e configurações de política predefinidas que suportam as atividades de colaboração e comunicação típicas para essa função.

Os pacotes de política suportam os seguintes tipos de política do Teams:

- Políticas de mensagens
- Políticas de reunião
- Política de configuração de aplicativo
- Políticas de chamada
- Políticas de eventos ao vivo

## <a name="policy-packages-included-in-teams"></a>Pacotes de política incluídos no Teams

Atualmente, o Teams inclui os seguintes pacotes de política.

|**Nome do pacote**  |**Descrição** |
|---------|---------|
|Education (aluno do ensino superior)    |Cria um conjunto de políticas e configurações de política que se aplicam a alunos do ensino superior.|
|Educação (Aluno primário)   |Cria um conjunto de políticas e configurações de política que se aplicam aos alunos principais.|
|Education (estudante secundário)    |Cria um conjunto de políticas e configurações de política que se aplicam a alunos secundários.         |
|Educação (Professor)    |Cria um conjunto de políticas e configurações de política que se aplicam aos professores.      |
|Educação (professor primário usando o aprendizado remoto)    |Cria um conjunto de políticas que se aplicam aos professores primários para maximizar a segurança e a colaboração dos alunos ao usar o aprendizado remoto.      |
|Educação (aluno primário usando o aprendizado remoto)    |Cria um conjunto de políticas que se aplicam aos alunos do ensino fundamental para maximizar a segurança e a colaboração dos alunos ao usarem o aprendizado remoto.      |
|Gerenciador de linha de frente |Cria um conjunto de políticas e aplica essas configurações aos gerentes de Fronttline em sua organização. |
|Trabalhador de linha de frente |Cria um conjunto de políticas e aplica essas configurações aos funcionários fronttline em sua organização. |
|Profissional da assistência médica  |Cria um conjunto de políticas e configurações de política que dão aos funcionários médicos, como residentes registrados, oficiais de carga, funcionários sociais, acesso total a chats, chamada, gerenciamento de turnos e reuniões. |
|Profissional de informações de saúde  |Cria um conjunto de políticas e configurações de política que dão aos profissionais de informações, como funcionários de INFORMAÇÕES, equipe de informações, funcionários financeiros e responsáveis pela conformidade, acesso total a chats, chamada e reuniões.|
|Sala do paciente de saúde  |Cria um conjunto de políticas e configurações de política que se aplicam a salas de pacientes em sua organização de saúde.|
|Usuário de pequenas e médias empresas (Business Voice) |Cria uma política de configuração de aplicativo que inclui os aplicativos para uma experiência de voz comercial.|
|Usuário de pequenas e médias empresas (sem o Business Voice) |Cria uma política de configuração de aplicativo relevante para usuários de pequenas e médias empresas do Teams (experiência não Business Voice).
|Diretor de segurança pública   |Cria um conjunto de políticas e configurações de política que se aplicam a agentes de segurança pública em sua organização.|

> [!NOTE]
> Adicionaremos mais pacotes de política em versões futuras do Teams, portanto, verifique se há mais informações atualizadas.  

Cada política individual recebe o nome do pacote de política para que você possa identificar facilmente as políticas vinculadas a um pacote de política.
Por exemplo, quando você atribui o pacote de política de Educação (Professor) aos professores da sua escola, uma política chamada Education_Teacher é criada para cada política no pacote.

![Screenshot of the Education (Teacher) policy package](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacotes de política personalizados

**Este recurso está na visualização particular**

Pacotes de política personalizados permitem que você empacote seu próprio conjunto de políticas para usuários com funções semelhantes em sua organização. Crie seus próprios pacotes de política adicionando os tipos de política e as políticas de que você precisa.

Para criar um novo pacote de política personalizado:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **pacotes de** política e clique em **Adicionar**.
    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot of Add button on Policy packages page in the admin center":::
2. Insira um nome e uma descrição para o pacote.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de tela da adição de um novo pacote de política personalizado":::
3. Selecione os tipos de política e os nomes de política a incluir no pacote.
4. Clique em **Salvar**.

## <a name="how-to-use-policy-packages"></a>Como usar pacotes de política

Os exemplos a seguir explicam como usar pacotes de política em sua organização.

![Visão geral de como usar pacotes de política](media/manage-policy-packages-overview.png)

- **[Exibição](#view-the-settings-of-a-policy-in-a-policy-package)**: Exibir as políticas em um pacote de política. Em seguida, veja as configurações de cada política em um pacote antes de atribuir o pacote. Certifique-se de entender cada configuração. Decida se os valores predefinidos são apropriados para sua organização ou se você precisa alterá-los para ser mais restritivo ou tolerante com base nas necessidades da sua organização.

    Se uma política for excluída, você ainda poderá exibir as configurações, mas não poderá alterar nenhuma configuração. Uma política excluída é re-criada com as configurações predefinidas quando você atribui o pacote de política.

- **[Personalizar](#customize-policies-in-a-policy-package)**: personalize as configurações de políticas no pacote de políticas para se ajustar às necessidades da sua organização.

- **[Assign](#assign-a-policy-package)**: Assign the policy package to users.  

> [!NOTE]
> Você também pode alterar as configurações de políticas em um pacote de política depois de atribuir um pacote. As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote.

Aqui estão as etapas para exibir, atribuir e personalizar pacotes de política no centro de administração do Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Exibir as configurações de uma política em um pacote de política

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione pacotes de política e selecione um pacote de política clicando à esquerda do nome do pacote.
2. Clique na política que você deseja exibir.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar políticas em um pacote de política

Você pode editar as configurações  de uma política por meio da página Pacotes de Política ou indo diretamente para a página de política no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, faça um dos seguintes:
    - Clique **em Pacotes de** Política e selecione o pacote de política clicando à esquerda do nome do pacote.
    - Clique no tipo de política.  Por exemplo, clique em **Políticas de mensagens.**
2. Selecione a política que você deseja editar. As políticas vinculadas a um pacote de política têm o mesmo nome do pacote de política.
3. Faça as alterações que você deseja e clique em **Salvar**.

### <a name="assign-a-policy-package"></a>Atribuir um pacote de política 

#### <a name="assign-a-policy-package-to-one-user"></a>Atribuir um pacote de política a um usuário

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Na página do usuário, clique em **Políticas** e, ao lado do pacote **De política,** clique em **Editar**.
3. No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e clique em **Salvar**.

#### <a name="assign-a-policy-package-to-multiple-users"></a>Atribuir um pacote de política a vários usuários

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para pacotes de política e selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.
2. Clique **em Gerenciar usuários.**
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

**Este recurso está na visualização particular**

As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas. Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Para saber mais, confira [Atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Atribuir um pacote de política a um conjunto grande (lote) de usuários

Use a tarefa de pacote de política de lote para atribuir um pacote de política a grandes conjuntos de usuários por vez. Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.

Um lote pode conter até 5.000 usuários. Você pode especificar os usuários por ID do objeto, UPN, endereço SIP ou endereço de email. Para saber mais, confira [Atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Solução de problemas

**Você recebe um erro ao atribuir um pacote de política**

Isso pode ocorrer se uma ou mais políticas no pacote não foram criadas ou aplicadas com êxito. Reatribua o pacote de política aos usuários. Tentar novamente a operação normalmente corrige esse problema.

## <a name="related-topics"></a>Tópicos relacionados

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)

[Pacotes de política do Teams para administradores EDU](policy-packages-edu.md)

[Pacotes de política do Teams para assistência médica](policy-packages-healthcare.md)

[Pacotes de política do Teams para o governo](policy-packages-gov.md)
