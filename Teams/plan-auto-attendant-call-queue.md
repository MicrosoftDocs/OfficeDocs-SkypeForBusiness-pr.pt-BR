---
title: Planejar os atendimentos automáticos e filas de chamada do Teams
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
- m365initiative-voice
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
description: Saiba mais sobre os atendimentos automáticos e filas de chamada e como usá-los para ajudar os chamadores a se moverem por um sistema de menus para alcançar pessoas ou departamentos em sua organização.
ms.openlocfilehash: 65dac48267379d17b76443e42eb70e2e866f6e8f
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125663"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planejar os atendimentos automáticos e filas de chamada do Teams

Os atenderes automáticos permitem configurar opções de menu para rotear chamadas com base na entrada do chamador. Opções de menu, como "Para Vendas, pressione 1.  Para Serviços pressionar 2", para um atender automático, uma organização pode fornecer uma série de opções que orientam os chamadores para seu destino rapidamente, sem depender de um operador humano para lidar com chamadas de entrada.

Filas de chamada são áreas de espera para chamadores. Para situações em que os chamadores precisam falar com alguém com uma especialização específica , como vendas ou serviço, em vez de uma pessoa específica, você pode usar filas de chamada para conectar os chamadores ao grupo de agentes que podem ajudá-los. Os chamadores são colocados em espera até que um agente atribuído à fila está disponível para fazer a chamada.

Usados em conjunto, os atendimentos automáticos e as filas de chamada podem roteá-los facilmente para a pessoa ou o departamento apropriado em sua organização.

## <a name="auto-attendants"></a>Atendedores automáticos

O objetivo principal de um chamador automático é direcionar um chamador para uma pessoa ou departamento apropriado com base na entrada do chamador para as opções de menu fornecidas. Os chamadores podem ser direcionados para pessoas específicas em sua organização, para filas de chamada onde eles esperam para falar com o próximo agente disponível ou para a caixa postal. Diferentes opções de roteamento de chamadas podem ser especificadas para horários comerciais, folgas e feriados.

Os prompts de menu podem ser criados usando texto em fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação com as mãos livres, mas as pessoas que estão ligando também podem usar o teclado do telefone para navegar pelos menus.

Cada assistente automático tem um idioma e um fuso horário específicos. Se você faz negócios em vários idiomas ou em várias partes do mundo, pode criar quantos diferentes assistentes automáticos precisar para acomodar os chamadores.

Para cada assistente automático, você pode configurar um operador. Embora você possa configurar chamadas de operador para ir para uma variedade de destinos, o recurso de operador foi projetado para permitir que os chamadores conversem com uma pessoa específica em sua organização que possa ajudá-los.

Os participantes automáticos podem ser configurados para permitir que os chamadores pesquisem no diretório da sua organização, seja por nome ou por número de extensão. Em um assistente automático, você pode especificar quem está disponível para a pesquisa de diretório escolhendo grupos de usuários para incluir ou excluir. (Isso é conhecido como escopo *de discagem.)*

Os chamadores podem chegar a um atender automaticamente por número de telefone direto, se configurado, ou sendo redirecionados de outro atender automático ou de uma fila de chamadas.

## <a name="call-queues"></a>Filas de chamadas

Uma fila de chamada é análoga a uma sala de espera em um prédio físico. Os chamadores aguardam em espera enquanto as chamadas são roteados para os agentes na fila. Filas de chamada são comumente usadas para funções de vendas e serviços. No entanto, filas de chamadas podem ser usadas para qualquer situação em que o número de chamadas ultrapasse sua capacidade interna, como um recepcionista em uma instalação ocupada.

As filas de chamadas permitem o roteamento específico de chamadas em casos em que o número total de chamadores na fila ou o tempo de espera excede os limites especificados. As chamadas podem ser roteada para pessoas específicas, caixa postal, outras filas de chamadas ou atendedores automáticos.

