---
title: "Criar uma fila de chamada do sistema telefônico"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061

description: "Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. "
---

# Criar uma fila de chamada do sistema telefônico

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo agente de chamada disponíveis lidar com a chamada enquanto as pessoas que chamada são ouvir música em espera. Você pode criar única ou várias filas de chamada para a sua organização.
  
Filas de chamada do sistema de telefone podem fornecer:
  
- Uma saudação organizacional.
    
- Música enquanto a pessoa estiver aguardando em espera.
    
- Redirecionamento de chamadas para chamar agentes em listas de distribuição habilitados para email e grupos de segurança.
    
- Como fazer as configurações de tamanho máximo de fila de chamada, tempo limite e opções de tratamento de chamada.
    
Quando alguém chama um número de telefone que está definido para cima para cima com uma fila de chamada, eles ouvirão uma saudação primeiro (se qualquer está configurado) e, em seguida, eles serão colocados na fila e esperar o próximo agente de chamada disponíveis. A pessoa que estiver ligando ouvirá música enquanto estiverem em espera aguardando, e as chamadas serão oferecidas para os agentes de chamada da maneira  *Primeiro a entrar, primeiro a sair*  (FIFO).
  
Todas as chamadas aguardando na fila serão distribuídas usando um modo de roteamento Atendedor ou modo de roteamento serial (disponível para somente a clientes de visualização):
  
- Com o roteamento Atendedor, a primeira chamada na fila tocarão todos os agentes ao mesmo tempo.
    
- Com o roteamento serial, a primeira chamada na fila tocarão todos os agentes de chamada um por vez (disponível para somente a clientes de visualização).
    
-     > [!NOTE]
    > Agentes de chamada estão **Offline**, definiram seu status de presença **como não** incomodar ou aceitaram fora a fila de chamadas não ser chamados.
  
- Somente uma notificação de chamada de entrada (para a chamada no início da fila) de cada vez será enviada para os agentes de chamadas.
    
- Depois que um agente aceita a chamada, a próxima chamada de entrada na fila começará a tocar para os agentes de chamadas.
    
## Etapa 1 - Introdução

Para começar a usar as filas de chamadas, é importante lembrar-se de que:
  
