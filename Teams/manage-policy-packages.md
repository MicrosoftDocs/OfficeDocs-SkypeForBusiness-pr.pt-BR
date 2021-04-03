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
ms.openlocfilehash: 125c89505727e4fd4e6c18419b32dc1b99dfb67b
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51583107"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gerenciar pacotes de política no Microsoft Teams

> [!NOTE]
> Um dos recursos discutidos neste artigo, pacotes [de política personalizados](#custom-policy-packages), está atualmente em visualização privada.

Um pacote de política no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários com funções semelhantes em sua organização. Construímos pacotes de política para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários em toda a sua organização.  

Você pode usar os pacotes [de política incluídos no Teams](#policy-packages-included-in-teams) ou criar seus próprios pacotes de política [personalizados](#custom-policy-packages) (em visualização privada).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de tela da página Pacotes de política no centro de administração":::

Você pode personalizar as configurações das políticas em um pacote de política para atender às necessidades de seus usuários. Quando você altera as configurações de políticas em um pacote, todos os usuários atribuídos a esse pacote obterão as configurações atualizadas. Você gerencia pacotes de política usando o Centro de administração do Microsoft Teams ou o PowerShell.

## <a name="what-is-a-policy-package"></a>O que é um pacote de política?

Os pacotes de política permitem que você controle os recursos do Teams que você deseja permitir ou restringir para conjuntos específicos de pessoas em toda a sua organização. Cada pacote de política no Teams é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que suportam as atividades de colaboração e comunicação típicas para essa função.

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
|Educação (estudante de ensino superior)    |Cria um conjunto de políticas e configurações de política que se aplicam aos alunos do ensino superior.|
|Educação (aluno do primário)   |Cria um conjunto de políticas e configurações de política que se aplicam aos alunos primários.|
|Educação (estudante do ensino médio)    |Cria um conjunto de políticas e configurações de política que se aplicam a alunos secundários.         |
|Educação (Professor)    |Cria um conjunto de políticas e configurações de política que se aplicam aos professores.      |
|Educação (professor primário usando aprendizagem remota)    |Cria um conjunto de políticas que se aplicam aos professores primários para maximizar a segurança e a colaboração dos alunos ao usar o aprendizado remoto.      |
|Educação (aluno do ensino fundamental usando o aprendizado remoto)    |Cria um conjunto de políticas que se aplicam aos alunos do ensino fundamental para maximizar a segurança e a colaboração dos alunos ao usarem o aprendizado remoto.      |
|Gerenciador de frontline |Cria um conjunto de políticas e aplica essas configurações aos gerentes de Linha de Frente em sua organização. |
|Trabalhador de linha de frente |Cria um conjunto de políticas e aplica essas configurações aos trabalhadores frontline em sua organização. |
|Profissional clínico da área de saúde  |Cria um conjunto de políticas e configurações de política que dão a funcionários da área de saúde, como enfermeiros registrados, enfermeiros chefe, médicos e assistentes sociais acesso total ao chat, chamadas, gerenciamento de turnos e reuniões. |
|Profissional de informações da área de saúde  |Cria um conjunto de políticas e configurações de política que dão aos operadores de informações na sua organização da área de saúde, como equipe de TI, de informática, equipe financeira e responsáveis pela conformidade acesso total ao chat, chamadas e reuniões.|
|Quartos dos pacientes de saúde  |Cria um conjunto de políticas e configurações de política que se aplicam aos quartos dos pacientes em sua organização de saúde.|
|Usuário de pequenas e médias empresas (Business Voice) |Cria uma política de configuração de aplicativo que inclui os aplicativos para uma experiência de voz comercial.|
|Usuário de pequenas e médias empresas (sem o Business Voice) |Cria uma política de configuração de aplicativo relevante para usuários do Teams de pequeno e médio porte (experiência que não é do Business Voice).
|Oficial de segurança pública   |Cria um conjunto de políticas e configurações de política que se aplicam aos agentes de segurança pública em sua organização.|

> [!NOTE]
> Adicionaremos mais pacotes de política em versões futuras do Teams, portanto, verifique se há informações mais atualizadas.  

Cada política individual recebe o nome do pacote de políticas, para que você possa identificar facilmente políticas vinculadas a um pacote de políticas.
Por exemplo, quando você atribui o pacote de política de Educação (Professor) aos professores em sua escola, uma política chamada Education_Teacher é criada para cada política no pacote.

![Captura de tela do pacote de política educação (professor)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacotes de política personalizados

**Este recurso está na visualização particular**

Pacotes de política personalizados permitem que você empacote seu próprio conjunto de políticas para usuários com funções semelhantes em sua organização. Crie seus próprios pacotes de política adicionando os tipos de política e as políticas de que você precisa.

Para criar um novo pacote de política personalizado:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **Pacotes de política** e clique em **Adicionar**.
    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de tela do botão Adicionar em pacotes de política no centro de administração":::
2. Insira um nome e uma descrição para o pacote.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de tela da adição de um novo pacote de política personalizado":::
3. Selecione os tipos de política e os nomes de política a incluir no pacote.
4. Clique em **Salvar**.

## <a name="how-to-use-policy-packages"></a>Como usar pacotes de política

As estruturas a seguir explicam como usar pacotes de política em sua organização.

![Visão geral de como usar pacotes de política](media/manage-policy-packages-overview.png)

- **[Exibir](#view-the-settings-of-a-policy-in-a-policy-package)**: Exibir as políticas em um pacote de política. Em seguida, exibir as configurações de cada política em um pacote antes de atribuir o pacote. Certifique-se de entender cada configuração. Decida se os valores predefinidos são apropriados para sua organização ou se você precisa alterá-los para que sejam mais restritivos ou tolerantes com base nas necessidades da sua organização.

    Se uma política for excluída, você ainda poderá exibir as configurações, mas não poderá alterar nenhuma configuração. Uma política excluída é re-criada com as configurações predefinida quando você atribui o pacote de política.

- **[Personalizar](#customize-policies-in-a-policy-package)**: personalizar as configurações de políticas no pacote de política para se ajustar às necessidades da sua organização.

- **[Atribuir](#assign-a-policy-package)**: atribuir o pacote de política aos usuários.  

> [!NOTE]
> Você também pode alterar as configurações de políticas em um pacote de política depois de atribuir um pacote. As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote.

Aqui estão as etapas de como exibir, atribuir e personalizar pacotes de política no centro de administração do Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Exibir as configurações de uma política em um pacote de política

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione Pacotes de política **e** selecione um pacote de política clicando à esquerda do nome do pacote.
2. Clique na política que você deseja exibir.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar políticas em um pacote de política

Você pode editar as configurações  de uma política por meio da página Pacotes de Política ou indo diretamente para a página de política no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, faça um dos seguintes:
    - Clique **em Pacotes de** Política e selecione o pacote de política clicando à esquerda do nome do pacote.
    - Clique no tipo de política.  Por exemplo, clique em **Políticas de mensagens.**
2. Selecione a política que você deseja editar. As políticas vinculadas a um pacote de política têm o mesmo nome do pacote de política.
3. Faça as alterações que você deseja e clique em **Salvar**.

### <a name="assign-a-policy-package"></a>Atribuir um pacote de política

#### <a name="assign-a-policy-package-to-one-user"></a>Atribuir um pacote de política a um usuário

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.
2. Na página do usuário, clique **em** Políticas e, ao lado de Pacote **de Política,** clique em **Editar**.
3. No painel **Atribuir pacote de** política, selecione o pacote que você deseja atribuir e clique em **Salvar**.

#### <a name="assign-a-policy-package-to-multiple-users"></a>Atribuir um pacote de política a vários usuários

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para Pacotes de Política **e** selecione o pacote de política que você deseja atribuir clicando à esquerda do nome do pacote.
2. Clique **em Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, clique em **Salvar**.

#### <a name="assign-a-policy-package-to-a-group"></a>Atribua o pacote de política a um grupo.

As atribuições de pacote de política aos grupos permitem atribuir várias políticas a um grupo de usuários, como uma lista de distribuição ou grupo de segurança. As atribuições de política serão propagadas para os membros do grupo, de acordo com as regras de precedência. À medida que os membros forem adicionados ou removidos de um grupo, as atribuições de política herdadas serão atualizadas. Esse método é recomendado para grupos de até 50.000 usuários, mas também funcionará com grupos maiores.

Para saber mais, confira [Atribuir um pacote de política a um grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Atribuir um pacote de política a um conjunto grande (lote) de usuários

Use a tarefa de pacote de política de lote para atribuir um pacote de política a grandes conjuntos de usuários por vez. Use o cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar um lote de usuários e o pacote de política que você deseja atribuir. As atribuições são processadas como uma operação de plano de fundo e uma ID de operação é gerada para cada lote.

Um lote pode conter até 5.000 usuários. Você pode especificar os usuários por ID do objeto, UPN, endereço SIP ou endereço de email. Para saber mais, confira [Atribuir um pacote de política a um lote de usuários](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Solução de problemas

**Você recebe um erro ao atribuir um pacote de política**

Isso pode ocorrer se uma ou mais políticas no pacote não foram criadas ou aplicadas com êxito. Reatribua o pacote de política aos usuários. Repetir a operação normalmente corrige esse problema.

## <a name="related-topics"></a>Tópicos relacionados

[Atribuir pacotes de política](assign-policy-packages.md)

[Pacotes de política do Teams para administradores EDU](policy-packages-edu.md)

[Pacotes de políticas do Teams para a área de saúde](policy-packages-healthcare.md)

[Pacotes de política do Teams para o governo](policy-packages-gov.md)