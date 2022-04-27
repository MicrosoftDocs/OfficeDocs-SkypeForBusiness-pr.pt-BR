---
title: Planejar para Teams atendedores automáticos e filas de chamadas
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
description: Saiba mais sobre atendedores automáticos e filas de chamadas e como usá-los para ajudar os chamadores a percorrer um sistema de menus para acessar pessoas ou departamentos em sua organização.
ms.openlocfilehash: 76755e722abdcde6673baac42681697165921aca
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059272"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planejar para Teams atendedores automáticos e filas de chamadas

Os atendedores automáticos permitem que você configure opções de menu para rotear chamadas com base na entrada do chamador. Opções de menu, como "Para Vendas, pressione 1.  Para serviços, pressione 2", para um atendedor automático, permita que uma organização forneça uma série de opções que orientam os chamadores para seu destino rapidamente, sem depender de um operador humano para lidar com chamadas de entrada.

As filas de chamadas estão aguardando áreas para chamadores. Para situações em que os chamadores precisam entrar em contato com alguém com uma especialização específica , como vendas ou serviço, em vez de uma pessoa específica, você pode usar filas de chamadas para conectar chamadores ao grupo de agentes que podem ajudá-los. Os chamadores são colocados em espera até que um agente atribuído à fila esteja disponível para receber sua chamada.

Usados juntos, os atendedores automáticos e as filas de chamadas podem rotear facilmente os chamadores para a pessoa ou o departamento apropriado em sua organização.

## <a name="auto-attendants"></a>Atendedores automáticos

A principal finalidade de um atendedor automático é direcionar um chamador para uma pessoa ou departamento apropriado com base na entrada do chamador para as opções de menu fornecidas. Os chamadores podem ser direcionados para pessoas específicas em sua organização, para chamar filas em que esperam para falar com o próximo agente disponível ou para a caixa postal. Diferentes opções de roteamento de chamadas podem ser especificadas para horário comercial, folga e feriados.

Os prompts de menu podem ser criados usando a conversão de texto em fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação sem mãos, mas as pessoas que estão chamando também podem usar o teclado do telefone para navegar pelos menus.

Cada atendedor automático tem um idioma e fuso horário específicos. Se você fizer negócios em vários idiomas ou em várias partes do mundo, poderá criar tantos atendedores automáticos diferentes quanto precisar para acomodar seus chamadores.

Para cada atendedor automático, você pode configurar um operador. Embora você possa configurar chamadas de operador para ir para vários destinos, o recurso de operador foi projetado para permitir que os chamadores conversem com uma pessoa específica em sua organização que possa ajudá-los.

Os atendedores automáticos podem ser configurados para permitir que os chamadores pesquisem o diretório da sua organização, seja por nome ou por número de extensão. Em um atendedor automático, você pode especificar quem está disponível para a pesquisa de diretório escolhendo grupos de usuários para incluir ou excluir. (Isso é conhecido como escopo *de discagem*.)

Os chamadores podem acessar um atendedor automático por número de telefone direto, se configurado, ou redirecionando-os de outro atendedor automático ou de uma fila de chamadas.

## <a name="call-queues"></a>Filas de chamadas

Uma fila de chamadas é análoga a uma sala de espera em um prédio físico. Os chamadores aguardam em espera enquanto as chamadas são roteados para os agentes na fila. Filas de chamadas são comumente usadas para funções de vendas e serviço. No entanto, as filas de chamadas podem ser usadas para qualquer situação em que o número de chamadas exceda sua capacidade interna, como uma recepção em uma instalação ocupada.

As filas de chamadas permitem o roteamento específico de chamadas em casos em que o número total de chamadores na fila ou o tempo de espera excede os limites especificados. As chamadas podem ser roteados para pessoas específicas, caixa postal, outras filas de chamadas ou atendedores automáticos.

Assim como os atendedores automáticos, as filas de chamadas têm uma configuração de idioma. Você poderá usar filas de chamadas diferentes se fizer negócios em vários idiomas. Os agentes podem ser membros de mais de uma fila se forem multilíngues.

Para cada fila de chamadas, você pode especificar se os agentes na fila podem recusar a execução de chamadas e se as chamadas devem ser roteados para eles com base na indicação de presença no Teams.

Você pode atribuir um número de telefone a uma fila de chamadas, no entanto, as filas de chamadas não fornecem roteamento de chamadas separado para fora do horário comercial e feriados. A menos que sua fila de chamadas esteja em equipe 24 horas por dia, recomendamos atribuir o número de telefone a um atendedor automático que redireciona para a fila de chamadas durante o horário comercial.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar atendedores automáticos e filas de chamadas, você precisa dos seguintes recursos:

