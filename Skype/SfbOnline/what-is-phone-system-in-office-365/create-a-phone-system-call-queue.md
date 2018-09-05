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
description: 'Saiba como configurar filas de chamadas para o Sistema de Telefonia do Office 365 (Cloud PBX) de modo a ter uma saudação da sua organização, música de espera e redirecionamento de chamadas para agentes em listas de distribuição e grupos de segurança. Você também pode definir o tamanho máximo da fila, o tempo limite e opções de administração de chamadas. '
ms.openlocfilehash: 5a3ace77542a86aea1dd77e1ddcf594f61abb738
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780419"
---
# <a name="create-a-phone-system-call-queue"></a>Criar uma fila de chamadas do Sistema de Telefonia

Filas de chamadas do Sistema de Telefonia incluem saudações usadas quando alguém liga para um número de telefone da sua organização, a capacidade de automaticamente colocar chamadas em espera e pesquisar o próximo operador disponível para atender a chamada enquanto a pessoa que ligou escuta a música de espera. Você pode criar uma única file de chamadas para a sua empresa, ou várias.
  
As filas de chamadas do Sistema de Telefonia oferecem:
  
- Uma saudação organizacional.
    
- Música enquanto a pessoa estiver aguardando em espera.
    
- Redirecionamento de chamadas para agentes usando listas de distribuição e grupos de segurança habilitados por e-mail.
    
- Configurações para tamanho máximo de fila de chamadas, tempo limite e opções de administração de chamadas.
    
Quando alguém liga para um número de telefone configurado com uma fila de chamadas, essa pessoa primeiro ouve uma saudação (se configurada) e depois é colocada na fila para aguardar o próximo agente disponível. A pessoa ouvirá música enquanto estiver esperando e a chamada será encaminhada para os agentes de chamadas seguindo o método FIFO,  *(primeiro a entrar, primeiro a sair)*.
  
Todas as chamadas em espera na fila são distribuídas usando um método de encaminhamento para atendedor ou método de encaminhamento em série:
  
- Com o encaminhamento para atendedor, a primeira chamada da fila chama todos agentes ao mesmo tempo.
    
- Com o encaminhamento em série, a primeira chamada da fila chama todos os agentes, um de cada vez.
    
    > [!NOTE]
    > Agentes de chamada que estão **Offline**, definiram sua presença como **Não incomodar** ou optaram por não serem incluídos na fila de chamadas e, portanto, não serão chamados.
  
- Somente uma notificação de chamada de entrada (para a chamada no início da fila) de cada vez será enviada para os agentes de chamadas.
    
- Depois que um agente aceita a chamada, a próxima chamada de entrada na fila começará a tocar para os agentes de chamadas.
    
## <a name="step-1---getting-started"></a>Etapa 1 - Introdução

Para começar a usar as filas de chamadas, é importante lembrar-se de que:
  
