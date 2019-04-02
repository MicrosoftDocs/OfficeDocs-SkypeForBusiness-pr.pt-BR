---
title: Criar uma fila de chamada
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Saiba como configurar o sistema telefônico para filas de chamada de sistema telefônico proporcionar um organizacional saudação, música de espera e redirecionando chamadas para chamar agentes em listas de distribuição e grupos de segurança. Você também pode definir o tamanho máximo da fila, o tempo limite e opções de manipulação de chamada.
ms.openlocfilehash: be8055dfe1d92caa7e3416740856ab2b6578e799
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026225"
---
# <a name="create-a-phone-system-call-queue"></a>Criar uma fila de chamada no Sistema Telefônico

Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera. Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.
  
Filas de chamada do sistema telefônico podem fornecer:
  
- Uma saudação organizacional.
- Música enquanto as pessoas estão aguardando espera.
- Redirecionando de chamadas para operadores em listas de distribuição habilitado para email e grupos de segurança de chamada.
- Criação de configurações para o tamanho máximo da fila de chamada, tempo limite e opções de manipulação de chamadas.

Quando alguém chama para um número de telefone que está associado uma fila de espera de chamada através da [conta do recurso](manage-resource-accounts.md), ele ouvirá uma saudação primeiro (se qualquer um estiver configurado) e, em seguida, eles serão colocados na fila e aguarde o próximo operador de chamada disponível. A pessoa chamando em ouvirá música enquanto eles estão em espera aguardando e as chamadas serão oferecidas aos operadores na ordem *Primeiro na, primeiro Out* (FIFO) chamada.
  
Aguardando na fila de todas as chamadas serão distribuídas usando um dos seguintes métodos:
  
- Com o Atendedor de roteamento, a primeira chamada na fila tocarão todos os operadores ao mesmo tempo.
- Com o roteamento em série, a primeira chamada na fila tocarão todos os agentes de chamada um de cada vez.
- Com o rodízio, roteamento de chamadas de entrada é balanceado para que cada agente de chamada receberá o mesmo número de chamadas da fila.

    > [!NOTE]
    > Agentes de chamada que estão **Offline**, tem definido sua presença como **Não incomodar** ou tem decidido para fora da fila de chamada não serão chamados.
  
- Somente uma notificação de chamada recebida (para a chamada no topo da fila) ao mesmo tempo será enviada para os operadores de chamada.
- Depois que um agente de chamada aceita a chamada, a próxima chamada de entrada na fila será iniciado toques agentes de chamada.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e Skype para Business Online.

## <a name="step-1---get-started"></a>Etapa 1 - Introdução

Para começar a usar as filas de chamada, é importante lembrar algumas coisas:
  
- Um atendedor automático é necessário ter uma conta de recurso associado. Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.
- Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).
- Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).

> [!NOTE] 
> Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.

