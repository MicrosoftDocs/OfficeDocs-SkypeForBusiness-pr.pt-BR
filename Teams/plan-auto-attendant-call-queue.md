---
title: Planejar atendimentos automáticos do Teams e filas de chamadas
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Saiba mais sobre atendentes automáticos e filas de chamadas e como usá-los para ajudar os chamadores a passar por um sistema de menus para alcançar pessoas ou departamentos em sua organização.
ms.openlocfilehash: 097d4d0e921e0481e4986cce6f599cbd55044138
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763612"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planejar atendimentos automáticos do Teams e filas de chamadas

Os atendentes automáticos permitem configurar opções de menu para rotear chamadas com base na entrada do chamador. As opções de menu para um atendente automático , como "For Sales, pressione 1--For Services press 2"-- permitem que uma organização forneça uma série de opções que orientam os chamadores para seu destino rapidamente, sem depender de um operador humano para lidar com chamadas recebidas.

Filas de chamadas são áreas de espera para chamadores. Para situações em que os chamadores precisam alcançar alguém com uma especialidade específica, como vendas ou serviço, em vez de uma pessoa específica, você pode usar filas de chamadas para conectar os chamadores ao grupo de agentes que podem ajudá-los. Os chamadores são colocados em espera até que um agente atribuído à fila esteja disponível para atender sua chamada.

Usados juntos, os atendentes automáticos e as filas de chamadas podem facilmente rotear os chamadores para a pessoa ou departamento apropriado em sua organização.

## <a name="auto-attendants"></a>Atendedores automáticos

A principal finalidade de um atendente automático é direcionar um chamador para uma pessoa ou departamento apropriado com base na entrada do chamador para as opções de menu fornecidas. Os chamadores podem ser direcionados a pessoas específicas em sua organização, para chamar filas em que esperam para conversar com o próximo agente disponível ou para a caixa postal. Diferentes opções de roteamento de chamadas podem ser especificadas para horário comercial, horas de folga e feriados.

Os prompts de menu podem ser criados usando texto em fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação de mãos livres, mas as pessoas que ligam também podem usar o teclado do telefone para navegar em menus.

Cada atendente automático tem um idioma e um fuso horário específicos. Se você fizer negócios em vários idiomas ou várias partes do mundo, poderá criar tantos atendentes automáticos diferentes quanto precisar para acomodar seus chamadores.

Para cada atendente automático, você pode configurar um operador. Embora você possa configurar chamadas de operador para ir a vários destinos, o recurso do operador foi projetado para permitir que os chamadores conversem com uma pessoa específica em sua organização que possa ajudá-los.

Os atendentes automáticos podem ser configurados para permitir que os chamadores pesquisem o diretório da sua organização, seja pelo nome ou pelo número de extensão. Em um atendente automático, você pode especificar quem está disponível para a pesquisa de diretório escolhendo grupos de usuários para incluir ou excluir. (Isso é conhecido como *escopo de discagem*.)

Os chamadores podem acessar um atendente automático por número de telefone direto, se configurado ou sendo redirecionados de outro atendente automático ou de uma fila de chamadas.

## <a name="call-queues"></a>Filas de chamadas

Uma fila de chamadas é análoga a uma sala de espera em um prédio físico. Os chamadores esperam em espera enquanto as chamadas são roteadas para os agentes na fila. Filas de chamadas são comumente usadas para vendas e funções de serviço. No entanto, filas de chamadas podem ser usadas para qualquer situação em que o número de chamadas excede sua capacidade interna, como uma recepcionista em uma instalação movimentada.

As filas de chamada permitem o roteamento específico de chamadas nos casos em que o número total de chamadores na fila ou o tempo de espera excede os limites especificados. As chamadas podem ser roteadas para pessoas específicas, caixa postal, outras filas de chamada ou atendentes automáticos.

Assim como os atendentes automáticos, as filas de chamadas têm cada uma configuração de idioma. Você pode usar filas de chamadas diferentes se fizer negócios em vários idiomas. Os agentes podem ser membros de mais de uma fila se forem multilíngues.