Como os participantes automáticos, as filas de chamada têm uma configuração de idioma. Você pode usar diferentes filas de chamada se fizer negócios em vários idiomas. Os agentes podem ser membros de mais de uma fila se eles são multilínge.

Para cada fila de chamadas, você pode especificar se os agentes na fila podem optar por não atender chamadas e se as chamadas devem ser roteados para eles com base em suas indicações de presença no Teams.

Você pode atribuir um número de telefone a uma fila de chamadas, no entanto, as filas de chamadas não fornecem roteamento de chamadas separado para horários de folga e feriados. A menos que sua fila de chamadas seja 24 horas por dia, recomendamos atribuir o número de telefone a um atender automático que redireciona para a fila de chamadas durante o horário comercial.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar os atendimentos automáticos e filas de chamada, você precisa dos seguintes recursos:

- Uma conta de recurso para cada atendimento automático e cada fila de chamada
- Um sistema telefônico gratuito – licença de usuário virtual para cada conta de recurso
- Pelo menos um número [de serviço da Microsoft,](getting-service-phone-numbers.md)um número de roteamento direto ou um número híbrido para cada conta de recurso que você deseja discar diretamente
 - O número do serviço pode ser um número de tarifa ou gratuita

Os agentes que recebem chamadas das filas de chamadas devem ser usuários online ou locais habilitados pelo Enterprise Voice. Além disso, se as filas de chamadas estão usando números de Roteamento Direto, os agentes que precisam fazer conferências ou transferências de chamadas também exigem:

- Uma política de roteamento de voz online atribuída se a fila de chamadas usar o modo de transferência
- Uma licença de AudioConferência ou uma política de roteamento de voz online atribuída se a fila de chamadas usar o modo de conferência

Se seus agentes estão usando o aplicativo Microsoft Teams para chamadas na fila de chamadas, eles precisam estar no modo TeamsOnly.

Ao transferir chamadas para um número de telefone externo, a conta de recurso que executa a transferência (ou seja, a associada ao atendimento automático ou fila de chamadas) deve ter um número de telefone e uma licença de Usuário Virtual do Sistema Telefônico do Microsoft 365. Além disso:

- Para uma conta de recurso com um número de Plano de Chamada, atribua uma licença [de Plano de](calling-plans-for-office-365.md) Chamada.
- Para uma conta de recurso com um número de Roteamento Direto, atribua uma [política de roteamento de voz online.](manage-voice-routing-policies.md)

> [!NOTE]
> Os números de serviço de Roteamento Direto para o atendimento automático e filas de chamadas são suportados somente para usuários e agentes de chamada do Microsoft Teams.<br>
> Não há suporte para transferências entre troncos do Plano de Chamada e troncos de Roteamento Direto.

## <a name="business-decisions"></a>Decisões de negócios

Antes de configurar seus atendimentos automáticos e filas de chamada, há algumas decisões que você deve tomar sobre como usar esses recursos em sua empresa. Essas decisões determinarão as configurações que você escolher ao configurar seus atendimentos automáticos e filas de chamada.

Documente suas respostas a essas perguntas e forneça as informações ao administrador que está fazendo a configuração.

- De quais idiomas você precisa? Onde esses idiomas são necessários - qual departamento ou grupo?
- Você deseja permitir entradas de voz de chamadores ou apenas entradas de discagem?
- Você precisa de roteamento de chamadas separado para horários de folga ou feriados? Quais são as horas e feriados?
- Você deseja permitir que os agentes em uma fila de chamadas optem por não atender chamadas?
- Você deseja que os agentes em suas filas de chamada ou seu operador tenham uma ID de chamada específica se eles discarem?
- Você deseja habilitar o estacionamento de chamada e [a](call-park-and-retrieve.md) recuperação em sua organização para ajudar em entregas de chamada entre pessoas ou departamentos?
- Para as solicitações de voz, você deseja gravar sua própria voz ou usar a voz gerada pelo sistema? (A voz gerada pelo sistema é fácil de atualizar.)

