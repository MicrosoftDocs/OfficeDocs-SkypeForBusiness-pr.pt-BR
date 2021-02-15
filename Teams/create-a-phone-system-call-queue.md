---
title: Criar uma fila de chamadas no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Saiba como configurar o Sistema de Telefonia para filas de chamadas com o Microsoft Teams, fornecendo uma mensagem de saudação, música de espera, redirecionamento de chamadas e outros recursos.
ms.openlocfilehash: cc0995a6355157de1b43a04caf7814e588232c48
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196745"
---
# <a name="create-a-call-queue"></a>Criar uma fila de chamadas

As filas de chamadas fornecem um método de roteamento de chamadas para as pessoas da organização que podem ajudar com um problema ou pergunta específica. As chamadas são distribuídas uma por vez para as pessoas na fila (que são conhecidas como *agentes*). 

As filas de chamada fornecem:

- Uma mensagem de saudação.

- Música enquanto as pessoas estão em espera em uma fila.

- Roteamento de chamadas, na ordem *Primeiro a Entrar, Primeiro a Sair* (PEPS), para os agentes.

- Opções de administração para estouro da fila e tempo limite.

Não deixe de ler [Planejar os atendedores automáticos e as filas de chamadas do Teams](plan-auto-attendant-call-queue.md) e siga as [etapas de introdução](plan-auto-attendant-call-queue.md#getting-started) antes de seguir os procedimentos deste artigo.

Para configurar uma fila de chamadas, no Centro de administração do Teams, expanda **Voz**, clique em **Filas de chamadas** e, em seguida, clique em **Adicionar**.

## <a name="resource-account-and-language"></a>Idioma e conta de recurso

![Captura de tela das configurações de idioma e da conta de recurso](media/call-queue-name-language.png)

1. Digite um nome para a fila de chamadas.

2. Clique em **Adicionar contas**, procure a conta de recurso que você deseja usar com a fila de chamadas, clique em **Adicionar** e, em seguida, clique em **Adicionar**. (Os agentes verão o nome da conta de recurso quando receberem uma chamada recebida.)

3. Escolha um [idioma com suporte.](create-a-phone-system-call-queue-languages.md) Esse idioma será usado para comandos de voz gerados pelo sistema e para a transcrição da caixa postal (se habilitados).

## <a name="greetings-and-music-on-hold-in-queue"></a>Saudações e música de espera na fila

Especifique se você deseja reproduzir uma saudação aos chamadores quando eles chegarem na fila. Carregue um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.

O Teams fornece música padrão aos chamadores enquanto eles estão em espera em uma fila. Se você quiser reproduzir um arquivo de áudio específico, escolha **Reproduzir um arquivo de áudio** e carregue um arquivo MP3, WAV ou WMA.

> [!NOTE]
> A gravação carregada não pode ser maior do que 5 MB.
> A música padrão fornecida nas filas de chamadas do Teams é livre de royalties pagáveis pela organização. 

## <a name="call-agents"></a>Agentes de chamada

Consulte a lista de [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para poder adicionar agentes a uma fila de chamada.

![Captura de tela das configurações de usuários e grupos para filas de chamada](media/call-queue-users-groups.png)

Você pode adicionar até 20 agentes individualmente e até 200 agentes por meio de grupos.

Para adicionar um usuário à fila, clique em **Adicionar usuários**, procure o usuário, clique em **Adicionar** e, em seguida, clique em **Adicionar**.

Para adicionar um grupo à fila, clique em **Adicionar grupos**, procure o grupo, clique em **Adicionar** e, em seguida, clique em **Adicionar**. Use listas de distribuição, grupos de segurança, grupos do Microsoft 365 ou equipes do Microsoft Teams.

> [!NOTE]
> Os novos usuários adicionados a um grupo podem levar até oito horas para receberem a sua primeira chamada.

## <a name="call-routing"></a>Roteamento de chamadas

![Captura de tela das configurações de método de roteamento e modo de conferência](media/call-queue-conference-mode-routing-method.png)

O **Modo de conferência** reduz significativamente o tempo necessário para que um chamador seja conectado a um agente, depois que o agente aceita a chamada. Para que o modo de conferência funcione, os agentes na fila de chamada devem usar um dos seguintes clientes:

  - A versão mais recente do cliente de área de trabalho do Microsoft Teams, do aplicativo Android ou do aplicativo iOS
  - Versão de telefone do Microsoft Teams 1449/1.0.94.2020051601 ou posterior
  
As contas do Teams dos agentes precisam ser definidas para o modo apenas Teams. Os agentes que não atendem aos requisitos não são incluídos na lista de roteamento de chamadas. É recomendável habilitar o modo de conferência para suas filas de chamadas se todos os agentes estiverem usando clientes compatíveis.

O **método de roteamento** determina a ordem na qual os agentes recebem chamadas da fila. Escolha uma destas opções:

- O **Roteamento de atendedor** chama todos os agentes na fila ao mesmo tempo. O primeiro agente de chamada que atender recebe a chamada.

- O **Roteamento em série** chama todos os agentes de chamada, um por um, na ordem especificada na **lista de agentes de chamada**. Se um agente ignora ou não atende uma chamada, ela tocará para o próximo agente e tentará com todos os agentes até que seja atendida ou atinja o tempo limite.

- O **Round robin** equilibra o roteamento das chamadas de entrada para que cada agente de chamada receba o mesmo número de chamadas da fila. Isso pode ser desejável em um ambiente de vendas de entrada para garantir igualdade de oportunidades entre todos os agentes de chamada.

- O **Ocioso por mais tempo** encaminha cada chamada para o agente que está ocioso há mais tempo. Um agente é considerado ocioso se seu estado de presença estiver Disponível ou se o estado de presença estiver Ausente por menos de 10 minutos. Os agentes cujo estado de presença esteja ausente há mais de 10 minutos não são considerados ociosos e não poderão receber chamadas até que alterem a presença para Disponível. 

![Captura de tela das configurações de roteamento, recusa e tempo de alerta](media/call-queue-presence-agents-time.png)


O **Roteamento baseado em presença** usa o status de disponibilidade dos agentes de chamada para determinar se um agente deve ser incluído na lista de roteamento de chamadas para o método de roteamento selecionado. Os agentes de chamada cujo status de disponibilidade está definido como **Disponível**, estão incluídos na lista de roteamento de chamadas e podem receber chamadas. Os agentes cujo status de disponibilidade está definido com qualquer outro status, são excluídos da lista de roteamento de chamadas e não receberão chamadas até que seu status de disponibilidade volte para **Disponível**. 

Habilite o roteamento de chamadas baseado em presença com qualquer um dos métodos de roteamento.

Se um agente optar por não receber chamadas, ele não será incluído na lista de roteamento de chamadas, independentemente do status de disponibilidade definido. 

> [!NOTE]
> Os agentes que usam o cliente do Skype for Business não são incluídos na lista de roteamento de chamadas quando o roteamento baseado em presença está habilitado. Se você tiver agentes que usam o Skype for Business, não habilite o roteamento de chamadas baseado em presença.

O **Tempo de alerta do agente** especifica por quanto tempo o telefone de um agente tocará antes que a fila redirecione a chamada para o próximo agente.

As seguintes configurações são recomendadas:

- **Modo de conferência** para **Automático**
- **Método de roteamento** para **Round robin** ou **Ocioso por mais tempo**
- **Roteamento baseado em presença** para **Ativado**
- **Tempo de alerta do agente:** para **20 segundos**

> [!NOTE]
> Se o roteamento baseado em presença não for habilitado e houver várias chamadas na fila, o sistema apresentará essas chamadas simultaneamente aos agentes, independentemente do status de presença. Isso resultará em várias notificações de chamada aos agentes, particularmente se alguns agentes não atenderem à chamada inicial apresentada.

## <a name="call-overflow-handling"></a>Administração de estouro de chamadas

![Captura de tela das configurações de estouro de chamadas](media/call-queue-overflow-handling.png)

O **Número máximo de chamadas na fila** especifica o número máximo de chamadas que podem esperar na fila a qualquer momento. O padrão é 50, mas pode variar de 0 a 200. Quando o limite é atingido, a chamada é tratada como especificado pela configuração **Quando é atingido o número máximo de chamadas**.

Você pode optar por desconectar a chamada ou redirecioná-la para qualquer um dos destinos de roteamento de chamadas. Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila. Para transferências externas, consulte [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e [transferências de números de telefone externos – detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para formatação de números.

> [!NOTE]
> Se o número máximo de chamadas for definido como 0, então a mensagem de saudação não será reproduzida.

## <a name="call-timeout-handling"></a>Administração de tempo limite de chamada

![Captura de tela das configurações de tempo limite de chamada](media/call-queue-timeout-handling.png)

**Tempo limite de chamada: o tempo máximo de espera** especifica o tempo máximo que uma chamada pode estar em espera na fila antes de ser redirecionada ou desconectada. É possível especificar um valor de 0 segundos a 45 minutos.

Você pode optar por desconectar a chamada ou redirecioná-la para um dos destinos de roteamento de chamadas. Por exemplo, você pode pedir ao chamador que deixe uma mensagem de voz para os agentes na fila. Para transferências externas, consulte [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e [transferências de números de telefone externos – detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) para formatação de números.

Quando você tiver selecionado as opções de tempo limite de chamada, clique em **Salvar**.

## <a name="caller-id-for-outbound-calls"></a>Identificação de Chamadas para chamadas de saída

Como os agentes em uma fila de chamadas podem discar para retornar uma chamada do cliente, considere configurar a identificação de chamadas dos membros de uma fila de chamadas para o número de serviço de um atendedor automático apropriado. Para mais informações, confira [Gerenciar políticas de identificação de chamadas no Microsoft Teams](caller-id-policies.md).

## <a name="supported-clients"></a>Clientes com suporte

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
  - Aplicativo Microsoft Teams para iPhone
  - Aplicativo Microsoft Teams para Android

    > [!NOTE]
    > As filas de chamadas que recebem um número de roteamento direto não têm suporte para clientes Skype for Business, clientes Lync ou para Telefones IP do Skype for Business como agentes.

## <a name="call-queue-cmdlets"></a>Cmdlets de fila de chamada

Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas. Veja aqui os cmdlets usados para administrar uma fila de chamadas.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