Para cada fila de chamadas, você pode especificar se os agentes na fila podem optar por não atender chamadas e se as chamadas devem ser roteadas para elas com base na indicação de presença no Teams.

Você pode atribuir um número de telefone a uma fila de chamadas, no entanto, as filas de chamadas não fornecem roteamento de chamadas separados para horários de folga e feriados. A menos que sua fila de chamadas esteja equipada 24 horas por dia, 7 dias por semana, recomendamos atribuir o número de telefone a um atendente automático que redirecione para a fila de chamadas durante o horário comercial.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar os atendentes automáticos e as filas de chamadas, você precisa dos seguintes recursos:

- Uma [Conta de Recurso](manage-resource-accounts.md) para cada atendente automático e cada fila de chamadas.
- Uma [licença gratuita Telefonia do Microsoft Teams Conta de Recursos](teams-add-on-licensing/virtual-user.md) para cada conta de recurso.
- Pelo menos um [número de serviço da Microsoft](getting-service-phone-numbers.md), [número do Operator Connect](operator-connect-plan.md), [número de roteamento direto](direct-routing-plan.md) ou um número híbrido para cada conta de recurso que você deseja discar diretamente de números de telefone externos.
  - O número de serviço pode ser um número de pedágio ou gratuito.

> [!NOTE]
> As contas de recurso estão desabilitadas para entrar e devem permanecer assim. Chat e presença não estão disponíveis para essas contas.

Os agentes que recebem chamadas das filas de chamada devem estar Enterprise Voice usuários online ou locais habilitados. Para obter mais informações, consulte [Atribuir, alterar ou remover um número de telefone para um usuário](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) e [Habilitar usuários para Roteamento Direto](/microsoftteams/direct-routing-enable-users). Além disso, se as filas de chamada estiverem usando números de Roteamento Direto, os agentes que precisam fazer conferências ou transferir chamadas também precisarão:

- Uma [política de roteamento de voz online](manage-voice-routing-policies.md) atribuída se a fila de chamadas usar o modo de transferência.
- Uma [licença de Conferência de Áudio](set-up-audio-conferencing-in-teams.md) ou [uma política de roteamento de voz online](manage-voice-routing-policies.md) atribuída se a fila de chamadas usar o modo de conferência.

Se seus agentes estiverem usando o aplicativo Microsoft Teams para chamadas de fila de chamadas, eles precisarão estar no modo TeamsOnly.

Ao usar uma conta de recurso para fins de ID de linha de chamada em filas de chamada, a conta de recurso deve ter uma licença de Conta de Recurso do Teams Phone e uma das seguintes atribuídas:

- Uma licença [de Plano de Chamada](calling-plans-for-office-365.md) e um número de telefone atribuído.
- Um número de telefone [do Operator Connect](operator-connect-plan.md) atribuído.
- Uma [política de roteamento de voz online](manage-voice-routing-policies.md).
  - A atribuição de número de telefone é opcional ao usar o Roteamento Direto.

Quando um atendente automático ou uma fila de chamadas está transferindo chamadas para um número externo, contas de recursos específicas, conforme descrito abaixo, devem ter uma licença da Conta de Recursos de Telefone do Teams e uma das seguintes atribuídas:

- Uma licença [de Plano de Chamada](calling-plans-for-office-365.md) e um número de telefone atribuído.
- Um número de telefone [do Operator Connect](operator-connect-plan.md) atribuído.
- Uma [política de roteamento de voz online](manage-voice-routing-policies.md).
  - A atribuição de número de telefone é opcional ao usar o Roteamento Direto.

Qual conta de recurso para licença:

- Licencia a conta de recurso no primeiro atendente automático que recebe a chamada quando o atendente automático é transferido para outros atendentes automáticos ou filas de chamadas que transferem chamadas externamente.
- Em todos os outros cenários de chamada, licencia a conta de recurso do atendente automático ou da fila de chamadas que executa a transferência externa.

