---
title: Gerenciar pacotes de política em equipes
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar, gerenciar e personalizar pacotes de políticas no Microsoft Teams para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários.
ms.openlocfilehash: 79e9bd09745d5d691abe468acf78f6b1ebf453d1
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69807436"
---
# <a name="managing-policy-packages-in-teams"></a>Gerenciando pacotes de políticas no Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Um pacote de política no Microsoft Teams é um conjunto de políticas e configurações de política predefinidas que você pode atribuir a usuários com funções semelhantes em sua organização. Criamos pacotes de políticas para simplificar, simplificar e ajudar a fornecer consistência ao gerenciar políticas para grupos de usuários em toda a sua organização.  

Você pode usar os [pacotes de política incluídos no Teams](#policy-packages-included-in-teams) ou [criar seus próprios pacotes de política personalizados](#custom-policy-packages).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de tela da página Pacotes de política no centro de administração." lightbox="media/policy-packages-admin-center.png":::

Você pode personalizar as configurações das políticas em um pacote de políticas para atender às necessidades de seus usuários. Quando você altera as configurações de políticas em um pacote, todos os usuários atribuídos a esse pacote obtêm as configurações atualizadas. Você gerencia pacotes de política usando o centro de administração do Microsoft Teams ou o PowerShell.

## <a name="what-is-a-policy-package"></a>O que é um pacote de políticas?

Os pacotes de política permitem controlar os recursos do Teams que você deseja permitir ou restringir para conjuntos específicos de pessoas em toda a sua organização. Cada pacote de política no Teams é projetado em torno de uma função de usuário e inclui políticas predefinidas e configurações de política que dão suporte às atividades de colaboração e comunicação que são típicas para essa função.

Os pacotes de política dão suporte aos seguintes tipos de política do Teams:

- Políticas de mensagens
- Políticas de reunião
- Política de instalação do aplicativo
- Políticas de chamada
- Políticas de eventos ao vivo

## <a name="policy-packages-included-in-teams"></a>Pacotes de política incluídos no Teams

Atualmente, o Teams inclui os seguintes pacotes de política.

| Nome do pacote | Descrição |
|---------|---------|
|Educação (aluno do ensino superior)    |Cria um conjunto de políticas e configurações de política que se aplicam aos alunos do ensino superior.|
|Educação (aluno do ensino fundamental)   |Cria um conjunto de políticas e configurações de política que se aplicam aos alunos primários.|
|Educação (aluno do ensino médio)    |Cria um conjunto de políticas e configurações de política que se aplicam a alunos secundários.         |
|Educação (Professor)    |Cria um conjunto de políticas e configurações de política que se aplicam aos professores.      |
|Educação (professor do ensino fundamental usando aprendizagem remota)    |Cria um conjunto de políticas que se aplicam aos professores primários para maximizar a segurança e a colaboração dos alunos ao usar o aprendizado remoto.      |
|Educação (aluno do ensino fundamental usando aprendizado remoto)    |Cria um conjunto de políticas que se aplicam aos alunos do ensino fundamental para maximizar a segurança e a colaboração dos alunos ao usarem o aprendizado remoto.      |
|Gerente de linha de frente |Cria um conjunto de políticas e aplica essas configurações aos gerentes do Frontline em sua organização. |
|Trabalhador de linha de frente |Cria um conjunto de políticas e aplica essas configurações aos trabalhadores do Frontline em sua organização. |
|Profissional clínico da área de saúde  |Cria um conjunto de políticas e configurações de política que dão a funcionários da área de saúde, como enfermeiros registrados, enfermeiros chefe, médicos e assistentes sociais acesso total ao chat, chamadas, gerenciamento de turnos e reuniões. |
|Profissional de informações da área de saúde  |Cria um conjunto de políticas e configurações de política que dão aos operadores de informações na sua organização da área de saúde, como equipe de TI, de informática, equipe financeira e responsáveis pela conformidade acesso total ao chat, chamadas e reuniões.|
|Quartos dos pacientes de saúde  |Cria um conjunto de políticas e configurações de política que se aplicam aos quartos dos pacientes em sua organização de saúde. |
|Oficial de segurança pública   |Cria um conjunto de políticas e configurações de política que se aplicam aos agentes de segurança pública em sua organização.|
|Usuário de pequenas e médias empresas (Business Voice) |Cria uma política de configuração de aplicativo que inclui os aplicativos para uma experiência de voz de negócios para os usuários.|
|Usuário de pequenas e médias empresas (sem o Business Voice) |Cria uma política de configuração de aplicativo relevante para usuários do Teams de pequenas e médias empresas sem nenhum recurso de voz comercial.

> [!NOTE]
> Adicionaremos mais pacotes de política em versões futuras do Teams, portanto, verifique as informações mais atualizadas.  

Cada política individual recebe o nome do pacote de políticas, para que você possa identificar facilmente políticas vinculadas a um pacote de políticas.
Por exemplo, quando você atribui o pacote de políticas de Educação (Professor) aos professores em sua escola, uma política chamada Education_Teacher é criada para cada política no pacote.

:::image type="content" source="media/teams-policy-packages-education.png" alt-text="Captura de tela do pacote de políticas de Educação (Professor)." lightbox="media/teams-policy-packages-education.png":::

## <a name="custom-policy-packages"></a>Pacotes de política personalizados

> [!NOTE]
> Pacotes de política personalizados exigem Teams Premium.

Pacotes de políticas personalizadas permitem empacotar seu próprio conjunto de políticas para usuários com funções semelhantes em sua organização. Crie seus próprios pacotes de política adicionando os tipos de política e as políticas de que você precisa.

Para criar um novo pacote de política personalizado:

1. No painel esquerdo do centro de administração do Microsoft Teams, selecione **Pacotes de política** e clique em **Adicionar**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de tela do botão Adicionar na página Pacotes de política no centro de administração." lightbox="media/policy-packages-add.png":::

2. Insira um nome e uma descrição para seu pacote.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de tela da adição de um novo pacote de política personalizado." lightbox="media/policy-packages-add-custom.png":::

3. Selecione os tipos de política e os nomes da política a serem incluídos no pacote.

4. Selecione **Salvar**.

## <a name="how-to-use-policy-packages"></a>Como usar pacotes de política

O tópico a seguir descreve como usar pacotes de políticas em sua organização.

![Visão geral de como usar pacotes de política.](media/manage-policy-packages-overview.png)

- **[Exibição](#view-the-settings-of-a-policy-in-a-policy-package)**: exibir as políticas em um pacote de políticas. Em seguida, exiba as configurações de cada política em um pacote antes de atribuir o pacote. Verifique se você entende cada configuração. Decida se os valores predefinidos são apropriados para sua organização ou se você precisa alterá-los para serem mais restritivos ou tolerantes com base nas necessidades da sua organização.

    Se uma política for excluída, você ainda poderá exibir as configurações, mas não poderá alterar nenhuma configuração. Uma política excluída é recriada com as configurações predefinidas ao atribuir o pacote de política.

- **[Personalizar](#customize-policies-in-a-policy-package)**: personalize as configurações das políticas no pacote de políticas para atender às necessidades da sua organização.

- **[Atribuir: atribua](#assign-a-policy-package)** o pacote de política aos usuários.  

> [!NOTE]
> Você também pode alterar as configurações de políticas em um pacote de política depois de atribuir um pacote. As alterações que você fizer nas configurações da política serão automaticamente aplicadas aos usuários que recebem o pacote.

Aqui estão as etapas de como exibir, atribuir e personalizar pacotes de políticas no centro de administração do Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Exibir as configurações de uma política em um pacote de política

1. No painel esquerdo do centro de administração do Microsoft Teams, selecione **Pacotes de política** e selecione um pacote de política clicando à esquerda do nome do pacote.

2. Selecione a política que você deseja exibir.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar políticas em um pacote de políticas

Você pode editar as configurações de uma política por meio da página **Pacotes de política** ou acessando diretamente a página de política no centro de administração do Microsoft Teams.

1. No painel esquerdo do centro de administração do Microsoft Teams, faça um dos seguintes procedimentos:
    - Selecione **Pacotes de política** e selecione o pacote de política clicando à esquerda do nome do pacote.
    - Selecione o tipo de política.  Por exemplo, clique **em Políticas de mensagens**.

2. Selecione a política que você deseja editar. As políticas vinculadas a um pacote de política têm o mesmo nome do pacote de política.

3. Faça as alterações desejadas e clique em **Salvar**.

### <a name="assign-a-policy-package"></a>Atribuir um pacote de política

Você pode atribuir um pacote de política a um usuário individual, um grupo ou um lote de usuários. Para obter mais informações sobre como atribuir pacotes de política, consulte [Atribuir pacotes de política a usuários e grupos](assign-policy-packages.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir pacotes de política](assign-policy-packages.md)
- [Pacotes de política do Teams para administradores do EDU](policy-packages-edu.md)
- [Pacotes de políticas do Teams para a área de saúde](policy-packages-healthcare.md)
- [Pacotes de política do Teams para o governo](policy-packages-gov.md)
