---
title: Planejar Teams atendimentos automáticos e filas de chamada
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Saiba mais sobre os atendimentos automáticos e filas de chamada e como usá-los para ajudar os chamadores a passar por um sistema de menus para alcançar pessoas ou departamentos em sua organização.
ms.openlocfilehash: 89c799f5d42adc3367f027a1dec258ba16d97aa6
ms.sourcegitcommit: c7904086e6956ad8d0e5544530bcc90d608b6e6a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2022
ms.locfileid: "62039884"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planejar Teams atendimentos automáticos e filas de chamada

Os atendentes automáticos permitem configurar opções de menu para rotear chamadas com base na entrada do chamador. Opções de menu, como "Para Vendas, pressione 1.  Para Serviços pressionar 2", para um atendimento automático, uma organização permite que uma organização forneça uma série de opções que orientam os chamadores para seu destino rapidamente, sem depender de um operador humano para lidar com chamadas de entrada.

Filas de chamada são áreas de espera para chamadores. Para situações em que os chamadores precisam chegar a alguém com uma especialidade específica , como vendas ou serviço, em vez de uma pessoa específica, você pode usar filas de chamada para conectar chamadores ao grupo de agentes que podem ajudá-los. Os chamadores são colocados em espera até que um agente atribuído à fila está disponível para fazer a chamada.

Usados em conjunto, os atendimentos automáticos e filas de chamada podem roteá-los facilmente para a pessoa ou departamento apropriado em sua organização.

## <a name="auto-attendants"></a>Atendedores automáticos

O principal objetivo de um atendimento automático é direcionar um chamador para uma pessoa ou departamento apropriado com base na entrada do chamador para as opções de menu fornecidas. Os chamadores podem ser direcionados para pessoas específicas em sua organização, para chamar filas em que aguardam para falar com o próximo agente disponível ou para a caixa postal. Diferentes opções de roteamento de chamadas podem ser especificadas para horários comerciais, horários de folga e feriados.

Os prompts de menu podem ser criados usando texto para fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação sem mãos, mas as pessoas que estão ligando também podem usar o teclado do telefone para navegar nos menus.

Cada atendente automático tem um idioma e fuso horário específicos. Se você fizer negócios em vários idiomas ou em várias partes do mundo, poderá criar tantos atendimentos automáticos diferentes quanto precisar para acomodar seus chamadores.

Para cada atendente automático, você pode configurar um operador. Embora você possa configurar chamadas de operador para ir para vários destinos, o recurso de operador foi projetado para permitir que os chamadores conversem com uma pessoa específica em sua organização que possa ajudá-los.

Os atendimentos automáticos podem ser configurados para permitir que os chamadores pesquisem o diretório da sua organização, por nome ou por número de extensão. Em um atendimento automático, você pode especificar quem está disponível para a pesquisa de diretório escolhendo grupos de usuários para incluir ou excluir. (Isso é conhecido como escopo *de discagem*.)

Os chamadores podem alcançar um atendimento automático pelo número de telefone direto, se configurado ou redirecionado de outro atendimento automático ou de uma fila de chamadas.

## <a name="call-queues"></a>Filas de chamadas

Uma fila de chamada é análoga a uma sala de espera em um edifício físico. Os chamadores aguardam em espera enquanto as chamadas são roteados para os agentes na fila. Filas de chamada são comumente usadas para vendas e funções de serviço. No entanto, filas de chamadas podem ser usadas para qualquer situação em que o número de chamadas exceda sua capacidade interna, como uma recepcionista em uma instalação de ocupado.

Filas de chamadas permitem roteamento específico de chamadas em casos em que o número total de chamadores na fila ou o tempo de espera excede os limites especificados. As chamadas podem ser roteados para pessoas específicas, caixa postal, outras filas de chamadas ou atendedores automáticos.

Como os atendimentos automáticos, as filas de chamada têm uma configuração de idioma. Você pode usar filas de chamada diferentes se fizer negócios em vários idiomas. Os agentes podem ser membros de mais de uma fila se eles são multilínge.

Para cada fila de chamadas, você pode especificar se os agentes na fila podem optar por não atender chamadas e se as chamadas devem ser roteados para eles com base na indicação de presença no Teams.

