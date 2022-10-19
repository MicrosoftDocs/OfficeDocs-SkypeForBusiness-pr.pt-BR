---
title: Planejar as Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Teams_ITAdmin_Rooms
- highpri
description: Este artigo explica as considerações de planejamento relevantes para implantar Salas do Microsoft Teams, a próxima geração de Sistemas de Salas do Skype.
ms.openlocfilehash: 0e6e3d53928a1a28572a8ea0a038ea772c934e7b
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584442"
---
# <a name="plan-microsoft-teams-rooms"></a>Planejar Salas do Microsoft Teams

Este artigo apresenta uma abordagem de ponta a ponta para planejar, entregar e operar Salas do Microsoft Teams como parte de sua estratégia geral de reunião e sala de conferência.

Você encontrará informações de planejamento abaixo que abrangem a abordagem recomendada e as principais decisões que você precisa tomar, com links para dar suporte a informações técnicas. Recomendamos que você examine as seções Planejar, Implantar e Gerenciar, mesmo que já esteja totalmente implantado.

## <a name="overview-of-microsoft-teams-rooms"></a>Visão geral do Salas do Microsoft Teams

Salas do Microsoft Teams oferece uma experiência de reunião completa que leva vídeo, áudio e compartilhamento de conteúdo EM HD para reuniões de todos os tamanhos, desde pequenas áreas de grupo até grandes salas de conferência.

![Um usuário toca em um Salas do Teams, com uma exibição em segundo plano.](../media/room-systems-image1.jpg "Um usuário toca em um console Salas do Teams, com uma exibição em segundo plano")

[Salas do Microsoft Teams ajuda é](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) um ótimo recurso para saber mais sobre Salas do Microsoft Teams e como ele pode adicionar valor como parte de sua implantação.

## <a name="microsoft-teams-rooms-components"></a>Salas do Microsoft Teams componentes

Salas do Microsoft Teams inclui os seguintes componentes principais para proporcionar uma ótima experiência do usuário:

- Console touchscreen
- Módulo de computação
- Salas do Microsoft Teams aplicativo
- Dispositivos periféricos (câmera, microfone, alto-falante)
- Telas externas (máximo de dois)
- Entrada HDMI

Você pode adquirir esses componentes como pacotes pré-instalados de vários fornecedores ou pode comprar os componentes com suporte individualmente seguindo os requisitos [documentados neste artigo](requirements.md).

## <a name="teams-rooms-licensing"></a>Salas do Teams licenciamento

Cada dispositivo de sala de reunião, como um console Salas do Teams, Surface Hub e painel do Teams, precisa de uma Salas do Teams de reunião. O Teams fornece duas licenças para Salas do Teams: Salas Microsoft Teams Pro e Salas do Microsoft Teams Básico.

Salas Microsoft Teams Pro é ótimo para organizações que têm 25 ou mais dispositivos de sala de reunião ou que desejam as experiências mais abrangentes de gerenciamento de dispositivos e reuniões. As reuniões híbridas do Teams tornam-se mais imersivas com recursos como Linha de frente, Câmera de conteúdo, supressão de ruído da tecnologia de IA e outros recursos disponíveis com Salas Microsoft Teams Pro. Salas do Teams administradores podem gerenciar centralmente todos os seus dispositivos Salas do Teams certificados do Centro de administração do Teams, desde a configuração de políticas de acesso condicional até a análise de telemetria avançada sobre a integridade do dispositivo e a qualidade da reunião.

Salas do Microsoft Teams Basic está disponível para organizações que têm apenas alguns dispositivos de sala de reunião e que precisam apenas da funcionalidade básica de reunião e gerenciamento. Salas do Microsoft Teams Basic permite que você participe de reuniões, compartilhe conteúdo e vídeo ao vivo, ingresse em reuniões do Zoom e webex com o Ingresso Direto de Convidado e execute o inventário e o monitoramento básicos de dispositivos no Centro de administração do Teams.

Antes de usar um dispositivo de sala de reunião, você precisa atribuir uma licença a ele. Para obter mais informações, [consulte Salas do Microsoft Teams licenças](rooms-licensing.md).

