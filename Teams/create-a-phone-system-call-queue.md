---
title: Criar uma fila de chamadas
ms.author: mikeplum
author: MikePlumleyMSFT
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Saiba como configurar o sistema telefônico para filas de chamadas em nuvem com o Microsoft Teams, que fornecem uma mensagem de saudação, suspender música, redirecionamento de chamada e outros recursos.
ms.openlocfilehash: be43c2dc378b985b63c47b9322b336eeadfeecb6
ms.sourcegitcommit: 515f6cf7c16c0ab6ea7acbbd59084ac89b57dfb8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47295304"
---
# <a name="create-a-cloud-call-queue"></a>Criar uma fila de chamada do Cloud

As filas de chamadas na nuvem podem fornecer:

- Uma mensagem de saudação.

- Música enquanto as pessoas estão aguardando a espera.

- Redirecionar chamadas para agentes de chamada em listas de distribuição habilitadas por email e grupos de segurança.

- Configuração de parâmetros diferentes, como tamanho máximo da fila, tempo limite e opções de tratamento de chamadas.

- Caixa postal compartilhada para chamadores deixar uma mensagem para uma organização.

Você não associa diretamente um número de telefone a uma fila de chamadas, em vez disso, o número de telefone está associado a uma [conta do recurso](manage-resource-accounts.md). Uma fila de chamadas pode ser discada diretamente ou acessada por uma seleção em um atendedor automático.

O chamador ouve música enquanto ela está em espera, e a chamada se conecta aos agentes de chamada em ordem *primeiro a entrar, primeiro a sair* (FIFO).

Todas as chamadas na fila são enviadas aos agentes por um dos seguintes métodos:

- Com o roteamento de atendedor, a primeira chamada na fila toca todos os agentes ao mesmo tempo.

- Com o roteamento serial, a primeira chamada na fila toca todos os agentes de chamada um por vez.

- Com roteamento de ociosidade mais longo, o agente de chamada cujo tempo está ocioso o tempo mais longo recebe a próxima chamada disponível. O tempo ocioso é definido como o período de tempo durante o qual o estado de presença de um agente de chamada é definido como **disponível** ou **ausente** (se for menor que 10 minutos), no momento da chamada. Se a presença de um agente de chamada estiver **ausente** por mais de 10 minutos, o cronômetro de ociosidade será redefinido.

- Com o rodízio, o roteamento de chamadas recebidas é balanceado para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.

Você pode definir as opções de gerenciamento de chamadas, como consentimento de agente/recusa, roteamento baseado em presença, tempo de espera de chamada e opções de tempo limite de chamada com qualquer um dos métodos acima.

Apenas uma notificação de chamada de entrada (para a chamada no início da fila) ao mesmo tempo vai para os agentes de chamada. Depois que um agente aceitar a chamada, a próxima chamada de entrada na fila começará a tocar nos agentes de chamadas.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.

## <a name="step-1--get-started"></a>Etapa 1-Introdução

Para começar a usar filas de chamadas, é importante lembrar-se de algumas coisas:

- Uma fila de chamadas é necessária para ter uma conta de recurso associada. Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.

- Ao atribuir um número de telefone a uma conta de recurso, agora você pode usar a [licença de usuário virtual](teams-add-on-licensing/virtual-user.md)de sistema telefônico sem custo. O sistema telefônico permite números de telefone no nível organizacional para uso com serviços de atendedor automático de baixo custo e fila de chamadas.

  > [!NOTE]
  > Os números do serviço de roteamento direto para filas de chamadas têm suporte somente para usuários e agentes do Microsoft Teams.

  > [!NOTE]
  > Para redirecionar chamadas para pessoas em sua organização que estão online, elas devem ter uma licença do **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamada do Microsoft 365 ou do Office 365. Consulte [atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute: ' Set-CsUser-Identity "Amos Marble"-EnterpriseVoiceEnabled $true.

- Para saber mais sobre planos de chamada, consulte [sistema telefônico e planos de chamada](calling-plan-landing-page.md) e [planos de chamada para o Microsoft 365 ou o Office 365](calling-plans-for-office-365.md).

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
    > As filas de chamadas atribuídas a um número de roteamento direto não dão suporte a clientes Skype for Business, clientes do Lync ou telefones IP do Skype for Business como agentes.

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>Etapa 2: obter ou transferir números de telefone de serviço de chamada tarifada ou gratuita

Antes de criar e configurar suas filas de chamadas, você precisa obter ou transferir seus números de serviço de chamada tarifada ou chamada gratuitas existentes. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md). Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecerão nos números de telefone de voz do **centro de administração do Microsoft Teams**  >  **Voice**  >  **Phone numbers**. Números de chamada gratuita serão listados com um **tipo** de serviço de número **: gratuito**.

