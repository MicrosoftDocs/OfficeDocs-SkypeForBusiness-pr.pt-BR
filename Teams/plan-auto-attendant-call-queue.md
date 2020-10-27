---
title: Planejar os atendedores automáticos e as filas de chamadas do teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Saiba mais sobre atendedores automáticos e filas de chamadas e como usá-los para ajudar os chamadores a percorrer um sistema de menu para alcançar pessoas ou departamentos em sua organização.
ms.openlocfilehash: 7407b9a2bbcd8d8b3fb5d15202d1bba518953f07
ms.sourcegitcommit: 6c24c77f0aad693d45dd5657c12bf876f62c495b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2020
ms.locfileid: "48765938"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planejar os atendedores automáticos e as filas de chamadas do teams

Os atendedores automáticos permitem que você configure opções de menu para direcionar chamadas com base na entrada do chamador. Opções de menu, como "para vendas, pressione 1.  Para os serviços pressione 2 ", para um atendedor automático, deixe uma organização oferecer uma série de opções que orientam o atendimento ao seu destino rapidamente, sem depender de uma operadora de pessoas para lidar com chamadas de entrada.

As filas de chamadas estão aguardando áreas para chamadores. Para situações em que os chamadores precisam se comunicar com alguém com uma especialidade específica, como vendas ou serviço, em vez de uma pessoa específica, você pode usar as filas de chamadas para conectar os chamadores ao grupo de agentes que podem auxiliá-los. Os chamadores são colocados em espera até que um agente atribuído à fila esteja disponível para fazer a chamada.

Usados juntos, atendedores automáticos e filas de chamadas podem facilmente direcionar os chamadores para a pessoa ou departamento apropriado de sua organização.

## <a name="auto-attendants"></a>Atendedores automáticos

O objetivo principal de um atendedor automático é direcionar um chamador para uma pessoa ou departamento apropriado com base na entrada do chamador para as opções de menu fornecidas. Os chamadores podem ser direcionados para pessoas específicas dentro de sua organização, para fazer chamadas de filas onde elas esperam para falar com o próximo agente disponível ou para o correio de voz. Diferentes opções de roteamento de chamadas podem ser especificadas para horário comercial, horas de folga e feriados.

Os prompts de menu podem ser criados usando a conversão de texto em fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação viva-voz, mas as pessoas que fizerem chamadas também poderão usar o teclado numérico do telefone para navegar pelos menus.

Cada atendedor automático tem um idioma e um fuso horário específicos. Se você faz negócios em vários idiomas ou em várias partes do mundo, pode criar quantos atendedores automáticos diferentes forem necessários para atender aos seus chamadores.

Para cada atendedor automático, você pode configurar um operador. Embora você possa configurar as chamadas do operador para ir para uma variedade de destinos, o recurso de operador foi projetado para permitir que os chamadores conversem com uma pessoa específica em sua organização, que pode ajudá-los.

Atendedores automáticos podem ser configurados para permitir que os chamadores pesquisem o diretório da sua organização, seja por nome ou por número de ramal. Em um atendedor automático, você pode especificar quem está disponível para a pesquisa de diretório, escolhendo grupos de usuários a serem incluídos ou excluídos. (Isso é conhecido como *escopo de discagem* .)

Os chamadores podem alcançar um atendedor automático por número de telefone direto, se configurado ou sendo Redirecionado de outro atendedor automático ou de uma fila de chamadas.

## <a name="call-queues"></a>Filas de chamadas

Uma fila de chamadas é análoga a uma sala de espera em um prédio físico. Os chamadores aguardam em espera enquanto as chamadas são roteadas para os agentes na fila à medida que se tornam disponíveis. As filas de chamadas são geralmente usadas para vendas e funções de serviço. No entanto, as filas de chamadas podem ser usadas para qualquer situação em que o número de chamadas excede sua capacidade interna, como uma recepcionista em um recurso ocupado.