- Sua organização deve ter (no mínimo) uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema telefônico** atribuídos afeta o número de números de serviço que estão disponíveis para serem usados para filas de chamada. O número de filas de chamada, que você pode ter depende do número de licenças de **Conferência de áudio** e de **Sistema telefônico** atribuídos em sua organização. Para saber mais sobre licenciamento,[Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Para redirecionar chamadas para as pessoas em sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para Enterprise Voice ou tem chamando de planos do Office 365. Consulte[Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para ativá-los para o Enterprise Voice, você pode usar o Windows PowerShell. Executar por exemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para saber mais sobre a chamada de planos do Office 365, consulte [O que são chamando planos no Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) e[Chamar planos do Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Os usuários hospedados no local usando o Lync Server 2010 não são suportados como um agentes de fila de chamadas. 
  
- Você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você tem no **Skype para o Centro de administração de negócios** ou transferido do outro provedor de serviços para filas de chamada do sistema telefônico. Para obter e usar os números de chamada gratuita do serviço, você precisa configurar comunicações créditos.
    
    > [!NOTE]
    > Os números de telefone (assinante) não podem ser atribuídos às filas de chamada  somente números de telefone de serviço chamadas gratuitas ou tarifas podem ser usados. 
  
- Quando você estiver distribuindo as chamadas de entrada da fila de chamada de um sistema telefônico, esses clientes são suportados para agentes de chamada:
    
  - Cliente de desktop Skype for Business 2016 (versões de 32 e 64 bits)
    
  - Cliente de desktop Lync 2013 (versões de 32 e 64 bits)
    
  - Todos os modelos de telefone IP compatíveis com o Skype for Business Online. Consulte [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype para Business Client (versão 16.8.196 e posteriores)
    
  - Android Skype para Business Client (versão 6.16.0.9 e posteriores)
    
  - iPhone Skype para Business Client (versão 6.16.0 e posteriores)
    
  - iPad Skype para Business Client (versão 6.16.0 e posteriores)
    
## Etapa 2 - Como adquirir e transferir números de telefone de serviço de chamada gratuita ou tarifada

Antes de poder criar e configurar seu filas de chamada, você precisará obter ou transferir sua chamada Tarifada existente ou serviço de chamada gratuito números. Depois de obter a chamada Tarifada ou números de telefone de chamada gratuita do serviço, elas aparecerão no **Skype para o Centro de administração de negócios** > **voz** > **números de telefone** e o será do **tipo de número** listado será listado como **serviço - chamada gratuito**. Para obter seus números de serviço, consulte [Obtendo números telefônicos de serviço do Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) ou se desejar transferir e número de serviço existente, consulte[Transferir números de telefone para o Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Skype para o Centro de administração de negócios para obter números de serviço. [Gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , em vez para ver como fazê-lo de fora dos Estados Unidos.
  
## Etapa 3 - Criar uma nova fila de chamada

No **Centro de administração do Skype for Business**, clique em **Encaminhamento de chamadas** > **Filas de chamadas** e clique em **Adicionar novas**:
  
### Definir o nome de exibição da fila de chamada, número de telefone e domínio (se houver)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nome** Digite um nome de exibição descritivo para a fila de chamadas. Esse nome é obrigatório e pode conter até 64 caracteres, incluindo espaços. <br/> Esse nome será exibido na notificação da chamada de entrada.  <br/> |
|**2** <br/> |**Número de telefone** Selecione uma Chamada Tarifada de serviço ou o número de telefone de chamada gratuita para a fila de chamada. Isso é opcional. <br/> Se nenhum for listado, você deverá obter os números de serviço antes de poder criar esta fila de chamadas. Para obter os números de serviço, consulte [Obtendo números telefônicos de serviço do Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) <br/> |
|**3** <br/> |**Domínio** Se algum estiver disponível, escolha o domínio do Office 365 que você deseja usar. Ele só estará disponível ser você tiver mais de um domínio sendo usado com o Office 365. Se você tiver mais de um, deverá escolher o nome do domínio na lista. <br/> Por exemplo, você poderia ter um domínio como:  _contoso.com or redmond.contoso.com_.  <br/> |
   
### Definir a saudação e a música reproduzida durante a espera

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Saudação** é opcional. Esta é a saudação que é tocada para as pessoas que ligarem para o número de fila de chamada. <br/> Você pode carregar um arquivo de áudio (formatos. wav, MP3 ou WMA).  <br/> |
|**2** <br/> |**Mantenha a música no** Você pode usar o padrão de música em espera fornecida com a fila de chamadas, ou você pode carregar um arquivo de áudio nos formatos. wav, mp3 ou WMA para usar como sua música personalizada em espera. <br/> |
   
### Selecione o método de distribuição de chamada (disponível para somente a clientes de visualização)

![Shows the call distribution method options](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Método de distribuição de chamadas** Você pode escolher **Atendedor** ou **Serial** para seu método de distribuição de fila de chamada. Todas as filas de chamada novos e existentes terá roteamento Atendedor selecionada por padrão. Para usar o roteamento serial, explicitamente você deve escolher a opção de roteamento **Serial** na interface do usuário e cmdlets. <br/> Quando o roteamento de serial é selecionado e fila chamada é salva, as chamadas da fila tocarão seus agentes um por vez, começando do início da lista de agente. Se um agente descarta ou não retomar uma chamada, a chamada tocarão o próximo agente na lista e tentará todos os agentes um por vez até que ele é selecionado ou tempos de espera na fila.  <br/> > [!NOTE]> Roteamento serial ignorará agentes que estão **Offline**, definiram seu status de presença **como não** incomodar ou tem **optado pelo check-out** do começo chamadas dessa fila.          |
   
### Selecione um agente recusa a opção (disponível para somente a clientes de visualização)

![Shows the agent opt out check box](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Agente de desativar essa opção opção** Você pode optar por permitir agentes de fila de chamada deixar de atender chamadas de uma determinada fila selecionando o **Agente recusar a opção**.  <br/> Essa opção permite que todos os agentes na fila para iniciar ou parar de receber chamadas dessa fila de chamada em serão. Você pode revogar o privilégios de recusa agente a qualquer momento, desmarcando a caixa de seleção causando agentes para tornar-se automaticamente optado para essa fila novamente (a configuração padrão para todos os agentes).  <br/> Para acessar a opção opt, agentes podem fazer o seguinte:  <br/> 1. abrir **Opções de** seu Skype da área de trabalho para o cliente de negócios. <br/> 2. na guia **Encaminhamento de chamadas**, clique no link **Editar configurações on-line** <br/> 3. na página de configurações do usuário, clique em **Ligar filas** e desmarque as caixas de seleção para qualquer filas que eles desejam desativar essa opção. <br/> |
   
### Adicionar agentes de chamada para uma fila de chamadas

![Set up call queues.](../images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
|||
|:-----|:-----|
|**1** <br/> | Os agentes de chamadas (50 no máximo) podem ser: <br/>  Um usuário Online com uma licença de **Sistema telefônico** habilitada para Enterprise Voice ou com um plano de chamada. <br/> > [!NOTE]>  Para redirecionar chamadas para as pessoas em sua organização que estiverem Online, ele devem ter uma licença de **Sistema telefônico** e ser habilitados para Enterprise Voice ou tem um plano de chamada. Consulte[Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para ativá-los para o Enterprise Voice, você pode usar o Windows PowerShell. Executar por exemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           Usuários online com um com uma licença de **Sistema telefônico** ou uma chamada planejar que são adicionados a uma lista de distribuição ou grupo de segurança habilitados para email. Ele poderá demorar até 30 minutos para um novo agente adicionado a uma lista de distribuição ou um grupo de segurança para começar a receber chamadas de uma fila de chamada. Um grupo de segurança ou lista de distribuição recém-criado, pode levar até 48 horas para se tornar disponível para ser usado com filas de chamada. <br/> > [!NOTE]>  Grupos do Office 365 (grupos moderno) não podem ser usados com filas de chamada.          > [!NOTE]>  Os usuários hospedados no local usando o Lync Server 2010 não são suportados.          |
   
### Definir o tamanho máximo da fila e o tempo máximo de espera

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
|||
|:-----|:-----|
|**1**|**Máximo chama na fila** Use isto para definir o máximo de chamadas que pode esperar na fila ao mesmo tempo. O padrão é 50, mas ele pode variar de 0 a 200.Quando esse limite for alcançado, a chamada será tratada da forma como você definiu na configuração **Quando o número máximo de chamadas é alcançado** abaixo.|
|**2**|**Quando o número máximo de chamadas é alcançado** Quando a fila de chamada atinge o tamanho máximo (definido usando a configuração **máximo chama na fila** ), você pode escolher o que acontece com novas chamadas. **Desconectar com um sinal de ocupado** A chamada será desconectada. **Encaminhar esta chamada para** Quando você escolhe isso, você terá estas opções: **Pessoa em sua empresa** Um usuário com uma licença de **Sistema telefônico** Online e ser habilitada para Enterprise Voice ou tem um plano de chamada. Você pode configurá-lo para a pessoa que estiver ligando possa ser enviada para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina esta pessoa para que suas chamadas sejam encaminhadas diretamente para a caixa postal.> [!NOTE]>  Os usuários hospedados no local usando o Lync Server 2010 não são suportados.          **Fila de chamadas** Você já deve ter criado outra fila de chamada, mas após fazer, você pode selecionar essa fila de chamada. **Atendedor automático** Você já deve ter criado um atendedor automático, mas após fazer, você pode selecionar que atendedor automático. Consulte[Configurar um atendedor automático de sistema telefônico](set-up-a-phone-system-auto-attendant.md). |
|**3**|**Quanto tempo uma chamada pode esperar na fila** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de seu tempo limite expirar e precisar ser redirecionada ou desconectada. Para onde ela será direcionada dependerá da configuração da opção **Quando uma chamada atinge o tempo limite.** Você pode definir um período de 0 a 45 minutos.> [!NOTE]> **Disponível para somente a clientes de visualização:** O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos. Isso permite manipular o fluxo de chamadas com alto nível. Por exemplo, você pode especificar que as chamadas que não são respondidas por um agente dentro de 30 segundos acessem um Atendedor de pesquisa de diretório.          |
|**4**|**Quando uma chamada atinge o tempo limite** Quando uma chamada atinge o tempo limite que você definiu na configuração **Por quanto tempo uma chamada pode esperar na fila**, é possível escolher o que acorrerá com essa chamada: **Desconectar** A chamada será desconectada. **Encaminhar esta chamada para** Quando você escolhe isso, você terá estas opções: **Pessoa em sua empresa** Um usuário com uma licença de **Sistema telefônico** Online e ser habilitada para Enterprise Voice ou têm planos de chamada. Você pode configurá-lo para a pessoa que estiver ligando possa ser enviada para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina esta pessoa para que suas chamadas sejam encaminhadas diretamente para a caixa postal.> [!NOTE]>  Os usuários hospedados no local usando o Lync Server 2010 não são suportados.          **Fila de chamadas** Você já deve ter criado outra fila de chamada, mas após fazer, você pode selecionar essa fila de chamada. **Atendedor automático** Você já deve ter criado um atendedor automático, mas após fazer, você pode selecionar que atendedor automático. Consulte[Configurar um atendedor automático de sistema telefônico](set-up-a-phone-system-auto-attendant.md). |
   
## Alterando a ID de chamador do usuário para ser o número de telefone de uma chamada de fila

Você pode proteger a identidade do usuário, alterando sua ID de chamador para as chamadas de saída para uma fila de chamada em vez disso, criando uma política usando o cmdlet **New-CallingLineIdentity**.
  
Para fazer isso, execute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity**. Para fazer isso, execute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Você pode obter mais informações sobre como fazer alterações nas configurações de ID do chamador na sua organização [Como a identificação de chamadas pode ser usada em sua organização](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.
  
### Cmdlets da fila de chamadas

Veja os cmdlets necessários para gerenciar uma fila de chamadas.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### Mais sobre o Windows PowerShell

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

