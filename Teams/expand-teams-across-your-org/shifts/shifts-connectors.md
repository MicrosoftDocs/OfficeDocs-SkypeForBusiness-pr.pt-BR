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
description: Saiba mais sobre os conectores do Shifts e como usá-los para conectar o Shifts ao seu sistema de gerenciamento de força de trabalho.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64592886"
---
# <a name="shifts-connectors"></a>Conectores de turnos

## <a name="overview"></a>Visão Geral

Os conectores shifts permitem que você integre o Shifts, a ferramenta de gerenciamento de agendamento no Microsoft Teams, com o sistema WFM (gerenciamento de força de trabalho). Depois de configurar uma conexão, os trabalhadores da linha de frente podem exibir e gerenciar diretamente suas agendas no sistema WFM de dentro do Shifts.

Conectar seu sistema WFM ao Teams capacita sua força de trabalho de linha de frente a gerenciar agendas com mais eficiência e simplifica os processos diários para maior envolvimento e produtividade. Seus funcionários de linha de frente têm um local para o agendamento, a comunicação e a colaboração precisam trabalhar, de qualquer lugar, em qualquer dispositivo.

Oferecemos conectores shifts gerenciados e de software livre. Este artigo fornece uma visão geral dos conectores do Shifts e como eles funcionam.

## <a name="how-shifts-connectors-work"></a>Como funcionam os conectores do Shifts

Os conectores sincronizam dados de agendamento entre o sistema WFM e o Shifts, trazendo os agendamentos da sua organização para Teams. Turnos é onde os funcionários da linha de frente se envolvem para suas necessidades de agendamento. Seu sistema WFM é o sistema de registro para regras de negócios, conformidade e inteligência.

Os fluxos de dados por meio do conector de ambas as maneiras para garantir que os agendamentos estejam sempre atualizados. Os agendamentos no sistema WFM são sincronizados com o Shifts. Além disso, as alterações feitas nos agendamentos no Shifts são sincronizadas novamente com o sistema WFM em tempo real. Como o sistema de registro, todas as regras de negócios são impostas pelo sistema WFM antes que os dados sejam salvos em Turnos.

## <a name="managed-shifts-connectors"></a>Conectores de Turnos Gerenciados

Os conectores do Managed Shifts são conectores desenvolvidos em colaboração com nossos parceiros. Os conectores gerenciados são hospedados e gerenciados por nós ou nossos parceiros. Com conectores gerenciados, apenas a configuração mínima é necessária.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams shifts connector for Blue Yonder
<a name="blue_yonder"> </a>

O Teams shifts do Blue Yonder é uma oferta interna hospedada e gerenciada pela Microsoft. Com esse conector, você pode integrar o Shifts ao Blue Yonder Workforce Management (Blue Yonder WFM) versões 2020.3, 2021.1 ou 2021.2 para gerenciar suas agendas e mantê-las atualizadas.  

> [!NOTE]
> Se você tiver o Blue Yonder WFM versão 2020.3 ou 2021.1, aplique o patch 2020.3.0.4 ou 2021.1.0.3. Esse patch corrige um problema em que os usuários obtêm uma mensagem de erro persistente no Shifts. Ele também corrige um problema que impede que os usuários atualizá-los no Shifts.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Captura de tela mostrando uma solicitação de troca em Turnos em um dispositivo móvel, solicitar aprovação em Teams na área de trabalho e um agendamento no Blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

Os gerentes de linha de frente podem:

- Publique turnos e agendamentos no WFM Do Remetente Azul e exiba-os em Turnos.
- Crie, gerencie e atribua turnos abertos no WFM Do Remetente Azul e exiba-os em Turnos.
- Atribua turnos abertos que foram criados no WFM Yonder Azul em Turnos.
- Crie, edite e exclua a folga no WFM do Remetente Azul e exiba em Turnos.
- Exiba e aprove solicitações de agendamento de trabalhos no WFM e nos Turnos do Remetente Azul.
- Defina e atualize a disponibilidade do trabalho no WFM do Remetente Azul e no modo de exibição em Turnos.

Os trabalhadores da linha de frente podem:

- Veja seus próprios turnos e seus turnos e cronogramas em Turnos.
- Solicitar folga, abrir turnos e trocar turnos em Turnos.
- Defina sua disponibilidade em Turnos.

No momento, não há suporte para as seguintes ações:

- Adicionar, editar, excluir, salvar ou publicar turnos em Turnos.
- Adicione, edite, exclua, salve ou publique folgas no Shifts.
- Adicionar, editar, excluir, salvar ou publicar turnos abertos no Shifts.

