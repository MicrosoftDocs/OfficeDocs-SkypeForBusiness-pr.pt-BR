---
title: Criar uma fila de chamadas no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Saiba como configurar filas de chamadas no Microsoft Teams. As filas de chamadas fornecem uma mensagem de saudação, música de espera, redirecionamento de chamadas e outros recursos.
ms.openlocfilehash: 7ddf3364420244e800827915c9232430ffc336c1
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046851"
---
# <a name="create-a-call-queue"></a>Criar uma fila de chamadas

As filas de chamadas encaminham chamadores para pessoas em sua organização que podem ajudar com um problema ou pergunta específico. As chamadas são distribuídas uma por vez para as pessoas na fila, que são conhecidas como *agentes*.

As filas de chamada fornecem:

- Uma mensagem de saudação.
- Música enquanto as pessoas estão em espera em uma fila.
- Roteamento de chamadas, na ordem *Primeiro a Entrar, Primeiro a Sair* (PEPS), para os agentes.
- Opções de administração para estouro da fila e tempo limite.

Antes de seguir os procedimentos neste artigo, verifique se você leu o Plano para atendedores [automáticos do Teams e as filas](plan-auto-attendant-call-queue.md) de chamadas e seguiu as etapas [de introdução](plan-auto-attendant-call-queue.md#getting-started).

## <a name="whats-new-for-call-queues-in-the-past-6-months"></a>Novidades para filas de chamadas nos últimos 6 meses

- Agosto
  - **Agora há suporte para** adicionar uma mensagem de saudação (TTS (Conversão de Texto em Fala) para a saudação principal da fila de chamadas.
  - **Os controles de mensagens** do sistema de ignorar caixa postal agora são expostos ao rotear para a caixa postal compartilhada, o que também se aplica **a Adicionar prompts de mensagem de** saudação.

## <a name="steps-to-create-a-call-queue"></a>Etapas para criar uma fila de chamadas

As etapas para configurar uma fila de chamadas incluem:

1. Configurar informações gerais
1. Definir a saudação e a música
1. Configurar o atendimento a chamadas
1. Escolher e atribuir agentes
1. Definir tratamento de estouro de chamada
1. Definir tratamento de tempo limite de chamada

As etapas descritas no artigo criam filas de chamadas usando o Centro de administração do Teams. Para obter instruções para criar filas de chamadas usando o PowerShell, consulte [Criando filas de chamadas com cmdlets do PowerShell](create-a-phone-system-call-queue-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>Siga estas etapas para configurar sua fila de chamadas

# <a name="step-1-general-info"></a>[Etapa 1: Informações gerais](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>Etapa 1: Configurar informações gerais

Para configurar uma fila de chamadas, no centro de administração do [Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851)**, expanda** Voz, selecione **Filas de chamadas** e, em seguida, **selecione Adicionar**.

Digite um nome para a fila de chamadas na caixa na parte superior.

### <a name="add-a-resource-account"></a>Adicionar uma conta de recurso

Para adicionar uma conta de recurso existente:

1. Em **Contas de recurso**, clique **no botão Adicionar** para adicionar uma conta de recurso para essa fila de chamadas.
1. No painel **Adicionar contas** , pesquise a conta de recurso a ser adicionada.
1. Selecione o **botão Adicionar** ao lado da conta de recurso que você deseja atribuir a essa fila de chamadas.
1. Na parte inferior do painel, selecione o **botão** Adicionar.

Se você precisar criar uma conta de recurso:

1. Em **Contas de recurso**, clique **no botão Adicionar** para adicionar uma conta de recurso para essa fila de chamadas.
1. No painel **Adicionar contas** , pesquise qualquer conjunto de letras para efetuar pull da lista suspensa de resultados.
1. Selecione o **botão + Adicionar uma conta de** recurso na parte inferior dos resultados.
1. No painel **Adicionar conta de** recurso:
    1. Digite um nome de **exibição descritivo**, que ficará visível para os agentes.
    1. Digite um nome de usuário **descritivo** para a conta de recurso.
    1. Selecione a **lista suspensa Tipo de conta** de recurso e selecione **Fila de chamadas**.
1. Na parte inferior do painel, selecione o **botão** Salvar.
1. No painel **Contas de** recursos, selecione o **botão** Adicionar.

Os agentes verão o nome da conta de recurso quando receberem uma chamada de entrada.

Para obter mais informações, consulte [Gerenciar contas de recursos do Teams](manage-resource-accounts.md).

### <a name="assign-a-calling-id-optional"></a>Atribuir uma ID de chamada (opcional)

**Disponível para usuários da área de trabalho de chamada colaborativa/canal do Teams e usuários do cliente móvel do Teams com filas de chamadas padrão.**

Você pode atribuir números de identificação de chamadas de saída para os agentes especificando uma ou mais contas de recurso com um número de telefone. Os agentes podem selecionar qual número de ID do chamador de saída usar com cada chamada de saída que fizerem. Dentro do Aplicativo de Chamadas, os agentes podem usar o número da Fila de Chamadas (CQ) /Atendedor Automático (AA) ou seu próprio DID (Direct InWard Dial) pessoal.

> [!NOTE]
> A conta de recurso usada para fins de ID de chamada deve ter uma licença **Telefonia do Microsoft Teams conta** de recurso e uma das seguintes atribuídas:
>
> - Uma licença do Plano de Chamadas e um número de telefone atribuído
> - Um número de telefone do Operator Connect atribuído
> - Uma política de roteamento de voz online (atribuição de número de telefone é opcional ao usar o Roteamento Direto)

1. Em **Atribuir ID de chamada**, selecione o **botão** Adicionar.
1. No painel **Adicionar contas** , pesquise as contas de recurso que você deseja permitir que os agentes usem para fins de ID do chamador de saída.
1. Selecione o **botão Adicionar** ao lado da conta de recurso com um número de telefone atribuído.
1. Selecione o **botão** Adicionar na parte inferior do painel.

Se você não tiver uma conta de recurso com um número de telefone atribuído:

1. Em **Contas de recurso**, clique no **botão Adicionar** para adicionar uma conta de recurso.
1. No painel **Adicionar contas** , pesquise qualquer conjunto de letras para efetuar pull da lista suspensa de resultados.
1. Selecione o **botão + Adicionar uma conta de** recurso na parte inferior dos resultados.
1. No painel **Adicionar conta de** recurso:
    1. Digite um nome de **exibição descritivo**, que ficará visível para chamar os destinatários.
    1. Digite um nome de usuário **descritivo** para a conta de recurso.
    1. Selecione a **lista suspensa Tipo de conta** de recurso e selecione **Fila de chamadas**.
1. Na parte inferior do painel, selecione o **botão** Salvar.
1. No painel **Contas de** recursos, selecione o **botão** Adicionar.

Depois de criar essa nova conta de recurso para a ID de chamada, você ainda precisará:

- Atribuir uma licença [de Conta de Recurso de Telefone do Teams](manage-resource-accounts.md#assign-a-license)
- Atribuir uma licença do Plano de Chamada da Microsoft, atribuir um número de telefone do Operator Connect ou atribuir uma política de roteamento de voz online para Roteamento Direto
- Atribua [o número de telefone de serviço à conta de recurso](manage-resource-accounts.md#assign-a-service-number), se você estiver usando o Plano de Chamadas da Microsoft

### <a name="set-the-call-queue-language"></a>Definir o idioma da fila de chamadas

Escolha um [idioma com suporte](create-a-phone-system-call-queue-languages.md).

Esse idioma será usado para prompts de voz gerados pelo sistema e transcrição de caixa postal, se você habilita-los.

Depois de selecionar um idioma, selecione o **botão Avançar** na parte inferior da página **Adicionar uma fila de** chamadas.

# <a name="step-2-greeting-and-music"></a>[Etapa 2: Saudação e música](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>Etapa 2: Adicionar uma saudação e música em espera

*Novo – **Agora há suporte para adicionar** uma mensagem de saudação (TTS (Conversão de Texto em Fala) para a saudação principal da fila de chamadas.*

Especifique se você deseja reproduzir uma *saudação* para os chamadores quando eles chegarem na fila.

- Se você selecionar **Reproduzir um** arquivo de áudio, deverá carregar um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir. A gravação carregada não pode ser maior do que 5 MB.

- Se você selecionar **Digitar uma** mensagem de saudação, o sistema lerá o texto que você digitar (até 1000 caracteres) quando a fila de chamadas atender a uma chamada.

O Teams fornece música padrão para os chamadores enquanto eles *estão em espera em uma fila*.

- A música padrão fornecida nas filas de chamadas do Teams é livre de royalties pagáveis pela organização.
- Se você quiser reproduzir um arquivo de áudio específico, escolha **Reproduzir um arquivo de áudio** e carregue um arquivo MP3, WAV ou WMA.

> [!NOTE]
> Você é responsável por limpar e proteger independentemente todos os direitos e permissões necessários para usar qualquer arquivo de música ou áudio com seu serviço do Microsoft Teams, que pode incluir propriedade intelectual e outros direitos em qualquer música, efeitos sonoros, áudio, marcas, nomes e outros conteúdos no arquivo de áudio de todos os proprietários de direitos relevantes, que podem incluir artistas,  atores, artistas, músicos, compositores, compositores, gravadoras, editores de música, sindicatos, grêmio, sociedades de direitos, organizações de gestão coletiva e quaisquer outras partes que são proprietários, controlam ou licenciam os direitos autorais de música, efeitos sonoros, áudio e outros direitos de propriedade intelectual.

Depois de selecionar uma saudação e música em espera, selecione o botão Avançar  na parte inferior da página Adicionar **uma fila de** chamadas.

# <a name="step-3-call-answering"></a>[Etapa 3: Atendimento de chamadas](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>Etapa 3: Configurar quem responderá às chamadas recebidas

Examine os [pré-requisitos para adicionar agentes a uma fila de chamadas](plan-auto-attendant-call-queue.md#prerequisites).

### <a name="teams-channel"></a>Canal do Teams

Você pode adicionar até 200 agentes por meio de um canal do Teams. Você deve ser um membro da equipe ou o criador ou proprietário do canal para adicionar um canal à fila.

Se você quiser usar [um canal do Teams para gerenciar a fila](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e):

1. Selecione o **botão de opção Escolher** uma equipe e **selecione Adicionar um canal**.
1. Pesquise a equipe que você deseja usar, selecione-a e selecione **Adicionar**.
1. Selecione o canal que você deseja usar (há suporte apenas para canais padrão) e selecione **Aplicar**.

Os seguintes clientes têm suporte ao usar um canal do Teams para filas de chamadas:

- Cliente Windows do Microsoft Teams
- Cliente Microsoft Teams para Mac

> [!NOTE]
> Se você usar essa opção, poderá levar até 24 horas para que a fila de chamadas esteja totalmente operacional.
>
> Se houver mais de 200 membros na equipe, somente os primeiros 200 membros, em ordem alfabética, serão adicionados como agentes à fila de chamadas.

### <a name="users-and-groups"></a>Usuários e grupos

Você pode adicionar até 20 agentes individualmente e até 200 agentes por meio de grupos.

Se você quiser adicionar usuários ou grupos individuais à fila:

1. Selecione o **botão de opção Escolher usuários e** grupos.

Para **adicionar um usuário** à fila:

1. Selecione **Adicionar usuários**, pesquise o usuário **, clique em** Adicionar e, em seguida, clique em **Adicionar**.

Para **adicionar um grupo** à fila:

1. Selecione **Adicionar grupos**, pesquise o grupo **, clique em** Adicionar e, em seguida, clique em **Adicionar**. 
    1. Use listas de distribuição, grupos de segurança, grupos do Microsoft 365 ou equipes do Microsoft Teams.

> [!NOTE]
> Os novos usuários adicionados a um grupo podem levar até oito horas para receberem a sua primeira chamada.
>
> Se houver mais de 200 membros no grupo, somente os primeiros 200 membros, em ordem alfabética, serão adicionados como agentes à fila de chamadas.

### <a name="conference-mode"></a>Modo de conferência

**O modo** de conferência reduz o tempo necessário para que um chamador seja conectado a um agente depois que o agente aceita a chamada. Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:

- A versão mais recente do cliente de área de trabalho do Microsoft Teams, do aplicativo Android ou do aplicativo iOS
- Telefonia do Microsoft Teams versão 1449/1.0.94.2020051601 ou posterior
  
As contas do Teams dos agentes devem ser definidas para o modo TeamsOnly. Os agentes que não atendem aos requisitos não são incluídos na lista de roteamento de chamadas. Recomendamos habilitar o modo de conferência para suas filas de chamadas se os agentes estão usando clientes compatíveis.

> [!TIP]
> Definir **o modo de conferência** **como Ativado** é a configuração recomendada.

> [!NOTE]
> Não há suporte para o modo de conferência se as chamadas telefônicas forem roteadas para a fila de um gateway de Roteamento Direto habilitado para Roteamento Baseado em Localização.
>
> Não há suporte para o modo de conferência se as chamadas telefônicas forem roteadas para a fila de Skype for Business Server.
> 
> O modo de conferência será necessário se os usuários do Teams precisarem consultar/transferir chamadas com filas de chamadas.
>
> Os agentes podem ouvir a música configurada em espera na fila por até 2 segundos ao ingressar pela primeira vez na chamada.


Depois de selecionar as opções de atendimento de chamadas, selecione o **botão** Avançar na parte inferior da página **Adicionar uma fila de** chamadas.

# <a name="step-4-agent-selection"></a>[Etapa 4: Seleção de agente](#tab/agent-selection)

## <a name="step-4-select-your-agent-routing-options"></a>Etapa 4: Selecionar as opções de roteamento do agente

O **método de roteamento** determina a ordem na qual os agentes recebem chamadas da fila.

Escolha uma destas opções:

- O **Roteamento de atendedor** chama todos os agentes na fila ao mesmo tempo. O primeiro agente de chamada que atender recebe a chamada.

- O **Roteamento em série** chama todos os agentes de chamada, um por um, na ordem especificada na **lista de agentes de chamada**. Se um agente ignorar ou não atender uma chamada, a chamada chamará o próximo agente. Isso se repetirá até que a chamada seja selecionada ou o tempo limite seja expirado.

- O **Round robin** equilibra o roteamento das chamadas de entrada para que cada agente de chamada receba o mesmo número de chamadas da fila. Esse método de roteamento pode ser desejável em um ambiente de vendas de entrada para garantir a oportunidade igual entre todos os agentes de chamada.

- O **Ocioso por mais tempo** encaminha cada chamada para o agente que está ocioso há mais tempo. Um agente será considerado ocioso se o estado de presença estiver Disponível. Agentes cujo estado de presença não está disponível não estarão qualificados para receber chamadas até que alterem sua presença para Disponível.

> [!TIP]
> Definir o Método **de Roteamento** **como Round robin** ou **Ocioso mais** longo é a configuração recomendada.

> [!NOTE]
> Se [a gravação de](teams-recording-policy.md) conformidade estiver habilitada nos agentes, não há suporte para  a combinação do modo **conferência** e do roteamento do Atendedor. Se você precisar usar o modo **conferência**, selecione **Roteamento Serial**, **Round robin** ou **Mais Longo ocioso** como o método **de roteamento**. Se você precisar usar o **roteamento do Atendedor**, defina **o modo de conferência** como **Desativado**.
>
> Ao usar **o mais longo ocioso** e quando houver menos chamadas na fila do que os agentes disponíveis, somente os dois primeiros agentes ociosos mais longos serão apresentados com chamadas da fila.
>
> Ao usar **o mais** longo ocioso, pode haver ocasiões em que um agente recebe uma chamada da fila logo após ficar indisponível ou um pequeno atraso ao receber uma chamada da fila depois de se tornar disponível.
>
> A apresentação de chamada da Fila de Chamadas para agentes pode entrar em conflito com restrições de Roteamento Baseado em Localização. Nesse caso, o agente receberá uma notificação do sistema de chamada, mas não poderá atender à chamada. Essa condição continuará até que outro agente esteja disponível para atender a chamada, o chamador desligue ou a condição de tempo limite da fila de chamadas ocorra.  

### <a name="presence-based-call-routing"></a>Roteamento de chamadas baseado em presença

**O roteamento de chamadas baseado** em presença usa o status de disponibilidade dos agentes de chamada para determinar se um agente deve ser incluído na lista de roteamento de chamadas para o método de roteamento selecionado.

Os agentes de chamada cujo status de disponibilidade está definido como **Disponível**, estão incluídos na lista de roteamento de chamadas e podem receber chamadas. Os agentes cujo status de disponibilidade está definido com qualquer outro status, são excluídos da lista de roteamento de chamadas e não receberão chamadas até que seu status de disponibilidade volte para **Disponível**.

Você pode **habilitar o roteamento de chamadas baseado em** presença com qualquer um dos métodos de roteamento.

Se um agente optar por não receber chamadas, ele não será incluído na lista de roteamento de chamadas, independentemente do status de disponibilidade definido.

> [!TIP]
> Definir o **roteamento baseado em presença** **é a** configuração recomendada.

> [!NOTE]
> Quando **o ocioso** mais longo é selecionado como o método de roteamento, o roteamento baseado em presença é necessário e habilitado automaticamente, embora a  alternância de roteamento baseado em presença esteja desativada e esmaeciada.
>
> Se o roteamento baseado em presença não estiver habilitado e houver várias chamadas na fila, o sistema apresentará essas chamadas simultaneamente aos agentes, independentemente do status de presença. Essa ação resultará em várias notificações de chamada aos agentes, especialmente se alguns agentes não atenderem à chamada inicial apresentada a eles.
>
> Ao usar o **roteamento** baseado em presença, pode haver ocasiões em que um agente recebe uma chamada da fila logo após ficar indisponível ou um pequeno atraso ao receber uma chamada da fila depois de se tornar disponível.
>
> Os agentes que usam o cliente do Skype for Business não são incluídos na lista de roteamento de chamadas quando o roteamento baseado em presença está habilitado. Se você tiver agentes que usam o Skype for Business, não habilite o roteamento de chamadas baseado em presença.

### <a name="call-agents-can-opt-out-of-taking-calls"></a>Os agentes de chamada podem recusar a chamada

Você pode especificar se os agentes de chamada têm a capacidade de recusar chamadas ou não.

Recomendamos a ativação **de agentes de chamada que podem recusar a execução de chamadas**.

### <a name="agent-alert-time"></a>Tempo de alerta do agente

O **Tempo de alerta do agente** especifica por quanto tempo o telefone de um agente tocará antes que a fila redirecione a chamada para o próximo agente.

> [!TIP]
> Definir o **tempo de alerta do** Agente para um mínimo **de 20 segundos** é a configuração recomendada.

Depois de selecionar as opções de roteamento de chamadas do agente, selecione o **botão** Avançar na parte inferior da página **Adicionar uma fila de chamadas** .

# <a name="step-5-call-overflow"></a>[Etapa 5: estouro de chamada](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>Etapa 5: Definir como lidar com estouro de chamada

O **Número máximo de chamadas na fila** especifica o número máximo de chamadas que podem esperar na fila a qualquer momento.

O padrão é 50, mas pode variar de 0 a 200.

Quando o limite é atingido, a chamada é tratada como especificado pela configuração **Quando é atingido o número máximo de chamadas**.

Você pode optar por **desconectar** a chamada ou **redirecioná-la** para qualquer um dos destinos de roteamento de chamadas.

Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila.

*Novo – **Ignorar os controles de mensagem** do sistema de caixa postal agora são expostos ao rotear para a caixa postal compartilhada, que também se aplica **a Adicionar um prompt de mensagem de** saudação.*

Para transferências externas, consulte [Pré-requisitos](./plan-auto-attendant-call-queue.md#prerequisites) e as [transferências](create-a-phone-system-auto-attendant.md?tabs=additional-resources) de número de telefone externo – detalhes técnicos para formatação de número.

> [!NOTE]
> Se o número máximo de chamadas for definido como 0, a mensagem de saudação não será reproduzida.

Depois de selecionar as opções de tratamento de estouro de chamada, selecione o **botão** Avançar na parte inferior da página Adicionar **uma fila de chamadas** .

# <a name="step-6-call-timeout"></a>[Etapa 6: Tempo limite da chamada](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>Etapa 6: Definir como lidar com tempos limite de chamada

**Tempo limite de chamada: o tempo máximo de espera** especifica o tempo máximo que uma chamada pode estar em espera na fila antes de ser redirecionada ou desconectada.

É possível especificar um valor de 0 segundos a 45 minutos.

Você pode optar por **desconectar** a chamada ou **redirecioná-la** para um dos destinos de roteamento de chamadas.

Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila.

*Novo – **Ignorar os controles de mensagem** do sistema de caixa postal agora são expostos ao rotear para a caixa postal compartilhada, que também se aplica **a Adicionar um prompt de mensagem de** saudação.*

Para transferências externas, consulte [Pré-requisitos](./plan-auto-attendant-call-queue.md#prerequisites) e as [transferências](create-a-phone-system-auto-attendant.md?tabs=additional-resources) de número de telefone externo – detalhes técnicos para formatação de número.

Depois de selecionar as opções de tratamento de tempo limite de chamada, selecione  o botão Enviar na parte inferior da página Adicionar **uma fila de** chamadas.

---

## <a name="resources-for-complex-scenarios"></a>Recursos para cenários complexos

### <a name="summary-of-recommended-call-queue-settings"></a>Resumo das configurações recomendadas da fila de chamadas

As seguintes configurações são recomendadas:

- **Modo de conferência** como **Ativado**
- **Método de roteamento** para **Round robin** ou **Ocioso por mais tempo**
- **Roteamento baseado em presença** para **Ativado**
- **Tempo de alerta do agente:** no mínimo **20 segundos**

### <a name="call-queue-feature-compatibility"></a>Compatibilidade de recursos da fila de chamadas

|Recurso                          |Teams Desktop<sup>1</sup> |Teams Web | Teams Mobile<sup>2</sup> |Skype for Business |Telefones IP | Filas de Chamadas Padrão |Filas de Chamadas Baseadas em Canal | Comentário |
|:--------------------------------|:------------------------:|:--------:|:--------------:|:---:|:--------:|:--------------------:|:------------------------:|:--------|
|**Métodos de roteamento de agente**        |                          |          |                |     |          |                      |                          |   |
|`Attendant Routing`              |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |*Padrão*     |
|`Longest Idle`<sup>3</sup>       |Y                         |Y         |Y               |N    |Y         |Y                     |Y                         |*Recomendado* |
|`Round Robin`                    |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |*Recomendado* |
|`Serial`                         |Y                         |Y         |Y               |Y    |Y         |Y<sup>4</sup>         |Y<sup>4</sup>             |   |
|**Opções de roteamento de agente**        |                          |          |                |     |          |                      |                          |   |
|`Presence Based Routing`<sup>3</sup>|Y                      |Y         |Y               |N    |Y         |Y                     |Y                         |*Padrão* |
|`Agents can Opt-out`               |Y                       |Y         |Y               |Y<sup>7</sup>|Y<sup>7</sup>|Y          |Y                         |*Padrão*     |
|**Modos de transferência**               |                          |          |                |     |          |                      |                          |   |
|`Conference Mode`<sup>5</sup>    |Y                         |Y         |Y               |N    |Y<sup>6</sup>|Y                  |Y                         |*Padrão* |
|`Transfer Mode`                  |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |   |
|**Chamada colaborativa**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |Y                       |N         |N               |N    |N         |n/a                   |Y<sup>8</sup>             |   |
|**ID do chamador dinâmico**            |                          |          |                |     |          |                      |                          |   |
|`Standard call queue`            |Y                         |Y         |Y               |N    |N         |Y                     |n/a                       |   |
|`Channel based call queue`       |Y                         |n/a       |n/a             |n/a  |n/a       |n/a                   |Y                         |   |
|**Métodos de conectividade PSTN**    |                          |          |                |     |          |                      |                          |Consulte a Observação 9   |
|`Calling Plans`                  |Y                         |Y         |Y               |Y    |Y         |Y                     |Y                         |   |
|`Direct Routing`                 |Y                         |Y         |Y               |N    |Y         |Y<sup>6</sup>         |Y                         |   |
|`Operator Connect`               |Y                         |Y         |Y               |     |Y         |Y<sup>6</sup>         |Y                         |   |
|**Diversos**                |                          |          |                |     |          |                      |                          |   |
|`Call toast shows Resource Account Name` |Y                 |N         |Y               |Y    |          |Y                     |Y                         |              |

#### <a name="notes"></a>Observações

1. Cliente Windows do Microsoft Teams, Cliente Mac do Microsoft Teams, Microsoft Teams na Infraestrutura de Área de Trabalho Virtualizada.
2. Aplicativo Microsoft Teams para iPhone, aplicativo Do Microsoft Teams para Android.
3. Selecionar o idle mais longo para o método de roteamento de agente habilitará automaticamente o roteamento baseado em presença.
4. Só é possível definir a ordem ao adicionar usuários individuais como parte das filas de chamadas padrão. Quando uma lista de distribuição ou canal do Teams é usado, a ordem será alfabética.
5. Não há suporte para o modo de conferência se as chamadas telefônicas forem roteadas para a fila de um gateway de Roteamento Direto habilitado para Roteamento Baseado em Localização.
6. Telefonia do Microsoft Teams apenas.
7. Por meio da página do Portal de Configurações do Usuário em [https://aka.ms/vmsettings](https://aka.ms/vmsettings).
- GCCH: [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp)
- DOD: [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp)
8. Há suporte apenas para canais públicos.
9. Atendedores Automáticos e Filas de Chamadas não podem transferir chamadas entre métodos de conectividade PSTN.

### <a name="supported-clients"></a>Clientes com suporte

Os clientes a seguir têm suporte para agentes de chamada em uma fila de chamada:

- Cliente de área de trabalho do Skype for Business 2016 (versões 32-bit e 64-bit)
- Cliente de área de trabalho do Lync 2013 (versões 32-bit e 64-bit)
- Todos os modelos de telefone IP com suporte para o Microsoft Teams. Confira [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
- Cliente Skype for Business para Mac (versão 16.8.196 e posterior)
- Cliente Skype for Business para Android (versão 6.16.0.9 e posterior)
- Cliente Skype for Business para iPhone (versão 6.16.0 e posterior)
- Cliente Skype for Business para iPad (versão 6.16.0 e posterior)
- Cliente Microsoft Teams para Windows (versões 32-bit e 64-bit)
- Cliente Microsoft Teams para Mac
- Microsoft Teams na [Infraestrutura de Área de Trabalho Virtualizada](teams-for-vdi.md) (Área de Trabalho Virtual do Windows, Citrix e VMware)
- Aplicativo Microsoft Teams para iPhone
- Aplicativo Microsoft Teams para Android

  > [!NOTE]
  > As filas de chamadas que recebem um número de roteamento direto não têm suporte para clientes Skype for Business, clientes Lync ou para Telefones IP do Skype for Business como agentes. O cliente do Teams só tem suporte com um [modo de coexistência somente do Teams](setting-your-coexistence-and-upgrade-settings.md).

### <a name="call-queue-diagnostic-tool"></a>Ferramenta de Diagnóstico de Fila de Chamadas

Se você for um administrador, poderá usar a seguinte ferramenta de diagnóstico para validar se uma fila de chamadas é capaz de receber chamadas:

1. Selecione **Executar testes** abaixo, o que preencherá o diagnóstico no Centro de Administração do Microsoft 365.

   > [!div class="nextstepaction"]
   > [Executar testes: Fila de Chamadas do Teams](https://aka.ms/TeamsCallQueueDiag)

2. No painel Executar diagnóstico, insira a Conta de Recurso no nome de usuário **ou** Email e selecione **Executar Testes**.

3. Os testes retornarão as melhores próximas etapas para lidar com as configurações de locatário, política e conta de recurso para validar se a fila de chamadas é capaz de receber chamadas.

### <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com Telefonia do Microsoft Teams](here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