As filas de chamadas permitem um roteamento específico de chamadas em casos onde o número total de chamadores na fila ou o tempo de espera excede os limites que você especificar. As chamadas podem ser roteadas para pessoas específicas, correio de voz, outras filas de chamadas ou atendedores automáticos.

Assim como atendedores automáticos, as filas de chamadas têm uma configuração de idioma. Você pode usar diferentes filas de chamadas se fizer negócios em vários idiomas. Os agentes podem ser membros de mais de uma fila se estiverem vários idiomas.

Para cada fila de chamadas, você pode especificar se os agentes na fila podem optar por não fazer chamadas e se as chamadas devem ser encaminhadas para elas com base na indicação de presença no Microsoft Teams.

Você pode atribuir um número de telefone a uma fila de chamadas, mas as filas de chamadas não fornecem um roteamento de chamadas separado para horas de folga e feriados. A menos que sua fila de chamadas seja equipada 24/7, recomendamos atribuir o número de telefone a um atendedor automático que redireciona para a fila de chamadas durante o horário comercial.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar atendedores automáticos e filas de chamadas, você precisa dos seguintes recursos:

- Uma conta de recurso para cada atendedor automático e todas as filas de chamadas
- Um sistema de telefonia livre-licença de usuário virtual para cada conta de recurso
- Um número de serviço para cada atendedor automático ou fila de chamadas que você deseja que seja diretamente discável
- Um plano de chamada para cada pessoa que receberá chamadas na fila de chamadas

> [!NOTE]
> Os números do serviço de roteamento direto para atendedor automático e filas de chamadas são suportados somente para usuários do Microsoft Teams e para agentes de chamadas.

## <a name="business-decisions"></a>Decisões comerciais

Antes de configurar seus atendedores automáticos e filas de chamadas, há algumas decisões que você deve tomar sobre como usar esses recursos na sua empresa. Essas decisões determinarão as configurações escolhidas quando você configura os atendedores automáticos e as filas de chamadas.

Documente as respostas a essas perguntas e forneça as informações para o administrador fazer a configuração.

- Quais idiomas são necessários? Onde são necessários estes idiomas-qual departamento ou grupo?
- Deseja permitir entradas de voz de chamadores ou somente entradas de discagem?
- Você precisa de um encaminhamento de chamadas separado para horas ou feriados? Quais são as horas e os feriados?
- Você deseja permitir que os agentes em uma fila de chamadas desautorizassem de fazer chamadas?
- Você deseja que os agentes em suas filas de chamadas ou sua operadora tenham uma ID de chamada específica se eles discarem?
- Você deseja habilitar o [estacionamento e a recuperação de chamadas](call-park-and-retrieve.md) em sua organização para ajudar a fazer chamadas para entregas entre pessoas ou departamentos?
- Para os prompts de voz, você quer gravar seu próprio ou usar a voz gerada pelo sistema? (É fácil atualizar a voz gerada pelo sistema.)

## <a name="technical-decisions"></a>Decisões técnicas

Ao usar atendedores automáticos e filas de chamadas para conectar os chamadores às pessoas em sua organização, há algumas decisões técnicas a serem tomadas antes de iniciar a configuração.

Os agentes podem ser adicionados a filas de chamadas das seguintes maneiras:

- Usuários individuais
- Listas de distribuição
- Grupos de segurança, incluindo os grupos de segurança habilitados para email
- Grupos ou equipes do Microsoft 365

Você pode usar uma combinação dessas opções para cada fila, se necessário. Os grupos que têm um endereço de email podem ser usados para correio de voz. Usar o Microsoft Teams oferece várias vantagens, incluindo armazenamento de arquivos compartilhado e chats entre agentes, uma caixa de correio comum em que os correios de voz podem ser recebidos e uma plataforma extensível que pode incluir a integração com os aplicativos de linha de negócios ou aplicativos de energia.

Recomendamos escolher uma estratégia para adicionar agentes de chamadas a filas antes de iniciar a configuração.