- Uma conta de recurso para cada atendedor automático e cada fila de chamadas
- Um sistema Telefone Microsoft gratuito – licença de usuário virtual para cada conta de recurso
- Pelo menos um número [de serviço da Microsoft](getting-service-phone-numbers.md), Conexão do operador, número de Roteamento Direto ou um número híbrido para cada conta de recurso que você deseja que seja discada diretamente
 - O número do serviço pode ser um número de chamada tarifada ou gratuita

> [!NOTE]
> As contas de recursos estão desabilitadas para entrar e devem permanecer assim. Chat e presença não são disponíveis para essas contas.

Os agentes que recebem chamadas das filas de chamadas devem Enterprise Voice usuários online ou locais habilitados. Além disso, se as filas de chamadas estão usando números de Roteamento Direto, os agentes que precisam fazer conferências ou transferir chamadas também exigirão:

- Uma política de roteamento de voz online atribuída se a fila de chamadas usar o modo de transferência
- Uma licença de Audioconferência ou uma política de roteamento de voz online atribuída se a fila de chamadas usar o modo de conferência

Se os agentes estiverem usando o aplicativo Microsoft Teams para chamadas de fila de chamadas, eles precisarão estar no modo TeamsOnly.

Ao usar uma conta de recurso para fins de ID de linha de chamada em filas de chamadas ou quando um atendedor automático ou fila de chamadas está transferindo chamadas para um número de telefone externo, a conta de recurso deve ter uma licença de usuário virtual do Sistema de Telefonia e uma das seguintes atribuídas:

- Uma [licença do Plano](calling-plans-for-office-365.md) de Chamadas e um número de telefone atribuído
- Um [Conexão do operador](operator-connect-plan.md) de telefone atribuído
- Uma [política de roteamento de voz online](manage-voice-routing-policies.md) (atribuição de número de telefone é opcional ao usar o Roteamento Direto)

