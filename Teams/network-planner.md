---
title: Usar o Planejador de rede para Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: O administrador pode aprender a usar o Planejador de Rede para determinar os requisitos de rede para Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045550"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usar o Planejador de rede para Microsoft Teams

O Planejador de Rede é uma nova ferramenta que está disponível no Teams de administração. Ele pode ser encontrado indo para o **Planejador****de Rede de** >  Planejamento. Em apenas algumas etapas, o Planejador de Rede pode ajudá-lo a determinar e organizar os requisitos de rede para conectar Microsoft Teams usuários em sua organização. Quando você fornece detalhes de sua rede e uso do Teams, o Planejador de Rede calcula seus requisitos de rede para implantar o Teams e o cloud voice nos locais físicos da sua organização.

![Captura de tela do Planejador de rede.](media/network-planner.png)

O planejador de rede permite que você:

- Crie representações de sua organização usando sites e personas recomendadas da Microsoft (funcionários do escritório, funcionários remotos e Teams sistema de sala).

    > [!NOTE]
    > As personas recomendadas foram desenvolvidas com base em dados Teams cenários de melhor uso e padrões de uso típicos. No entanto, você pode criar até três personas personalizadas, além das três personas recomendadas.

- Gere relatórios e calcule os requisitos de largura de banda para Teams uso.

Para usar o Planejador de rede, você deve ser um administrador global, Teams administrador ou Teams comunicações.

## <a name="create-a-custom-persona"></a>Criar uma persona personalizada

Siga estas etapas para criar uma persona personalizada:

1. Vá para o Planejador de rede no centro Microsoft Teams administrador.

2. Na guia **Personas** , clique **em + Persona personalizada**. 

3. No painel **Nova persona** personalizada, adicione um nome e uma descrição para a nova persona.

4. Selecione as permissões que essa persona usará dentro da organização.

5. Clique em **Salvar**.

## <a name="build-your-plan"></a>Criar seu plano

Siga estas etapas para começar a criar seu plano de rede:

1. Vá para o Planejador de rede no centro Microsoft Teams administrador.

2. Na guia **Plano de Rede** , clique **em Adicionar um plano de rede**.

3. Insira um nome e uma descrição para seu plano de rede. O plano de rede aparecerá na lista de planos disponíveis.

4. Clique no nome do plano para selecionar o novo plano.

5. Adicione sites para criar uma representação da configuração de rede da sua organização.

    Dependendo da rede da sua organização, talvez você queira usar sites para representar um prédio, um local de escritório ou outra coisa. Os sites podem ser conectados por uma WAN para permitir o compartilhamento de conexões de Internet e/ou PSTN. Para obter melhores resultados, crie sites com conexões locais antes de criar sites que se conectam remotamente à Internet ou PSTN.

    Para criar um site:

    1. Adicione um nome e uma descrição ao seu site.

    2. Em **Configurações de rede**, adicione o número de usuários de rede nesse site (obrigatório).

    3. Adicione detalhes de rede: habilitada para WAN, capacidade wan, saída da Internet (**Local** ou **Remota) e** saída PSTN (nenhuma, local ou remota).

      > [!NOTE]
      > Você deve adicionar números de capacidade de WAN e Internet para ver recomendações de largura de banda específicas ao gerar um relatório.

    4. Clique em **Salvar**.

## <a name="create-a-report"></a>Criar um relatório

Depois de adicionar todos os sites, você pode criar um relatório, da seguinte maneira.

1. Na guia **Relatórios** , clique **em Iniciar um relatório**.

2. Para cada site criado, distribua o número de usuários entre as personas disponíveis. Se você usar as personas recomendadas da Microsoft, o número será distribuído automaticamente (80% de trabalho do office e 20% de trabalho remoto).

3. Depois de concluir a distribuição, clique em **Gerar relatório**.

    O relatório gerado mostrará os requisitos de largura de banda em várias exibições diferentes para que você possa entender claramente a saída:
    - Uma tabela com cálculos individuais exibirá os requisitos de largura de banda para cada atividade permitida.
    - Uma exibição adicional mostrará as necessidades gerais de largura de banda com recomendações.

4. Clique em **Salvar**. Seu relatório estará disponível na lista de relatórios para exibição posterior.

## <a name="example-scenario"></a>Exemplo de cenário

Para obter um exemplo de como usar o Planejador de rede para configurar um plano de rede e gerar um relatório usando estas etapas, baixe o planejador de rede How-To PowerPoint [conjunto](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (somente em inglês).
