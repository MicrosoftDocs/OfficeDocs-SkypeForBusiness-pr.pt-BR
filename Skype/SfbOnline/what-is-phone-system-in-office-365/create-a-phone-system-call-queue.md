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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 9b86bec84846dff36e509488eb34f0415fe8cd95
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2018
ms.locfileid: "21708346"
---
# <a name="create-a-phone-system-call-queue"></a>Criar uma fila de chamadas do Sistema de Telefonia

Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera. Você pode criar um único ou vários filas de chamada para sua organização.
  
Filas de chamada do sistema telefônico podem fornecer:
  
- Uma saudação organizacional.
    
- Música enquanto a pessoa estiver aguardando em espera.
    
- Redirecionando de chamadas para operadores em listas de distribuição habilitado para email e grupos de segurança de chamada.
    
- Criação de configurações para o tamanho máximo da fila de chamada, tempo limite e opções de manipulação de chamadas.
    
Quando alguém ligar um número de telefone que está definido para cima backup com uma fila de espera de chamada, ele ouvirá uma saudação primeiro (se qualquer um estiver configurado) e, em seguida, eles serão colocados na fila e aguarde o próximo operador de chamada disponível. A pessoa que liga ouvirá música quando estiverem esperando e as chamadas serão oferecidas aos agentes de chamada do modo  *Primeiro a entrar, Primeiro a sair*  (FIFO).
  
Aguardando na fila de todas as chamadas serão distribuídas usando um modo de roteamento attendant ou o modo serial de roteamento:
  
- Com o Atendedor de roteamento, a primeira chamada na fila tocarão todos os operadores ao mesmo tempo.
    
- Com o roteamento em série, a primeira chamada na fila tocarão todos os agentes de chamada um de cada vez.
    
    > [!NOTE]
    > Agentes de chamada que estão **Offline**, tem definido sua presença como **Não incomodar** ou tem decidido para fora da fila de chamada não serão chamados.
  
- Somente uma notificação de chamada de entrada (para a chamada no início da fila) de cada vez será enviada para os agentes de chamadas.
    
- Depois que um agente aceita a chamada, a próxima chamada de entrada na fila começará a tocar para os agentes de chamadas.
    
## <a name="step-1---getting-started"></a>Etapa 1 - Introdução

Para começar a usar as filas de chamadas, é importante lembrar-se de que:
  