- Sua organização deve ter (no mínimo), uma licença de **Sistema de Telefonia** Enterprise E3 plus ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema de Telefonia** atribuídas afeta o número de números de serviço disponíveis para uso nas filas de chamadas. O número de filas de chamadas que você pode ter depende do número de licenças de **Sistema de Telefonia** e **Audioconferência** atribuídas na sua organização. Para saber mais sobre o licenciamento, vá [aqui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Para redirecionar chamadas para pessoas na sua organização que estão Online, elas devem ter uma licença de **Sistema de Telefonia** e ser habilitadas para o Enterprise Voice ou ter Planos de Chamadas do Office 365. Veja [Atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para saber mais sobre os Planos de Chamadas do Office 365, consulte [O que são os Planos de Chamadas do Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) e [Planos de Chamadas para Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Usuários com hospedagem local usando o Lync Server 2010 não têm suportados como agentes de fila uma chamadas. 
  
- Você só pode atribuir números de telefone de serviço gratuitos e pagos que obteve no **centro de administração do Skype for Business** ou que transferiu de outro provedor de serviços para as filas de chamadas do Sistema de Telefonia. Para obter e usar números de serviço gratuitos, você precisa configurar Créditos de Comunicações.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os números de telefone (assinante) não podem ser atribuídos às filas de chamada  somente números de telefone de serviço chamadas gratuitas ou tarifas podem ser usados. 
  
- Quando estiver distribuindo as chamadas de uma fila de Sistema de Telefonia, esses clientes têm suporte para agentes de chamadas:
    
  - Cliente de desktop Skype for Business 2016 (versões de 32 e 64 bits)
    
  - Cliente de desktop Lync 2013 (versões de 32 e 64 bits)
    
  - Todos os modelos de telefone IP com suporte para Skype for Business Online. Consulte [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Cliente Mac do Skype for Business (versão 16.8.196 e posterior) 
    
  - Cliente Android do Skype for Business (versão 6.16.0.9 e posterior)
    
  - Cliente iPhone do Skype for Business (versão 6.16.0 e posterior)
    
  - Cliente iPad do Skype for Business (versão 6.16.0 e posterior)

  - Cliente do Windows para Microsoft Teams (versões de 32 e 64 bits)

  - Cliente Mac para Microsoft Teams

  - Aplicativo do Microsoft Teams para iPhone

  - Aplicativo do Microsoft Teams para Android
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Etapa 2 - Como adquirir e transferir números de telefone de serviço de chamada gratuita ou paga

Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada. Após obter os números de telefone de serviço gratuitos ou pagos, eles serão exibidos no **centro de administração do Skype for Business** > **Voz** > **Números de telefone**, e o **Tipo de número** listado será **Serviço - Gratuito**. Para obter seus números de serviço, consulte [Obter números de telefone de serviço para Skype for Business e Microsoft Teams](getting-service-phone-numbers.md), ou se deseja transferir um número de serviço existente, consulte [Transferir números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, não será possível usar o centro de administração do Skype for Business para obter os números de serviço. Acesse [Gerenciar números de telefone da sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para ver como fazer isso fora dos Estados Unidos.
  
## <a name="step-3---create-a-new-call-queue"></a>Etapa 3 - Criar uma nova Fila de Chamadas

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**

No **centro de administração do Skype for Business**, clique em **Encaminhamento de chamadas** > **Filas de chamadas** e depois em **Adicionar novas**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Definir o nome de exibição da fila de chamada, número de telefone e domínio (se houver)

![Configurar uma fila de chamadas.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Número 1](../images/sfbcallout1.png)<br/>
**Nome** Digite um nome de exibição descritivo para a fila de chamadas. Esse nome é obrigatório e pode ter até 64 caracteres, incluindo espaços. <br/> Esse nome será exibido na notificação da chamada de entrada.
***
![Número 2](../images/sfbcallout2.png)<br/>**Número de telefone** Selecione um número de telefone de serviço gratuito ou pago para a fila de chamadas. Isso é opcional. <br/> Se não houver nenhum listado, você deve obter os números de serviço antes de poder criar esta fila de chamadas. Para obter seus números de serviço, consulte [Obter números de telefone de serviço para Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)
***
![Número 3](../images/sfbcallout3.png)<br/>**Domínio** Se algum estiver disponível, escolha o domínio do Office 365 que você deseja usar. Ele só estará disponível ser você tiver mais de um domínio sendo usado com o Office 365. Se você tiver mais de um, deverá escolher o nome do domínio na lista. <br/> Por exemplo, você poderia ter um domínio como:  _contoso.com or redmond.contoso.com_.
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Definir a saudação e a música reproduzida durante a espera

![Configurar uma fila de chamadas.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>A **saudação** é opcional. Essa é a saudação reproduzida para pessoas que ligam para o número da fila de chamadas. <br/> Você pode carregar um arquivo de áudio (formatos .wav, .mp3 ou .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>**Música de espera**, Você pode usar a música de espera padrão fornecida com a fila de chamadas ou carregar um arquivo de áudio nos formatos .wav, mp3 ou .wma para usar como música de espera personalizada. 
   

### <a name="select-the-call-distribution-method"></a>Selecione o método de distribuição de chamadas

![Mostra as opções de métodos de distribuição de chamadas](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Método de distribuição de chamadas** Você pode escolher o método de distribuição para **Atendedor** ou **em Série** para a sua fila de chamadas. Todas as filas de chamadas novas e existentes terão encaminhamento para o atendedor como padrão. Para mudar isso, você deve escolher explicitamente a opção de encaminhamento em **Série** na interface do usuário e nos cmdlets. <br/><br/> Quando o encaminhamento em série é escolhido e a fila de chamadas é salvo, as chamadas na fila ligaram para os seus agentes um por um, começando pelo início da lista de agentes. Se um agente ignora ou não atende uma chamada, ela passa para o próximo operador da lista, tentando cada agente, um por um, até que seja atendida ou exceda o tempo de espera na fila.   

> [!NOTE]
> O encaminhamento em série ignora agentes que estão **Offline**, com a presença definida como **Não incomodar** ou que **recusaram** receber chamadas da fila de espera. 
   
### <a name="select-an-agent-opt-out-option"></a>Selecionar uma opção de recusa do agente

![Exibe a caixa de seleção de recusa para o agente](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Opção de recusa do agente** Você pode optar por permitir que os agentes se recusem a receber chamadas de uma determinada fila selecionando a **Opção de recusa do agente**.  <br/> Habilitar essa opção permite que todos os agentes da fila de espera recebam ou deixem de receber chamadas dessa fila quando quiserem. Você pode revogar os privilégios de recusa do agente a qualquer momento desmarcando a caixa de seleção, o que faz com que eles automaticamente aceitem participar da fila novamente (configuração padrão para todos os agentes).  <br/><br/> Para acessar a opção de recusa, os agentes podem:
 1. Abrir as **Opções** no cliente Skype for Business na área de trabalho. 
 2. Na guia **Encaminhamento de chamadas**, clicar no link **Editar configurações online**.
 3. Na página de configurações do usuário, clicar em **Filas de Chamadas**e desmarcar as caixas de seleção de todas as filas que desejam recusar.
 
    > [!NOTE] 
    > Agentes que usam clientes Mac, móveis ou do Lync 2013 ou usuários Hybrid Voice hospedados no local usando o servidor Skype for Business 2015, podem ir em [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para acessar a opção de recusa.
   
### <a name="add-call-agents-to-a-call-queue"></a>Adicionar agentes a uma fila de chamadas

![Configurar filas de chamadas.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>Agentes de chamadas (máximo de 50) podem ser:
*    Um usuário Online com uma licença de **Sistema de Telefonia** e habilitados para o Enterprise Voice ou com um Plano de Chamadas. <br/><br/> **Observação:** Para redirecionar chamadas para pessoas na sua organização que estão Online, elas devem ter uma licença de **Sistema de Telefonia** e ser habilitadas para o Enterprise Voice ou ter um Plano de Chamadas. Veja [Atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Usuários online com uma licença de **Sistema de Telefonia** e um Plano de Chamadas que são adicionados a um grupo do Office 365, uma lista de distribuição habilitada para e-mails ou um grupo de segurança. Poderá demorar até 30 minutos para que um novo agente adicionado a uma lista de distribuição ou um grupo de segurança comece a receber chamadas de uma fila. Um grupo de segurança ou uma de lista de distribuição recém-criados podem levar até 48 horas para se tornar disponíveis para uso com filas de chamadas. Grupos recém-criados do Office 365 ficam disponíveis quase que imediatamente. <br/> 

    > [!NOTE] 
    > Não há suporte para usuários hospedados no local usando o Lync Server 2010.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Definir o tamanho máximo da fila e o tempo máximo de espera

![Configurar uma fila de chamadas.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/>**Máximo de chamadas na fila** Use isso para definir o tempo máximo que as chamadas podem esperar na fila ao mesmo tempo. O valor padrão é 50, mas pode variar de 0 a 200. Quando esse limite é atingido, a chamada é manipulada da maneira definida na configuração **Quando o número máximo de chamadas é atingido** abaixo.
***
![Número 2](../images/sfbcallout2.png)<br/><br/>**Quando o número máximo de chamadas é atingido** Quando a fila de chamadas atinge seu tamanho máximo (defina com a configuração **Máximo de chamadas na fila**), você pode decidir o que acontece com as chamadas recebidas.
*    **Desconectar com um sinal de ocupado** A chamada será desconectada.
*    **Encaminhar esta chamada para** Quando você escolhe isso, terá estas opções:
     *    Pessoa na sua empresa Um usuário Online com uma licença de Sistema de Telefonia e habilitado para o Enterprise Voice ou com um Plano de Chamadas.** ** ** ** Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione uma **Pessoa em sua empresa** e defina que essa pessoa terá suas chamadas encaminhadas diretamente para a caixa postal. <br/> <br/>Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](/microsoftteams/set-up-phone-system-voicemail). 
     
        > [!Note]
        > Não há suporte para usuários hospedados no local usando o Lync Server 2010.<br/>
     
     *    **Fila de Chamadas** Você já deve ter criado uma outra fila de chamadas, depois que fizer isso, você pode selecionar essa fila.
     *    **Atendedor Automático** Você já deve ter criado um atendedor automático, então poderá selecioná-lo. Veja [Configurar o atendedor automático do Sistema de Telefonia](set-up-a-phone-system-auto-attendant.md).
***
![Número 3](../images/sfbcallout3.png)<br/><br/>**Quanto tempo uma chamada pode esperar na fila** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de seu tempo limite expirar e precisar ser redirecionada ou desconectada. Para onde ela será direcionada dependerá da configuração da opção **Quando uma chamada atinge o tempo limite.** Você pode definir um período de 0 a 45 minutos. <br/><br/> O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos. Isso permite que você administre o fluxo de chamadas com mais precisão. Por exemplo, você pode especificar que todas as chamadas não atendidas por um agente em até 30 segundos vão para um Atendedor Automático de Pesquisa de Diretório. 

***
![Número 4](../images/sfbcallout4.png)<br/><br/>**Quando uma chamada atinge o tempo limite** Quando uma chamada atinge o tempo limite que você definiu na configuração **Por quanto tempo uma chamada pode esperar na fila**, é possível escolher o que acorrerá com essa chamada:
*    **Desconectar** A chamada será desconectada.
*    **Encaminhar esta chamada para** Quando você escolhe isso, terá estas opções:
     *    **Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema de Telefonia** e habilitado para o Enterprise Voice ou com um Plano de Chamadas. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione uma **Pessoa em sua empresa** e defina que essa pessoa terá suas chamadas encaminhadas diretamente para a caixa postal. </br><br/>  Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](/microsoftteams/set-up-phone-system-voicemail). 

        > [!Note]
        > Não há suporte para usuários hospedados no local usando o Lync Server 2010.<br/>

     *    **Fila de Chamadas** Você já deve ter criado uma outra fila de chamadas, depois que fizer isso, você pode selecionar essa fila.
     *    **Atendedor Automático** Você já deve ter criado um atendedor automático, então poderá selecioná-lo. Veja [Configurar o atendedor automático do Sistema de Telefonia](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Alterar a identificação de chamadas do usuário para um número de telefone de fila de chamadas

Você pode proteger a identidade de um usuário alterando a identificação de chamadas dele para chamadas de saída para uma fila de chamadas criando uma política com o cmdlet **New-CallingLineIdentity**.
  
Para isso, execute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Então, aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity**. Para isso, execute:
  
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

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
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

  
 
