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
description: Este artigo explica as considerações de planejamento relevantes para a implantação de Salas do Microsoft Teams, a próxima geração de Sistemas de Salas do Skype.
ms.openlocfilehash: fae50e076467efdfe69115d967f3d6564ba9266a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726272"
---
# <a name="plan-microsoft-teams-rooms"></a>Planejar salas do Microsoft Teams

Este artigo apresenta uma abordagem de ponta a ponta para planejar, fornecer e operar salas do Microsoft Teams como parte da estratégia geral de reunião e sala de conferência.

Você encontrará informações de planejamento abaixo abordando a abordagem recomendada e as principais decisões que você precisa tomar, com links para dar suporte a informações técnicas. Recomendamos que você revise as seções Planejar, Implantar e Gerenciar, mesmo que já esteja totalmente implantado.

## <a name="overview-of-microsoft-teams-rooms"></a>Visão geral das Salas do Microsoft Teams

As Salas do Microsoft Teams proporcionam uma experiência completa de reunião que traz vídeo HD, áudio e compartilhamento de conteúdo para reuniões de todos os tamanhos, de pequenas áreas de reunião a salas de conferência grandes.

![Um console, um microfone e uma tela grande montada em uma parede de sala de conferência ilustram os elementos de um exemplo de configuração de Salas do Microsoft Teams.](../media/room-systems-image1.png "Um console, um microfone e uma tela grande montada em uma parede de sala de conferência ilustram os elementos de um exemplo de configuração de Salas do Microsoft Teams.")

