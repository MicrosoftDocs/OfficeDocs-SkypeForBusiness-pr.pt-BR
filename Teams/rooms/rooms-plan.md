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
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Este artigo explica as considerações relevantes de planejamento para a implantação de Salas do Microsoft Teams, a próxima geração de Sistemas de Salas do Skype.
ms.openlocfilehash: ccc24aea1a45d2aa75c3b1a5de668b520483c2bd
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662466"
---
# <a name="plan-microsoft-teams-rooms"></a>Planejar salas do Microsoft Teams

Este artigo apresenta uma abordagem de ponta a ponta para planejar, fornecer e operar salas do Microsoft Teams como parte de sua estratégia geral de reuniões e salas de conferência.

Você encontrará informações de planejamento abaixo abrangendo a abordagem recomendada e as principais decisões que você precisa tomar, com links para dar suporte a informações técnicas. Recomendamos que você revise as seções Plano, Implantar e Gerenciar, mesmo que já esteja totalmente implantado.

## <a name="overview-of-microsoft-teams-rooms"></a>Visão geral das Salas do Microsoft Teams

As Salas do Microsoft Teams proporcionam uma experiência completa de reunião que traz vídeo, áudio e compartilhamento de conteúdo EM HD para reuniões de todos os tamanhos, desde pequenas áreas de trabalho até salas de conferência grandes.

![Um console, microfone e tela grande montados em uma parede de sala de conferência ilustram os elementos de um exemplo de configuração de Salas do Microsoft Teams.](../media/room-systems-image1.png "Um console, microfone e tela grande montados em uma parede de sala de conferência ilustram os elementos de um exemplo de configuração de Salas do Microsoft Teams.")