[!INCLUDE [mtr-user-licensing](../includes/mtr-user-licensing.md)]

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![decidir a implantação.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você implantará Salas do Microsoft Teams em sua organização? </li><li>Como você adquirirá seus Salas do Microsoft Teams sistemas?</li></ul> |
| ![identificar atividades.](../media/audio_conferencing_image9.png)<br/>Próximas etapas | <ul><li>Identifique quem realizará as principais atividades em toda a implantação.</li><li>Examine as salas de reunião que você tem (e planeje configurar) para entender onde deseja implantar Salas do Microsoft Teams e os dispositivos periféricos que seriam apropriados para o tamanho da sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quem realizará as principais atividades em toda a implantação

Use a abordagem ilustrada abaixo para orientar você em sua implantação e personalizar as saídas de exemplo fornecidas conforme necessário para sua organização.

Comece compreendendo quais salas de conferência você tem e imaginando o que funcionaria melhor para você no futuro e, em seguida, percorrer a seleção e a aquisição do equipamento necessário, preparar seus sites, configurar e implantar seu serviço, gerenciar alterações e adoção do usuário e desenvolver operações e procedimentos de manutenção.

![Comece compreendendo o que você tem e imaginando o que funcionaria melhor para você e, em seguida, passar pela seleção e aquisição do equipamento de que precisa, preparar seus sites, configurar e implantar seu serviço, gerenciar alterações e adoção do usuário e desenvolver operações e procedimentos de manutenção.](../media/room-systems-image2.png "Comece compreendendo o que você tem e imaginando o que funcionaria melhor para você e, em seguida, passar pela seleção e aquisição do equipamento de que precisa, preparar seus sites, configurar e implantar seu serviço, gerenciar alterações e adoção do usuário e desenvolver operações e procedimentos de manutenção.")

Talvez seja necessário coordenar essas atividades em várias equipes. Fornecemos uma visão de alto nível das principais atividades que você deve abordar e também sugestões para as equipes que normalmente estão envolvidas na implantação e gerenciamento de sistemas de salas de conferência, para ajudá-lo a decidir com quem você precisa trabalhar.

| Tarefa                       | Quem pode realizar a tarefa           | Atribuído a | Links para este conteúdo |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salas de inventário            | Equipe de Instalações/AV/Equipe de Projeto de TI |             | [Inventário de sala e planejamento de funcionalidades](#room-inventory-and-capability-planning) |
| Recursos do plano          | Equipe de Projeto de TI                        |             | [Inventário de sala e planejamento de funcionalidades](#room-inventory-and-capability-planning) |
| Seleção de dispositivo           | Equipe de Projeto de TI/Equipe da AV              |             | [Seleção de dispositivo](#device-selection) |
| Aquisição                | Equipe de Projeto de TI/Equipe da AV              |             | [Aquisição](#procurement) |
| Preparação do site             | Equipe de Instalações/AV/Equipe de Projeto de TI |             | [Preparação do site](rooms-deploy.md#site-readiness) |
| Prontidão de serviço          | Equipe de Projeto de TI                        |             | [Prontidão de serviço](rooms-deploy.md#service-readiness) |
| Configuração              | Equipe de Projeto de TI                        |             | [Configuração e implantação](rooms-deploy.md#configuration-and-deployment) |
| Implantação                 | Equipe de Instalações/AV/Equipe de Projeto de TI |             | [Lista de verificação da implantação](console.md#microsoft-teams-rooms-deployment-checklist) |
| Adoção                   | Equipe de Instalações/AV/Equipe de Projeto de TI |             | [Adoção](#plan-for-adoption-and-change-management) |
| Manutenção e operações | Equipe av/equipe de projeto de TI              |             | [Visão geral do gerenciamento](rooms-manage.md) |

## <a name="room-inventory-and-capability-planning"></a>Inventário de sala e planejamento de funcionalidades

A primeira etapa é inventariar os espaços de reunião e as salas de conferência existentes da sua organização para entender o ambiente, o tamanho da sala, o layout e a finalidade. Em seguida, você pode identificar os recursos que deseja que cada sala tenha, como câmeras inteligentes, quadro de comunicações, câmera de conteúdo etc.

Depois de criar um inventário dos equipamentos e funcionalidades em cada sala existente, seus requisitos para essa sala são alimentados em seu planejamento de seleção de dispositivo para criar uma solução de conferência avançada. As modalidades (áudio, vídeo) necessárias para cada sala, além do tamanho e da finalidade da sala, desempenham um papel importante na decisão de qual solução é mais apropriada para cada sala.

Como parte de sua descoberta, é fundamental considerar a acústica e o layout da sala. Por exemplo, verifique se as cadeiras na sala não bloquearão a exibição da câmera. Verifique se a sala não tem eco excessivo ou ar-condicionado barulhento e se ela tem energia suficiente para as telas e Salas do Microsoft Teams. Há muitos fatores a considerar que sua equipe ou parceiro de áudio-visual (AV) poderá aconselhar.

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![salas de deplyment.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Examine as salas no escopo e defina Salas do Microsoft Teams configurações para elas.</li></ul>|

_Exemplo de inventário de sala de reunião/conferência_

| Site      | Nome da sala | Tipo de sala | Número de pessoas | No escopo? | Recursos atuais da sala           | Recursos futuros da sala |
|-----------|-----------|-----------|------------------|-----------|-------------------------------------|--------------------------|
| QG de Londres | Curie     | Média    | 6&ndash;12       | Sim       | Voz                        | 1 tela, áudio e vídeo mais apresentação<br>Acesso PSTN |
| Sydney HQ | Hill      | Grande     | 12&ndash;16      | Sim       | Unidade AV herdada, 1 tela e câmera | 2 telas, áudio e vídeo mais apresentação<br>Acesso PSTN |

## <a name="device-selection"></a>Seleção de dispositivo

Avalie qual Salas do Microsoft Teams solução é a mais adequada para cada sala com base nos recursos futuros que você deseja para a sala. Decida quais dispositivos periféricos AV são os mais adequados, dependendo do tamanho e do layout da sala.

Para obter diretrizes sobre o tipo de dispositivos de sistema e periféricos por tipo de sala e tamanho, consulte [o artigo Salas do Microsoft Teams requisitos](requirements.md).

Com base no fornecedor de sua preferência, use as informações fornecidas no artigo de requisitos para definir o Salas do Microsoft Teams e a configuração de dispositivo periférico com suporte por tipo de sala e use-o como um modelo para sua implantação.

**Dica Pro** – Alguns tipos de sala podem não ser aplicáveis à sua implantação.

| &nbsp; | &nbsp; |
|---|---|
| ![salas no escopo.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão | <ul><li>No inventário, quais tipos de salas estão no escopo da implantação?</li><li>Quais sistemas você implantará para cada tipo de sala?</li></ul> |
| ![coletar material.](../media/audio_conferencing_image9.png)<br/>Próximas etapas | <ul><li>Comece a coletar o principal material operacional para seus sistemas escolhidos e envolva sua equipe de compras.</li></ul> |

_Modelo Salas do Microsoft Teams implantação de exemplo para sua organização_

| Tipo/tamanho da sala     | Número de pessoas | Salas do Microsoft Teams sistema | Dispositivos periféricos | Exibição(s)      |
|--------------------|------------------|------------------------------|--------------------|-----------------|
| Foco 10' por 9'    | 2&ndash;4        |                              |                    |                 |
| Pequeno 16' por 16'   | 4&ndash;6        |                              |                    |                 |
| Média de 18' por 20'  | 6&ndash;12       |                              |                    |                 |
| Grande 15' por 32'   | 12&ndash;16      |                              |                    |                 |

**Dica Pro –** Agora é um ótimo momento para começar a coletar informações sobre Salas do Microsoft Teams solução que você escolheu.

## <a name="procurement"></a>Aquisição

Você pode adquirir o sistema escolhido como um pacote ou uma solução integrada por meio de parceiros de dispositivo.

Você pode adquirir Salas do Microsoft Teams de vários parceiros listados no artigo [de requisitos](requirements.md). Visite os sites dos parceiros para saber mais sobre essas soluções e opções de aquisição.

Dependendo da escala e da abordagem de implantação, você pode decidir ter os dispositivos periféricos Salas do Microsoft Teams e com suporte enviados para um local central para configuração inicial e atribuição. Essa pode ser uma boa abordagem para uma distribuição em etapas em vários sites. Ou você pode optar por enviar os pacotes diretamente para seus sites.

| &nbsp; | &nbsp; |
|---|---|
| ![componentes de remessa.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você enviará os componentes diretamente para um site ou para uma instalação de preparo?</li><li>Quem gerenciará a instalação de preparo (se você decidir usar uma)?</li></ul> |
| ![planejar operações.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Planejar operações.</li><li>Planeje a adoção e o gerenciamento de alterações.</li></ul> |

## <a name="plan-for-operations"></a>Planejar operações

Sua organização deve executar tarefas de monitoramento, administração e gerenciamento continuamente e é fundamental concordar com quem realizará essas tarefas no início da implantação.

Muitas organizações têm uma equipe ou parceiro av que gerencia suas salas de conferência e dispositivos. Ou você pode ter ajuda da Microsoft para gerenciar Salas do Teams usando Salas Microsoft Teams Pro. Decida quem gerenciará os dispositivos Salas do Microsoft Teams no futuro para monitorar o desempenho, bem como implantar atualizações de software e hotfixes.

Considere para qual fila de assistência técnica você roteará chamadas relacionadas Salas do Microsoft Teams e forneça perguntas frequentes para a equipe de assistência técnica para que eles possam entender melhor como usar o Salas do Microsoft Teams e as principais etapas de solução de problemas que podem ser executadas. Um bom ponto de partida para essas perguntas frequentes é a ajuda [do usuário](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e [problemas conhecidos](known-issues.md).

| &nbsp; | &nbsp; |
|---|---|
| ![escolha gerente.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará Salas do Microsoft Teams.</li><li>Decida para qual fila de assistência técnica rotear Salas do Microsoft Teams chamadas relacionadas.</li></ul> |
| ![preparar contas de host.](../media/audio_conferencing_image9.png)<br/>Próximas etapas |<ul><li>Prepare-se para hospedar contas.</li></ul> |

## <a name="plan-for-adoption-and-change-management"></a>Planejar a adoção e o gerenciamento de alterações

Salas do Microsoft Teams sistemas introduzem novos recursos para seus usuários. É importante que você reconheça que isso será uma alteração para seus usuários e você deve garantir que sua campanha de marketing interna identifique os benefícios que o novo sistema terá para seus usuários e os principais pontos de discussão que os clientes potenciais podem usar para discutir com suas equipes.

Considere o agendamento de eventos de apresentação e de aplicação de cartazes em cada site para informar os usuários sobre os novos recursos. Você também pode criar "guias de início rápido" na sala. Considere encontrar um campeão de reuniões em cada site que possa ajudar outras pessoas a se atualizarem e começar a usar os dispositivos.
