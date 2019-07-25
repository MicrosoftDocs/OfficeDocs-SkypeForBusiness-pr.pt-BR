---
title: Plano para salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: Este artigo explica as considerações de planejamento pertinentes para a implantação de salas do Microsoft Teams, a próxima geração de sistemas de sala do Skype.
ms.openlocfilehash: e5c902b5e4e015bfcc9be3b2d3927365483f3396
ms.sourcegitcommit: a84b8de70149d9688bde64809912dc470377807e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2019
ms.locfileid: "35851542"
---
# <a name="plan-microsoft-teams-rooms"></a>Planejar salas do Microsoft Teams

Este artigo apresenta uma abordagem completa para planejar, fornecer e operar as salas do Microsoft Teams como parte de sua estratégia geral de reunião e sala de conferência.

Você encontrará informações sobre o planejamento abaixo da abordagem recomendada e das principais decisões que precisará fazer, com links para informações técnicas de suporte. Recomendamos que você examine as seções planejar, implantar e gerenciar, mesmo se já estiver totalmente implantado.

## <a name="overview-of-microsoft-teams-rooms"></a>Visão geral dos salas do Microsoft Teams

As salas do Microsoft Teams fornecem uma experiência de reunião completa que traz vídeo em alta definição, áudio e compartilhamento de conteúdo para reuniões de todos os portes, desde pequenas áreas huddle a grandes salas de conferência.

![Um console, um microfone e uma tela grande montada em uma parede da sala de conferência ilustram os elementos de um exemplo de configuração de salas do Microsoft Teams.] (../media/room-systems-image1.png "Um console, um microfone e uma tela grande montada em uma parede da sala de conferência ilustram os elementos de um exemplo de configuração de salas do Microsoft Teams.")

