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
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592886"
---
# <a name="shifts-connectors"></a>Conectores de turnos

## <a name="overview"></a>Visão geral

Os conectores de turnos permitem integrar Shifts, a ferramenta de gerenciamento de agendamento no Microsoft Teams, com seu sistema de gerenciamento de força de trabalho (WFM). Depois de configurar uma conexão, seus funcionários de linha de frente podem exibir e gerenciar seus agendamentos em seu sistema WFM de dentro de Shifts.

Conectar seu sistema WFM ao Teams capacita sua força de trabalho de linha de frente para gerenciar agendas com mais eficiência e simplifica os processos diários para maior envolvimento e produtividade. Seus funcionários de linha de frente têm um local para o agendamento, a comunicação e a colaboração precisam trabalhar, de qualquer lugar, em qualquer dispositivo.

Oferecemos conectores shifts gerenciados e de código aberto. Este artigo fornece uma visão geral dos conectores shifts e como eles funcionam.

## <a name="how-shifts-connectors-work"></a>Como funcionam os conectores de turnos

Conectores sincronizam dados de agendamento entre o sistema WFM e Shifts, trazendo os agendamentos da sua organização para Teams. Turnos é onde seus funcionários de linha de frente se envolvem para suas necessidades de agendamento. Seu sistema WFM é o sistema de registro para regras de negócios, conformidade e inteligência.

Fluxos de dados por meio do conector de ambas as maneiras para garantir que os agendamentos sempre estão atualizados. Os agendamentos no sistema WFM são sincronizados com Shifts. E, as alterações feitas nos cronogramas em Shifts são sincronizadas de volta ao sistema WFM em tempo real. Como o sistema de registro, todas as regras comerciais são impostas pelo sistema WFM antes que os dados sejam salvos em Shifts.

## <a name="managed-shifts-connectors"></a>Conectores de Turnos Gerenciados

Os conectores de Turnos Gerenciados são conectores desenvolvidos em colaboração com nossos parceiros. Os conectores gerenciados são hospedados e gerenciados por nós ou por nossos parceiros. Com conectores gerenciados, apenas a configuração mínima é necessária.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams shifts connector for Blue Yonder
<a name="blue_yonder"> </a>

O Teams de turnos para Blue Yonder é uma oferta de primeira parte hospedada e gerenciada pela Microsoft. Com esse conector, você pode integrar Shifts com o Blue Yonder Workforce Management (Blue Yonder WFM) versões 2020.3, 2021.1 ou 2021.2 para gerenciar seus agendamentos e mantê-los atualizados.  

> [!NOTE]
> Se você tiver Blue Yonder WFM versão 2020.3 ou 2021.1, aplique o patch 2020.3.0.4 ou 2021.1.0.3. Esse patch corrige um problema em que os usuários receberão uma mensagem de erro persistente em Shifts. Ele também corrige um problema que impede que os usuários atualizá-los em Shifts.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Captura de tela mostrando uma solicitação de troca em Shifts em um dispositivo móvel, solicitando aprovação Teams na área de trabalho e uma agenda no WFM do Blue Yonder." lightbox="../../media/shifts-connector-blue-yonder.png":::

Os gerentes de linha de frente podem:

- Publique turnos e agendamentos no WFM do Blue Yonder e os veja em Shifts.
- Crie, gerencie e atribua turnos abertos no WFM do Blue Yonder e exibi-los em Shifts.
- Atribua turnos abertos que foram criados no WFM do Blue Yonder em Shifts.
- Criar, editar e excluir o tempo de folga no WFM do Blue Yonder e exibir em Shifts.
- Exibir e aprovar solicitações de agendamento de funcionários no WFM do Blue Yonder e shifts.
- Definir e atualizar a disponibilidade do trabalho no WFM do Blue Yonder e exibir em Shifts.

Os trabalhadores de linha de frente podem:

- Veja seus próprios turnos e agendamentos de sua equipe em Shifts.
- Solicitar folga, turnos abertos e turnos de troca em Turnos.
- De definir sua disponibilidade em Turnos.

No momento, não há suporte para as seguintes ações:

- Adicionar, editar, excluir, salvar ou publicar turnos em Turnos.
- Adicionar, editar, excluir, salvar ou publicar folga em Shifts.
- Adicionar, editar, excluir, salvar ou publicar turnos abertos em Shifts.

Quando um gerente de linha de frente ou um trabalhador tenta fazer qualquer uma dessas ações em Shifts, ele receberá uma mensagem para que ele saiba que a ação não tem suporte.

