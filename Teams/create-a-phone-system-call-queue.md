---
title: Criar uma fila de chamadas
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Saiba como configurar o sistema telefônico para filas de chamadas em nuvem com o Microsoft Teams.
ms.openlocfilehash: f3eb106c0acb9c79d60f45cc11770f26e3e59a1e
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516689"
---
# <a name="create-a-cloud-call-queue"></a>Criar uma fila de chamada do Cloud

As filas de chamadas na nuvem podem fornecer:

- Uma mensagem de saudação.
- Música enquanto as pessoas estão aguardando a espera.
- Redirecionar chamadas para agentes de chamada em listas de distribuição habilitadas por email e grupos de segurança.
- Configuração de parâmetros diferentes, como tamanho máximo da fila, tempo limite e opções de tratamento de chamadas.

Você pode associar um número de telefone a uma fila de chamadas usando uma [conta de recurso](manage-resource-accounts.md). Uma fila de chamadas pode ser discada diretamente ou acessada por uma seleção em um atendedor automático.

O chamador ouve música enquanto ela está em espera, e a chamada se conecta aos agentes de chamada em ordem *primeiro a entrar, primeiro a sair* (FIFO).

Todas as chamadas na fila são enviadas aos agentes por um dos seguintes métodos:

- Com o roteamento de atendedor, a primeira chamada na fila toca todos os agentes ao mesmo tempo.
- Com o roteamento serial, a primeira chamada na fila toca todos os agentes de chamada um por vez.
- Com o rodízio, o roteamento de chamadas recebidas é balanceado para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.

    > [!NOTE]
    > Os agentes de chamada que estiverem **offline**, definiram sua presença como **não incomodar** ou recusaram a fila de chamadas não receberão chamadas.

- Apenas uma notificação de chamada de entrada (para a chamada no início da fila) ao mesmo tempo vai para os agentes de chamada.
- Depois que um agente aceitar a chamada, a próxima chamada de entrada na fila começará a tocar nos agentes de chamadas.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.

## <a name="step-1--get-started"></a>Etapa 1-Introdução

Para começar a usar filas de chamadas, é importante lembrar-se de algumas coisas:

- Uma fila de chamadas é necessária para ter uma conta de recurso associada. Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.
- Ao atribuir um número de telefone a uma conta de recurso, agora você pode usar a [licença de usuário virtual](teams-add-on-licensing/virtual-user.md)de sistema telefônico sem custo. O sistema telefônico permite números de telefone no nível organizacional para uso com serviços de atendedor automático de baixo custo e fila de chamadas.

> [!NOTE]
> Os números do serviço de roteamento direto para filas de chamadas têm suporte somente para usuários e agentes do Microsoft Teams.