A [ajuda das salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) é um ótimo recurso para saber mais sobre as salas do Microsoft Teams e como elas podem agregar valor como parte da sua implantação. Além disso, recomendamos assistir a este [vídeo de visão geral](https://youtu.be/tNey5KZVCl0). 

## <a name="microsoft-teams-rooms-components"></a>Componentes de salas do Microsoft Teams

As salas do Microsoft Teams incluem os seguintes componentes chave para oferecer uma excelente experiência do usuário:

- Painel de controle com tela touch
- Nós
- Aplicativo salas do Microsoft Teams
- Dock/Extender
- Dispositivos periféricos (câmera, microfone, alto-falante)
- Telas externas (máximo de duas)
- Entrada HDMI

Você pode adquirir esses componentes como pacotes pré-instalados de diversos fornecedores ou pode comprar os componentes compatíveis individualmente, seguindo os [requisitos documentados neste artigo](requirements.md).

Além da combinação do Surface pro/Dock, você também pode comprar salas do Microsoft Teams com o painel de controle de tela sensível ao toque, computação, Dock e dispositivos periféricos de chave integrados. 

Normalmente, os pacotes e as unidades integradas incluem software pré-instalado, e se você comprar componentes compatíveis individualmente para os sistemas Surface pro, será necessário instalar o software. Para obter instruções, confira [Este artigo sobre a instalação de software em dispositivos](room-systems-scale.md). 

Você pode implantar salas do Microsoft Teams com o Microsoft Teams, o Skype for Business online ou implantações locais ou do Skype for Business.  Consulte a [atualização](skype-room-systems-v2.md) do licenciamento da sala de reunião do teams para obter informações sobre as licenças necessárias.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você vai implantar salas do Microsoft Teams em sua organização? </li><li>Como você obterá seus sistemas de salas do Microsoft Teams: incluídos em componentes separados ou como uma unidade integrada?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas | <ul><li>Identifique quem realizará as principais atividades em toda a sua implantação.</li><li>Examine as salas de reunião que você tem (e planeje configurar) para compreender onde deseja implantar as salas do Microsoft Teams e os dispositivos periféricos que seriam apropriados para o tamanho da sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identifique quem realizará as principais atividades em toda a sua implantação

Use a abordagem ilustrada abaixo para orientá-lo na sua implantação e personalize as amostras de saídas fornecidas em todos esses artigos, conforme necessário para a sua organização.

Comece a entender quais salas de conferência você tem e que concepção o que funciona melhor para você no futuro e, em seguida, percorra a seleção e procuring o equipamento que você precisa, preparando seus sites, Configurando e implantando o serviço, gerenciando mudanças e adoção do usuário e desenvolvimento de operações e procedimentos de manutenção.

![Comece a entender o que você tem e que o que funciona melhor para você e, em seguida, percorra a seleção e procuring o equipamento necessário, preparando seus sites, Configurando e implantando o serviço, gerenciando alterações e adoção do usuário e desenvolvimento de operações e procedimentos de manutenção.] (../media/room-systems-image2.png "Comece a entender o que você tem e que o que funciona melhor para você e, em seguida, percorra a seleção e procuring o equipamento necessário, preparando seus sites, Configurando e implantando o serviço, gerenciando alterações e adoção do usuário e desenvolvimento de operações e procedimentos de manutenção.")

Talvez seja necessário coordenar essas atividades em várias equipes. Oferecemos uma exibição de alto nível das principais atividades que você deve abranger e também sugestões para as equipes que normalmente estão envolvidas na implantação e gerenciamento de sistemas de sala de conferência, para ajudar você a decidir com quem precisa trabalhar.

| Tarefa                       | Quem pode empreender a tarefa           | Atribuídas a | Links para este conteúdo |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salas de estoque            | Equipe de recursos/equipe de projeto de ti/equipe de AV |             | [Planejamento da sala e planejamento de recursos](#room-inventory-and-capability-planning)        |
| Recursos de plano          | Equipe de projeto de ti                        |             | [Planejamento da sala e planejamento de recursos](#room-inventory-and-capability-planning)                       |
| Seleção de dispositivo           | Equipe de projetos de ti/equipe de AV              |             | [Seleção de dispositivo](#device-selection)                      |
| Aquisições                | Equipe de projetos de ti/equipe de AV              |             | [Aquisições](#procurement)                      |
| Preparação do site             | Equipe de recursos/equipe de projeto de ti/equipe de AV |             | [Preparação do site](room-systems-v2.md#site-readiness)                      |
| Prontidão de serviço          | Equipe de projeto de ti                        |             | [Prontidão de serviço](room-systems-v2.md#service-readiness)                      |
| Configuração              | Equipe de projeto de ti                        |             | [Configuração e implantação](room-systems-v2.md#configuration-and-deployment)                      |
| Implantação                 | Equipe de recursos/equipe de projeto de ti/equipe de AV |             | [Lista de verificação da implantação](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adotar                   | Equipe de recursos/equipe de projeto de ti/equipe de AV |             | [Adotar](#plan-for-adoption-and-change-management)                      |
| Manutenção e operações | Equipe de projeto de ti/equipe AV              |             | [Visão geral do gerenciamento](skype-room-systems-v2.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Planejamento da sala e planejamento de recursos

A primeira etapa é inventariar a reunião e as salas de conferência existentes da sua organização para compreender o ambiente, o tamanho da sala, o layout e a finalidade e para identificar os recursos que você deseja que cada sala do escopo tenha no futuro, como o que mais rico os recursos de colaboração serão habilitados na sala. 

Depois de criar um inventário do equipamento e dos recursos em cada sala existente, seus requisitos para essa sala são inseridos em sua seleção de dispositivo, planejando criar uma solução avançada de conferência. As modalidades (áudio, vídeo) necessárias para cada sala — além do tamanho da sala e da finalidade, todas desempenham um papel importante para decidir qual solução é mais adequada para cada sala. 

Como parte da sua descoberta, é fundamental considerar o layout e as acústicas da sala. Por exemplo, verifique se as cadeiras da sala não bloqueiam o modo de exibição de câmera. Verifique se a sala não tem ar para ondas excessivas ou ruidosas e se há energia suficiente para as telas e salas do Microsoft Teams. Há muitos fatores a considerar que sua equipe de áudio (AV) ou parceiro poderá aconselhar. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Quais salas estão em escopo para esta implantação?</li><li>Quais sites estão em escopo para a sua implantação?</li><li>Quem realizará o inventário de salas de reunião?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Examine as salas em escopo e defina as configurações de salas do Microsoft Teams para elas.</li></ul>|

_Exemplo de inventário de sala de reunião/conferência_

| Site  | Nome da sala | Tipo de sala | Número de pessoas  | Em escopo? | Recursos de sala atuais       | Recursos de sala futura     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| HQ de Londres | Curie         | Média        | 6&ndash;12                  | Sim          | Falante                        | 1 tela, áudio e vídeo, além de uma apresentação<br>Acesso PSTN |
| HQ de Sydney | Pico          | Grande         | 12&ndash;16                 | Sim          | Unidade AV herdada, 1 tela e câmera | 2 telas, áudio e vídeo e apresentação<br>Acesso PSTN |

## <a name="device-selection"></a>Seleção de dispositivo 

Avalie qual a solução de salas do Microsoft Teams é a mais adequada para cada sala com base nos recursos futuros que você deseja para a sala. Decidir quais dispositivos periféricos AV são os mais adequados, dependendo do tamanho e do layout da sala. 

Para obter orientação para o tipo de sistema e dispositivos periféricos por tipo e tamanho de sala, consulte o artigo requisitos de sala do [Microsoft Teams](requirements.md) . 

Com base no fornecedor de sua preferência, use as informações fornecidas no artigo de requisitos para definir as salas do Microsoft Teams e a configuração de dispositivo periférico compatível por tipo de sala e use-o como um modelo para sua implantação. 

**Dica de pro** – alguns tipos de sala podem não ser aplicáveis à sua implantação.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Do seu inventário, quais tipos de salas estão no escopo da sua implantação?</li><li>Quais sistemas você vai implantar para cada tipo de sala?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a reunir materiais operacionais importantes para seus sistemas escolhidos e para contratar sua equipe de compras.</li></ul>|

_Exemplo de modelo de implantação de salas do Microsoft Teams para sua organização_

| **Tipo/tamanho da sala** | **Número de pessoas**  | **Sistema de salas do Microsoft Teams** | **Dispositivos periféricos**  | **Exibição (s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Foco 10 ' a 9 '      | 2&ndash;4                   |                                  |                         |                 |
| Pequeno 16 ' por 16 '     | 4&ndash;6                   |                                  |                         |                 |
| Média 18 ' a 20 '    | 6&ndash;12                  |                                  |                         |                 |
| Grande 15 ' por 32 '     | 12&ndash;16                 |                                  |                         |                 |

**Dica de pro –** Agora é um ótimo momento para começar a reunir informações sobre a solução de salas do Microsoft Teams que você escolheu.

## <a name="procurement"></a>Aquisições 

Você pode adquirir seu sistema escolhido como um pacote ou uma solução integrada por meio de parceiros de dispositivo. Você também pode adquirir um Dock Device Dock e preparar sua própria solução de salas do Microsoft Teams usando um dispositivo de Surface pro e dispositivos de periféricos antivírus _compatíveis_ . 

Você pode adquirir salas do Microsoft Teams de vários parceiros que estão listados no [artigo requisitos](requirements.md). Visite os websites dos parceiros para saber mais sobre essas soluções e opções de aquisição. 

Dependendo de sua escala de implantação e abordagem, você pode decidir ter as salas do Microsoft Teams e os dispositivos periféricos com suporte enviados para um local central para configuração e atribuição iniciais. Essa pode ser uma boa abordagem para uma distribuição em estágios em muitos sites. Ou você pode optar por enviar os pacotes diretamente para seus sites. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você enviará os componentes diretamente para um site ou para um recurso de preparação?</li><li>Quem gerenciará o recurso de preparação (se você decidir usá-lo)?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Planejar operações.</li><li>Planeje a adoção e o gerenciamento de alterações.</li></ul>|

## <a name="plan-for-operations"></a>Planejar operações 

Sua organização deve executar tarefas de monitoramento, administração e gerenciamento continuamente, e é fundamental concordar sobre quem realizará essas tarefas em início à sua implantação. 

Muitas organizações têm uma equipe de AV ou um parceiro que gerencia seus dispositivos e salas de conferência. Essa equipe deve estar envolvida para concordar com quem gerenciará os dispositivos de salas do Microsoft Teams que serão encaminhados para monitorar o desempenho e implantar atualizações e hotfixes de software. 

Considere qual fila do helpdesk você direcionará as chamadas relacionadas ao Microsoft Teams Rooms֪ – e forneça uma pergunta frequente à equipe de assistência técnica para que elas possam entender melhor como usar as salas do Microsoft Teams e as principais etapas para solução de problemas que podem ser tomadas. Um bom ponto de partida para esta pergunta frequente é a [ajuda do usuário](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e a [lista de problemas conhecidos](known-issues.md).

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decidir quem vai gerenciar as salas do Microsoft Teams.</li><li>Decidir qual fila do helpdesk você deve direcionar as chamadas relacionadas ao Microsoft Teams.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para contas de host. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planejar a adoção e o gerenciamento de alterações

Os sistemas de salas do Microsoft Teams apresentam novos recursos para seus usuários. É importante que você reconheça que isso será uma mudança para seus usuários, e você deve garantir que a sua campanha identifique os benefícios que o novo sistema terá para seus usuários e os principais pontos de conversa que os líderes podem usar para discutir com suas equipes. 

Considere agendar eventos de mostrar e mostrar eventos e pôster em cada site para informar os usuários sobre os novos recursos. Você também pode criar "guias de início rápido" em sala. " Considere encontrar um especialista em reuniões em cada site que pode ajudar outras pessoas a se familiarizar e começar a usar os dispositivos.