## <a name="technical-decisions"></a>Decisões técnicas

Ao usar os atendimentos automáticos e filas de chamada para conectar os chamadores às pessoas em sua organização, há algumas decisões técnicas a tomar antes de iniciar a configuração.

Os agentes podem ser adicionados às filas de chamada das seguintes maneiras:

- Usuários individuais
- Listas de distribuição
- Grupos de segurança, incluindo grupos de segurança habilitados para email
- Grupos ou Equipes do Microsoft 365

Você pode usar uma combinação dessas opções para cada fila, se necessário. Os grupos que têm um endereço de email podem ser usados para a caixa postal. O uso do Teams oferece várias vantagens, incluindo o armazenamento compartilhado de arquivos e o chat entre agentes, uma caixa de correio comum onde as mensagens de voz podem ser recebidas e uma plataforma extensível que pode incluir integração com seus aplicativos de linha de negócios ou power apps.

Recomendamos escolher uma estratégia para adicionar agentes de chamada às filas antes de iniciar a configuração.

Se você tiver um atender automático e uma infraestrutura de fila de chamadas existentes e estiver migrando para o Teams, precisará de um plano para transferir os números de telefone existentes para os novos atenderes automáticos e filas de chamadas. Talvez seja necessário criar um pedido [de portabilidade](phone-number-calling-plans/port-order-overview.md) para mover seus números de outros provedores. Recomendamos que você adquira temporariamente um ou mais novos números de telefone e teste os fluxos de fila de chamadas e o atendimento automático antes de alternar entre os números que você tem no serviço no momento.

*O modo de* conferência é uma opção nas filas de chamadas que reduz significativamente o tempo necessário para conectar chamadas VOIP do Teams e chamadas PSTN a um agente. Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:

- A versão mais recente do cliente de área de trabalho do Microsoft Teams, aplicativo Android ou aplicativo iOS
  - Versão 1449/1.0.94.2020051601 ou posterior do Microsoft Teams
  
Definir as contas do Teams dos agentes para o modo somente do Teams. Os agentes que não atendem aos requisitos não estão incluídos na lista de roteamento de chamadas.

Recomendamos habilite o modo de conferência para suas filas de chamada se todos os agentes estão usando clientes compatíveis.

## <a name="plan-your-call-routing-flow"></a>Planejar seu fluxo de roteamento de chamadas

Como parte do processo de planejamento, recomendamos que você trabalhe o roteamento de chamadas para sua organização em um diagrama. O diagrama ajuda a determinar o roteamento mais eficiente para as pessoas que estão ligando para sua organização. Você também pode usar o diagrama para determinar os atendimentos automáticos e filas de chamada que precisa criar, juntamente com requisitos relacionados, como números de serviço, licenças e contas de recursos.

Vamos ver como os atenderes automáticos e filas de chamadas encaminham chamadas.

Os atenderes automáticos roteam todas as chamadas de uma das seguintes maneiras:

- **Redirecionar imediatamente** - as chamadas podem ser redirecionadas para um dos destinos de roteamento de chamadas (listados abaixo) imediatamente ao atender ou após uma saudação inicial.
- **Redirecionar com base nas** opções de discagem: os chamadores podem ser direcionados para escolher entre as opções atribuídas aos números no teclado de telefone, de 0 a 9. Cada tecla de discagem pode ter destinos de roteamento de chamada.
- **Disque** as pessoas por nome ou extensão- os chamadores podem ser direcionados para discar o número de extensão da pessoa que estão tentando entrar em contato no diretório da sua organização ou por ortografia do nome da pessoa.
- **Desconectar** - um atendimento automático pode desligar a chamada.

> [!NOTE]
> Um único Assistente Automático só pode dar suporte a um único método "discar por".  Para permitir que os chamadores disquem por nome e por número, você precisará criar um atendimento automático que tenha uma opção para discar por nome e outro para discar por extensão.  Cada uma dessas opções será roteada para separar os participantes automáticos configurados para esses cenários de "discagem por".

