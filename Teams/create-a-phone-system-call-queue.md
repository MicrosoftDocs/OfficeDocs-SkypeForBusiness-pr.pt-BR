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
description: Saiba como configurar o sistema telefônico para filas de chamadas com o Microsoft Teams, que fornecem uma mensagem de saudação, suspender música, redirecionamento de chamada e outros recursos.
ms.openlocfilehash: 0253fb15a8672d83e672e3e3e18f8455d292214c
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145888"
---
# <a name="create-a-call-queue"></a>Criar uma fila de chamadas

As filas de chamadas fornecem um método de roteamento de chamadores para as pessoas em sua organização que podem ajudá-lo com um problema ou dúvida específico. As chamadas são distribuídas uma de cada vez para as pessoas na fila (que são conhecidas como *agentes*). 

As filas de chamadas fornecem:

- Uma mensagem de saudação.

- Música enquanto as pessoas estão aguardando em espera em uma fila.

- Roteamento de chamadas em *primeiro lugar, em primeiro lugar* (FIFO) para agentes.

- Opções de manipulação para estouro de fila e tempo limite.

Verifique se você leu o [plano de atendedores automáticos e filas de chamadas do teams](plan-auto-attendant-call-queue.md) e seguiu as [etapas de introdução](plan-auto-attendant-call-queue.md#getting-started) antes de seguir os procedimentos deste artigo.

Para configurar uma fila de chamadas, no centro de administração do Teams, expanda **voz**, clique em **filas de chamadas** e, em seguida, clique em **Adicionar**.

## <a name="resource-account-and-language"></a>Conta e idioma do recurso

![Captura de tela da conta do recurso e das configurações de idioma](media/call-queue-name-language.png)

1. Digite um nome para a fila de chamadas. Os agentes verão esse nome quando receberem uma chamada de entrada da fila.

2. Clique em **Adicionar contas**, procure a conta de recurso que você deseja usar com esta fila de chamadas, clique em **Adicionar** e, em seguida, clique em **Adicionar**.

3. Escolha um idioma. Esse idioma será usado para solicitações de voz geradas pelo sistema e para a transcrição de correio de voz (se você habilitá-las).

## <a name="greetings-and-music-on-hold-in-queue"></a>Saudações e música em espera na fila

Especifique se deseja reproduzir uma saudação para os chamadores quando chegarem na fila. Você deve carregar um arquivo MP3, WAV ou WMA contendo a saudação que deseja reproduzir.

O Teams oferece música padrão para chamadores enquanto estiverem em espera em uma fila. Se você quiser executar um arquivo de áudio específico, escolha **executar um arquivo de áudio** e carregar um arquivo MP3, WAV ou WMA.

> [!NOTE]
> A gravação carregada não pode ter mais de 5 MB.
> A música padrão fornecida nas filas de chamadas do teams é de graça dos royalties pagos por sua organização. 

## <a name="call-agents"></a>Agentes de chamada

Confira os [pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para poder adicionar agentes a uma fila de chamadas.

![Captura de tela de configurações de usuários e grupos para filas de chamadas](media/call-queue-users-groups.png)

Você pode adicionar até 20 agentes individualmente e até 200 agentes por meio de grupos.

Para adicionar um usuário à fila, clique em **Adicionar usuários**, procure o usuário, clique em **Adicionar** e, em seguida, clique em **Adicionar**.

Para adicionar um grupo à fila, clique em **Adicionar grupos**, procure o grupo, clique em **Adicionar** e, em seguida, clique em **Adicionar**. Você pode usar listas de distribuição, grupos de segurança e grupos do Microsoft 365 ou Microsoft Teams Teams.

> [!NOTE]
> Novos usuários adicionados a um grupo podem levar até oito horas para que a primeira chamada seja recebida.

## <a name="call-routing"></a>Roteamento de chamadas

![Captura de tela das configurações do modo de conferência e do método de roteamento](media/call-queue-conference-mode-routing-method.png)

O **modo de conferência** reduz significativamente o tempo necessário para que um chamador seja conectado a um agente, após o agente aceitar a chamada. Para que o modo de conferência funcione, os agentes na fila de chamadas devem usar um dos seguintes clientes:

  - A versão mais recente do cliente de desktop do Microsoft Teams, do aplicativo Android ou do aplicativo iOS
  - Microsoft Teams Phone versão 1449/1.0.94.2020051601 ou posterior
  
Contas de equipe dos agentes devem ser definidas no modo somente para equipes. Os agentes que não atendem aos requisitos não são incluídos na lista de circulação de chamadas. Recomendamos habilitar o modo de conferência para suas filas de chamadas se os seus agentes estiverem usando clientes compatíveis.

O **método de roteamento** determina a ordem em que os agentes recebem chamadas da fila. Escolha uma destas opções:

- O **Roteamento do atendente** toca todos os agentes na fila ao mesmo tempo. O primeiro agente de chamadas para atender a chamada recebe a chamada.

- O **Roteamento serial** toca todos os agentes de chamada um por um na ordem especificada na lista de **agentes de chamada** . Se um agente ignorar ou não atender a chamada, a chamada tocará no próximo agente e experimentará todos os agentes até que ele seja retirado ou expirado.

- A **repetição redonda** equilibra o roteamento de chamadas de entrada para que cada agente de chamadas obtenha o mesmo número de chamadas da fila. Isso pode ser desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.

- O mais **longo** é direcionado a cada chamada para o agente que esteve ocioso ao longo do tempo mais longo. Um agente será considerado ocioso se seu estado de presença estiver disponível ou se o estado de presença ficar ausente por menos de 10 minutos. Os agentes cujo estado de presença esteve ausente por mais de 10 minutos não são considerados ociosos e não ficarão qualificados para receber chamadas até que eles alterem sua presença para disponível. 

![Captura de tela das configurações de roteamento, cancelamento e tempo de alerta](media/call-queue-presence-agents-time.png)


O **roteamento baseado em presença** usa o status de disponibilidade dos agentes de chamada para determinar se um agente deve ser incluído na lista de roteamento de chamadas para o método de roteamento selecionado. Os agentes de chamada cujo status de disponibilidade está definido como **disponível** estão incluídos na lista de circulação de chamadas e podem receber chamadas. Os agentes cujo status de disponibilidade é definido como qualquer outro status serão excluídos da lista de roteamento de chamadas e não receberão chamadas até que seu status de disponibilidade mude novamente para **disponível**. 

Você pode habilitar o roteamento de chamadas baseado em presença com qualquer um dos métodos de roteamento.

Se um agente optar por não receber chamadas, ele não será incluído na lista de roteamento de chamadas, independentemente do seu status de disponibilidade definido como. 

> [!NOTE]
> Os agentes que usam o cliente Skype for Business não são incluídos na lista de roteamento de chamadas quando o roteamento baseado em presença está habilitado. Se você tiver agentes que usam o Skype for Business, não habilite o encaminhamento de chamadas baseado em presença.

**Tempo de alerta do agente** especifica quanto tempo o telefone do agente tocará antes de a fila redirecionar a chamada para o próximo agente.

As configurações a seguir são recomendadas:

- **Modo de conferência** para **automático**
- **Método de roteamento** para **Round Robin** ou **Idle mais longo**
- **Roteamento baseado em presença** para **ativado**
- **Tempo de alerta do agente:** para **20 segundos**

> [!NOTE]
> Se o roteamento baseado em presença não estiver habilitado e houver várias chamadas na fila, o sistema apresentará essas chamadas simultaneamente para os agentes, independentemente do status de presença. Isso resultará em várias notificações de chamada para agentes, principalmente se alguns agentes não atenderem à chamada inicial apresentada a eles.

## <a name="call-overflow-handling"></a>Tratamento de estouro de chamadas

![Captura de tela das configurações de estouro de chamadas](media/call-queue-overflow-handling.png)

O **máximo de chamadas na fila** especifica o número máximo de chamadas que podem esperar na fila a qualquer momento. O padrão é 50, mas pode variar de 0 a 200. Quando esse limite for atingido, a chamada será manipulada conforme especificado pela configuração **quando o número máximo de chamadas for atingido** .

Você pode optar por desconectar a chamada ou redirecioná-la para qualquer um dos destinos de roteamento de chamadas. Por exemplo, você pode ter o chamador deixar um correio de voz para os agentes na fila. Para transferências externas, consulte [pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e as [transferências de número de telefone externo-detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de formatação de números.

> [!NOTE]
> Se o número máximo de chamadas for definido como 0, a mensagem de saudação não será reproduzida.

## <a name="call-timeout-handling"></a>Tratamento de tempo limite de chamada

![Captura de tela das configurações de tempo limite de chamada](media/call-queue-timeout-handling.png)

Tempo **limite de chamada: o tempo de espera máximo** especifica o tempo máximo que uma chamada pode estar em espera na fila antes de ser redirecionada ou desconectada. Você pode especificar um valor entre 0 segundo e 45 minutos.

Você pode optar por desconectar a chamada ou redirecioná-la para um dos destinos de roteamento de chamadas. Por exemplo, você pode ter o chamador deixar um correio de voz para os agentes na fila. Para transferências externas, consulte [pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) e as [transferências de número de telefone externo-detalhes técnicos](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de formatação de números.

Depois de selecionar as opções de tempo limite de uma chamada, clique em **salvar**.

## <a name="caller-id-for-outbound-calls"></a>IDENTIFICAÇÃO de chamada para chamadas de saída

Como os agentes em uma fila de chamadas podem discar para retornar uma chamada de cliente, considere definir a identificação de chamadas para membros de uma fila de chamadas para o número de serviço de um atendedor automático apropriado. Consulte [gerenciar políticas de identificação de chamadas no Microsoft Teams](caller-id-policies.md) para obter mais informações.

## <a name="supported-clients"></a>Clientes com suporte

Os seguintes clientes têm suporte para agentes de chamada em uma fila de chamadas:

  - Cliente de área de trabalho do Skype for Business 2016 (versões de 32 bits e de 64 bits)
  - Lync desktop cliente 2013 (versões de 32 bits e de 64 bits)
  - Todos os modelos de telefone IP com suporte para Microsoft Teams. Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Cliente Skype for Business para Mac (versão 16.8.196 e posterior)
  - Cliente Skype for Business Android (versão 6.16.0.9 e posterior)
  - Cliente Skype for Business (versão 6.16.0 e posterior) do iPhone
  - Cliente Skype for Business para iPad (versão 6.16.0 e posterior)
  - Microsoft Teams Windows Client (versões de 32 bits e 64 bits)
  - Cliente Mac do Microsoft Teams
  - Aplicativo iPhone do Microsoft Teams
  - Aplicativo Android do Microsoft Teams

    > [!NOTE]
    > As filas de chamadas atribuídas a um número de roteamento direto não dão suporte a clientes Skype for Business, clientes do Lync ou telefones IP do Skype for Business como agentes.

## <a name="call-queue-cmdlets"></a>Cmdlets da fila de chamadas

Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas. Estes são os cmdlets que você usa para gerenciar uma fila de chamadas.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](getting-service-phone-numbers.md)

[Disponibilidade de audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
