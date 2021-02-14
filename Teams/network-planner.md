---
title: Usar o Planejador de rede do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: O administrador pode aprender a usar o Planejador de Rede para determinar os requisitos de rede do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611795"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usar o Planejador de rede do Microsoft Teams

O Planejador de Rede é uma nova ferramenta disponível no Centro de administração do Teams. Ele pode ser encontrado indo para **Planejamento**  >  **do Planejador de Rede.** Em apenas algumas etapas, o Planejador de Rede pode ajudá-lo a determinar e organizar os requisitos de rede para conectar usuários do Microsoft Teams em toda a organização. Quando você fornece os detalhes da rede e o uso do Teams, o Planejador de Rede calcula seus requisitos de rede para implantar o Teams e a voz na nuvem nos locais físicos da sua organização.

![Captura de tela do Planejador de rede](media/network-planner.png)

O planejador de rede permite que você:

- Crie representações da sua organização usando sites e personas recomendadas da Microsoft (funcionários de escritório, trabalhadores remotos e sistema de sala do Teams).

    > [!NOTE]
    > As personas recomendadas foram desenvolvidas com base em dados de cenários de melhor uso do Teams e padrões de uso típicos. No entanto, você pode criar até três personas personalizadas além das três personas recomendadas.

- Gere relatórios e calcule os requisitos de largura de banda para o uso do Teams.

Para usar o Planejador de rede, você deve ser um Administrador Global, Administrador de Serviços do Teams ou Administrador de Comunicações do Teams.

## <a name="create-a-custom-persona"></a>Criar uma persona personalizada

Siga estas etapas para criar uma persona personalizada:

1. Vá para o Planejador de rede no Centro de administração do Microsoft Teams.

2. Na guia **Personas,** clique **em + Persona personalizada.** 

3. No painel **Nova persona** personalizada, adicione um nome e uma descrição para a nova persona.

4. Selecione as permissões que essa persona usará dentro da organização.

5. Clique em **Salvar**.

## <a name="build-your-plan"></a>Criar seu plano

Siga estas etapas para começar a criar seu plano de rede:

1. Vá para o Planejador de rede no Centro de administração do Microsoft Teams.

2. Na guia **Plano de Rede,** clique **em Adicionar um plano de rede.**

3. Insira um nome e uma descrição para seu plano de rede. O plano de rede aparecerá na lista de planos disponíveis.

4. Clique no nome do plano para selecionar o novo plano.

5. Adicione sites para criar uma representação da configuração de rede da sua organização.

    Dependendo da rede da sua organização, talvez você queira usar sites para representar um prédio, um local de escritório ou algo diferente. Os sites podem estar conectados por uma WAN para permitir o compartilhamento de conexões de Internet e/ou PSTN. Para melhores resultados, crie sites com conexões locais antes de criar sites que se conectam remotamente à Internet ou PSTN.

    Para criar um site:

    1. Adicione um nome e uma descrição para o seu site.

    2. Em **Configurações de rede,** adicione o número de usuários de rede nesse site (obrigatório).

    3. Adicione detalhes da rede: habilitado para WAN, capacidade wan, saída da Internet **(Local** ou **Remota)** e saída PSTN (nenhuma, local ou remota).

      > [!NOTE]
      > Você deve adicionar WAN e números de capacidade da Internet para ver recomendações de largura de banda específicas ao gerar um relatório.

    4. Clique em **Salvar**.

## <a name="create-a-report"></a>Criar um relatório

Depois de adicionar todos os sites, você pode criar um relatório, da seguinte forma.

1. Na guia **Relatórios,** clique em **Iniciar um relatório.**

2. Para cada site que você criar, distribua o número de usuários em todas as personas disponíveis. Se você usar as personas recomendadas da Microsoft, o número será distribuído automaticamente (80% de funcionários de escritório e 20% de trabalhadores remotos).

3. Depois de concluir a distribuição, clique em **Gerar relatório.**

    O relatório gerado mostrará os requisitos de largura de banda em várias exibições diferentes para que você possa entender claramente a saída:
    - Uma tabela com cálculos individuais exibirá os requisitos de largura de banda para cada atividade permitida.
    - Um modo de exibição adicional mostrará as necessidades gerais de largura de banda com recomendações.

4. Clique em **Salvar**. Seu relatório estará disponível na lista de relatórios para visualização posterior.

## <a name="example-scenario"></a>Cenário de exemplo

Para ver um exemplo de como usar o Planejador de rede para configurar um plano de rede e gerar um relatório usando estas etapas, baixe o planejador de rede How-To conjunto do [PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (somente em inglês).