Se você tiver uma infraestrutura de atendedor automático e de fila de chamadas existente e estiver migrando para o Microsoft Teams, será necessário um plano para transferir os números de telefone existentes para os novos atendedores automáticos e filas de chamadas. Talvez seja necessário criar um [pedido de portabilidade](phone-number-calling-plans/port-order-overview.md) para mover seus números de outros provedores. Recomendamos que você adquira temporariamente um ou mais números de telefone novos e teste o atendedor automático e os fluxos de fila de chamadas antes de alterá-los pelos números que você tem em serviço no momento.

O *modo de conferência* é uma opção em filas de chamadas que reduz significativamente o tempo necessário para conectar chamadas de VoIP de equipe e chamadas PSTNs a um agente. Para que o modo de conferência funcione, os agentes na fila de chamadas devem usar um dos seguintes clientes:

- A versão mais recente do cliente de desktop do Microsoft Teams, do aplicativo Android ou do aplicativo iOS
  - Microsoft Teams Phone versão 1449/1.0.94.2020051601 ou posterior
  
Definir contas de equipe dos agentes para o modo somente do teams. Os agentes que não atendem aos requisitos não são incluídos na lista de circulação de chamadas.

Recomendamos habilitar o modo de conferência para suas filas de chamadas se os seus agentes estiverem usando clientes compatíveis.

> [!NOTE]
> Ocupado em ocupado não é compatível com o modo de conferência. Os agentes em chamadas de fila de não chamada ainda poderão ser apresentados com uma chamada na fila de chamadas se o roteamento baseado em presença não estiver habilitado.

## <a name="plan-your-call-routing-flow"></a>Planejar o fluxo de roteamento de chamadas

Como parte do processo de planejamento, recomendamos que você trabalhe no roteamento de chamadas para sua organização em um diagrama. O diagrama ajuda a determinar o roteamento mais eficiente para as pessoas que fizerem chamadas para a sua organização. Você também pode usar o diagrama para determinar os atendedores automáticos e as filas de chamadas que você precisa criar, juntamente com requisitos relacionados, como números de serviço, licenças e contas de recursos.

Vamos examinar como atendedores automáticos e as filas de chamadas roteiam chamadas.

Atendedores automáticos roteiam todas as chamadas de uma das seguintes maneiras:

- **Redirecionar imediatamente** -as chamadas podem ser redirecionadas para um dos destinos de roteamento de chamadas (listados abaixo) imediatamente após a resposta ou após uma saudação inicial.
- **Redirecionar com base nas opções de discagem** -os chamadores podem ser direcionados para escolher entre as opções atribuídas aos números no teclado de telefone, 0-9. Cada chave de discagem pode ser atribuída a destinos de roteamento de chamadas.
- **Discar pessoas por nome ou extensão** -os chamadores podem ser direcionados para discar o número do ramal da pessoa que ele está tentando acessar no diretório da sua organização ou verificando a ortografia do nome da pessoa.
- **Desconectar** -um atendedor automático pode desligar a chamada.

> [!NOTE]
> Um único atendedor automático pode dar suporte apenas a um único método "discar por".  Para permitir que os chamadores disquem por nome e número, você precisará criar um atendedor automático que tenha uma opção para discar por nome e o outro para discar por extensão.  Cada uma dessas opções irá direcionar para os cenários de "discar por" separados.

Quando as chamadas são redirecionadas por um atendedor automático ou fila de chamadas, você pode escolher entre os seguintes destinos de roteamento de chamadas:

- **Pessoa na organização** -uma pessoa em sua organização que pode receber chamadas de voz. Pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server.
- **Aplicativo de voz** -outro atendedor automático ou uma fila de chamadas. Escolha a conta do recurso associada ao destino.
- **Número de telefone externo** – qualquer número de telefone. (Veja [detalhes técnicos da transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- Correio **de voz-a** caixa de correio de voz associada a um grupo do Microsoft 365 que você especificar.
- **Operator** (somente atendedor automático)-o operador definido para o atendedor automático. A definição de um operador é opcional. Um operador pode ser qualquer um dos outros destinos nesta lista.

Atendedores automáticos oferecem opções de roteamento de chamadas separadas para chamadas recebidas fora do horário comercial e em feriados. O encaminhamento de chamadas após o expediente permite todas as opções listadas acima, enquanto o encaminhamento de chamadas de feriados permite redirecionar ou desconectar uma chamada, mas nenhuma opção de tecla de discagem.

As filas de chamadas posicionam o chamador em espera até que um agente atribuído à fila esteja disponível para fazer a chamada. Há duas situações em que um chamador pode ser direcionado da fila:

- **Estouro de chamadas** -se o número de chamadas na fila exceder o limite definido, novos chamadores serão redirecionados da fila.
- **Tempo limite da chamada** -se um chamador estivesse na fila mais tempo do que a configuração de tempo limite configurada, ele será redirecionado para fora da fila.

Chamadas redirecionadas de uma fila podem ser enviadas para qualquer um dos destinos de roteamento de chamadas listados acima, exceto para um operador. (As filas de chamadas não têm operadores, mas você pode redirecionar chamadores para o mesmo destino de uma operadora que você configurou para um atendedor automático.)

O exemplo a seguir mostra um exemplo de roteamento de chamadas usando atendedores automáticos e filas de chamadas.

![Diagrama de encaminhamento de chamadas usando atendedores automáticos e filas de chamadas](media/attendant-and-queue-call-routing.png)

No exemplo acima:

- A chave zero (0) redireciona os chamadores para um operador. A operadora desse atendedor automático foi configurada como uma **pessoa na organização** .
- A chave um (1) redireciona os chamadores para a fila de chamadas de vendas. Esta fila de chamadas está conectada a uma equipe que contém a equipe de vendas atribuída à fila.
- As duas (2) teclas redirecionam os chamadores para a fila de chamadas de chamadas de suporte. Esta fila de chamadas está conectada a uma equipe que contém a equipe de suporte atribuída à equipe.
- A fila de chamadas de suporte tem um número de telefone direto por meio de um atendedor automático interveniente. Ter um atendedor automático responda à linha de suporte permite horas de desativação e encaminhamento de chamadas de férias.
- A tecla três (3) redireciona os usuários para outro atendedor automático do diretório da empresa. O atendedor automático do diretório da empresa permite que os chamadores chamem pessoas na organização discando seu nome ou extensão.

Recomendamos que você crie um ou mais diagramas semelhantes ao acima para mapear o encaminhamento de chamadas. Certifique-se de incluir o seguinte no seu diagrama ou documentação que acompanha:

- Quais atendedores automáticos terão acesso direto por números de telefone?
- Quais são os requisitos de roteamento fora de horas e de férias para cada atendedor automático?
- A associação para cada fila de chamadas. (Você pode adicionar usuários individualmente ou mapear a fila para diferentes tipos de grupos. Mapear uma fila para uma equipe oferece a experiência mais versátil.)

Veja algumas práticas recomendadas de roteamento de chamadas:

- Examine seu sistema de chamadas existente e analise os tipos e a frequência das chamadas recebidas. Use essas informações para ajudar a informar o atendedor automático e a estrutura da fila de chamadas.
- Coloque as opções mais comuns mais antigas do menu para direcionar as chamadas o mais rápido possível.
- Evite conectar números de serviço diretamente a filas de chamadas, a menos que as filas estejam disponíveis 24/7. As filas de chamadas não permitem a manipulação de chamadas em separado por horas ou feriados. Se você quiser ter uma fila com um número direto, atribua o número a um atendedor automático que será redirecionado automaticamente para a fila durante o horário comercial.
- Se você receber várias chamadas que solicitam informações básicas sobre a sua empresa, como horário comercial, local ou endereço do site, considere a criação de um atendedor automático para responder a essas perguntas com mensagens gravadas.
- Manter a lista de itens de menu para cinco ou menos. Os chamadores podem ter problemas para lembrar-se de mais de cinco opções. Use atendedores automáticos aninhados se mais opções forem necessárias para direcionar uma chamada apropriadamente.
- Descreva o serviço primeiro e, em seguida, pressione a opção para pressionar (por exemplo, para vendas, pressione 1) em vez de o contrário (por exemplo, Pressione 1 para vendas.
- Terminologia do usuário que seus chamadores compreenderão em vez do que você pode usar internamente.
- Evitar atualizações frequentes para roteamento de chamadas. Se você alterar as opções de menu para um atendedor automático no futuro, ligue para isso nos prompts de voz para os primeiros 30 dias.

## <a name="resource-accounts-and-phone-numbers"></a>Contas de recursos e números de telefone

O Microsoft Teams usa *[contas de recursos](manage-resource-accounts.md)* para conectar atendedores automáticos e filas de chamadas para cada um deles e atribuir a eles números de telefone, se desejado.

- Cada fila de chamadas e atendedor automático requer pelo menos uma conta do recurso.
- Cada conta de recurso requer um sistema telefônico gratuito-licença de usuário virtual.
- Uma conta de recurso pode, opcionalmente, atribuir um ou mais números de serviço. (Esse é o modo como os números de telefone são atribuídos aos atendedores automáticos e às filas de chamadas.)

Você pode atribuir um [número de serviço da Microsoft](getting-service-phone-numbers.md), um número de roteamento direto ou um número híbrido a uma conta de recurso.

Você pode usar números de serviço de chamada tarifada ou gratuita. Você não pode usar números de telefone de usuários para atendedores automáticos ou filas de chamadas.

## <a name="getting-started"></a>Introdução

Depois de concluir as tarefas de planejamento neste artigo, siga estas etapas para obter seus atendedores automáticos e as filas de chamadas configuradas:

1. Obtenha os números de serviço de que você precisa para os atendedores automáticos e as filas de chamadas que você deseja que sejam acessíveis pela discagem direta de fora da sua organização. Isso pode incluir a [transferência de números de outro provedor](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou a [solicitação de novos números de serviço](getting-service-phone-numbers.md).

2. Obter um [sistema telefônico-licença de usuário virtual](teams-add-on-licensing/virtual-user.md) para cada conta de recurso que você planeja criar. Essas licenças são gratuitas, portanto, sugerimos que você tenha alguns recursos adicionais para que você decida fazer alterações em suas contas de recursos no futuro.

3. [Crie uma conta de recurso](manage-resource-accounts.md) para cada atendedor automático e fila de chamadas que você deseja criar. Atribua a cada conta um sistema telefônico-licença de usuário virtual e, opcionalmente, um número de serviço.

4. [Crie os feriados](set-up-holidays-in-teams.md) para os quais você deseja ter roteamento de chamadas separado nos atendedores automáticos.

5. Opcionalmente, [Configure o estacionamento e a recuperação de chamadas](call-park-and-retrieve.md) se quiser usar esse recurso para ajudar com transferências de chamadas.

6. Crie os grupos que você deseja usar para conter os agentes de chamada para as filas de chamadas.

7. Se você pretende permitir discagem por extensão, certifique-se de ter adicionado o número de extensão dos usuários ao perfil do Active Directory do Azure.

Depois de concluir as etapas acima, você estará pronto para criar seus atendedores automáticos e filas de chamadas. Como atendedores automáticos e filas de chamadas podem redirecionar chamadas para as outras, consulte o diagrama de fluxo de trabalho que você criou para determinar qual atendedor automático ou fila de chamadas deve ser criado primeiro. No exemplo do diagrama acima, você criaria as filas de chamadas de vendas e suporte antes de criar o atendedor automático principal da Contoso porque o atendedor automático principal precisa direcionar os chamadores para as filas de chamadas de vendas e suporte.

Consulte os artigos a seguir para obter informações sobre como criar atendedores automáticos e filas de chamadas:

- [Configurar um atendedor automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Tópicos relacionados

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Disponibilidade de audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Exemplo de pequenas empresas - Configurar um atendedor automático](/microsoftteams/tutorial-org-aa)