Você pode atribuir um número de telefone a uma fila de chamadas, no entanto, as filas de chamada não fornecem roteamento de chamadas separados para horários de folga e feriados. A menos que sua fila de chamadas esteja com funcionários 24/7, recomendamos atribuir o número de telefone a um atendimento automático que redireciona para a fila de chamadas durante o horário comercial.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar os atendimentos automáticos e filas de chamada, você precisa dos seguintes recursos:

- Uma conta de recurso para cada atendimento automático e cada fila de chamada
- Uma licença Microsoft Teams Telefone de usuário virtual para cada conta de recurso
- Pelo menos um número de serviço da [Microsoft,](getting-service-phone-numbers.md)um número de operador Conexão, um número de Roteamento Direto ou um número híbrido para cada conta de recurso que você deseja discar diretamente
 - O número de serviço pode ser um número gratuito ou de tarifação gratuita

> [!NOTE]
> As contas de recursos estão desabilitadas para entrar e devem permanecer assim. Chat e presença não são avaissaláveis para essas contas.

Os agentes que recebem chamadas das filas de chamadas devem estar Enterprise Voice usuários online ou locais habilitados. Além disso, se as filas de chamadas estão usando números de Roteamento Direto, os agentes que precisam fazer chamadas de conferência ou transferência também exigem:

- Uma política de roteamento de voz online atribuída se a fila de chamadas usa o modo de transferência
- Uma licença de Audioconferência ou uma política de roteamento de voz online atribuída se a fila de chamadas usar o modo de conferência

Se seus agentes estão usando o aplicativo Microsoft Teams para chamadas de fila de chamadas, eles precisam estar no modo TeamsOnly.

Ao usar uma conta de recurso para fins de ID de linha de chamada em filas de chamada ou quando um atendimento automático ou fila de chamadas está transferindo chamadas para um número de telefone externo, a conta de recurso deve ter uma licença de usuário virtual Teams Telefone e uma das seguintes atribuídas:

- Uma [licença do Plano de](calling-plans-for-office-365.md) Chamadas e um número de telefone atribuído
- Um [número de Conexão](operator-connect-plan.md) operador atribuído
- Uma [política de roteamento de](manage-voice-routing-policies.md) voz online (atribuição de número de telefone é opcional ao usar Roteamento Direto)