> [!NOTE]
> Se o Plano de Chamada atribuído à conta de recurso ficar desabilitado ou for removido, os [Créditos de Comunicação](what-are-communications-credits.md), se estiverem disponíveis no locatário (sem serem atribuídos à conta de recursos), serão consumidos. Se não houver nenhum Plano de Chamada ou Créditos de Comunicação, a chamada falhará.
>
> Há suporte para números de serviço de roteamento direto para filas de atendimento automático e de chamada somente para usuários do Microsoft Teams e agentes de chamada.
> 
> Não há suporte para transferências entre o Plano de Chamada, o Operator Connect e os troncos de Roteamento Direto.
> 
> Em um cenário híbrido, a conta de recursos deve ser criada localmente. Para obter mais informações, consulte [Filas de chamadas do Plan Cloud](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Decisões de negócios

Antes de configurar seus atendentes automáticos e filas de chamadas, há algumas decisões que você deve tomar sobre como usar esses recursos em sua empresa. Essas decisões determinarão as configurações escolhidas quando você configurar seus atendentes automáticos e as filas de chamadas.

Documente suas respostas para essas perguntas e forneça as informações ao administrador que está fazendo a configuração.

- Quais idiomas você precisa? Onde esses idiomas são necessários - qual departamento ou grupo?
- Deseja permitir entradas de voz de chamadores ou apenas de entradas de discagem?
- Você precisa de roteamento de chamadas separado para horários de folga ou feriados? Quais são as horas e feriados?
- Deseja permitir que agentes em uma fila de chamadas optem por não atender chamadas?
- Você deseja que os agentes em suas filas de chamada ou seu operador tenham uma ID de chamador específica se eles discarem para fora?
- Deseja habilitar o [estacionamento e a recuperação de chamadas](call-park-and-retrieve.md) em sua organização para ajudar com entregas de chamadas entre pessoas ou departamentos?
- Para os prompts de voz, você deseja gravar o próprio ou usar a voz gerada pelo sistema?
  - A voz gerada pelo sistema é fácil de atualizar.

## <a name="technical-decisions"></a>Decisões técnicas

Ao usar atendentes automáticos e filas de chamadas para conectar os chamadores às pessoas em sua organização, há algumas decisões técnicas a serem tomadas antes de iniciar a configuração.

Os agentes podem ser adicionados às filas de chamadas das seguintes maneiras:

- Usuários individuais
- Listas de distribuição
- Grupos de segurança, incluindo grupos de segurança habilitados para email
- Grupos do Microsoft 365 ou Teams

Você pode usar uma combinação dessas opções para cada fila, se necessário. Grupos que têm um endereço de email podem ser usados para caixa postal. O uso do Teams oferece muitas vantagens, incluindo armazenamento de arquivos compartilhados e chat entre agentes, uma caixa de correio comum em que as mensagens de voz podem ser recebidas e uma plataforma extensível que pode incluir integração com seus aplicativos de linha de negócios ou Power Apps.

Recomendamos escolher uma estratégia para adicionar agentes de chamada a filas antes de iniciar sua configuração.

Se você tiver uma infraestrutura de fila de atendimento automático e chamada existente e estiver migrando para o Teams, precisará de um plano para transferir seus números de telefone existentes para os novos atendentes automáticos e filas de chamadas. Talvez seja necessário criar uma [ordem de porta](phone-number-calling-plans/port-order-overview.md) para mover seus números de outros provedores. Recomendamos que você adquira temporariamente um ou mais novos números de telefone e teste seus fluxos de fila de atendimento automático e de chamada antes de alterná-los sobre os números que você tem atualmente em serviço.

**O modo de conferência** é uma opção em filas de chamada que reduz significativamente o tempo necessário para conectar chamadas VOIP do Teams e chamadas PSTN a um agente. Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:

- A versão mais recente do cliente da área de trabalho do Microsoft Teams, aplicativo Android ou aplicativo iOS.
- Microsoft Phone System versão 1449/1.0.94.2020051601 ou posterior.
  
Defina contas do Teams de agentes para o modo somente do Teams. Os agentes que não atendem aos requisitos não são incluídos na lista de roteamento de chamadas.

O modo de conferência está habilitado por padrão. Se você tiver agentes que não atendem aos requisitos, o modo de conferência deve ser desabilitado manualmente durante a configuração da fila de chamadas.

Os planos **de fluxo de roteamento** de chamadas ajudam a determinar o roteamento mais eficiente para pessoas que ligam para sua organização. Para saber como planejar o fluxo de roteamento de chamadas, consulte [Planejar o fluxo de roteamento de chamadas](plan-your-call-routing-flow.md).

## <a name="getting-started"></a>Introdução

Depois de concluir as tarefas de planejamento neste artigo, siga estas etapas para configurar os atendentes automáticos e as filas de chamadas:

1. Obtenha os números de serviço necessários para os atendentes automáticos e as filas de chamadas que você deseja estar acessíveis discando diretamente de fora de sua organização. Isso pode incluir [a transferência de números de outro provedor](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [a solicitação de novos números de serviço](getting-service-phone-numbers.md).

2. Obtenha uma [licença de Conta de Recurso de Telefone do Teams](teams-add-on-licensing/virtual-user.md) para cada conta de recurso que você planeja criar. Essas licenças são gratuitas, portanto, sugerimos obter alguns adicionais caso você decida fazer alterações em suas contas de recursos no futuro.

3. [Crie uma conta de recurso](manage-resource-accounts.md) para cada atendente automático e uma fila de chamadas que você deseja criar. Atribua uma licença da Conta de Recurso de Telefone do Teams a cada conta de recurso que será chamada diretamente e, opcionalmente, um número de serviço.

4. [Crie os feriados para os](set-up-holidays-in-teams.md) quais você deseja ter roteamento de chamadas separado em seus atendentes automáticos.

5. Opcionalmente, [configure o estacionamento de chamadas e a recuperação](call-park-and-retrieve.md) se você quiser usar esse recurso para ajudar com transferências de chamadas.

6. Crie os grupos que você deseja usar para conter os agentes de chamada para as filas de chamada.

7. Se você planeja permitir discar por extensão, verifique se você adicionou o número de extensão dos usuários ao perfil do Azure Active Directory (Azure AD).

Depois de concluir as etapas acima, você estará pronto para criar seus atendentes automáticos e filas de chamadas. Como os atendentes automáticos e as filas de chamadas podem redirecionar chamadas uns para os outros, consulte o diagrama de fluxo de trabalho criado para determinar qual atendimento automático ou fila de chamadas deve ser criado primeiro. No exemplo no diagrama acima, você criaria as filas de chamadas de vendas e suporte antes de criar o atendente automático principal da Contoso, pois o atendente automático principal precisa direcionar os chamadores para as filas de chamadas de vendas e suporte.

Confira os seguintes artigos para obter informações sobre como criar atendentes automáticos e filas de chamadas:

- [Configurar um atendente automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md)

> [!IMPORTANT]
> O token GUID de Azure AD de um usuário é armazenado como parte da configuração de fila de atendimento automático ou chamada quando o usuário é configurado como:
>
>  - um atendente automático ou um **usuário autorizado** da fila de chamadas.
>  - um **operador** de atendimento automático.
>  - um **ponto de transferência de pessoa na organização** .
>  - um membro individual de uma fila de chamadas.
> 
> As configurações de fila de atendimento automático e de chamada não são sincronizadas com Azure AD eventos do ciclo de vida.  Os administradores do Teams precisam atualizar manualmente as configurações de fila de atendimento automático e chamada para remover esses dados pessoais quando um usuário incluído na configuração deixar a organização.
>
> Isso não se aplica a associações de agente de fila de chamadas configuradas por meio de listas de distribuição ou canais. Ele também não se aplica aos usuários que são acessados por meio do recurso **Discar por Nome** ou **Discar por Número** de atendentes automáticos.

Se você precisar de recursos mais extensos, como integração com fluxos de trabalho, bots e SMS, considere [Serviços de Comunicação do Azure](/azure/communication-services/overview).

## <a name="related-topics"></a>Tópicos relacionados

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
