---
title: Usar o planejador de rede para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: Saiba como usar o planejador de rede para determinar os requisitos de rede do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c05aa9cba7305b755d4e9290467c92cf71244095
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701563"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usar o planejador de rede para o Microsoft Teams

Bem-vindo ao planejador de rede. Em apenas algumas etapas, o planejador de rede pode ajudá-lo a determinar e organizar os requisitos de rede para a conexão de usuários do Microsoft Teams em toda a sua organização. Quando você fornece os detalhes da rede e o uso das equipes, o planejador de rede calcula os requisitos de rede para a implantação de equipes e voz na nuvem nos locais físicos da sua organização.

![Captura de tela do planejador de rede](media/network-planner.png)

O planejador de rede permite que você:

- Crie representações de sua organização usando sites e as pessoas recomendadas da Microsoft (funcionários do Office, funcionários remotos e sistema da sala de equipe).

    > [!NOTE]
    > As pessoas mais recomendadas foram desenvolvidas com base nos dados dos melhores cenários de uso e nos padrões de uso típicos do teams. No entanto, você pode criar até três personas personalizadas, além das três pessoas recomendadas.

- Gere relatórios e calcule requisitos de largura de banda para uso do teams.

Para usar o planejador de rede, você deve ser um administrador global, administrador de serviços do teams ou administrador de comunicações do teams.

## <a name="create-a-custom-persona"></a>Criar uma pessoa personalizada

Siga estas etapas para criar uma pessoa personalizada:

1. Vá para o planejador de rede no centro de administração do Microsoft Teams.

2. Na guia **pessoas** , clique em **+ Personalizar pessoa**. 

3. No painel **novo persona personalizado** , adicione um nome e uma descrição para o novo persona.

4. Selecione as permissões que esta pessoa usará dentro da organização.

5. Clique em **Salvar**.

## <a name="build-your-plan"></a>Crie seu plano

Siga estas etapas para começar a criar seu plano de rede:

1. Vá para o planejador de rede no centro de administração do Microsoft Teams.

2. Na guia **plano de rede** , clique em **Adicionar um plano de rede**.

3. Insira um nome e uma descrição para o plano de rede. O plano de rede será exibido na lista de planos disponíveis.

4. Clique no nome do plano para selecionar o novo plano.

5. Adicione sites para criar uma representação da configuração de rede da sua organização.

    Dependendo da rede da sua organização, talvez você queira usar sites para representar um edifício, um local de escritório ou outra coisa. Os sites podem ser conectados por uma WAN para permitir o compartilhamento de conexões de Internet e/ou PSTN. Para obter melhores resultados, crie sites com conexões locais antes de criar sites que se conectam remotamente à Internet ou à PSTN.

    Para criar um site:

    1. Adicione um nome e uma descrição para o seu site.

    2. Em **configurações de rede**, adicione o número de usuários da rede nesse site (obrigatório).

    3. Adicionar detalhes de rede: habilitados para WAN, capacidade WAN, egresso de Internet (**local** ou **remota**) e egresso PSTN (nenhum, local ou remota).

      > [!NOTE]
      > Você deve adicionar números de capacidade de Internet e WAN para ver recomendações específicas de largura de banda ao gerar um relatório.

    4. Clique em **Salvar**.

## <a name="create-a-report"></a>Criar um relatório

Depois de adicionar todos os sites, você pode criar um relatório da seguinte maneira.

1. Na guia **relatórios** , clique em **Iniciar um relatório**.

2. Para cada site que você criar, distribua o número de usuários nas pessoas disponíveis. Se você usar as pessoas recomendadas pela Microsoft, o número será distribuído automaticamente (80% de trabalho do Office e 20% de trabalho remoto).

3. Depois de concluir a distribuição, clique em **gerar relatório**.

    O relatório gerado mostrará os requisitos de largura de banda em vários modos de exibição diferentes para que você possa entender claramente a saída:
    - Uma tabela com cálculos individuais mostrará requisitos de largura de banda para cada atividade permitida.
    - Um modo de exibição adicional mostrará as necessidades gerais de largura de banda com recomendações.

4. Clique em **Salvar**. Seu relatório estará disponível na lista relatórios para exibição posterior.

## <a name="example-scenario"></a>Cenário de exemplo

Para obter um exemplo de como usar o planejador de rede para configurar um plano de rede e gerar um relatório usando essas etapas, baixe o conjunto do [PowerPoint de instruções](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) do planejador de rede (somente em inglês).
