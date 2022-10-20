---
title: Planejar seu fluxo de roteamento de chamadas para o Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
description: Saiba como planejar seu fluxo de roteamento de chamadas para atendedores automáticos e filas de chamadas no Microsoft Teams.
ms.openlocfilehash: 876198578bfc0387f00890d393a90ed73bc215c5
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614454"
---
# <a name="plan-your-call-routing-flow"></a>Planejar o fluxo de roteamento de chamadas

Como parte do processo de planejamento, recomendamos que você trabalhe o roteamento de chamadas para sua organização em um diagrama. O diagrama ajuda a determinar o roteamento mais eficiente para as pessoas que estão ligando para sua organização. Você também pode usar o diagrama para determinar os atendedores automáticos e as filas de chamadas que você precisa criar, juntamente com os requisitos relacionados, como números de serviço, licenças e contas de recursos.

Vamos examinar como atendedores automáticos e filas de chamadas roteiam chamadas.

Os atendedores automáticos roteiam todas as chamadas de uma das seguintes maneiras:

- **Redirecionar imediatamente** – as chamadas podem ser redirecionadas para um dos destinos de roteamento de chamadas (listados abaixo) imediatamente após o atendimento ou após uma saudação inicial.
- **Redirecionar com base nas** opções de discagem – os chamadores podem ser direcionados para escolher entre as opções atribuídas aos números em seu teclado de telefone, 0-9. Cada chave de discagem pode receber destinos de roteamento de chamadas.
- **Discar** pessoas por nome ou extensão – os chamadores podem ser direcionados para discar o número de extensão da pessoa que estão tentando acessar no diretório da sua organização ou ortografia do nome da pessoa.
- **Desconectar** - um atendedor automático pode desligar a chamada.

> [!NOTE]
> Um único atendedor automático só pode dar suporte a um único método "dial by".  Para permitir que os chamadores disquem por nome e por número, você precisará criar um atendedor automático que tenha uma opção para discar por nome e o outro para discar por extensão.  Cada uma dessas opções será roteada para atendedores automáticos separados configurados para esses cenários de "discagem por".

Quando as chamadas são redirecionadas por um atendedor automático ou fila de chamadas, você pode escolher entre os seguintes destinos de roteamento de chamadas:

- **Pessoa na organização -** uma pessoa em sua organização que é capaz de receber chamadas de voz. Pode ser um usuário online ou um usuário hospedado localmente usando Skype for Business Server.
- **Aplicativo de voz** – outro atendedor automático ou uma fila de chamadas. Escolha a conta de recurso associada ao destino.
- **Número de telefone externo** - qualquer número de telefone. Consulte [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md?tabs=additional-resources).

- **Caixa** postal – a caixa de correio de voz associada a um grupo do Microsoft 365 especificado por você. Você pode escolher se deseja transcrições de caixa postal e "Deixe uma mensagem após o tom". prompt do sistema.
- **Operador** (somente atendedor automático) – o operador definido para o atendedor automático. Definir um operador é opcional. Um operador pode ser qualquer um dos outros destinos nesta lista.

Os atendedores automáticos oferecem opções de roteamento de chamadas separadas para chamadas recebidas fora do horário comercial e em feriados.

As filas de chamadas positam o chamador em espera até que um agente atribuído à fila esteja disponível para fazer sua chamada. Há duas situações em que um chamador pode ser direcionado para fora da fila:

- **Estouro** de chamada – se o número de chamadas na fila exceder o limite definido, novos chamadores serão redirecionados para fora da fila.
- **Tempo limite de** chamada – se um chamador estiver na fila por mais tempo do que a configuração de tempo limite definida, ele será redirecionado para fora da fila.

Chamadas redirecionadas de uma fila podem ser enviadas para qualquer um dos destinos de roteamento de chamadas listados acima, exceto para um operador. (As filas de chamadas não têm operadores, mas você pode redirecionar os chamadores para o mesmo destino que um operador configurado para um atendedor automático.)

O exemplo a seguir mostra um exemplo de roteamento de chamadas usando atendedores automáticos e filas de chamadas.

![Diagrama de roteamento de chamadas usando atendedores automáticos e filas de chamadas.](media/attendant-and-queue-call-routing.png)

No exemplo acima:

- A chave zero (0) redireciona os chamadores para um operador. O operador para esse atendedor automático foi configurado como **uma Pessoa na organização**.
- A chave (1) redireciona os chamadores para a fila de chamadas de vendas. Essa fila de chamadas está conectada a uma equipe que contém a equipe de vendas atribuída à fila.
- A chave dois (2) redireciona os chamadores para a fila de chamadas de suporte. Essa fila de chamadas está conectada a uma equipe que contém a equipe de suporte atribuída à equipe.
- A fila de chamadas de suporte tem um número de telefone direto por meio de um atendedor automático intermediador. Ter um atendedor automático na linha de suporte permite que o roteamento de chamadas de feriados e fora do horário de folga seja separado.
- A chave de três (3) redireciona os usuários para outro atendedor automático para o diretório da empresa. O atendedor automático do diretório da empresa permite que os chamadores liguem para indivíduos na organização discando seu nome ou extensão.

Recomendamos que você crie um ou mais diagramas semelhantes ao mostrado acima para mapear o roteamento de chamadas. Inclua o seguinte no diagrama ou na documentação que o acompanha:

- Quais atendedores automáticos terão acesso direto por meio de números de telefone?
- Quais são os requisitos de roteamento de folga e feriados para cada atendedor automático?
- A associação para cada fila de chamadas. (Você pode adicionar usuários individualmente ou mapear a fila para diferentes tipos de grupos. Mapear uma fila para uma equipe fornece a experiência mais versátil.)

Aqui estão algumas práticas recomendadas de roteamento de chamadas:

- Examine o sistema de chamadas existente e analise os tipos e a frequência de chamadas de entrada. Use essas informações para ajudar a informar o atendedor automático e a estrutura da fila de chamadas.
- Coloque as opções mais comuns mais cedo no menu para rotear chamadas o mais rápido possível.
- Evite conectar números de serviço diretamente a filas de chamadas, a menos que as filas estejam disponíveis 24 horas por dia, 7 dias por semana. As filas de chamadas não permitem a manipulação de chamadas separadas para fora do horário comercial ou feriados. Se você quiser ter uma fila com um número direto, atribua o número a um atendedor automático que redireciona automaticamente para a fila durante o horário comercial.
- Se você receber várias chamadas solicitando informações básicas sobre sua empresa, como horário comercial, local ou endereço do site, considere criar um atendedor automático para responder a essas perguntas com mensagens gravadas.
- Mantenha a lista de itens de menu para cinco ou menos. Os chamadores podem ter problemas para se lembrar de mais de cinco opções. Use atendedores automáticos aninhados se mais opções forem necessárias para rotear corretamente uma chamada.
- Descreva o serviço primeiro, seguido pela opção de pressionar (por exemplo: Para Vendas pressione 1) em vez do contrário (por exemplo, Pressione 1 para Vendas).
- A terminologia do usuário que seus chamadores entenderão em vez do que você pode usar internamente.
- Evite atualizações frequentes para roteamento de chamadas. Se você alterar suas opções de menu para um atendedor automático no futuro, chame-o nos prompts de voz para os primeiros 30 dias.
