---
title: Criar uma fila de chamadas do Sistema de Telefonia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar filas de chamadas para o Sistema de Telefonia do Office 365 (Cloud PBX) de modo a ter uma saudação da sua organização, música de espera e redirecionamento de chamadas para agentes em listas de distribuição e grupos de segurança. Você também pode definir o tamanho máximo da fila, o tempo limite e opções de administração de chamadas. '
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375145"
---
# <a name="create-a-phone-system-call-queue"></a>Criar uma fila de chamadas do Sistema de Telefonia

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
As filas de chamadas do Sistema de Telefonia oferecem:
  
- Uma saudação organizacional.
    
- Música enquanto a pessoa estiver aguardando em espera.
    
- Redirecionando de chamadas para operadores em listas de distribuição habilitado para email e grupos de segurança de chamada.
    
- Criação de configurações para o tamanho máximo da fila de chamada, tempo limite e opções de manipulação de chamadas.
    
When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.
  
Aguardando na fila de todas as chamadas serão distribuídas usando um modo de roteamento attendant ou o modo serial de roteamento:
  
- Com o Atendedor de roteamento, a primeira chamada na fila tocarão todos os operadores ao mesmo tempo.
    
- Com o encaminhamento em série, a primeira chamada da fila chama todos os agentes, um de cada vez.
    
    > [!NOTE]
    > Agentes de chamada que estão **Offline**, definiram sua presença como **Não incomodar** ou optaram por não serem incluídos na fila de chamadas e, portanto, não serão chamados.
  
- Somente uma notificação de chamada de entrada (para a chamada no início da fila) de cada vez será enviada para os agentes de chamadas.
    
- Depois que um agente aceita a chamada, a próxima chamada de entrada na fila começará a tocar para os agentes de chamadas.
    
## <a name="step-1---getting-started"></a>Etapa 1 - Introdução

Para começar a usar as filas de chamadas, é importante lembrar-se de que:
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para saber mais sobre os Planos de Chamadas do Office 365, consulte [O que são os Planos de Chamadas do Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) e [Planos de Chamadas para Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Usuários hospedados no local usando o Lync Server 2010 não são suportados como agentes de fila uma chamada. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os números de telefone (assinante) não podem ser atribuídos às filas de chamada  somente números de telefone de serviço chamadas gratuitas ou tarifas podem ser usados. 
  
- Quando você estiver distribuindo as chamadas de entrada de uma fila de espera de chamada de sistema telefônico, esses clientes são suportados para os agentes de chamada:
    
  - Cliente de desktop Skype for Business 2016 (versões de 32 e 64 bits)
    
  - Cliente de desktop Lync 2013 (versões de 32 e 64 bits)
    
  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Cliente Mac do Skype for Business (versão 16.8.196 e posterior) 
    
  - Cliente Android do Skype for Business (versão 6.16.0.9 e posterior)
    
  - Cliente iPhone do Skype for Business (versão 6.16.0 e posterior)
    
  - Cliente iPad do Skype for Business (versão 6.16.0 e posterior)

  - Cliente do Windows para Microsoft Teams (versões de 32 e 64 bits)

  - Cliente Mac para Microsoft Teams

  - Aplicativo do Microsoft Teams para iPhone

  - Aplicativo do Microsoft Teams para Android
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Etapa 2 - Como adquirir e transferir números de telefone de serviço de chamada gratuita ou tarifada

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>Etapa 3 - Criar uma nova fila de chamada

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

No **Centro de administração do Skype for Business**, clique em **Encaminhamento de chamadas** > **Filas de chamadas** e clique em **Adicionar novas**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Definir o nome de exibição da fila de chamada, número de telefone e domínio (se houver)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Número 1](../images/sfbcallout1.png)<br/>
**Nome** Digite um nome de exibição descritivo para a fila de chamadas. Esse nome é obrigatório e pode conter até 64 caracteres, incluindo espaços.<br/> Esse nome será exibido na notificação da chamada de entrada.
***
![Número 2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Número 3](../images/sfbcallout3.png)<br/>**Domínio** Se algum estiver disponível, escolha o domínio do Office 365 que você deseja usar. Ele só estará disponível ser você tiver mais de um domínio sendo usado com o Office 365. Se você tiver mais de um, deverá escolher o nome do domínio na lista. <br/> Por exemplo, você poderia ter um domínio como:  _contoso.com or redmond.contoso.com_.
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Definir a saudação e a música reproduzida durante a espera

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. wma).
***
![Número 2](../images/sfbcallout2.png)<br/>**Música de espera** Você pode usar o padrão de música em espera fornecida com a fila chamada ou você pode carregar um arquivo de áudio nos formatos. wav, mp3 ou. wma a ser usado como sua música personalizada em espera. 
   