> [!NOTE]
> Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365. Consulte [Atribuir Skype para licenças de negócios](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [equipes da Microsoft atribuir licenças](assign-teams-licenses.md). Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para saber mais sobre a chamada de planos do Office 365, consulte [sistema telefônico e chamar planos](calling-plan-landing-page.md) e [Chamar planos do Office 365](calling-plans-for-office-365.md).

- Você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou transferidos do outro provedor de serviços para as filas de chamada do sistema telefônico. Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.

    > [!NOTE]
    > Números de telefone do usuário (assinante) não podem ser atribuídos a chamada filas-apenas tarifas de serviço ou números de telefone gratuitos podem ser usados.
  
- Quando você estiver distribuindo as chamadas de entrada de uma fila de espera de chamada de sistema telefônico, esses clientes são suportados para os agentes de chamada:

  - Skype para o cliente de desktop de negócios 2016 (versões de 32 e 64 bits)

  - Cliente de desktop do Lync 2013 (versões de 32 e 64 bits)

  - Todos os modelos de telefone IP, suportados for Microsoft Teams. Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Mac Skype para Business Client (versão 16.8.196 e posterior)

  - Skype Android para Business Client (versão 6.16.0.9 e posterior)

  - iPhone Skype para Business Client (versão 6.16.0 e posterior)

  - iPad Skype para Business Client (versão 6.16.0 e posterior)

  - Cliente do Microsoft Windows de equipes (versões de 32 e 64 bits)

  - Cliente do Microsoft equipes Mac

  - Microsoft Teams iPhone app

  - App Android de equipes da Microsoft

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Etapa 2: obtendo ou transferência de Chamada Tarifada ou números de telefone de chamada gratuita do serviço

Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada. Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**. Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você deseja transferir um número existente de serviço, consulte [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço. Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.

Se você estiver configurando atendedores automáticos, você só pode precisar atribuir um número de telefone a conta do recurso do atendedor automático principal e faça com que ele chamadores diretos para sua fila de espera de chamada. Se for esse o caso, a fila chamada precisará ser criados antes que você pode criar uma opção no atendedor automático que seleciona a fila de chamada.
  
## <a name="step-3---create-a-new-call-queue"></a>Etapa 3: criar uma nova fila de chamada

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Cada fila de chamada é necessário ter uma [conta do recurso](manage-resource-accounts.md)de associada. Você deve criar a conta do recurso primeiro, depois você pode associá-lo à fila de chamada.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o Centro de administração do Microsoft Teams

No **Centro de administração de equipes da Microsoft**, **voz** >  **filas de chamada**, clique em **+ Adicionar novo**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Definir a conta de recursos e o nome de exibição do fila chamada

![Configurando uma fila de espera de chamada.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Número 1](media/sfbcallout1.png)
**Name** Insira um nome de exibição descritivo para a fila de chamada. Isso é necessário e pode conter até 64 caracteres, incluindo espaços.

 Esse nome será exibido na notificação para a chamada de entrada.

* * *

![Número 2](media/sfbcallout2.png)

**Adicionar contas** Selecione uma conta de recurso. A conta do recurso pode ou não ser associada a um tarifas do serviço ou o número de telefone gratuitos para a fila de chamada, mas cada fila de chamada exige uma conta de recurso associado.

Se não existem quaisquer listado, você precisa obter os números de serviço e atribuí-las a uma conta de recursos antes de criar essa fila de espera de chamada, conforme descrito anteriormente. Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Você precisará criar uma conta de recurso, conforme descrito em [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) se quiser que sua fila de chamada para ter um número de telefone associados.

> [!NOTE]
> Se você quer ou precisa atribuir um **domínio** você faria isso atribuindo-o para a conta do recurso para a fila de chamada.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Definir a saudação e música tocado enquanto estiver em espera

![Configurando uma fila de espera de chamada.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Número 1](media/sfbcallout1.png)

**Saudação** é opcional. Esta é a saudação que será reproduzida para as pessoas que a chamada para o número de chamada da fila.

Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. wma).

![Número 2](media/sfbcallout2.png)

**Música de espera** Você pode usar o padrão de música em espera fornecida com a fila chamada ou você pode carregar um arquivo de áudio nos formatos. wav, mp3 ou. wma a ser usado como sua música personalizada em espera.

* * *

### <a name="select-the-call-answering-options"></a>Selecione as opções de atendimento de chamadas

![Mostra a chamada opções de método de distribuição](media/5d249515-d532-4af2-90da-011404028b89.png)

![Número 1](media/sfbcallout1.png)

Você pode selecionar até 200 agentes de chamada pertencentes a listas de mala direta especificadas ou grupos. Agentes de chamada devem ser:

- Um usuário Online com uma licença de **Sistema telefônico** e habilitados para o Enterprise Voice ou com um plano de chamada.

  > [!NOTE]
  > Para redirecionar chamadas para pessoas na sua organização que estiverem Online, ele devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem um plano de chamar. Consulte [Atribuir Skype para licenças de negócios](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [equipes da Microsoft atribuir licenças](assign-teams-licenses.md).

 Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Usuários online com uma licença de **Sistema telefônico** e um plano de chamada que são adicionados a um grupo do Office 365, uma lista de distribuição habilitado para email ou um grupo de segurança. Poderá demorar até 30 minutos para um novo operador adicionado para uma lista de distribuição ou um grupo de segurança para começar a receber chamadas de uma fila de chamada. Um grupo de segurança ou de lista de distribuição recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamada. Recém-criadas grupos do Office 365 estão disponíveis quase imediatamente.

![Configure filas de chamada.](media/skype-for-business-add-agents-to-call-queue.png)

![Número 2](media/sfbcallout2.png)

**Método de roteamento** Você pode escolher o **Attendant**, **Serial**ou **Round Robin** para seu método de distribuição de fila de chamada. Todas as filas de chamada novas e existentes terão roteamento attendant selecionada por padrão. Quando o roteamento attendant é usado, a primeira chamada na fila tocarão todos os agentes de chamada ao mesmo tempo. O agente de chamada primeiro para atender a chamada obtém a chamada.

- **Roteamento Attendant** faz com que a primeira chamada na fila para ligar para todos os agentes de chamada ao mesmo tempo. O agente de chamada primeiro para atender a chamada obtém a chamada.
- **Roteamento em série** faz com que as chamadas recebidas toquem agentes de chamada um por um, começando do início da lista de agentes de chamadas. Se um operador descarta ou não atender uma chamada, a chamada tocará o próximo operador na lista e tentará todos os operadores gradativamente até que ele é buscado ou tempos de espera na fila.
  > [!NOTE]
  > Roteamento em série irá ignorar os operadores que estão **Offline**, tem definido sua presença como **Não incomodar**ou tem **retirado** de obtenção de chamadas da fila de espera.
- **Rodízio** equilibra o roteamento de chamadas de entrada, de modo que cada agente de chamada receberá o mesmo número de chamadas da fila. Isso pode ser muito desejável em um ambiente de venda de entrada para garantir a oportunidade de igual entre todos os agentes de chamada.

### <a name="select-an-agent-opt-out-option"></a>Selecione um operador rejeitar opção

![Caixa de seleção mostra o agente rejeitar](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Número 1](media/sfbcallout1.png)

**Agente rejeitar opção** Você pode optar por permitir que os agentes de fila de chamada recusar aproveitando chamadas a partir de uma determinada fila, selecionando a **Opção rejeitar agente**.

A habilitação dessa opção permite que todos os agentes na fila de espera para iniciar ou parar de receber chamadas dessa fila de espera de chamada em serão. Você pode revogar os privilégios do operador recusar a qualquer momento, desmarcando a caixa de seleção, causando a se tornar aceitos automaticamente para essa fila novamente (configuração padrão para todos os agentes) agentes.

Para acessar a opção de recusar, operadores podem fazer o seguinte:

 1. Abrir **Opções** seu Skype da área de trabalho para o cliente de negócios.
 2. Na guia **Encaminhamento de chamadas** , clique no link **Editar configurações online** .
 3. Na página de configurações do usuário, clique em **Chamar filas**e desmarque as caixas de seleção para qualquer filas para o qual deseja rejeitar.

    > [!NOTE]
    > Agentes usando aplicativos ou pontos de extremidade diferente do Skype para Desktop de negócios pode acessar o consentimento check-out de opção do portal de configurações do usuário [https://aka.ms/cqsettings](https://aka.ms/cqsettings).

![Número 2](media/sfbcallout2.png)
**configuração de alerta de operador**

Isso define a duração de um operador que sejam notificado de uma chamada antes da série ou os métodos de roteamento Round Robin mova para o próximo operador.

A configuração padrão é 30 segundos, mas ela pode ser definida por até 3 minutos.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Definir o excesso de chamada e o tempo limite opções de tratamento

![Configure uma fila de espera de chamada.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Número 1](media/sfbcallout1.png)

**Máximo de chamadas na fila** Use esta opção para definir o máximo de chamadas que pode esperar na fila ao mesmo tempo. O valor padrão é 50, mas ela pode variar de 0 a 200. Quando esse limite for atingido, a chamada será tratada de forma que você definiu na configuração **quando o número máximo de chamadas é atingido** abaixo.

* * *

![Número 2](media/sfbcallout2.png)

**Quando o número máximo de chamadas é atingido** Quando a fila chamada atinge seu tamanho máximo (definido usando a configuração **máximo de chamadas na fila** ), você pode escolher o que acontece às novas chamadas de entrada.

- **Desconectar** A chamada será desconectada.
- **Redirecionar para** Quando você escolhe essa opção, selecione uma destas opções:

  - **Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter um plano de chamada. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.

  Para saber sobre o licenciamento necessários para a caixa postal, consulte [Configure a caixa postal de nuvem](set-up-phone-system-voicemail.md).

  - **Aplicativo de voz** Selecione o nome de qualquer um uma fila de espera de chamada ou que já tenha sido criado atendedor automático.

* * *

![Número 3](media/sfbcallout3.png)

**Tempo limite de chamada: tempo de espera máximo** Você também pode decidir quanto tempo uma chamada pode ser em espera na fila antes ele expire e precisa ser redirecionados ou desconectada. Onde ele será redirecionado baseia-se em como você pode definir a configuração **quando uma chamada expire** . Você pode definir um tempo de 0 a 45 minutos.

O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos. Isso permite que você manipule o fluxo de chamadas com granularidade menor. Por exemplo, você pode especificar que todas as chamadas não respondidas por um agente dentro de 30 segundos ir para um atendedor automático de pesquisa de diretório.

![Número 4](media/sfbcallout4.png)

**Quando a chamada esgota** Quando a chamada alcança o limite definido na configuração de **quanto tempo uma chamada pode esperar na fila** , você pode escolher o que acontece com essa chamada:

- **Desconectar** A chamada será desconectada.
- **Redirecionar essa chamada para** Quando você escolhe essa opção, você terá estas opções:
  - **Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter planos de chamada. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.

  Para saber sobre o licenciamento necessários para a caixa postal, consulte [Configure a caixa postal de nuvem](set-up-phone-system-voicemail.md).

  - **Aplicativo de voz** Selecione o nome de qualquer um uma fila de espera de chamada ou que já tenha sido criado atendedor automático.

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>Alterando o ID do usuário chamador para chamadas de saída 

Você pode proteger a identidade de um usuário, alterando seu ID do chamador para chamadas de saída para uma fila de espera de chamada, atendedor automático ou qualquer número de serviço em vez disso, criando uma política utilizando o cmdlet **New-CsCallingLineIdentity** .

Para fazer isso, execute:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Aplica a política ao usuário usando o cmdlet **Grant-CallingLineIdentity** . Para fazer isso, execute:
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Você pode obter mais informações sobre como fazer alterações nas configurações de ID de chamador em sua organização no artigo [como ID do chamador pode ser usado na sua organização](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="want-to-know-more"></a>Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar filas de chamada.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de fila de chamada

Aqui estão os cmdlets que você precisa para gerenciar uma fila de espera de chamada.
  
- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e Microsoft Teams usando um único ponto de administração que pode simplificar o seu trabalho diário, quando você tem várias tarefas fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Por que você precisa usar o PowerShell do Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Microsoft Teams, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Gerenciar o Office 365 com o Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurar seu computador para o Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Tópicos relacionados

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obter números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
