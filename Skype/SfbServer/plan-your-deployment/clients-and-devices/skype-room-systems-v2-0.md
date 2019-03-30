---
title: Planejar para salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: Este artigo explica as considerações de planejamento relevantes para a implantação de salas de equipes da Microsoft, a próxima geração de sistemas de sala Skype.
ms.openlocfilehash: 7de824eee31b29b4b229d7b4d1b8eb7d60f5a632
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013047"
---
# <a name="plan-microsoft-teams-rooms"></a>Planejar as salas de equipes da Microsoft

Este artigo apresenta uma abordagem de ponta a ponta para o planejamento, fornecendo e salas de equipes operacionais do Microsoft como parte de sua estratégia de sala de conferência e a reunião geral.

Você encontrará informações abaixo que abrangem a abordagem recomendada e as principais decisões que precisam ser feitas, com links para informações técnicas de suportadas de planejamento. Recomendamos que você revise as seções de planejar, implantar e gerenciar, mesmo se você já totalmente estiver implantado.

## <a name="overview-of-microsoft-teams-rooms"></a>Visão geral das salas de equipes da Microsoft

Salas de equipes da Microsoft oferece uma experiência de reunião completa que traz o compartilhamento de conteúdo, áudio e vídeo HD para reuniões de todos os tamanhos, provenientes de áreas de huddle pequenas salas de conferência grande.

![Um console, microfone e tela grande montado em uma parede de sala de conferência ilustram os elementos de um programa de instalação do Microsoft equipes salas de exemplo.] (../../media/room-systems-image1.png "Um console, microfone e tela grande montado em uma parede de sala de conferência ilustram os elementos de um programa de instalação do Microsoft equipes salas de exemplo.")