> [!NOTE]
> Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço. Vá para [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez de ver como fazer isso de fora dos Estados Unidos.

Ao configurar vários atendedores automáticos, você normalmente atribuiria um número de telefone à conta principal do recurso do atendedor automático. As contas de recursos associadas a atendedores automáticos aninhados ou filas de chamadas geralmente não são necessárias para números de telefone. Esse atendedor automático pode direcionar os chamadores para suas filas de chamadas ou atendedores automáticos aninhados, mesmo que eles não tenham um número de telefone. Nessas situações, você pode criar todos os atendedores automáticos e filas de chamadas em seu sistema sem atribuir opções de discagem e, em seguida, editar as configurações mais tarde. Uma fila de chamadas ou atendedor automático deve existir para defini-lo como uma opção de menu.

## <a name="step-3--create-a-call-queue"></a>Etapa 3 — criar uma fila de chamadas

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Todas as filas de chamadas são necessárias para ter uma [conta de recurso](manage-resource-accounts.md)associada. Você deve criar a conta do recurso primeiro, então você pode associá-la à fila de chamadas.

### <a name="use-the-microsoft-teams-admin-center"></a>Usar o centro de administração do Microsoft Teams

No **centro de administração do Microsoft Teams**, **Voice**  >  **filas de chamadas**de voz e clique em **+ Adicionar novo**:

### <a name="set-the-display-name-and-resource-account"></a>Definir o nome para exibição e a conta do recurso

![Captura de tela de uma nova fila de chamadas com textos explicativos numerados](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![O ícone do número 1 faz referência a um texto explicativo no nome anterior da captura de tela ](media/teamscallout1.png)
 **Name** digite um nome de exibição descritivo para a fila de chamadas. Esse nome é necessário e pode conter até 64 caracteres, incluindo espaços.

 Esse nome será exibido na notificação para a chamada recebida.

* * *

![O ícone do número 2 faz referência a um balão na captura de tela anterior ](media/teamscallout2.png)
 **Adicionar contas** selecione uma conta de recurso. Todas as filas de chamadas são necessárias para ter uma conta de recurso. Não é necessário ter contas de recursos para ter um número de telefone de chamada tarifada ou gratuita do serviço.

Se não houver lista, obtenha números de serviço e atribua-os a uma conta de recurso antes de criar a fila de chamadas, conforme descrito anteriormente. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md). Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter informações específicas sobre como atribuir um número de telefone.

> [!NOTE]
> Se você quiser ou precisar atribuir um **domínio** , ele será atribuído à conta do recurso para a fila de chamadas.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Definir a saudação e a música jogadas enquanto em espera

![captura de tela das opções de saudação e música com textos explicativos numerados](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![O ícone do número 1 faz referência a um texto explicativo na captura de tela anterior ](media/teamscallout1.png)
 **saudação** da saudação opcional para as pessoas que chamam o número da fila de chamadas.

Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. WMA).

![O ícone do número 2 faz referência a um texto explicativo nas músicas de captura de tela anteriores ](media/teamscallout2.png)
 **em espera** , você pode usar a música padrão em espera fornecida com a fila de chamadas. Você também pode carregar um arquivo de áudio nos formatos. wav, MP3 ou. WMA para usar como sua música personalizada em espera.

* * *

### <a name="select-the-call-answering-options"></a>Selecionar as opções de atendimento de chamada

![Captura de tela das opções de atendimento de chamadas](media/teams-cq-call-answering-options.png)

![O ícone do número 1 faz referência a um texto explicativo na captura de tela anterior ](media/teamscallout1.png)
 **agentes e grupos** para adicionar agentes individuais diretamente, sem adicioná-los a um grupo, clique em **Adicionar usuários**. Coloque agentes individuais na ordem em que você deseja que eles recebam a chamada. Você pode adicionar até 20 agentes individuais (para adicionar mais de 20, colocá-los em um grupo).

As chamadas são roteadas primeiro para agentes individuais e depois para os agentes em grupos. 

Você pode selecionar até 200 agentes de chamada que pertencem a qualquer uma das seguintes listas de endereçamento ou grupos:

- Grupo do Microsoft 365
- Grupo de segurança
- Lista de distribuição

Os agentes de chamada selecionados devem ser um dos seguintes: 

- Usuários online com uma licença do sistema telefônico e Enterprise Voice habilitadas
- Usuários online com um plano de chamada
- Usuários locais do Skype for Business Server

  > [!NOTE]
  > Isso também se aplica se você quiser redirecionar chamadas para as pessoas em sua organização que estão online. Esses indivíduos devem ter uma licença do sistema telefônico e o Enterprise Voice habilitados *ou* ter um plano de chamadas. Para obter mais informações, consulte [atribuir licenças do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [atribuir licenças do Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)ou [qual plano de chamada é ideal para você?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

   Para habilitar um agente para Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Usuários com uma licença do sistema telefônico ou um plano de chamadas que são adicionados a um grupo do Microsoft 365, uma lista de distribuição habilitada para email ou um grupo de segurança. Quando você adiciona um agente em uma lista de distribuição ou um grupo de segurança como um agente de fila de chamada, pode levar até três horas para que a primeira chamada seja recebida. Uma lista de distribuição ou um grupo de segurança recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamadas. Os grupos do Microsoft 365 recém criados estão disponíveis quase que imediatamente.

- Se seus agentes estiverem usando o aplicativo Microsoft Teams para chamadas da fila de chamadas, eles precisarão estar no modo TeamsOnly.

![O ícone do número 2 faz referência a um texto explicativo no modo de conferência anterior em ](media/teamscallout2.png)
 **modo de conferência** reduz significativamente o tempo necessário para que o chamador seja conectado a um agente, após o agente aceitar a chamada. Se você tiver mais de uma fila de chamadas, poderá habilitar o modo de conferência em algumas ou todas as suas filas de chamadas; habilitar ou desabilitar o modo de conferência em uma fila de chamadas não afeta nenhuma outra fila de chamadas.

O modo de conferência está desabilitado por padrão, mas pode ser habilitado a qualquer momento se os seguintes requisitos forem atendidos:

- Os agentes adicionados à fila de chamadas precisam usar um dos seguintes clientes:

  - A versão mais recente do cliente de desktop do Microsoft Teams, do aplicativo Android ou do aplicativo iOS
  - Microsoft Teams Phone versão 1449/1.0.94.2020051601 ou posterior
  
- Contas de equipe dos agentes devem ser definidas para o modo somente de equipes

> [!IMPORTANT]
> Se os requisitos do agente acima não forem atendidos e o modo de conferência estiver habilitado em uma fila de chamadas, os agentes que não atendem aos requisitos não serão incluídos na lista de circulação de chamadas. Os agentes que não estão na lista de circulação de chamadas não recebem chamadas. Se você tiver agentes que não atendem aos requisitos de agente acima, não habilite o modo de conferência na fila de chamadas.

Depois que o modo de conferência estiver habilitado em uma fila de chamadas, as chamadas serão beneficiadas do tempo de conexão mais rápido se forem recebidas por meio de um dos seguintes métodos:

- Chamadas de VoIP de outro cliente de desktop do Microsoft Teams
- Chamadas PSTN de plano de chamada
- Chamadas PSTN de roteamento direto

A maioria das chamadas é recebida por meio de um dos métodos listados acima. Se uma chamada for recebida por meio de outro método (como uma chamada de VoIP de um cliente Skype for Business), a chamada ainda será adicionada à fila de chamadas, mas não se beneficiará do tempo de conexão mais rápido.

> [!NOTE]
> Ocupado em ocupado não é compatível com o modo de conferência. Os agentes em chamadas de fila de não chamada ainda poderão ser apresentados com uma chamada na fila de chamadas se o roteamento baseado em presença não estiver habilitado.


![O ícone do número 3 faz referência a um balão no método de roteamento de captura de tela anterior, ](media/teamscallout3.png)
 **Routing method** você pode escolher **atendedor**, **serial**, **Idle mais longo**ou **rodízio** como método de distribuição. Todas as filas de chamadas novas e existentes têm roteamento de atendedor selecionado por padrão. Quando o roteamento do atendente é usado, a primeira chamada na fila toca em todos os agentes de chamada ao mesmo tempo. O primeiro agente de chamadas para atender a chamada recebe a chamada.

- O **Roteamento de atendedor** faz com que a primeira chamada na fila toque em todos os agentes de chamada ao mesmo tempo. O primeiro agente de chamadas para atender a chamada recebe a chamada.
- **Roteamento serial** as chamadas recebidas entram em contato com todos os agentes de chamada, um por um, do início da lista de agentes de chamadas. Os agentes não podem ser solicitados na lista agente de chamadas. Se um agente ignorar ou não atender a chamada, a chamada tocará no próximo agente e experimentará todos os agentes até que ele seja retirado ou expirado.
- As rotas **ociosas mais longas** a próxima chamada disponível para o agente de chamadas, cujo tempo está ocioso o mais longo. O tempo ocioso é definido como o período de tempo durante o qual o estado de presença de um agente de chamada é definido como **disponível** ou **ausente** (se for menor que 10 minutos), no momento da chamada. Se a presença de um agente de chamada estiver definida como **ausente** por mais de 10 minutos, o cronômetro de ociosidade será redefinido. Os Estados de presença de usuários são consultados a cada minuto.

    É importante saber que habilitar essa configuração força o **roteamento baseado em presença** a ser habilitado também.

    > [!IMPORTANT]
    > Os agentes que usam o cliente Skype for Business não receberão chamadas quando a configuração ociosa mais longa estiver habilitada. Se você tiver agentes que usam o Skype ou o negócio, não habilite essa configuração.
- O direcionamento de **rodízio** equilibra a circulação de chamadas de entrada para que cada agente de chamadas obtenha o mesmo número de chamadas da fila. Isso pode ser desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.

![O ícone do número 4 faz referência a um balão no roteamento baseado em presença de roteamento baseado em presença de captura de tela anterior ](media/teamscallout4.png)
 **Presence-based routing** que usa o status de disponibilidade dos agentes de chamada para determinar se um agente deve ser incluído na lista de roteamento de chamadas para o método de roteamento selecionado. Os agentes de chamada cujo status de disponibilidade está definido como **disponível** estão incluídos na lista de circulação de chamadas e podem receber chamadas. Os agentes cujo status de disponibilidade é definido como qualquer outro status serão excluídos da lista de roteamento de chamadas e não receberão chamadas até que seu status de disponibilidade mude novamente para **disponível**.  

Você pode habilitar o roteamento de chamadas baseado em presença com qualquer um dos métodos de roteamento.

Se um agente optar por não receber chamadas, ele não será incluído na lista de roteamento de chamadas, independentemente do seu status de disponibilidade definido como. 

> [!IMPORTANT]
> Os agentes que usam o cliente Skype for Business não são incluídos na lista de roteamento de chamadas quando o roteamento baseado em presença está habilitado, independentemente de seu status de disponibilidade. Os agentes que não estão na lista de circulação de chamadas não recebem chamadas. Se você tiver agentes que usam o Skype for Business, não habilite o encaminhamento de chamadas baseado em presença.

> [!IMPORTANT]
> Nas filas de chamadas de alto volume, as configurações recomendadas são:
>
> Modo de conferência: automático<br>
> Método de roteamento: roteamento de atendedor<br>
> Roteamento baseado em presença: ativado<br>
> Tempo de alerta do agente: 20 segundos


### <a name="select-an-agent-opt-out-option"></a>Selecionar uma opção de cancelamento de agente

![Captura de tela de opções de cancelamento de agente com textos explicativos numerados](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![O ícone do número 1 faz referência a um texto explicativo no agente de captura de tela anterior ](media/teamscallout1.png)
 **pode cancelar a entrada de chamadas** que você pode optar por permitir que os agentes da fila de chamada optem por fazer chamadas de uma fila específica habilitando essa opção.

Habilitar essa opção permite que todos os agentes nesta fila sejam iniciados ou parem de receber chamadas desta fila de chamadas. Você pode revogar o privilégio de cancelamento de agente a qualquer momento desmarcando a caixa de seleção, fazendo com que os agentes se tornem automaticamente para esta fila de novo (a configuração padrão para todos os agentes).

Para acessar a opção de recusa, os agentes podem:

 1. Abra **as opções** no cliente do Skype for Business da área de trabalho.
 2. Na guia **encaminhamento de chamadas** , clique no link **Editar configurações online** .
 3. Na página Configurações do usuário, clique em **filas de chamadas**e desmarque as caixas de seleção para recusar as filas.

    > [!NOTE]
    > Os agentes que usam aplicativos ou pontos de extremidade diferentes da área de trabalho do Skype for Business podem acessar a opção de cancelamento no portal de configurações do usuário [https://aka.ms/cqsettings](https://aka.ms/cqsettings) .
    >
    > Se os agentes estiverem em clientes da área de trabalho do Microsoft Teams, eles poderão se recusar usando as configurações de chamada. 

![O ícone do número 2 faz referência a um balão na configuração de ](media/teamscallout2.png)
 **alerta** anterior do agente de captura de tela

Isso define a duração de um agente sendo notificado sobre uma chamada antes que os métodos de roteamento serial ou Round Robin se movam para o próximo agente.

A configuração padrão é 30 segundos, mas pode ser definida por até 3 minutos.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Configurar o estouro de chamadas e as opções de controle de tempo limite

![Captura de tela das opções de tratamento de estouro com textos explicativos numerados](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![O ícone do número 1 faz referência a um texto explicativo na captura de tela anterior as ](media/teamscallout1.png)
 **chamadas máximas na fila** usam essa configuração para definir o máximo de chamadas que podem esperar na fila ao mesmo tempo. O padrão é 50, mas pode variar de 0 a 200. Quando esse limite for atingido, a chamada será manipulada da maneira que você definiu **quando a configuração número máximo de chamadas for atingida** abaixo.

* * *

![O ícone do número 2 faz referência a um texto explicativo na captura de tela anterior ](media/teamscallout2.png)
 **quando o número máximo de chamadas é atingido** quando a fila de chamadas atinge seu tamanho máximo (definido usando o **máximo de chamadas na configuração de fila** ), você pode escolher o que acontece com as novas chamadas de entrada.

- **Desconectar** A chamada está desconectada.

- **Redirecionar para** Ao escolher essa opção, selecione uma das seguintes opções:

  - **Pessoa na organização** Um usuário online com uma licença do sistema de telefonia e está habilitado para o Enterprise Voice ou tem um plano de chamadas.

  - **Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.

  - **Número de telefone externo** Escolha esta imagem para transferir o chamador para um número de telefone externo que você especificar. Observe o seguinte:

    - A conta do recurso associada ao aplicativo que faz a transferência PSTN deve ter um número de telefone e receber uma licença do sistema de telefonia virtual. Não há suporte para licenças do sistema telefônico. Além disso, a conta do recurso deve ter um dos seguintes:
        - Para uma conta de recurso com um número de plano de chamada, atribua uma licença de [plano de chamada](calling-plans-for-office-365.md) .
        - Para uma conta de recurso com um número de roteamento direto, atribua uma [política de roteamento de voz online](manage-voice-routing-policies.md).
    - O número de telefone de saída exibido é determinado da seguinte maneira:
        - Para números de plano de chamada, o número de telefone do chamador original é exibido.
        - Para números de roteamento direto, o número enviado é baseado na configuração P-Assertd-Identity (PAI) no SBC, da seguinte maneira:
            - Se definido como Disabled, o número de telefone do chamador original será exibido. Esta é a configuração padrão e recomendada.
            - Se definido como habilitado, o número de telefone da conta do recurso será exibido.
    - Não há suporte para transferências entre troncos de plano de chamada e troncos diretos de roteamento.
    
  - **Correio de voz** Selecione o grupo do Microsoft 365 que contém os usuários em sua organização que precisam acessar o correio de voz recebido por esta fila de chamadas e, em seguida, selecione uma das seguintes opções:
      - **Reproduzir um arquivo de áudio** Se você escolher essa opção, selecione **carregar arquivo** para carregar uma mensagem de saudação gravada. A gravação não pode ter mais de 5 MB. 
      - **Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que deseja que o sistema Leia (até 1000 caracteres). Por exemplo, você pode digitar "Desculpe que não podemos fazer sua chamada neste momento. Deixe seu nome, número de telefone e motivo para a sua chamada após o sinal de bipe. "

      Ative a transcrição se quiser habilitar a transcrição de voz para texto de mensagens de voz.

      As mensagens de correio de voz são enviadas para o grupo do Microsoft 365 que você especificar. Para acessar mensagens de correio de voz, os membros do grupo podem abri-los navegando para o grupo no Outlook.

* * *

![O ícone do número 3 faz referência a um balão no tempo limite de chamada de captura de tela anterior ](media/teamscallout3.png)
 **: tempo de espera máximo** você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de expirar e precisar ser redirecionada ou desconectada. O local em que é redirecionado é baseado em como você define a configuração **quando uma chamada atinge o tempo limite** . Você pode definir uma hora de 0 a 45 minutos.

O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos. Isso permite que você manipule o fluxo de chamadas com granularidade mais fina. Por exemplo, você pode especificar que as chamadas não atendidas por um agente dentro de 30 segundos vão para um atendedor automático de pesquisa de diretório.

![O ícone do número 4 faz referência a um balão na captura de tela anterior ](media/teamscallout4.png)
 **quando a chamada atinge o tempo limite** quando a chamada atinge o limite que você definiu no **tempo em que uma chamada pode esperar na configuração da fila** , você pode escolher o que acontecerá com a chamada:

- **Desconectar** A chamada está desconectada.

- **Redirecionar esta chamada para** Ao escolher esta opção, você tem estas opções:

  - **Pessoa na organização** Um usuário online com uma licença do sistema de telefonia e habilitado para o Enterprise Voice ou ter planos de chamada.

  - **Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que você já criou.

  - **Número de telefone externo** Escolha esta imagem para transferir o chamador para um número de telefone externo que você especificar. Observe o seguinte:

    - A conta do recurso associada ao aplicativo que faz a transferência PSTN deve ter um número de telefone e receber uma licença do sistema de telefonia virtual. Não há suporte para licenças do sistema telefônico. Além disso, a conta do recurso deve ter um dos seguintes:
        - Para uma conta de recurso com um número de plano de chamada, atribua uma licença de [plano de chamada](calling-plans-for-office-365.md) .
        - Para uma conta de recurso com um número de roteamento direto, atribua uma [política de roteamento de voz online](manage-voice-routing-policies.md).
    - O número de telefone de saída exibido é determinado da seguinte maneira:
        - Para números de plano de chamada, o número de telefone do chamador original é exibido.
        - Para números de roteamento direto, o número enviado é baseado na configuração P-Assertd-Identity (PAI) no SBC, da seguinte maneira:
            - Se definido como Disabled, o número de telefone do chamador original será exibido. Esta é a configuração padrão e recomendada.
            - Se definido como habilitado, o número de telefone da conta do recurso será exibido.
    - Não há suporte para transferências entre troncos de plano de chamada e troncos diretos de roteamento.
    - **Correio de voz** Selecione o grupo do Microsoft 365 que contém os usuários em sua organização que precisam acessar o correio de voz recebido por esta fila de chamadas e, em seguida, selecione uma das seguintes opções:
      - **Reproduzir um arquivo de áudio** Se você escolher essa opção, selecione **carregar arquivo** para carregar uma mensagem de saudação gravada. A gravação não pode ter mais de 5 MB.
      
      - **Digite uma mensagem de saudação** Se você escolher essa opção, insira o texto que deseja que o sistema Leia (até 1000 caracteres). Por exemplo, você pode digitar "Desculpe que não podemos fazer sua chamada neste momento. Deixe seu nome, número de telefone e motivo para a sua chamada após o sinal de bipe. "

      Ative a transcrição se quiser habilitar a transcrição de voz para texto de mensagens de voz.

      As mensagens de correio de voz são enviadas para o grupo do Microsoft 365 que você especificar. Para acessar mensagens de correio de voz, os membros do grupo podem abri-los navegando para o grupo no Outlook.

## <a name="change-caller-id-for-outbound-calls"></a>Alterar a identificação de chamada para chamadas de saída

Para proteger a identidade de um agente de chamada, altere a identificação de chamadas para chamadas de saída para uma fila de chamadas, atendedor automático ou qualquer número de serviço com o cmdlet **New-CsCallingLineIdentity** , como no exemplo a seguir:

```powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Em seguida, aplique a política ao usuário com o cmdlet **Grant-CallingLineIdentity** como no exemplo a seguir: 

```powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Para obter mais informações, consulte [como a identificação de chamadas pode ser usada em sua organização](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlets da fila de chamadas

Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas. Estes são os cmdlets que você usa para gerenciar uma fila de chamadas.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Microsoft Teams com um único ponto de administração. Isso pode simplificar o seu trabalho diário, quando você tem várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Por que você precisa usar o PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o centro de administração do Microsoft Teams quando você faz alterações para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurar seu computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