Quando as chamadas são redirecionadas por um atender automático ou fila de chamadas, você pode escolher entre os seguintes destinos de roteamento de chamada:

- **Pessoa na organização** - uma pessoa em sua organização que pode receber chamadas de voz. Pode ser um usuário online ou um usuário hospedado localmente usando o Skype for Business Server.
- **Aplicativo de voz** – outro atendimento automático ou uma fila de chamadas. Escolha a conta de recurso associada ao destino.
- **Número de telefone externo** – qualquer número de telefone. (Veja [detalhes técnicos da transferência externa).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Caixa** postal : a caixa postal associada a um grupo do Microsoft 365 especificado por você.
- **Operador** (somente o atendimento automático) – o operador definido para o atendimento automático. Definir um operador é opcional. Um operador pode ser qualquer um dos outros destinos nesta lista.

Os atenderes automáticos oferecem opções de roteamento de chamadas separadas para chamadas recebidas fora do horário comercial e em feriados. O roteamento de chamadas após o expediente permite todas as opções listadas acima, enquanto o roteamento de chamadas de feriados permite apenas redirecionar ou desconectar uma chamada, mas nenhuma opção de tecla de discagem.

As filas de chamada item o chamador em espera até que um agente atribuído à fila está disponível para fazer a chamada. Há duas situações em que um chamador pode ser direcionado para fora da fila:

- **Estouro de** chamadas – se o número de chamadas na fila exceder o limite definido, novos chamadores serão redirecionados para fora da fila.
- **Tempo de tempo de** chamada - se um chamador estiver na fila por mais tempo do que a configuração de tempo configurada, ele será redirecionado para fora da fila.

As chamadas redirecionadas para fora de uma fila podem ser enviadas para qualquer um dos destinos de roteamento de chamadas listados acima, exceto para um operador. (As filas de chamada não têm operadores, mas você pode redirecionar os chamadores para o mesmo destino que um operador configurado para um atendimento automático.)

O exemplo a seguir mostra um exemplo de roteamento de chamadas usando os atendimentos automáticos e filas de chamadas.

![Diagrama de roteamento de chamadas usando os atendimentos automáticos e filas de chamadas](media/attendant-and-queue-call-routing.png)

No exemplo acima:

- A tecla zero (0) redireciona os chamadores para um operador. O operador desse atendimento automático foi configurado como uma **Pessoa na organização.**
- A chave (1) redireciona os chamadores para a fila de chamada de vendas. Essa fila de chamada está conectada a uma equipe que contém a equipe de vendas atribuída à fila.
- A chave (2) redireciona os chamadores para a fila de chamada de suporte. Essa fila de chamada está conectada a uma equipe que contém a equipe de suporte atribuída à equipe.
- A fila de chamadas de suporte tem um número de telefone direto por meio de um atender automático. Ter um atendedor automático respondendo à linha de suporte permite separar horários de folga e roteamento de chamadas de feriados.
- A chave três (3) redireciona os usuários para outro assistente automático para o diretório da empresa. O assistente automático de diretório da empresa permite que os chamadores liguem para indivíduos na organização discando seu nome ou extensão.

Recomendamos que você crie um ou mais diagramas semelhantes ao acima para mapear o roteamento de chamadas. Inclua o seguinte no diagrama ou na documentação que o acompanha:

- Quais atenderes automáticos terão acesso direto por meio de números de telefone?
- Quais são os requisitos de roteamento de folgas e feriados para cada atendimento automático?
- A associação para cada fila de chamada. (Você pode adicionar usuários individualmente ou mapear a fila para diferentes tipos de grupos. Mapear uma fila para uma equipe oferece a experiência mais versátil.)

Aqui estão algumas práticas recomendadas de roteamento de chamadas:

- Analise seu sistema de chamadas existente e analise os tipos e a frequência de chamadas recebidas. Use essas informações para ajudar a informar o seu atendimento automático e a estrutura da fila de chamada.
- Coloque as opções mais comuns mais cedo no menu para encaminhar chamadas o mais rapidamente possível.
- Evite conectar números de serviço diretamente às filas de chamada, a menos que as filas sejam disponibilizadas 24 horas por dia, 7 dias por dia. As filas de chamada não permitem a manipulação de chamada separada para horários de folga ou feriados. Se você quiser ter uma fila com um número direto, atribua o número a um atendimento automático que redireciona automaticamente para a fila durante o horário comercial.
- Se você receber várias chamadas solicitando informações básicas sobre sua empresa, como horário comercial, local ou endereço do site, considere a possibilidade de criar um atendedores automáticos para responder a essas perguntas com mensagens gravadas.
- Mantenha a lista de itens de menu para cinco ou menos. Os chamadores podem ter problemas para se lembrar de mais de cinco opções. Use os participantes automáticos aninhados se mais opções são necessárias para encaminhar uma chamada corretamente.
- Descreva o serviço primeiro, seguido da opção de pressionar (por exemplo: Para Vendas pressione 1) em vez de o contrário (por exemplo. Pressione 1 para Vendas).
- A terminologia do usuário que seus chamadores entenderão, em vez do que você pode usar internamente.
- Evite atualizações frequentes no roteamento de chamadas. Se você alterar suas opções de menu para um assistente automático no futuro, chame-o no aviso de voz para os primeiros 30 dias.

## <a name="getting-started"></a>Introdução

Depois de concluir as tarefas de planejamento neste artigo, siga estas etapas para configurar os assistentes automáticos e as filas de chamada:

1. Para obter os números de serviço necessários para os atendimentos automáticos e filas de chamada que você deseja que sejam acessíveis, ligue diretamente de fora da sua organização. Isso pode incluir [a transferência de números de outro provedor ou](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) a [solicitação de novos números de serviço.](getting-service-phone-numbers.md)

2. Obter um [Sistema de Telefonia – Licença de Usuário Virtual](teams-add-on-licensing/virtual-user.md) para cada conta de recurso que você planeja criar. Essas licenças são gratuitas, portanto, sugerimos receber algumas extra caso você decida fazer alterações nas suas contas de recursos no futuro.

3. [Crie uma conta de recurso](manage-resource-accounts.md) para cada atendimento automático e fila de chamada que você deseja criar. Atribua a cada conta um Sistema telefônico – licença de Usuário Virtual e, opcionalmente, um número de serviço.

4. [Crie os feriados para](set-up-holidays-in-teams.md) os quais você deseja ter o roteamento de chamadas separado em seus atendimentos automáticos.

5. Opcionalmente, [configurar o](call-park-and-retrieve.md) parque de transporte de chamada e a recuperação se você quiser usar esse recurso para ajudar com transferências de chamada.

6. Crie os grupos que você deseja usar para conter os agentes de chamada para as filas de chamada.

7. Se você planeja permitir a discagem por extensão, verifique se adicionou o número de extensão dos usuários ao perfil do Azure Active Directory.

Depois de concluir as etapas acima, você estará pronto para criar seus atendimentos automáticos e filas de chamada. Como os atenderes automáticos e as filas de chamada podem redirecionar chamadas uns para os outros, confira o diagrama de fluxo de trabalho que você criou para determinar qual atender automático ou fila de chamadas deve ser criada primeiro. No exemplo no diagrama acima, você criaria as filas de chamada de vendas e suporte antes de criar o atendimento automático principal da Contoso, pois o principal atendimento automático precisa direcionar os chamadores para as filas de vendas e dar suporte a chamada.

Confira os artigos a seguir para obter informações sobre como criar atendimentos automáticos e filas de chamada:

- [Configurar um assistente automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Tópicos relacionados

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Disponibilidade de audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Criar uma fila de chamada – tutorial para pequenas empresas](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurar um assistente automático – tutorial para pequenas empresas](business-voice/create-a-phone-system-auto-attendant-smb.md)