[Ajuda do Microsoft equipes salas](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) é um ótimo recurso para descobrir mias sobre salas de equipes da Microsoft e como ele pode adicionar o valor como parte da sua implantação. Além disso, é recomendável assistindo a este [vídeo de visão geral](https://youtu.be/tNey5KZVCl0). 

## <a name="microsoft-teams-rooms-components"></a>Componentes de salas de equipes da Microsoft

Salas de equipes da Microsoft inclui os seguintes componentes principais para oferecer uma experiência de usuário excelente:

- Painel de controle de tela sensível ao toque
- Compute
- Aplicativo de salas de equipes da Microsoft
- Encaixe/extender
- Dispositivos periféricos (câmera, microfone, alto-falante)
- Telas externas (máximo de duas)
- Entrada HDMI

Você pode adquirir esses componentes como pré-instalado pacotes de vários fornecedores, ou você pode adquirir os componentes suportados individualmente seguindo os [requisitos documentados neste artigo](requirements.md).

Além da combinação de Surface Pro / encaixe, você pode também aquisição salas de equipes da Microsoft com o painel de controle de tela sensível ao toque, compute, encaixa e dispositivos periféricos integrados de chave. 

Normalmente, os pacotes e unidades integradas incluem software pré-instalado, enquanto se comprar componentes suportados individualmente para os sistemas Surface Pro, você precisará instalar o software. Para obter instruções, consulte [Este artigo sobre como instalar o software em dispositivos](../../deploy/deploy-clients/room-systems-scale.md). 

Você pode implantar salas de equipes da Microsoft com equipes, Skype para Business Online ou Skype para implantações híbridas ou local de negócios.  Consulte [Licenciamento de salas de equipes da Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) para obter informações sobre as licenças necessárias.

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você implantará salas de equipes da Microsoft em sua organização? </li><li>Como você adquirir seus sistemas de salas de equipes da Microsoft — incluído, como componentes separados, ou como uma unidade integrada?</li></ul> |
| ![](../../media/audio_conferencing_image9.png)<br/>Próximas etapas | <ul><li>Identifica quem será se responsabilizarão as principais atividades em toda sua implantação.</li><li>Revise as salas de reunião ter (e planeje configurar a) para entender onde você deseja implantar o Microsoft equipes salas e os dispositivos periféricos que seriam apropriado para o tamanho da sala.</li></ul> |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identificar quem será se responsabilizarão as principais atividades em toda sua implantação

Usar a abordagem ilustrada abaixo para guiá-lo por meio de sua implantação e personalize as saídas de amostra fornecidas em toda estes artigos conforme necessário para sua organização.

Comece com noções básicas sobre qual conferência salas que você tem envisioning o que funciona melhor para você no futuro, percorrer, em seguida, selecionando e aquisição do equipamento necessário, preparando seus sites, configurar e implantar seu serviço, gerenciamento de mudanças e adoção de usuário e desenvolvimento de procedimentos de manutenção e operações.

![Inicial com noções básicas sobre o que você tem e envisioning o que funciona melhor para você, em seguida, percorre selecionando e aquisição do equipamento necessário, preparando seus sites, configurar e implantar seu serviço, gerenciando a adoção de alteração e de usuário, e desenvolvendo operações e procedimentos de manutenção.] (../../media/room-systems-image2.png "Inicial com noções básicas sobre o que você tem e envisioning o que funciona melhor para você, em seguida, percorre selecionando e aquisição do equipamento necessário, preparando seus sites, configurar e implantar seu serviço, gerenciando a adoção de alteração e de usuário, e desenvolvendo operações e procedimentos de manutenção.")

Talvez você precise coordenar essas atividades em várias equipes. Fornecemos uma exibição de alto nível das principais atividades que você deve abranger e também sugestões para as equipes que são normalmente envolvidas na implantação e gerenciamento de sistemas de sala de conferência, para ajudá-lo a decidir o que você precisa trabalhar com.

| Tarefa                       | Quem pode tomar a tarefa           | Atribuído a | Links para este conteúdo |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salas de inventário            | Instalações / equipe AV / equipe de projeto de TI |             | [Inventário de sala e planejamento de capacidade](#room-inventory-and-capability-planning)        |
| Planejar recursos          | IT equipe do projeto                        |             | [Inventário de sala e planejamento de capacidade](#room-inventory-and-capability-planning)                       |
| Seleção de dispositivo           | IT equipe do projeto / AV de equipe              |             | [Seleção de dispositivo](#device-selection)                      |
| Compras                | IT equipe do projeto / AV de equipe              |             | [Compras](#procurement)                      |
| Preparação de site             | Instalações / equipe AV / equipe de projeto de TI |             | [Preparação de site](../../deploy/deploy-clients/room-systems-v2.md#site-readiness)                      |
| Prontidão de serviço          | IT equipe do projeto                        |             | [Prontidão de serviço](../../deploy/deploy-clients/room-systems-v2.md#service-readiness)                      |
| Configuração              | IT equipe do projeto                        |             | [Configuração e implantação](../../deploy/deploy-clients/room-systems-v2.md#configuration-and-deployment)                      |
| Implantação                 | Instalações / equipe AV / equipe de projeto de TI |             | [Lista de verificação da implantação](../../deploy/deploy-clients/console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adoção                   | Instalações / equipe AV / equipe de projeto de TI |             | [Adoção](#plan-for-adoption-and-change-management)                      |
| Manutenção e operações | Equipe de AV / equipe de projeto de TI              |             | [Visão geral do gerenciamento](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventário de sala e planejamento de capacidade

A primeira etapa é inventário de reunião existente da sua organização e salas de conferência para compreender o seu ambiente, tamanho da sala, layout e finalidade e para identificar os recursos desejados cada sala de escopo ter no futuro como quais mais rica recursos de colaboração serão habilitados na sala. 

Depois de criar um inventário dos recursos de equipamentos e em cada sala existente, seus requisitos para sala feed em sua seleção de dispositivo planejamento para criar uma solução de conferência avançado. Modalidades (áudio, vídeo) necessárias para cada sala — além de room size e finalidade — todos têm um papel importante ao decidir qual solução é mais apropriada para cada sala. 

Como parte da sua descoberta, chave a serem considerados acústica de sala e layout-lo do. Por exemplo, verifique se as cadeiras na sala não bloqueiam a visualização da câmera. Verifique que a sala não tem excessivo eco ou com ruído ar condicionado e que ele tem energia suficiente para que as telas e salas de equipes da Microsoft. Há vários fatores a serem considerados que sua equipe de audiovisuais (AV) ou parceiro poderão aconselhar sobre. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Quais salas fazem parte do escopo dessa implantação?</li><li>Os sites que estão no escopo para sua implantação?</li><li>Quem irá se responsabilizarão reunião salas inventário?</li></ul> |
| ![](../../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Revise as salas no escopo e definir as configurações de salas de equipes da Microsoft para eles.</li></ul>|

_Inventário de sala de reunião/conferência de amostra_

| Site  | Nome da sala | Tipo de sala | Número de pessoas  | No escopo? | Recursos atuais de sala       | Recursos de sala futuras     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| Matriz de Londres | Curie         | Média        | 6&ndash;12                  | Sim          | Viva-voz                        | 1 tela, áudio e vídeo plus apresentação<br>Acesso ao PSTN |
| Matriz de Sidnei | Hill          | Grande         | 12&ndash;16                 | Sim          | Herdado AV unidade, 1 tela e câmera | 2 telas, áudio e vídeos plus apresentação<br>Acesso ao PSTN |

**Dica pro** – se você tiver muitos sites inventário, você talvez queira baixar e usar a [distribuição de Site e planejamento de migração - questionário de Site](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_15).

## <a name="device-selection"></a>Seleção de dispositivo 

Avalie qual solução de salas de equipes da Microsoft é o mais adequado para cada sala de acordo com os recursos de futuros desejado para a sala. Decida quais dispositivos periféricos de AV são o melhor ajuste, dependendo do tamanho de sala e layout. 

Para obter orientação para o tipo de sistema e dispositivos periféricos por tipo de sala e tamanho, consulte o artigo de [requisitos de salas de equipes da Microsoft](requirements.md) . 

Com base no fornecedor que você preferir, use as informações fornecidas no artigo requisitos para definir as salas de equipes da Microsoft e a configuração de dispositivo periféricos suportado por tipo de sala e use esta opção como um modelo para sua implantação. 

**Dica pro** – alguns tipos de sala talvez não sejam aplicáveis para sua implantação.

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>A partir de seu inventário, quais tipos de salas são no escopo para sua implantação?</li><li>Quais sistemas você implantará para cada tipo de sala?</li></ul>|
| ![](../../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie reunir material da chave operacional para seus sistemas escolhidos e entre em contato com sua equipe de compras.</li></ul>|

_Amostra de modelo de implantação de salas de equipes da Microsoft para sua organização_

| **Tipo/tamanho da sala** | **Número de pessoas**  | **Sistema de salas de equipes da Microsoft** | **Dispositivos periféricos**  | **Display(s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Foco 10' por 9'      | 2&ndash;4                   |                                  |                         |                 |
| Pequeno 16' por 16'     | 4&ndash;6                   |                                  |                         |                 |
| Médio 18' por 20'    | 6&ndash;12                  |                                  |                         |                 |
| Grande 15' por 32 °     | 12&ndash;16                 |                                  |                         |                 |

**Dica Pro –** Agora é um ótimo momento para iniciar a coleta de informações sobre a solução de salas de equipes da Microsoft que você escolheu. Recomendamos que você trabalhe com seu fornecedor para discutir Concluindo o modelo de design para capturar informações que serão relevantes à sua implantação; Você pode [baixar esse modelo úteis](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_11) do MyAdvisor. 

## <a name="procurement"></a>Compras 

Você pode adquirir seu sistema escolhido como um pacote ou uma solução integrada via parceiros de dispositivo. Você também pode adquirir um encaixe do dispositivo de parceiro e preparar sua própria solução de salas de equipes da Microsoft usando um dispositivo Surface Pro e existentes, dispositivos periféricos _suportado_ AV. 

Você pode adquirir salas de equipes da Microsoft a partir de um número de parceiros que estão listados no [artigo requirements](requirements.md). Visite sites dos parceiros para saber mais sobre essas opções de compras e soluções. 

Dependendo da sua escala de implantação e a abordagem, você pode decidir têm as salas de equipes da Microsoft e suporte para dispositivos periféricos enviados para um local central para a configuração inicial e a atribuição. Isso pode ser uma boa abordagem para uma distribuição em estágios entre muitos sites. Ou então, você pode optar por enviar os pacotes diretamente aos seus sites. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Você fornecerá os componentes diretamente a um site ou a um recurso de preparo?</li><li>Quem irá gerenciar a facilidade de preparo (se você decidir usar um)?</li></ul>|
| ![](../../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Plano de operações.</li><li>Planejar a adoção e gerenciamento de alterações.</li></ul>|

## <a name="plan-for-operations"></a>Plano de operações 

Sua organização deve executar tarefas de monitoramento, administração e gerenciamento em constantemente e a chave de TI concordar que irá se responsabilizarão essas tarefas logo em sua implantação. 

Muitas organizações têm uma equipe de AV ou parceiro quem gerencia suas salas de conferência e dispositivos. Essa equipe deve estar envolvida nos concordar quem irá gerenciar os dispositivos de salas de equipes da Microsoft no futuro para monitorar o desempenho e implantar atualizações de software e hotfixes. 

Considere a possibilidade de fila para a qual helpdesk você rotear chamadas relacionadas ao Microsoft equipes Rooms֪ para e fornecer uma FAQ para a equipe de assistência técnica para que eles podem melhor entender como usar salas de equipes da Microsoft e a chave passos podem ser realizadas para solucionar problemas. Um bom ponto de partida para estas perguntas Frequentes é a [Ajuda do usuário](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) e a [lista de problemas conhecidos do](../../manage/skype-room-systems-v2/known-issues.md).

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem irá gerenciar salas de equipes da Microsoft.</li><li>Decida qual fila de assistência técnica para rotear chamadas relacionadas ao Microsoft equipes salas para.</li></ul>|
| ![](../../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Preparar-se para contas de host. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planejar a adoção e gerenciamento de alterações

Sistemas de salas de equipes da Microsoft apresentam novos recursos para seus usuários. É importante que você reconhece que isso será uma mudança para seus usuários, e você deve garantir que sua campanha identifica os benefícios que do novo sistema terá para seus usuários e os líderes de chave estratégias competitivas podem usar para discutir com suas equipes. 

Considere a possibilidade de agendamento de cartaz e eventos show-and-tell cai em cada local para informar os usuários dos novos recursos. Você também pode criar na sala "rápido iniciar guias". Considere a possibilidade de localizar um campeão de reuniões em cada site que possa ajudar a outras pessoas para acelerar e começar a usar os dispositivos.