> [!NOTE]
> Se o Plano de Chamada atribuído à conta de recurso for desabilitado ou removido, os [Créditos](what-are-communications-credits.md)de Comunicações , se disponíveis no locatário (sem a aplicação da conta de recurso), serão consumidos. Se não houver nenhum Plano de Chamada ou Créditos de Comunicação, a chamada falhará.
>
> Os números de serviço de Roteamento Direto para o atendimento automático e filas de chamadas são suportados somente Microsoft Teams usuários e agentes de chamada.
> 
> Não há suporte para transferências entre o Plano de Chamadas, Conexão operador e troncos de Roteamento Direto.
> 
> Em um cenário híbrido, a conta de recurso deve ser criada no local. Para obter mais informações, consulte [Plan Cloud call queues](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Decisões de negócios

Antes de configurar seus atendimentos automáticos e filas de chamada, há algumas decisões que você deve tomar sobre como usar esses recursos em sua empresa. Essas decisões determinarão as configurações escolhidas ao configurar seus atendimentos automáticos e filas de chamada.

Documente suas respostas a essas perguntas e forneça as informações ao administrador que está fazendo a configuração.

- De que idiomas você precisa? Onde esses idiomas são necessários - qual departamento ou grupo?
- Deseja permitir entradas de voz de chamadores ou apenas entradas de discagem?
- Você precisa de roteamento de chamadas separados para horários de folga ou feriados? Quais são os horários e feriados?
- Você deseja permitir que os agentes em uma fila de chamadas optem por não atender chamadas?
- Você deseja que os agentes em suas filas de chamada ou em sua operadora tenham uma ID de chamador específica se eles discarem?
- Você deseja [habilitar](call-park-and-retrieve.md) o estacionamento de chamada e a recuperação em sua organização para ajudar com as entregas de chamada entre pessoas ou departamentos?
- Para os prompts de voz, você deseja gravar sua própria ou usar a voz gerada pelo sistema? (A voz gerada pelo sistema é fácil de atualizar.)

## <a name="technical-decisions"></a>Decisões técnicas

Ao usar os atendimentos automáticos e filas de chamada para conectar chamadores a pessoas em sua organização, há algumas decisões técnicas a tomar antes de iniciar a configuração.

Agentes podem ser adicionados às filas de chamada das seguintes maneiras:

- Usuários individuais
- Listas de distribuição
- Grupos de segurança, incluindo grupos de segurança habilitados para email
- Microsoft 365 grupos ou Teams

Você pode usar uma combinação dessas opções para cada fila, se necessário. Os grupos que têm um endereço de email podem ser usados para caixa postal. O uso Teams oferece muitas vantagens, incluindo armazenamento de arquivos compartilhados e chat entre agentes, uma caixa de correio comum onde as caixas postal podem ser recebidas e uma plataforma extensível que pode incluir a integração com seus aplicativos de linha de negócios ou Power Apps.

Recomendamos escolher uma estratégia para adicionar agentes de chamada às filas antes de iniciar sua configuração.

Se você tiver uma infraestrutura de fila de chamadas e atendimento automático existente e estiver migrando para o Teams, precisará de um plano para transferir seus números de telefone existentes para os novos atendimentos automáticos e filas de chamadas. Talvez seja necessário criar uma ordem [de porta para](phone-number-calling-plans/port-order-overview.md) mover seus números de outros provedores. Recomendamos que você adquira temporariamente um ou mais novos números de telefone e teste seus fluxos de fila de chamadas e atendimento automáticos antes de alterná-los sobre os números que você tem no serviço.

*O modo de* conferência é uma opção em filas de chamadas que reduz significativamente o tempo necessário para conectar Teams chamadas VOIP e PSTN a um agente. Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:

- A versão mais recente do cliente de área de trabalho do Microsoft Teams, do aplicativo Android ou do aplicativo iOS
- Microsoft Teams Telefone versão 1449/1.0.94.2020051601 ou posterior
  
De definir as contas Teams agentes para Teams modo somente de Teams. Os agentes que não atendem aos requisitos não são incluídos na lista de roteamento de chamadas.

É recomendável habilitar o modo de conferência para suas filas de chamadas se todos os agentes estiverem usando clientes compatíveis.

## <a name="plan-your-call-routing-flow"></a>Planejar seu fluxo de roteamento de chamadas

Como parte do processo de planejamento, recomendamos que você trabalhe o roteamento de chamadas para sua organização em um diagrama. O diagrama ajuda a determinar o roteamento mais eficiente para as pessoas que estão ligando para sua organização. Você também pode usar o diagrama para determinar os atendimentos automáticos e filas de chamada que você precisa criar, juntamente com requisitos relacionados, como números de serviço, licenças e contas de recursos.

Vamos ver como os atendimentos automáticos e filas de chamadas roteiam chamadas.

Os atendimentos automáticos roteam todas as chamadas de uma das seguintes maneiras:

- **Redirecionar imediatamente** - as chamadas podem ser redirecionadas para um dos destinos de roteamento de chamadas (listados abaixo) imediatamente após o atendimento ou após uma saudação inicial.
- **Redirecionamento com base** nas opções de discagem - os chamadores podem ser direcionados para escolher entre as opções atribuídas aos números em seu teclado telefônico, 0-9. Cada tecla de discagem pode ser atribuída a destinos de roteamento de chamadas.
- **Discar** pessoas por nome ou extensão - os chamadores podem ser direcionados para discar o número de extensão da pessoa que estão tentando alcançar no diretório da sua organização ou ortografia do nome da pessoa.
- **Desconecte** - um atendente automático pode desligar a chamada.

> [!NOTE]
> Um único assistente automático só pode dar suporte a um único método "discar por".  Para permitir que os chamadores disquem por nome e por número, você precisará criar um atendimento automático que tenha uma opção de discagem por nome e outra para discagem por extensão.  Cada uma dessas opções será roteada para os atendimentos automáticos separados configurados para esses cenários de "discagem por".

Quando as chamadas são redirecionadas por um atendimento automático ou fila de chamadas, você pode escolher entre os seguintes destinos de roteamento de chamadas:

- **Pessoa na organização** - uma pessoa em sua organização que é capaz de receber chamadas de voz. Pode ser um usuário online ou um usuário hospedado no local usando Skype for Business Server.
- **Aplicativo de voz** - outro atendimento automático ou uma fila de chamadas. Escolha a conta de recurso associada ao destino.
- **Número de telefone externo** - qualquer número de telefone. (Consulte [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Caixa** postal - a caixa de correio de voz associada a um grupo Microsoft 365 que você especificar. Você pode escolher se deseja transcrições de caixa postal e o "Por favor, deixe uma mensagem após o tom". prompt do sistema.
- **Operador** (somente o atendimento automático) - o operador definido para o atendimento automático. Definir um operador é opcional. Um operador pode ser qualquer um dos outros destinos nesta lista.

Os atendimentos automáticos oferecem opções de roteamento de chamadas separadas para chamadas recebidas fora do horário comercial e feriados. O roteamento de chamadas após o horário permite todas as opções listadas acima, enquanto o roteamento de chamadas de feriado permite apenas redirecionar ou desconectar uma chamada, mas nenhuma opção de chave de discagem.

Filas de chamada coloca o chamador em espera até que um agente atribuído à fila está disponível para fazer a chamada. Há duas situações em que um chamador pode ser direcionado para fora da fila:

- **Estouro** de chamada - se o número de chamadas na fila exceder o limite definido, os novos chamadores serão redirecionados para fora da fila.
- **Tempo de espera de** chamada - se um chamador estiver na fila por mais tempo do que a configuração de tempo de espera configurado, ele será redirecionado para fora da fila.

As chamadas redirecionadas de uma fila podem ser enviadas para qualquer um dos destinos de roteamento de chamadas listados acima, exceto para um operador. (As filas de chamada não têm operadores, mas você pode redirecionar os chamadores para o mesmo destino que um operador que você configurou para um atendimento automático.)

O exemplo a seguir mostra um exemplo de roteamento de chamadas usando atendimentos automáticos e filas de chamadas.

![Diagrama de roteamento de chamadas usando os atendimentos automáticos e filas de chamadas.](media/attendant-and-queue-call-routing.png)

No exemplo acima:

- A tecla zero (0) redireciona os chamadores para um operador. O operador desse atendimento automático foi configurado como uma **Pessoa na organização**.
- A chave um (1) redireciona os chamadores para a fila de chamada de vendas. Essa fila de chamada está conectada a uma equipe que contém a equipe de vendas atribuída à fila.
- As duas (2) teclas redirecionam os chamadores para a fila de chamada de suporte. Essa fila de chamada está conectada a uma equipe que contém a equipe de suporte atribuída à equipe.
- A fila de chamadas de suporte tem um número de telefone direto por meio de um atendente automático intervenindo. Ter um atendedor automático na linha de suporte permite horários de folga separados e roteamento de chamadas de feriado.
- As três (3) chaves redirecionam os usuários para outro atendimento automático para o diretório da empresa. O atendimento automático do diretório da empresa permite que os chamadores chamem pessoas na organização discando seu nome ou extensão.

Recomendamos que você crie um ou mais diagramas semelhantes ao acima para mapear o roteamento de chamadas. Certifique-se de incluir o seguinte no diagrama ou na documentação que acompanha:

- Quais atendentes automáticos terão acesso direto por meio de números de telefone?
- Quais são os requisitos de roteamento de folga e feriado para cada atendimento automático?
- A associação para cada fila de chamada. (Você pode adicionar usuários individualmente ou mapear a fila para diferentes tipos de grupos. Mapear uma fila para uma equipe fornece a experiência mais versátil.)

Aqui estão algumas práticas recomendadas de roteamento de chamadas:

- Analise o sistema de chamadas existente e analise os tipos e a frequência de chamadas de entrada. Use essas informações para ajudar a informar o seu atendimento automático e a estrutura da fila de chamada.
- Coloque as opções mais comuns mais cedo no menu para rotear chamadas o mais rapidamente possível.
- Evite conectar números de serviço diretamente a filas de chamada, a menos que as filas estão disponíveis 24/7. Filas de chamada não permitem tratamento de chamada separada para horários de folga ou feriados. Se você quiser ter uma fila com um número direto, atribua o número a um atendente automático que redireciona automaticamente para a fila durante o horário comercial.
- Se você receber várias chamadas solicitando informações básicas sobre sua empresa, como horário comercial, local ou endereço do site, considere a criação de um atendedora automático para responder a essas perguntas com mensagens gravadas.
- Mantenha a lista de itens de menu para cinco ou menos. Os chamadores podem ter problemas para lembrar mais de cinco opções. Use os atendentes automáticos aninhados se mais opções são necessárias para rotear corretamente uma chamada.
- Descreva o serviço primeiro, seguido da opção para pressionar (por exemplo: Para Vendas pressione 1) em vez do contrário (por exemplo. Pressione 1 para Vendas).
- Terminologia do usuário que seus chamadores entenderão, em vez do que você pode usar internamente.
- Evite atualizações frequentes para roteamento de chamadas. Se você alterar suas opções de menu para um assistente automático no futuro, chame-o nos prompts de voz para os primeiros 30 dias.

## <a name="getting-started"></a>Introdução

Depois de concluir as tarefas de planejamento neste artigo, siga estas etapas para configurar seus atendimentos automáticos e filas de chamada:

1. Obter os números de serviço necessários para os atendimentos automáticos e filas de chamada que você deseja que sejam acessíveis discando diretamente de fora da sua organização. Isso pode incluir [a transferência de números de outro provedor ou](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) a [solicitação de novos números de serviço.](getting-service-phone-numbers.md)

2. Obter uma [Teams Telefone - Licença de usuário virtual](teams-add-on-licensing/virtual-user.md) para cada conta de recurso que você planeja criar. Essas licenças são gratuitas, portanto, sugerimos obter alguns extras caso você decida fazer alterações em suas contas de recursos no futuro.

3. [Crie uma conta de recurso](manage-resource-accounts.md) para cada atendimento automático e fila de chamada que você deseja criar. Atribua a cada conta uma Teams Telefone - Licença de usuário virtual e, opcionalmente, um número de serviço.

4. [Crie os feriados](set-up-holidays-in-teams.md) para os quais você deseja ter roteamento de chamadas separado em seus atendimentos automáticos.

5. Opcionalmente, [configurar estacionamento](call-park-and-retrieve.md) de chamada e recuperação se você quiser usar esse recurso para ajudar com transferências de chamada.

6. Crie os grupos que você deseja usar para conter os agentes de chamada para as filas de chamada.

7. Se você planeja permitir a discagem por extensão, certifique-se de ter adicionado o número de extensão dos usuários ao perfil Azure Active Directory usuário.

Depois de concluir as etapas acima, você estará pronto para criar seus atendimentos automáticos e filas de chamada. Como os atendimentos automáticos e filas de chamadas podem redirecionar chamadas umas para as outras, consulte o diagrama de fluxo de trabalho criado para determinar qual atendimento automático ou fila de chamadas deve ser criado primeiro. No exemplo no diagrama acima, você criaria as filas de chamada de vendas e suportaria as filas de chamada antes de criar o atendimento automático principal da Contoso, pois o principal atendimento automático precisa direcionar os chamadores para as vendas e dar suporte às filas de chamada.

Consulte os artigos a seguir para obter informações sobre como criar atendimentos automáticos e filas de chamada:

- [Configurar um atendimento automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md)

Se você precisar de recursos mais abrangentes, como integração com fluxos de trabalho, bots e SMS, considere os Serviços de Comunicação do [Azure.](/azure/communication-services/overview)

## <a name="related-topics"></a>Tópicos relacionados

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Criar uma fila de chamada - tutorial de pequenas empresas](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurar um atendimento automático - tutorial de pequenas empresas](business-voice/create-a-phone-system-auto-attendant-smb.md)