#### <a name="example-scenario"></a>Exemplo de cenário

O Eden, um gerente, publica um cronograma no WFM do Blue Yonder, que é sincronizado com shifts no Teams através do conector. Alex, um membro da equipe, é notificado Teams em seu dispositivo móvel e visualiza sua agenda e turnos atribuídos.

Alex precisa tirar uma folga e solicitar um dia de folga usando Shifts. A solicitação é enviada para Blue Yonder WFM por meio do conector em tempo real. Blue Yonder WFM garante que a solicitação seja compatível com as regras de negócios e que a solicitação seja criada. O Éden vê e aprova a solicitação no Blue Yonder WFM, e a aprovação é sincronizada com Teams. (O Éden também pode ver e aprovar a solicitação em Turnos). Alex é notificado Teams que sua solicitação foi aprovada e visualiza sua agenda atualizada.

Alex quer trocar um turno com um colega de trabalho. Em Turnos, Alex vê uma lista de todos os turnos que estão qualificados para uma troca com base em regras de negócios no WFM do Blue Yonder. Alex escolhe um turno atualmente atribuído a Gena. Gena é notificada em Teams em seu dispositivo móvel e aceita a solicitação de troca. O Éden vê e aprova a solicitação em Shifts, e a aprovação é sincronizada com o WFM do Blue Yonder. (O Eden também pode ver e aprovar a solicitação em Blue Yonder WFM). Alex e Gena são notificados Teams e exibir seus agendamentos atualizados.

#### <a name="set-up-a-connection"></a>Configurar uma conexão

A integração de turnos com o WFM do Blue Yonder usando o conector leva apenas algumas etapas. Você pode usar o assistente de conector shifts no Centro de administração do Microsoft 365 para configurar rapidamente uma conexão. O assistente configura o conector com base nas configurações escolhidas e cria a conexão. Se você preferir usar o PowerShell, também fornecemos scripts do PowerShell que você pode usar para se conectar.

Para obter orientações passo a passo, consulte:

- [Use o assistente de conector de turnos para conectar Shifts ao Gerenciamento de Força de Trabalho de Zona Azul](shifts-connector-wizard.md)
- [Usar o PowerShell para conectar Turnos ao Gerenciamento de Força de Trabalho do Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)

Depois que uma conexão for configurada, você poderá usar o PowerShell para atualizar e alterar as configurações de conexão a qualquer momento, conforme necessário. Quanto ao conector em si, você não precisa se preocupar com atualizações ou manutenção. Nós cuidamos disso.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Conector reflexis shifts para Microsoft Teams

O conector Reflexis Shifts para Microsoft Teams é hospedado e gerenciado por Zebra. Com esse conector, você pode integrar Shifts ao sistema WFM reflexis para gerenciar seus cronogramas e mantê-los atualizados.

Os funcionários de linha de frente têm acesso à agenda em Turnos no Teams e suas solicitações são sincronizadas de Turnos para Agendador de Força de Trabalho Reflexis (RWS). O status de solicitações e turnos criados no RWS são sincronizados com shifts em Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Captura de tela mostrando a lista de turnos em um dispositivo móvel e uma agenda em Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Os gerentes de linha de frente podem:

- Publicar turnos e agendamentos no Reflexis e exibi-los em Turnos.
- Edite turnos em Reflexis e Shifts.
- Crie, gerencie e atribua turnos abertos em Reflexis e Shifts.
- Exibir e aprovar solicitações de agendamento de funcionários em Reflexis e Turnos.

Os trabalhadores de linha de frente podem:

- Veja seus próprios turnos e agendamentos de sua equipe em Shifts.
- Solicitar folga, abrir turnos e trocar e oferecer turnos em Turnos.

Para saber mais, vá para https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Conectores de Shifts de código aberto

Os conectores de Shifts de código aberto são integrações orientadas pela comunidade [criadas em Shifts Graph APIs](/graph/api/resources/shift). Os seguintes conectores de código aberto estão disponíveis:

- Kronos-to-Teams WFC local
- Conector de turnos do JDA para Teams (para Blue Yonder versão 2017 a 2020.2)

Cada conector vem com orientações detalhadas de implantação e configuração. Eles incluem scripts de implantação do Azure Resource Manager (ARM) que permitem hospedar todos os serviços necessários Microsoft Azure. O código-fonte e os scripts de implantação estão disponíveis para download em um [GitHub repositório](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors). Você pode implantar como está ou personalizar ou estender para atender às suas necessidades.

Para saber mais, confira [Conectores de turnos prontos para produção](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