### <a name="select-the-call-distribution-method"></a>Selecione o método de distribuição de chamadas

![Mostra as opções de métodos de distribuição de chamadas](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> O encaminhamento em série ignora agentes que estão **Offline**, com a presença definida como **Não incomodar** ou que **recusaram** receber chamadas da fila de espera. 
   
### <a name="select-an-agent-opt-out-option"></a>Selecionar uma opção de recusa do agente

![Exibe a caixa de seleção de recusa para o agente](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Opção de recusa do agente** Você pode optar por permitir que os agentes se recusem a receber chamadas de uma determinada fila selecionando a **Opção de recusa do agente**.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> Para acessar a opção de recusa, os agentes podem:
 1. Abrir as **Opções** no cliente Skype for Business na área de trabalho. 
 2. Na guia **Encaminhamento de chamadas**, clicar no link **Editar configurações online**.
 3. Na página de configurações do usuário, clicar em **Filas de Chamadas**e desmarcar as caixas de seleção de todas as filas que desejam recusar.
 
    > [!NOTE] 
    > Agentes que usam clientes Mac, móveis ou do Lync 2013 ou usuários Hybrid Voice hospedados no local usando o servidor Skype for Business 2015, podem ir em [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para acessar a opção de recusa.
   
### <a name="add-call-agents-to-a-call-queue"></a>Adicionar agentes de chamada para uma fila de chamadas

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>Agentes de chamadas (máximo de 50) podem ser:
* Um usuário Online com uma licença de **Sistema de Telefonia** e habilitados para o Enterprise Voice ou com um Plano de Chamadas. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > Usuários hospedados no local usando o Lync Server 2010 não são suportados.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Definir o tamanho máximo da fila e o tempo máximo de espera

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Número 2](../images/sfbcallout2.png)<br/><br/>**Quando o número máximo de chamadas é atingido** Quando a fila chamada atinge seu tamanho máximo (definido usando a configuração **máximo de chamadas na fila** ), você pode escolher o que acontece às novas chamadas de entrada.
* **Desconectar com um sinal de ocupado** A chamada será desconectada.
* **Encaminhar essa chamada para** Quando você escolhe essa opção, você terá estas opções:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](/microsoftteams/set-up-phone-system-voicemail). 
     
    > [!Note]
    > Usuários hospedados no local usando o Lync Server 2010 não são suportados.<br/>
     
  * **Fila de chamadas** Você já deve ter criado outra fila de espera de chamada, mas depois que você fizer isso, você pode selecionar essa fila de chamada.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Número 3](../images/sfbcallout3.png)<br/><br/>**Quanto tempo uma chamada pode esperar na fila** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de seu tempo limite expirar e precisar ser redirecionada ou desconectada. Para onde ela será direcionada dependerá da configuração da opção **Quando uma chamada atinge o tempo limite.** Você pode definir um período de 0 a 45 minutos. <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Número 4](../images/sfbcallout4.png)<br/><br/>**Quando uma chamada atinge o tempo limite** Quando uma chamada atinge o tempo limite que você definiu na configuração **Por quanto tempo uma chamada pode esperar na fila**, é possível escolher o que acorrerá com essa chamada:
* **Desconectar** A chamada será desconectada.
* **Encaminhar essa chamada para** Quando você escolhe essa opção, você terá estas opções:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Usuários hospedados no local usando o Lync Server 2010 não são suportados.<br/>

  * **Fila de chamadas** Você já deve ter criado outra fila de espera de chamada, mas depois que você fizer isso, você pode selecionar essa fila de chamada.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Alterar a identificação de chamadas do usuário para um número de telefone de fila de chamadas

Você pode proteger a identidade de um usuário alterando a identificação de chamadas dele para chamadas de saída para uma fila de chamadas criando uma política com o cmdlet **New-CallingLineIdentity**.
  
Para fazer isso, execute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Você pode obter mais informações sobre como fazer alterações nas configurações de identificação de chamadas em sua organização [aqui](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.
  
### <a name="call-queue-cmdlets"></a>Cmdlets da fila de chamadas

Veja os cmdlets necessários para gerenciar uma fila de chamadas.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