Quando um gerente de linha de frente ou um trabalhador tentar executar qualquer uma dessas ações no Shifts, ele receberá uma mensagem para informar que a ação não tem suporte.

#### <a name="example-scenario"></a>Exemplo de cenário

O Eden, um gerente, publica uma agenda no Blue Yonder WFM, que é sincronizado com o Shifts no Teams por meio do conector. Alex, um membro da equipe, é notificado Teams em seu dispositivo móvel, e exibe sua agenda e turnos atribuídos.

Alex precisa tirar uma folga e solicitar um dia de folga usando o Shifts. A solicitação é enviada ao Blue Yonder WFM por meio do conector em tempo real. O Blue Yonder WFM garante que a solicitação esteja em conformidade com as regras de negócio e que a solicitação seja criada. O Eden vê e aprova a solicitação no Blue Yonder WFM e a aprovação é sincronizada com Teams. (O Éden também pode ver e aprovar a solicitação em Turnos). Alex é notificado Teams que seu pedido foi aprovado e exibe sua agenda atualizada.

Alex quer trocar de turno com um colega de trabalho. No Shifts, Alex vê uma lista de todos os turnos que estão qualificados para uma troca com base em regras de negócios no Blue Yonder WFM. Alex escolhe um turno que está atualmente atribuído à Gena. A Gena é notificada Teams em seu dispositivo móvel e aceita a solicitação de troca. O Eden vê e aprova a solicitação em Turnos, e a aprovação é sincronizada com o WFM do Remetente Azul. (O Eden também pode ver e aprovar a solicitação no Blue Yonder WFM). Alex e Gena são notificados Teams e exibem seus agendamentos atualizados.

#### <a name="set-up-a-connection"></a>Configurar uma conexão

A integração do Shifts ao Blue Yonder WFM usando o conector leva apenas algumas etapas. Você pode usar o assistente do conector shifts no Centro de administração do Microsoft 365 para configurar rapidamente uma conexão. O assistente configura o conector com base nas configurações escolhidas e cria a conexão. Se você preferir usar o PowerShell, também forneceremos scripts do PowerShell que você pode usar para se conectar.

Para obter diretrizes passo a passo, consulte:

- [Usar o assistente do conector do Shifts para conectar o Shifts ao Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usar o PowerShell para conectar turnos ao Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Depois que uma conexão for configurada, você poderá usar o PowerShell para atualizar e alterar as configurações de conexão a qualquer momento, conforme necessário. Quanto ao conector em si, você não precisa se preocupar com atualizações ou manutenção. Nós cuidamos disso.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Conector reflexis shifts para Microsoft Teams

O conector reflexis shifts para Microsoft Teams é hospedado e gerenciado pela Zebra. Com esse conector, você pode integrar o Shifts ao sistema Reflexis WFM para gerenciar suas agendas e mantê-las atualizadas.

Os trabalhadores da linha de frente têm acesso ao seu agendamento em Turnos Teams e suas solicitações são sincronizadas de Turnos para Agendador de Força de Trabalho Reflexis (RWS). O status de solicitações e turnos criados no RWS é sincronizado com shifts Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Captura de tela mostrando a lista de turnos em um dispositivo móvel e uma agenda no Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Os gerentes de linha de frente podem:

- Publique turnos e agendamentos no Reflexis e exiba-os em Turnos.
- Edite turnos em Reflexis e Shifts.
- Crie, gerencie e atribua turnos abertos em Reflexis e Shifts.
- Exiba e aprove solicitações de agendamento de trabalhadores em Reflexis e Turnos.

Os trabalhadores da linha de frente podem:

- Veja seus próprios turnos e seus turnos e cronogramas em Turnos.
- Solicite folga, abra turnos e troque e ofereça turnos em Turnos.

Para saber mais, vá para https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Conectores shifts de software livre

Conectores shifts de software livre são integrações orientadas pela comunidade [criadas em Shifts Graph APIs](/graph/api/resources/shift). Os seguintes conectores de software livre estão disponíveis:

- Kronos-to-Teams WFC local
- Conector shifts de JDA para Teams (para Blue Yonder versão 2017 a 2020.2)

Cada conector vem com diretrizes detalhadas de implantação e configuração. Eles incluem scripts de implantação do ARM (Azure Resource Manager) que permitem hospedar todos os serviços necessários no Microsoft Azure. O código-fonte e os scripts de implantação estão disponíveis para download em um [GitHub repositório](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors). Você pode implantar como está ou personalizar ou estender para atender às suas necessidades.

Para saber mais, confira [conectores shifts prontos para produção](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