[A ajuda das Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) é um ótimo recurso para saber mais sobre salas do Microsoft Teams e como ela pode adicionar valor como parte da sua implantação. Além disso, recomendamos assistir a este [vídeo de visão geral](https://youtu.be/tNey5KZVCl0). 

## <a name="microsoft-teams-rooms-components"></a>Componentes das Salas do Microsoft Teams

As Salas do Microsoft Teams incluem os seguintes componentes principais para oferecer uma ótima experiência do usuário:

- Painel de controle touchscreen
- Compute
- Aplicativo salas do Microsoft Teams
- Dock/extender
- Dispositivos periféricos (câmera, microfone, alto-falante)
- Telas externas (máximo de duas)
- Entrada HDMI

Você pode adquirir esses componentes como pacotes pré-instalados de vários fornecedores ou comprar os componentes com suporte individualmente seguindo os requisitos [documentados neste artigo](requirements.md).

Além da combinação Surface Pro/dock, você também pode comprar salas do Microsoft Teams com o painel de controle touchscreen, computação, encaixe e principais dispositivos periféricos integrados. 

Normalmente, os pacotes e unidades integradas incluem software pré-instalado, enquanto se você comprar componentes com suporte individualmente para os sistemas Surface Pro, precisará instalar o software. Para obter instruções, [consulte este artigo sobre a instalação de software em dispositivos](rooms-scale.md). 

Você pode implantar salas do Microsoft Teams com o Microsoft Teams, Skype for Business Online ou implantações híbridas ou locais do Skype for Business.  Consulte a [Atualização de Licenciamento](rooms-licensing.md) da Sala de Reunião do Teams para obter informações sobre as licenças necessárias.

|    |     |
|-----------|------------|
|![decidir implantação](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você implantará salas do Microsoft Teams em sua organização? </li><li>Como você obterá seus sistemas de Salas do Microsoft Teams , empacotados, como componentes separados ou como uma unidade integrada?</li></ul> |
| ![identificar atividades](../media/audio_conferencing_image9.png)<br/>Próximas etapas | <ul><li>Identifique quem realizará as principais atividades em toda a sua implantação.</li><li>Revise as salas de reunião que você tem (e planeje a configuração) para entender onde você deseja implantar salas do Microsoft Teams e os dispositivos periféricos que seriam apropriados para o tamanho da sala.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quem realizará as principais atividades em toda a sua implantação

Use a abordagem ilustrada abaixo para orientá-lo através de sua implantação e personalizar as saídas de exemplo fornecidas em todos esses artigos, conforme necessário para sua organização.

Comece compreendendo quais salas de conferência você tem e visualizando o que funcionaria melhor para você no futuro e, em seguida, vá selecionando e selecionando o equipamento de que precisa, preparando seus sites, configurando e implantando seu serviço, gerenciando alterações e adoção do usuário e desenvolvendo operações e procedimentos de manutenção.

![Comece compreendendo o que você tem e visualizando o que funcionaria melhor para você e, em seguida, vá selecionando e selecionando o equipamento de que você precisa, preparando seus sites, configurando e implantando seu serviço, gerenciando a mudança e a adoção do usuário e desenvolvendo operações e procedimentos de manutenção.](../media/room-systems-image2.png "Comece compreendendo o que você tem e visualizando o que funcionaria melhor para você e, em seguida, vá selecionando e selecionando o equipamento de que você precisa, preparando seus sites, configurando e implantando seu serviço, gerenciando a mudança e a adoção do usuário e desenvolvendo operações e procedimentos de manutenção.")

Talvez seja necessário coordenar essas atividades em várias equipes. Fornecemos uma visão de alto nível das principais atividades que você deve abranger e também sugestões para as equipes que normalmente estão envolvidas na implantação e gerenciamento de sistemas de sala de conferência, para ajudá-lo a decidir com quem você precisa trabalhar.

| Tarefas                       | Quem pode realizar a tarefa           | Atribuído a | Links para esse conteúdo |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salas de inventário            | Equipe de Instalações /AV/Equipe de Projeto de IT |             | [Inventário de sala e planejamento de recursos](#room-inventory-and-capability-planning)        |
| Planejar recursos          | Equipe de Projeto de IT                        |             | [Inventário de sala e planejamento de recursos](#room-inventory-and-capability-planning)                       |
| Seleção de dispositivo           | Equipe de Projeto de IT/Equipe av              |             | [Seleção de dispositivo](#device-selection)                      |
| Aquisição                | Equipe de Projeto de IT/Equipe av              |             | [Aquisição](#procurement)                      |
| Preparação do site             | Equipe de Instalações /AV/Equipe de Projeto de IT |             | [Preparação do site](rooms-deploy.md#site-readiness)                      |
| Prontidão de serviço          | Equipe de Projeto de IT                        |             | [Prontidão de serviço](rooms-deploy.md#service-readiness)                      |
| Configuração              | Equipe de Projeto de IT                        |             | [Configuração e implantação](rooms-deploy.md#configuration-and-deployment)                      |
| Implantação                 | Equipe de Instalações /AV/Equipe de Projeto de IT |             | [Lista de verificação da implantação](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adoção                   | Equipe de Instalações /AV/Equipe de Projeto de IT |             | [Adoção](#plan-for-adoption-and-change-management)                      |
| Manutenção e operações | Equipe av /equipe de projeto de IT              |             | [Visão geral do gerenciamento](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventário de sala e planejamento de recursos

A primeira etapa é fazer um inventário das salas de reunião e conferência existentes da sua organização para entender seu ambiente, tamanho da sala, layout e finalidade e identificar os recursos que você deseja que cada sala no escopo tenha no futuro, como quais recursos de colaboração mais avançados serão habilitados na sala. 

Depois de criar um inventário dos equipamentos e recursos em cada sala existente, seus requisitos para essa sala são alimentados pelo planejamento de seleção de dispositivos para criar uma solução de conferência rica. As modalidades (áudio, vídeo) necessárias para cada sala, além do tamanho da sala e da finalidade, todas desempenham um papel importante na decisão de qual solução é mais apropriada para cada sala. 

Como parte da descoberta, é fundamental considerar a acústico e o layout da sala. Por exemplo, verifique se as cadeiras na sala não bloquearão a exibição da câmera. Verifique se a sala não tem eco excessivo ou ar condicionado barulhento e se ela tem energia suficiente para as telas e salas do Microsoft Teams. Há muitos fatores a considerar que sua equipe ou parceiro audiovisual (AV) poderá aconselhá-lo. 

|    |     |
|-----------|------------|
| ![Salas de deplyment](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Revise as salas no escopo e defina as configurações das Salas do Microsoft Teams para elas.</li></ul>|

_Inventário de sala de reunião/conferência de exemplo_

| Site  | Nome da sala | Tipo de sala | Número de pessoas  | No escopo? | Recursos de sala atuais       | Recursos de sala futuras     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| QG de Londres | Curie         | Média        | 6 &ndash; 12                  | Sim          | Speakerphone                        | 1 tela, áudio e vídeo mais apresentação<br>Acesso PSTN |
| QG de Sydney | Monte          | Grande         | 12 &ndash; 16                 | Sim          | Unidade AV herdda, 1 tela e câmera | 2 telas, áudio e vídeo mais apresentação<br>Acesso PSTN |

## <a name="device-selection"></a>Seleção de dispositivo 

Avalie qual solução de Salas do Microsoft Teams é a mais adequada para cada sala com base nos recursos futuros que você deseja para a sala. Decida quais dispositivos periféricos AV são os mais apropriados, dependendo do tamanho da sala e do layout. 

Para obter orientações sobre o tipo de sistema e dispositivos periféricos por tipo de sala e tamanho, consulte o artigo Requisitos de Salas [do Microsoft Teams.](requirements.md) 

Com base no fornecedor que você preferir, use as informações fornecidas no artigo requisitos para definir suas Salas do Microsoft Teams e configuração de dispositivo periférico com suporte por tipo de sala e use-as como um modelo para sua implantação. 

**Dica pro** – Alguns tipos de sala podem não ser aplicáveis à sua implantação.

|    |     |
|-----------|------------|
| ![salas no escopo](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>No inventário, quais tipos de salas estão no escopo da implantação?</li><li>Quais sistemas você implantará para cada tipo de sala?</li></ul>|
| ![coletar material](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a coletar material operacional de chave para seus sistemas escolhidos e envolva sua equipe de compras.</li></ul>|

_Exemplo do modelo de implantação de Salas do Microsoft Teams para sua organização_

| **Tipo/tamanho da sala** | **Número de pessoas**  | **Sistema de Salas do Microsoft Teams** | **Dispositivos periféricos**  | **Display(s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Foco 10' por 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Pequeno 16' por 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| Média de 18' por 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| Grande 15' por 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Dica pro –** Agora é uma ótima hora para começar a coletar informações sobre a solução de Salas do Microsoft Teams que você escolheu.

## <a name="procurement"></a>Aquisição 

Você pode adquirir seu sistema escolhido como um pacote ou uma solução integrada por meio de parceiros de dispositivo. Você também pode adquirir um encaixe de dispositivo parceiro e preparar sua própria solução de Salas do Microsoft Teams usando um dispositivo Surface Pro e dispositivos periféricos _AV_ existentes e compatíveis. 

Você pode adquirir salas do Microsoft Teams de vários parceiros listados no artigo [requisitos.](requirements.md) Visite os sites dos parceiros para saber mais sobre essas soluções e opções de compras. 

Dependendo da escala e da abordagem de implantação, você pode decidir ter as Salas do Microsoft Teams e dispositivos periféricos com suporte enviados para um local central para configuração inicial e atribuição. Essa pode ser uma boa abordagem para uma aplicação em estágios em vários sites. Ou você pode optar por enviar os pacotes diretamente para seus sites. 

|    |     |
|-----------|------------|
| ![componentes de ship](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você enviará os componentes diretamente para um site ou para uma instalação de preparação?</li><li>Quem gerenciará a instalação de preparação (se você decidir usar um)?</li></ul>|
| ![plan operations](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Planejar operações.</li><li>Planejar a adoção e gerenciamento de alterações.</li></ul>|

## <a name="plan-for-operations"></a>Planejar operações 

Sua organização deve executar tarefas de monitoramento, administração e gerenciamento de forma contínua, e é fundamental concordar com quem realizará essas tarefas no início da sua implantação. 

Muitas organizações têm uma equipe av ou parceiro que gerencia suas salas de conferência e dispositivos. Essa equipe deve estar envolvida em concordar com quem gerenciará os dispositivos do Microsoft Teams Rooms em frente para monitorar o desempenho e implantar atualizações de software e hotfixes. 

Considere para qual fila de ajuda você encaminhará chamadas relacionadas ao Microsoft Teams Rooms֪ e forneça uma perguntas frequentes à equipe de assistência técnica para que eles possam entender melhor como usar salas do Microsoft Teams e as principais etapas de solução de problemas que podem ser tomadas. Um bom ponto de partida para essa perguntas frequentes é a [ajuda do usuário](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e problemas [conhecidos.](known-issues.md)

|    |     |
|-----------|------------|
| ![escolher gerente](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará salas do Microsoft Teams.</li><li>Decida para qual fila auxiliar encaminhar chamadas relacionadas ao Microsoft Teams Rooms.</li></ul>|
| ![preparar contas host](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para hospedar contas. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planejar a adoção e gerenciamento de alterações

Os sistemas de Salas do Microsoft Teams apresentam novos recursos aos seus usuários. É importante que você reconheça que isso será uma mudança para seus usuários, e você deve garantir que sua campanha identifique os benefícios que o novo sistema terá para seus usuários e os principais pontos de discussão que os leads podem usar para discutir com suas equipes. 

Considere o agendamento de eventos de exibição e de apresentação e exibição de cartazes em cada site para informar os usuários sobre os novos recursos. Você também pode criar "guias de início rápido" na sala. Considere encontrar um campeão de reuniões em cada site que possa ajudar outras pessoas a se agilizar e começar a usar os dispositivos.