> [!NOTE]
> Para redirecionar chamadas para pessoas em sua organização que estão online, elas devem ter uma licença do **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamadas do Office 365. Consulte [atribuir licenças do Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [atribuir licenças do Microsoft Teams](assign-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, executar:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Para saber mais sobre os planos de chamada do Office 365, consulte [sistema telefônico e planos de chamada](calling-plan-landing-page.md) e [planos de chamadas do Office 365](calling-plans-for-office-365.md).

- Você só pode atribuir filas de chamadas em nuvem e números de telefone de serviço de chamada gratuita que você recebeu no **centro de administração do Microsoft Teams** ou transferido de outro provedor de serviços. Créditos de comunicações são necessários para números de serviço de chamada gratuita.

    > [!NOTE]
    > Os números de telefone do usuário (assinante) não podem ser atribuídos a filas de chamadas-somente números de telefone de serviço de chamada tarifada ou de chamada gratuita podem ser usados.

- Os seguintes clientes têm suporte para agentes de chamada associados a uma fila de chamadas em nuvem:

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
    > As filas de chamadas atribuídas a um número de roteamento direto não oferecerão suporte para clientes do Skype for Business, clientes do Lync ou telefones IP do Skype for Business como agentes. 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Etapa 2: obter ou transferir números de telefone de serviço de chamada tarifada ou gratuita

Antes de criar e configurar suas filas de chamadas, você precisa obter ou transferir seus números de serviço de chamada tarifada ou chamada gratuitas existentes. Depois de obter os números**** > **de telefone de** > serviço de chamada tarifada ou gratuita, eles aparecerão no centro de administração do centro > de **Administração do Microsoft Teams****, e**o **tipo de número** será listado como **Serviço — chamada gratuita**. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).

> [!NOTE]
> Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço. Vá para [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez de ver como fazer isso de fora dos Estados Unidos.

Ao configurar vários atendedores automáticos, você pode atribuir apenas um número de telefone à conta principal do recurso do atendedor automático, que pode direcionar os chamadores para suas filas de chamadas ou atendedores automáticos aninhados. Nessas situações, crie todos os atendedores automáticos e filas de chamadas em seu sistema sem atribuir opções de discagem e, em seguida, edite as configurações mais tarde. Isso é necessário porque você não tem permissão para criar uma opção de vinculação a uma fila de chamadas ou atendedor automático que ainda não existe.

## <a name="step-3--create-a-new-call-queue"></a>Etapa 3 — criar uma nova fila de chamadas

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Todas as filas de chamadas são necessárias para ter uma [conta de recurso](manage-resource-accounts.md)associada. Você deve criar a conta do recurso primeiro, então você pode associá-la à fila de chamadas.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar o centro de administração do Microsoft Teams

No **centro de administração do Microsoft Teams**,**filas de chamadas**de **voz** > e clique em **+ Adicionar novo**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Definir o nome de exibição da fila de chamadas e a conta do recurso

![Captura de tela de uma nova fila de chamadas com textos explicativos numerados](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo no](media/sfbcallout1.png)
**nome** anterior da captura de tela Insira um nome de exibição descritivo para a fila de chamadas. Esse nome é necessário e pode conter até 64 caracteres, incluindo espaços.

 Esse nome será exibido na notificação para a chamada recebida.

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

**Adicionar contas** Selecione uma conta de recurso. A conta do recurso pode ou não estar associada a um número de telefone de chamada tarifada ou gratuita do serviço para a fila de chamadas, mas cada fila de chamadas exige uma conta de recurso associada.

Se não houver uma lista, você precisará obter números de serviço e atribuí-los a uma conta de recurso antes de poder criar esta fila de chamadas, conforme descrito anteriormente. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md). Crie uma conta de recurso, conforme descrito em [gerenciar contas de recursos no Teams](manage-resource-accounts.md) , se quiser que a fila de chamadas tenha um número de telefone associado.

> [!NOTE]
> Se quiser ou precisar atribuir um **domínio** , você pode fazê-lo atribuindo-o à conta do recurso para a fila de chamadas.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Definir a saudação e a música jogadas enquanto em espera

![captura de tela das opções de saudação e música com textos explicativos numerados](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

A **saudação** é opcional. Esta é a saudação que é reproduzida para as pessoas que ligarem para o número da fila de chamadas.

Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. WMA).

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

**Música em espera** Você pode usar a música padrão em espera fornecida com a fila de chamadas ou pode carregar um arquivo de áudio nos formatos. wav, MP3 ou. WMA para usar como sua música personalizada em espera.

* * *

### <a name="select-the-call-answering-options"></a>Selecionar as opções de atendimento de chamada

![Captura de tela das opções de atendimento de chamadas, com textos explicativos numerados](media/5d249515-d532-4af2-90da-011404028b89.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

Você pode selecionar até 200 agentes de chamada que pertencem a qualquer uma das seguintes listas de endereçamento ou grupos:

- Grupo do Office 365
- Grupo de segurança
- Lista de distribuição

Os agentes de chamada selecionados devem ser um dos seguintes: 

- Usuários online com uma licença do sistema telefônico e Enterprise Voice habilitadas 
- Usuários online com um plano de chamada
- Usuários locais do Skype for Business Server

  > [!NOTE]
  > Isso também se aplica se você quiser redirecionar chamadas para as pessoas em sua organização que estão online. Esses indivíduos devem ter uma licença do **sistema telefônico** e o Enterprise Voice habilitados **ou** ter um plano de chamadas. Para obter mais informações, consulte [atribuir licenças do Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [atribuir licenças do Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)ou [qual plano de chamada é ideal para você?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

 Para habilitar um agente para Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Usuários com uma licença do **sistema telefônico** ou um plano de chamadas que são adicionados a um grupo do Office 365; uma lista de distribuição habilitada para email; ou um grupo de segurança. Pode levar até três horas para um agente recém-adicionado em uma lista de distribuição ou um grupo de segurança para começar a receber chamadas de uma fila de chamadas. Uma lista de distribuição ou um grupo de segurança recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamadas. Os grupos do Office 365 recém-criados estão disponíveis quase que imediatamente.

- Se seus agentes estiverem usando o aplicativo Microsoft Teams para fazer chamadas na fila de chamadas, eles precisarão estar no modo TeamsOnly.

![Captura de tela do painel Adicionar agentes de chamada](media/skype-for-business-add-agents-to-call-queue.png)

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

**Método de roteamento** Você pode escolher o **atendedor**, a **série**ou o **rodízio** para o método de distribuição da fila de chamadas. Todas as filas de chamadas novas e existentes terão o roteamento de atendedor selecionado por padrão. Quando o roteamento do atendente é usado, a primeira chamada na fila toca em todos os agentes de chamada ao mesmo tempo. O primeiro agente de chamadas para atender a chamada recebe a chamada.

- O **Roteamento de atendedor** faz com que a primeira chamada na fila toque em todos os agentes de chamada ao mesmo tempo. O primeiro agente de chamadas para atender a chamada recebe a chamada.
- **Roteamento serial** as chamadas recebidas para os agentes de chamada um por um, começando do início da lista de agentes de chamadas. Os agentes não podem ser ordenados na lista agente de chamadas. Se um agente ignorar ou não atender a chamada, a chamada tocará o próximo agente na lista e experimentará todos os agentes, um por vez, até que ele seja retirado ou expire em espera na fila.
  > [!NOTE]
  > O roteamento serial vai ignorar os agentes que estiverem **offline**, definir sua presença como **não incomodar** **ou optar por** não receber chamadas desta fila.
- O direcionamento de **rodízio** equilibra a circulação de chamadas de entrada para que cada agente de chamadas obtenha o mesmo número de chamadas da fila. Isso pode ser desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.

### <a name="select-an-agent-opt-out-option"></a>Selecionar uma opção de cancelamento de agente

![Captura de tela de opções de cancelamento de agente com textos explicativos numerados](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

O **agente pode optar por não receber chamadas** Você pode optar por permitir que os agentes da fila de chamadas optem por fazer chamadas de uma determinada fila habilitando esta opção.

Habilitar essa opção permite que todos os agentes nesta fila sejam iniciados ou parem de receber chamadas desta fila de chamadas. Você pode revogar o privilégio de cancelamento de agente a qualquer momento desmarcando a caixa de seleção, fazendo com que os agentes se tornem automaticamente para esta fila de novo (a configuração padrão para todos os agentes).

Para acessar a opção de recusa, os agentes podem fazer o seguinte:

 1. Abra **as opções** no cliente do Skype for Business da área de trabalho.
 2. Na guia **encaminhamento de chamadas** , clique no link **Editar configurações online** .
 3. Na página Configurações do usuário, clique em **filas de chamadas**e desmarque as caixas de seleção das filas das quais deseja recusar.

    > [!NOTE]
    > Os agentes que usam aplicativos ou pontos de extremidade diferentes da área de trabalho do Skype for Business podem acessar a opção de cancelamento no portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings)de configurações do usuário.

![Ícone do número 2, fazendo referência a um texto explicativo na](media/sfbcallout2.png)
**configuração de alerta** anterior do agente de captura de tela

Isso define a duração de um agente sendo notificado sobre uma chamada antes que os métodos de roteamento serial ou Round Robin se movam para o próximo agente.

A configuração padrão é 30 segundos, mas pode ser definida por até 3 minutos.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Configurar o estouro de chamadas e as opções de controle de tempo limite

![Captura de tela das opções de tratamento de estouro com textos explicativos numerados](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

**Máximo de chamadas na fila** Use esta configuração para definir o número máximo de chamadas que podem esperar na fila ao mesmo tempo. O padrão é 50, mas pode variar de 0 a 200. Quando esse limite for atingido, a chamada será manipulada da maneira que você definiu **quando a configuração número máximo de chamadas for atingida** abaixo.

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

**Quando o número máximo de chamadas for atingido** Quando a fila de chamadas atinge seu tamanho máximo (definido usando o **máximo de chamadas na** configuração de fila), você pode escolher o que acontece com as novas chamadas recebidas.

- **Desconectar** A chamada está desconectada.
- **Redirecionar para** Ao escolher essa opção, selecione uma das seguintes opções:

  - **Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter um plano de chamada. Você pode configurá-lo para que o chamador possa ser enviado para o correio de voz. Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.

  Para saber mais sobre as licenças necessárias para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).

  - **Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.

* * *

![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout3.png)

**Tempo limite de chamada: tempo máximo de espera** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de expirar e precisar ser redirecionada ou desconectada. O local em que é redirecionado é baseado em como você define a configuração **quando uma chamada atinge o tempo limite** . Você pode definir uma hora de 0 a 45 minutos.

O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos. Isso permite que você manipule o fluxo de chamadas com granularidade mais fina. Por exemplo, você pode especificar que as chamadas não atendidas por um agente dentro de 30 segundos vão para um atendedor automático de pesquisa de diretório.

![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout4.png)

**Quando a chamada** expira Quando a chamada atingir o limite que você definiu no **tempo em que uma chamada pode esperar na configuração de fila** , você pode escolher o que acontecerá com esta chamada:

- **Desconectar** A chamada está desconectada.
- **Redirecionar esta chamada para** Ao escolher esta opção, você tem estas opções:
  - **Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter planos de chamada. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.

  Para saber mais sobre o licenciamento necessário para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).

  - **Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.

## <a name="change-a-users-caller-id-for-outbound-calls"></a>Alterar a identificação de chamada de um usuário para chamadas de saída

Você pode proteger a identidade de um usuário alterando a identificação de chamadas para chamadas de saída para uma fila de chamadas, atendedor automático ou qualquer número de serviço, em vez disso, usando o cmdlet **New-CsCallingLineIdentity** .

Para fazer isso, execute:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Em seguida, aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity** . Para fazer isso, execute:

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Você pode obter mais informações sobre como definir as configurações de identificação de chamadas em sua organização no artigo [como a identificação de chamadas pode ser usada em sua organização](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlets da fila de chamadas

Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas. Estes são os cmdlets que você usa para gerenciar uma fila de chamadas.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Microsoft Teams com um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Por que você precisa usar o PowerShell do Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o centro de administração do Microsoft Teams, como, por exemplo, quando você está realizando alterações de vários usuários de uma vez. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Gerenciar o Office 365 com o Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurar seu computador para o Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Tópicos relacionados

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