> [!NOTE]
> Se o Plano de Chamadas atribuído à conta de recurso for desabilitado ou for removido, os Créditos de Comunicação, se disponíveis no locatário (sem serem [atribuídos](what-are-communications-credits.md) à conta de recurso), serão consumidos. Se não houver Nenhum Plano de Chamada ou Créditos de Comunicação, a chamada falhará.
>
> Há suporte para números de serviço de Roteamento Direto para atendedor automático e filas de chamadas Microsoft Teams usuários e agentes de chamada.
> 
> Não há suporte para transferências entre o Plano de Chamadas, Conexão do operador e os troncos de Roteamento Direto.
> 
> Em um cenário híbrido, a conta de recurso deve ser criada localmente. Para obter mais informações, consulte [Plan Cloud call queues](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Decisões de negócios

Antes de configurar seus atendedores automáticos e filas de chamadas, há algumas decisões que você deve tomar sobre como usar esses recursos em sua empresa. Essas decisões determinarão as configurações que você escolhe ao configurar seus atendedores automáticos e filas de chamadas.

Documente suas respostas a essas perguntas e forneça as informações ao administrador que está fazendo a configuração.

- De quais idiomas você precisa? Onde esses idiomas são necessários - qual departamento ou grupo?
- Deseja permitir entradas de voz de chamadores ou apenas de discagem de entradas?
- Você precisa de roteamento de chamadas separado para folgas ou feriados? Quais são as horas e feriados?
- Deseja permitir que os agentes em uma fila de chamadas recusem chamadas?
- Você deseja que os agentes em suas filas de chamadas ou seu operador tenham uma ID de chamador específica se eles discam?
- Deseja habilitar o [estacionamento de chamadas](call-park-and-retrieve.md) e a recuperação em sua organização para ajudar com as entregas de chamadas entre pessoas ou departamentos?
- Para os prompts de voz, você deseja gravar sua própria voz ou usar a voz gerada pelo sistema? (A voz gerada pelo sistema é fácil de atualizar.)

## <a name="technical-decisions"></a>Decisões técnicas

Ao usar atendedores automáticos e filas de chamadas para conectar chamadores a pessoas em sua organização, há algumas decisões técnicas a serem tomadas antes de iniciar a configuração.

Os agentes podem ser adicionados às filas de chamadas das seguintes maneiras:

- Usuários individuais
- Listas de distribuição
- Grupos de segurança, incluindo grupos de segurança habilitados para email
- Grupos do Microsoft 365 ou Teams

Você pode usar uma combinação dessas opções para cada fila, se necessário. Os grupos que têm um endereço de email podem ser usados para caixa postal. O uso Teams oferece muitas vantagens, incluindo armazenamento de arquivos compartilhados e chat entre agentes, uma caixa de correio comum em que as caixas de correio podem ser recebidas e uma plataforma extensível que pode incluir a integração com seus aplicativos de linha de negócios ou Power Apps.

Recomendamos escolher uma estratégia para adicionar agentes de chamada às filas antes de iniciar a configuração.

Se você tiver um atendedor automático e uma infraestrutura de fila de chamadas existentes e estiver migrando para o Teams, precisará de um plano para transferir seus números de telefone existentes para os novos atendedores automáticos e filas de chamadas. Talvez seja necessário criar uma ordem [de portabilidade](phone-number-calling-plans/port-order-overview.md) para mover seus números de outros provedores. Recomendamos que você adquira temporariamente um ou mais números de telefone novos e teste seus fluxos de atendedor automático e fila de chamadas antes de alternar entre os números que você tem atualmente em serviço.

*O modo* de conferência é uma opção em filas de chamadas que reduz significativamente o tempo necessário para conectar Teams chamadas VOIP e PSTN a um agente. Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:

- A versão mais recente do cliente de área de trabalho do Microsoft Teams, do aplicativo Android ou do aplicativo iOS
- Telefone Microsoft System versão 1449/1.0.94.2020051601 ou posterior
  
Defina as contas Teams agentes para Teams modo somente de uso. Os agentes que não atendem aos requisitos não são incluídos na lista de roteamento de chamadas.

É recomendável habilitar o modo de conferência para suas filas de chamadas se todos os agentes estiverem usando clientes compatíveis.

## <a name="plan-your-call-routing-flow"></a>Planejar o fluxo de roteamento de chamadas

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
- **Número de telefone externo** - qualquer número de telefone. (Consulte [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Caixa** postal – a caixa postal associada a um grupo Microsoft 365 que você especificar. Você pode escolher se deseja transcrições de caixa postal e "Deixe uma mensagem após o tom". prompt do sistema.
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

## <a name="getting-started"></a>Introdução

Depois de concluir as tarefas de planejamento neste artigo, siga estas etapas para configurar os atendedores automáticos e as filas de chamadas:

1. Obtenha os números de serviço necessários para os atendedores automáticos e as filas de chamadas que você deseja que sejam acessíveis discando diretamente de fora da sua organização. Isso pode incluir [a transferência de números de outro provedor ou](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) [a solicitação de novos números de serviço](getting-service-phone-numbers.md).

2. Obtenha uma [Sistema de Telefonia - Licença de usuário virtual](teams-add-on-licensing/virtual-user.md) para cada conta de recurso que você planeja criar. Essas licenças são gratuitas, portanto, sugerimos obter alguns extras caso você decida fazer alterações em suas contas de recursos no futuro.

3. [Crie uma conta de recurso](manage-resource-accounts.md) para cada atendedor automático e fila de chamadas que você deseja criar. Atribua a cada conta uma Sistema de Telefonia - Licença de Usuário Virtual e, opcionalmente, um número de serviço.

4. [Crie os feriados para](set-up-holidays-in-teams.md) os quais você deseja ter roteamento de chamadas separado em seus atendedores automáticos.

5. Opcionalmente, [configure o estacionamento de chamadas](call-park-and-retrieve.md) e a recuperação se quiser usar esse recurso para ajudar com transferências de chamadas.

6. Crie os grupos que você deseja usar para conter os agentes de chamada para as filas de chamadas.

7. Se você planeja permitir a discagem por extensão, verifique se adicionou o número de extensão dos usuários ao perfil Azure Active Directory usuário.

Depois de concluir as etapas acima, você estará pronto para criar seus atendedores automáticos e filas de chamadas. Como os atendedores automáticos e as filas de chamadas podem redirecionar chamadas entre si, consulte o diagrama de fluxo de trabalho que você criou para determinar qual atendedor automático ou fila de chamadas deve ser criado primeiro. No exemplo no diagrama acima, você criaria as filas de chamadas de vendas e suporte antes de criar o atendedor automático principal da Contoso, pois o atendedor automático principal precisa direcionar os chamadores para as filas de chamadas de vendas e de suporte.

Consulte os seguintes artigos para obter informações sobre como criar atendedores automáticos e filas de chamadas:

- [Configurar um atendedor automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md)

Se você precisar de recursos mais abrangentes, como integração com fluxos de trabalho, bots e SMS, considere [Serviços de Comunicação do Azure](/azure/communication-services/overview).

## <a name="related-topics"></a>Tópicos relacionados

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Criar uma fila de chamadas – tutorial de pequenas empresas](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurar um atendedor automático – tutorial de pequenas empresas](business-voice/create-a-phone-system-auto-attendant-smb.md)