- Sua organização deve ter (no mínimo), uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema telefônico** atribuídos afeta o número de números de serviço que estão disponíveis para serem usados para as filas de chamada. O número de filas de chamada, que você pode ter é dependente do número de licenças de **Sistema telefônico** e **Conferência de áudio** que são atribuídas em sua organização. Para saber mais sobre licenciamento, vá [aqui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para saber mais sobre a chamada de planos do Office 365, consulte [Cite chamar planos no Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) e [Chamar planos do Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Usuários hospedados no local usando o Lync Server 2010 não são suportados como agentes de fila uma chamada. 
  
- Você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Skype para centro de administração de negócios** ou transferidos do outro provedor de serviços para as filas de chamada do sistema telefônico. Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os números de telefone (assinante) não podem ser atribuídos às filas de chamada  somente números de telefone de serviço chamadas gratuitas ou tarifas podem ser usados. 
  
- Quando você estiver distribuindo as chamadas de entrada de uma fila de espera de chamada de sistema telefônico, esses clientes são suportados para os agentes de chamada:
    
  - Cliente de desktop Skype for Business 2016 (versões de 32 e 64 bits)
    
  - Cliente de desktop Lync 2013 (versões de 32 e 64 bits)
    
  - Todos os modelos de telefone IP suportados para o Skype for Business Online. Consulte [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype para Business Client (versão 16.8.196 e posterior) 
    
  - Skype Android para Business Client (versão 6.16.0.9 e posterior)
    
  - iPhone Skype para Business Client (versão 6.16.0 e posterior)
    
  - iPad Skype para Business Client (versão 6.16.0 e posterior)

  - Cliente do Microsoft Windows de equipes (versões de 32 e 64 bits)

  - Cliente do Microsoft equipes Mac

  - Microsoft Teams iPhone app

  - App Android de equipes da Microsoft
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Etapa 2 - Como adquirir e transferir números de telefone de serviço de chamada gratuita ou tarifada

Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada. Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidos no **Skype para centro de administração de negócios** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - chamada gratuita **. Para obter seus números de serviço, consulte [Getting números de telefone de serviço para Skype para equipes da Microsoft e de negócios](getting-service-phone-numbers.md) ou se você deseja transferir e o número de serviço existente, consulte [transferir os números de telefone para o Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Skype para centro de administração de negócios para obter os números de serviço. Vá para [gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.
  
## <a name="step-3---create-a-new-call-queue"></a>Etapa 3 - Criar uma nova fila de chamada

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

No **Centro de administração do Skype for Business**, clique em **Encaminhamento de chamadas** > **Filas de chamadas** e clique em **Adicionar novas**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Definir o nome de exibição da fila de chamada, número de telefone e domínio (se houver)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Número 1](../images/sfbcallout1.png)<br/>
**Nome** Digite um nome de exibição descritivo para a fila de chamadas. Esse nome é obrigatório e pode conter até 64 caracteres, incluindo espaços.<br/> Esse nome será exibido na notificação da chamada de entrada.
***
![Número 2](../images/sfbcallout2.png)<br/>**Número de telefone** Selecione um número de telefone de serviço de chamada gratuita ou tarifada para a fila de chamadas. Isso é opcional. <br/> Se nenhum for listado, você deverá obter os números de serviço antes de poder criar esta fila de chamadas. Para obter seus números de serviço, consulte [Getting números de telefone de serviço para Skype para equipes da Microsoft e de negócios](getting-service-phone-numbers.md)
***
![Número 3](../images/sfbcallout3.png)<br/>**Domínio** Se algum estiver disponível, escolha o domínio do Office 365 que você deseja usar. Ele só estará disponível ser você tiver mais de um domínio sendo usado com o Office 365. Se você tiver mais de um, deverá escolher o nome do domínio na lista.<br/> Por exemplo, você poderia ter um domínio como:  _contoso.com or redmond.contoso.com_.
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Definir a saudação e a música reproduzida durante a espera

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Saudação** é opcional. Esta é a saudação que será reproduzida para as pessoas que a chamada para o número de chamada da fila. <br/> Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. wma).
***
![Número 2](../images/sfbcallout2.png)<br/>**Música de espera** Você pode usar o padrão de música em espera fornecida com a fila chamada ou você pode carregar um arquivo de áudio nos formatos. wav, mp3 ou. wma a ser usado como sua música personalizada em espera. 
   

### <a name="select-the-call-distribution-method"></a>Selecione o método de distribuição de chamada

![Mostra a chamada opções de método de distribuição](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Chame o método de distribuição** Você pode escolher **Attendant** ou **Serial** para seu método de distribuição de fila de chamada. Todas as filas de chamada novas e existentes terão roteamento attendant selecionada por padrão. Para usar o roteamento em série, você deve escolher explicitamente a opção de roteamento **Serial** na interface do usuário e cmdlets. <br/><br/> Quando o roteamento em série for escolhido e a fila de chamada é salvo, as chamadas da fila tocarão seus agentes um por um, começando do início da lista de operadores. Se um operador descarta ou não atender uma chamada, a chamada tocará o próximo operador na lista e tentará todos os operadores gradativamente até que ele é buscado ou tempos de espera na fila.   

> [!NOTE]
> Roteamento em série irá ignorar os operadores que estão **Offline**, tem definido sua presença como **Não incomodar**ou tem **retirado** de obtenção de chamadas da fila de espera. 
   
### <a name="select-an-agent-opt-out-option"></a>Selecione um operador rejeitar opção

![Caixa de seleção mostra o agente rejeitar](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Agente rejeitar opção** Você pode optar por permitir que os agentes de fila de chamada recusar aproveitando chamadas a partir de uma determinada fila, selecionando a **Opção rejeitar agente**.  <br/> A habilitação dessa opção permite que todos os agentes na fila de espera para iniciar ou parar de receber a chamada dessa fila de espera de chamada em serão. Você pode revogar os privilégios do operador recusar a qualquer momento, desmarcando a caixa de seleção, causando a se tornar aceitos automaticamente para essa fila novamente (configuração padrão para todos os agentes) agentes.  <br/><br/> Para acessar a opção de recusar, operadores podem fazer o seguinte:
 1. Abrir **Opções** seu Skype da área de trabalho para o cliente de negócios. 
 2. Na guia **Encaminhamento de chamadas** , clique no link **Editar configurações online** .
 3. Na página de configurações do usuário, clique em **Chamar filas**e desmarque as caixas de seleção para qualquer filas para o qual deseja rejeitar.
 
    > [!NOTE] 
    > Agentes usando Mac, mobile, ou clientes do Lync 2013 ou usuários de voz híbrida que estão hospedados no local usando Skype para o servidor de negócios 2015, pode ir para [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para acessar o consentimento check-out de opção.
   
### <a name="add-call-agents-to-a-call-queue"></a>Adicionar agentes de chamada para uma fila de chamadas

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>Agentes de chamada (máximo de 50) podem ser:
*    Um usuário Online com uma licença de **Sistema telefônico** e habilitados para o Enterprise Voice ou com um plano de chamada. <br/><br/> **Observação:**  Para redirecionar chamadas para pessoas na sua organização que estiverem Online, ele devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem um plano de chamar. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Usuários online com uma licença de **Sistema telefônico** e um plano de chamada que são adicionados a um grupo do Office 365, uma lista de distribuição habilitado para email ou um grupo de segurança. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. Um grupo de segurança ou de lista de distribuição recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamada. Recém-criadas grupos do Office 365 estão disponíveis quase imediatamente. <br/> 

    > [!NOTE] 
    > Usuários hospedados no local usando o Lync Server 2010 não são suportados.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Definir o tamanho máximo da fila e o tempo máximo de espera

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>**Máximo de chamadas na fila** Use isso para definir o tempo máximo que as chamadas podem esperar na fila ao mesmo tempo. O valor padrão é 50, mas ela pode variar de 0 a 200. quando esse limite for atingido, a chamada será manipulada de forma que você definiu na configuração **quando o número máximo de chamadas for alcançado** abaixo.
***
![Número 2](../images/sfbcallout2.png)<br/><br/>**Quando o número máximo de chamadas é atingido** Quando a fila chamada atinge seu tamanho máximo (definido usando a configuração **máximo de chamadas na fila** ), você pode escolher o que acontece às novas chamadas de entrada.
*    **Desconectar com um sinal de ocupado** A chamada será desconectada.
*    **Encaminhar essa chamada para** Quando você escolhe essa opção, você terá estas opções:
     *    **Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter um plano de chamada. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal. <br/> <br/>Para saber sobre o licenciamento necessários para a caixa postal, consulte [Configure a caixa postal do sistema telefônico](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Usuários hospedados no local usando o Lync Server 2010 não são suportados.<br/>
     
     *    **Fila de chamadas** Você já deve ter criado outra fila de espera de chamada, mas depois que você fizer isso, você pode selecionar essa fila de chamada.
     *    **Atendedor automático** Você já deve ter criado um atendedor automático, mas depois que você fizer isso, você pode selecionar esse atendedor automático. Consulte [Configurar um atendedor automático de sistema telefônico](set-up-a-phone-system-auto-attendant.md).
***
![Número 3](../images/sfbcallout3.png)<br/><br/>**Quanto tempo uma chamada pode esperar na fila** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de seu tempo limite expirar e precisar ser redirecionada ou desconectada. Para onde ela será direcionada dependerá da configuração da opção **Quando uma chamada atinge o tempo limite.** Você pode definir um período de 0 a 45 minutos. <br/><br/> O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos. Isso permite que você manipule o fluxo de chamadas com granularidade menor. Por exemplo, você pode especificar que todas as chamadas não respondidas por um agente dentro de 30 segundos ir para um atendedor automático da pesquisa diretório. 

***
![Número 4](../images/sfbcallout4.png)<br/><br/>**Quando uma chamada atinge o tempo limite** Quando uma chamada atinge o tempo limite que você definiu na configuração **Por quanto tempo uma chamada pode esperar na fila**, é possível escolher o que acorrerá com essa chamada:
*    **Desconectar** A chamada será desconectada.
*    **Encaminhar essa chamada para** Quando você escolhe essa opção, você terá estas opções:
     *    **Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter planos de chamada. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal. </br><br/>  Para saber sobre o licenciamento necessários para a caixa postal, consulte [Configure a caixa postal do sistema telefônico](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Usuários hospedados no local usando o Lync Server 2010 não são suportados.<br/>

     *    **Fila de chamadas** Você já deve ter criado outra fila de espera de chamada, mas depois que você fizer isso, você pode selecionar essa fila de chamada.
     *    **Atendedor automático** Você já deve ter criado um atendedor automático, mas depois que você fizer isso, você pode selecionar esse atendedor automático. Consulte [Configurar um atendedor automático de sistema telefônico](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Alterar a ID de chamador do usuário para ser um número de telefone da chamada de uma fila

Você pode proteger a identidade de um usuário alterando sua ID de chamador das chamadas de saída para uma fila de chamada em vez disso, criando uma política utilizando o cmdlet **New-CallingLineIdentity** .
  
Para fazer isso, execute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Aplica a política ao usuário usando o cmdlet **Grant-CallingLineIdentity** . Para fazer isso, execute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Você pode obter mais informações sobre como fazer alterações nas configurações de ID de chamador em sua organização [aqui](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.
  
### <a name="call-queue-cmdlets"></a>Cmdlets da fila de chamadas

Veja os cmdlets necessários para gerenciar uma fila de chamadas.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
