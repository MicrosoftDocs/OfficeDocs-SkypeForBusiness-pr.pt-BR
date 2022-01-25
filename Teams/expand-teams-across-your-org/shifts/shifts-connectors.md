---
title: Conectores de turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre conectores shifts e como usá-los para conectar Shifts ao seu sistema de gerenciamento de força de trabalho.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192472"
---
# <a name="shifts-connectors"></a>Conectores de turnos

## <a name="overview"></a>Visão Geral

Os conectores de turnos permitem integrar Shifts, a ferramenta de gerenciamento de agendamento no Microsoft Teams, com seu sistema de gerenciamento de força de trabalho (WFM). Depois de configurar uma conexão, seus funcionários de linha de frente podem exibir e gerenciar seus agendamentos em seu sistema WFM de dentro de Shifts.

Conectar seu sistema WFM ao Teams capacita sua força de trabalho de linha de frente para gerenciar agendas de forma mais eficiente e simplifica os processos diários para maior envolvimento e produtividade. Seus funcionários de linha de frente têm um local para o agendamento, a comunicação e a colaboração precisam trabalhar, de qualquer lugar, em qualquer dispositivo.

Oferecemos conectores shifts gerenciados e de código aberto. Este artigo fornece uma visão geral dos conectores shifts e como eles funcionam.

## <a name="how-shifts-connectors-work"></a>Como funcionam os conectores de turnos

Conectores sincronizam dados de agendamento entre o sistema WFM e Shifts, trazendo os agendamentos da sua organização para Teams. Turnos é onde seus funcionários de linha de frente se envolvem para suas necessidades de agendamento. Seu sistema WFM é o sistema de registro para regras de negócios, conformidade e inteligência.

Fluxos de dados por meio do conector de ambas as maneiras para garantir que os agendamentos sempre estão atualizados. Os agendamentos no sistema WFM são sincronizados com Shifts. E, as alterações feitas nos cronogramas em Shifts são sincronizadas de volta ao sistema WFM em tempo real. Como o sistema de registro, todas as regras comerciais são impostas pelo sistema WFM antes que os dados sejam salvos em Shifts.

## <a name="managed-shifts-connectors"></a>Conectores de Turnos Gerenciados

Os conectores de Turnos Gerenciados são conectores desenvolvidos em colaboração com nossos parceiros. Os conectores gerenciados são hospedados e gerenciados por nós ou por nossos parceiros. Com conectores gerenciados, apenas a configuração mínima é necessária.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Conector reflexis shifts para Microsoft Teams

O conector Reflexis Shifts para Microsoft Teams é hospedado e gerenciado por Zebra. Com esse conector, você pode integrar Shifts ao sistema WFM reflexis para gerenciar seus cronogramas e mantê-los atualizados.

Os funcionários de linha de frente têm acesso ao agendamento em Turnos no Teams e suas solicitações são sincronizadas de Turnos para Agendador de Força de Trabalho Reflexis (RWS). O status de solicitações e turnos criados no RWS são sincronizados com shifts em Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Captura de tela mostrando a lista de turnos em um dispositivo móvel e uma agenda em Reflexis" lightbox="../../media/shifts-connector-reflexis.png":::

Os gerentes de linha de frente podem:

- Publicar turnos e agendamentos no Reflexis e exibi-los em Turnos.
- Edite turnos em Reflexis e Shifts.
- Crie, gerencie e atribua turnos abertos em Reflexis e Shifts.
- Exibir e aprovar solicitações de agendamento de funcionários em Reflexis e Turnos.

Os trabalhadores de linha de frente podem:

- Veja seus próprios turnos e agendamentos de sua equipe em Shifts.
- Solicitar folga, abrir turnos e trocar e oferecer turnos em Turnos.

Para saber mais, vá para https://connect.zebra.com/microsoft-connectors .

## <a name="open-source-shifts-connectors"></a>Conectores de Shifts de código aberto

Os conectores de Shifts de código aberto são integrações orientadas pela comunidade criadas em [Shifts Graph APIs](/graph/api/resources/shift). Os seguintes conectores de código aberto estão disponíveis:

- Kronos-to-Teams WFC local
- Conector de turnos do JDA para Teams (para Blue Yonder versão 2017 a 2020.2)

Cada conector vem com orientações detalhadas de implantação e configuração. Eles incluem scripts de implantação do Gerenciador de Recursos do Azure (ARM) que permitem hospedar todos os serviços necessários Microsoft Azure. O código-fonte e os scripts de implantação estão disponíveis para download em um [GitHub repositório](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors). Você pode implantar como está ou personalizar ou estender para atender às suas necessidades.

Para saber mais, confira [Conectores de turnos](/microsoftteams/platform/samples/shifts-wfm-connectors)prontos para produção.

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