[A ajuda do Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) é um ótimo recurso para saber mais sobre as Salas do Microsoft Teams e como ela pode agregar valor como parte da sua implantação. Além disso, recomendamos assistir a este vídeo [de visão geral.](https://youtu.be/tNey5KZVCl0) 

## <a name="microsoft-teams-rooms-components"></a>Componentes de Salas do Microsoft Teams

As Salas do Microsoft Teams incluem os seguintes componentes principais para proporcionar uma ótima experiência do usuário:

- Painel de controle de tela touch
- Calcular
- Aplicativo Salas do Microsoft Teams
- Dock/eção
- Dispositivos periféricos (câmera, microfone, alto-falante)
- Telas externas (máximo de duas)
- Entrada HDMI

Você pode adquirir esses componentes como pacotes pré-instalados de vários fornecedores ou pode comprar os componentes com suporte individualmente seguindo os requisitos [documentados neste artigo.](requirements.md)

Além da combinação surface pro/dock, você também pode comprar Salas do Microsoft Teams com o painel de controle de tela sensível ao toque, computador, encaixe e principais dispositivos periféricos integrados. 

Normalmente, os pacotes e unidades integradas incluem software pré-instalado, enquanto se você comprar componentes com suporte individualmente para os sistemas Surface Pro, precisará instalar o software. Para obter instruções, consulte [este artigo sobre como instalar o software em dispositivos.](rooms-scale.md) 

Você pode implantar salas do Microsoft Teams com o Microsoft Teams, Skype for Business Online ou implantações híbridas ou locais do Skype for Business.  Consulte a [Atualização de Licenciamento de Sala de Reunião](rooms-licensing.md) do Teams para obter informações sobre as licenças necessárias.

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você implantará as Salas do Microsoft Teams em sua organização? </li><li>Como você adquirirá seus sistemas de Salas do Microsoft Teams , agrupados, como componentes separados ou como uma unidade integrada?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas | <ul><li>Identifique quem realizará as principais atividades em toda a sua implantação.</li><li>Revise as salas de reunião que você tem (e planeje configurar) para entender onde você deseja implantar as Salas do Microsoft Teams e os dispositivos periféricos que seriam apropriados para o tamanho da sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quem realizará as principais atividades em toda a sua implantação

Use a abordagem ilustrada abaixo para orientá-lo em sua implantação e personalizar as saídas de exemplo fornecidas em todos esses artigos, conforme necessário para sua organização.

Comece compreendendo quais salas de conferência você tem e visualizando o que funcionaria melhor para você no futuro e, em seguida, comece selecionando e procurando o equipamento de que precisa, preparando seus sites, configurando e implantando seu serviço, gerenciando mudanças e adoção de usuários e desenvolvendo operações e procedimentos de manutenção.

![Comece compreendendo o que você tem e visualizando o que funcionaria melhor para você e, em seguida, comece selecionando e procingando o equipamento de que precisa, preparando seus sites, configurando e implantando seu serviço, gerenciando mudanças e adoção de usuários e desenvolvendo operações e procedimentos de manutenção.](../media/room-systems-image2.png "Comece compreendendo o que você tem e visualizando o que funcionaria melhor para você e, em seguida, comece selecionando e procingando o equipamento de que precisa, preparando seus sites, configurando e implantando seu serviço, gerenciando mudanças e adoção de usuários e desenvolvendo operações e procedimentos de manutenção.")

Talvez seja necessário coordenar essas atividades em várias equipes. Fornecemos uma visão geral das principais atividades que você deve abranger e também sugestões para as equipes que normalmente estão envolvidas na implantação e no gerenciamento de sistemas de sala de conferência, para ajudá-lo a decidir com quem você precisa trabalhar.

| Tarefas                       | Quem pode realizar a tarefa           | Atribuído a | Links para esse conteúdo |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salas de estoque            | Instalações/ equipe av / equipe de projeto de IT |             | [Planejamento de estoque e recursos de sala](#room-inventory-and-capability-planning)        |
| Recursos do plano          | Equipe de Projeto de IT                        |             | [Planejamento de estoque e recursos de sala](#room-inventory-and-capability-planning)                       |
| Seleção de dispositivo           | Equipe de Projeto de IT/Equipe av              |             | [Seleção de dispositivo](#device-selection)                      |
| Aquisição                | Equipe de Projeto de IT/Equipe av              |             | [Aquisição](#procurement)                      |
| Preparação do site             | Instalações/ equipe av / equipe de projeto de IT |             | [Preparação do site](rooms-deploy.md#site-readiness)                      |
| Prontidão de serviço          | Equipe de Projeto de IT                        |             | [Prontidão de serviço](rooms-deploy.md#service-readiness)                      |
| Configuração              | Equipe de Projeto de IT                        |             | [Configuração e implantação](rooms-deploy.md#configuration-and-deployment)                      |
| Implantação                 | Instalações/ equipe av / equipe de projeto de IT |             | [Lista de verificação da implantação](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adoção                   | Instalações/ equipe av / equipe de projeto de IT |             | [Adoção](#plan-for-adoption-and-change-management)                      |
| Manutenção e operações | Equipe av/equipe de projeto de IT              |             | [Visão geral do gerenciamento](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Planejamento de estoque e recursos de sala

A primeira etapa é fazer inventário das salas de reunião e conferência existentes da sua organização para entender o ambiente, o tamanho da sala, o layout e a finalidade, e identificar os recursos que você deseja que cada sala no escopo tenha no futuro, como quais recursos de colaboração mais avançados serão habilitados na sala. 

Depois de criar um inventário dos equipamentos e recursos em cada sala existente, seus requisitos para essa sala de alimentação no seu dispositivo de seleção planejam criar uma solução de conferência completa. As modalidades (áudio, vídeo) necessárias para cada sala , além do tamanho da sala e da finalidade, desempenham um papel importante na decisão de qual solução é mais apropriada para cada sala. 

Como parte de sua descoberta, é fundamental considerar a acústico e o layout da sala. Por exemplo, verifique se as cadeiras na sala não bloquearão a exibição da câmera. Verifique se a sala não tem eco ou ambiente de ar barulhento em excesso e se ela tem energia suficiente para as telas e salas do Microsoft Teams. Há muitos fatores a considerar que sua equipe ou parceiro audiovisual (AV) poderá orientá-lo. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Quais salas estão no escopo dessa implantação?</li><li>Quais sites estão no escopo da sua implantação?</li><li>Quem realizará o inventário de salas de reunião?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Revise as salas no escopo e defina as configurações de Salas do Microsoft Teams para elas.</li></ul>|

_Exemplo de inventário de sala de reunião/conferência_

| Site  | Nome da sala | Tipo de sala | Número de pessoas  | No escopo? | Recursos atuais da sala       | Recursos futuros da sala     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| London HQ | Curie         | Média        | 6 &ndash; 12                  | Sim          | Voz                        | 1 tela, áudio e vídeo mais apresentação<br>Acesso PSTN |
| Sydney HQ | Hill          | Grande         | 12 &ndash; 16                 | Sim          | Unidade AV herdda, 1 tela e câmera | 2 telas, áudio e vídeo mais apresentação<br>Acesso PSTN |

## <a name="device-selection"></a>Seleção de dispositivo 

Avalie qual solução de Salas do Microsoft Teams é a mais adequada para cada sala com base nos recursos futuros que você deseja para a sala. Decida quais dispositivos periféricos AV são o melhor ajuste, dependendo do tamanho e do layout da sala. 

Para obter orientações sobre o tipo de sistema e dispositivos periféricos por tipo de sala e tamanho, consulte o artigo de requisitos de Salas [do Microsoft Teams.](requirements.md) 

Com base no fornecedor de sua preferência, use as informações fornecidas no artigo de requisitos para definir suas Salas do Microsoft Teams e configuração de dispositivo periférico com suporte por tipo de sala e use-as como um modelo para sua implantação. 

**Dica profissional** : alguns tipos de sala podem não ser aplicáveis à sua implantação.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Em seu inventário, quais tipos de salas estão no escopo da sua implantação?</li><li>Quais sistemas você implantará para cada tipo de sala?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a reunir o material operacional principal para seus sistemas escolhidos e envolva sua equipe de aquisição.</li></ul>|

_Exemplo de modelo de implantação de Salas do Microsoft Teams para sua organização_

| **Tipo/tamanho da sala** | **Número de pessoas**  | **Sistema salas do Microsoft Teams** | **Dispositivos periféricos**  | **Exibição(s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Foco 10' por 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Pequeno 16' por 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| Média 18' por 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| Grande 15' por 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Dica do profissional –** Agora é um ótimo momento para começar a reunir informações sobre a solução de Salas do Microsoft Teams que você escolheu.

## <a name="procurement"></a>Aquisição 

Você pode adquirir seu sistema escolhido como um pacote ou uma solução integrada por meio de parceiros de dispositivo. Você também pode adquirir um encaixe de dispositivo parceiro e preparar sua própria solução de Salas do Microsoft Teams usando um dispositivo Surface Pro e dispositivos _periféricos_ AV existentes e compatíveis. 

Você pode adquirir salas do Microsoft Teams de vários parceiros listados no artigo [de requisitos.](requirements.md) Visite os sites dos parceiros para saber mais sobre essas soluções e opções de aquisição. 

Dependendo da escala e da abordagem de implantação, você pode decidir que as Salas do Microsoft Teams e os dispositivos periféricos compatíveis tenham sido enviados para um local central para configuração inicial e atribuição. Essa pode ser uma boa abordagem para uma aplicação em estágios em vários sites. Ou você pode optar por enviar os pacotes diretamente para seus sites. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você enviará os componentes diretamente para um site ou para uma instalação de preparação?</li><li>Quem gerenciará a instalação de preparação (se você decidir usar uma)?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Planejar operações.</li><li>Planejar a adoção e o gerenciamento de alterações.</li></ul>|

## <a name="plan-for-operations"></a>Planejar operações 

Sua organização deve executar tarefas de monitoramento, administração e gerenciamento continuamente, e é fundamental concordar com quem realizará essas tarefas no início da sua implantação. 

Muitas organizações têm uma equipe av ou um parceiro que gerencia suas salas de conferência e dispositivos. Essa equipe deve estar envolvida em concordar com quem gerenciará os dispositivos de Salas do Microsoft Teams futuramente para monitorar o desempenho e implantar atualizações de software e hotfixes. 

Considere para qual fila de assistência técnica você encaminhará as chamadas relacionadas ao Microsoft Teams Rooms֪ e forneça perguntas frequentes à equipe de assistência técnica para que eles possam entender melhor como usar as Salas do Microsoft Teams e as principais etapas de solução de problemas que podem ser seguidas. Um bom ponto de partida para essas perguntas frequentes é a ajuda [do usuário](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e [problemas conhecidos.](known-issues.md)

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará as Salas do Microsoft Teams.</li><li>Decida para qual fila de serviços de ajuda encaminhar chamadas relacionadas ao Microsoft Teams Rooms.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Preparar-se para hospedar contas. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planejar a adoção e gerenciamento de alterações

Os sistemas de Salas do Microsoft Teams introduzem novos recursos para os usuários. É importante que você reconheça que essa será uma alteração para os usuários, e você deve garantir que sua campanha identifique os benefícios que o novo sistema terá para seus usuários e os principais pontos de discussão que os usuários podem usar para discutir com suas equipes. 

Considere o agendamento de eventos de apresentação e de informações e de cartazes em cada site para informar os usuários sobre os novos recursos. Você também pode criar "guias de início rápido" na sala. Considere encontrar um campeão de reuniões em cada site que possa ajudar outras pessoas a se manterem em dia e começar a usar os dispositivos.
