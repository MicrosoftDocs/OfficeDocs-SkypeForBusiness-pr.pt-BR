---
title: Criar ou modificar uma fila de espera no Skype para negócios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Criar ou modificar uma fila de espera do grupo de resposta, em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 6af6f9e4bea089f8b6194a06d1890e7d7e1699ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892913"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Criar ou modificar uma fila de espera no Skype para negócios
 
Criar ou modificar uma fila de espera do grupo de resposta, em Skype para Business Server Enterprise Voice.
  
As filas retêm os chamadores até que um agente atenda à chamada. Quando o aplicativo grupo de resposta procura um operador disponível, ele pesquisará os grupos de operadores na ordem em que você os listar. Você pode selecionar os grupos de agentes que são atribuídos à fila e especificar o comportamento dela, como a limitação do número de chamadas que a fila pode reter e o período de tempo que uma chamada aguarda até que um agente a atenda.
  
Use um dos seguintes procedimentos para criar ou modificar uma fila.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Usar Skype para painel de controle do Business Server para criar ou modificar uma fila

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
    > [!NOTE]
    > Se você for um dos Gerentes do Grupo de Resposta delegados para um fluxo de trabalho gerenciado, é possível criar ou modificar filas de grupo de resposta e atribuí-las aos fluxos de trabalho gerenciados. 
  
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Grupos de Resposta** e clique em **Fila**.
    
4. Na página **Fila**, siga um destes procedimentos:
    
   - Para criar uma nova fila, clique em **Nova**. Em **Selecionar um serviço**, digite uma parte ou o nome inteiro do serviço do **ApplicationServer** onde deseja adicionar a fila no campo de pesquisa. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.
    
   - Para modificar uma fila existente, digite uma parte ou o nome inteiro da fila no campo de pesquisa. Na lista resultante de filas, clique na fila que você deseja, em **Editar**e em **Mostrar detalhes**.
    
5. Em **Nome**, digite um nome identificador para a fila.
    
6. Em **Descrição**, digite uma descrição para a fila.
    
7. Em **Grupos**, especifique os grupos que você deseja atribuir à fila. Siga um destes procedimentos: 
    
   - Para adicionar um grupo à fila, clique em **Selecionar**. No campo de pesquisa **Selecionar grupos**, digite o parte ou o nome inteiro do grupo de agentes que você deseja atribuir à fila, clique no grupo de agentes desejado e em **OK**.
    
   - Para remover um grupo da fila, na lista de grupos de agentes, clique no grupo que você deseja remover e em **Remover**.
    
   - Para alterar a ordem em que os agentes são pesquisados, na lista de grupos de agentes, clique em um grupo e na seta para cima ou para baixo.
    
     > [!NOTE]
     > Quando o servidor pesquisa por um agente disponível para a fila, ele usa a ordem do grupo. Ou seja, o primeiro grupo da lista é pesquisado primeiro, seguido pelo segundo e assim sucessivamente. 
  
8. Para especificar um período máximo de tempo para um chamador aguardar em espera antes que um agente responda à chamada, marque a caixa de seleção  **Habilitar o tempo limite da fila** e, em seguida, faça o seguinte:
    
    a. Em **Período de tempo limite (segundos)**, especifique o número máximo de segundos que um chamador aguarda antes de um agente responder à chamada.
    
    b. Em **Ação de Chamada**, selecione a ação que ocorre quando o tempo limite de uma chamada se esgota da seguinte maneira:
    
   - Para desconectar a chamada após o tempo limite, clique em **Desconectar**.
    
   - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal**e, em seguida, no campo **endereço SIP** , digite um endereço da caixa postal no formato sip: * \<username\>*@ *\<domainname\> * (para Por exemplo, sip:bob@contoso.com).
    
   - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone**e, no campo **endereço SIP** , digite o número de telefone no formato sip: * \<número\>*@ *\<domainname\>* (por exemplo, sip:+14255550121@contoso.com).
    
   - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para endereço SIP**e, em seguida, no campo **endereço SIP** , digite o URI do usuário no formato sip: _ \<username\>_@ _\<domainname\>_.
    
   - Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila**e, em seguida, procure na fila a ser usada.
    
9. Para especificar um número máximo de chamadas que a fila de espera poderá conter, marque a caixa de seleção **Habilitar o estouro da fila** e faça o seguinte:
    
    a. Em **Número máximo de chamadas**, selecione o número máximo de chamadas que a fila de espera conterá. 
    
    b. Em **Encaminhar a chamada**, selecione qual chamada será encaminhada quando a fila estiver cheia: **Chamada Mais Recente** ou **Chamada Mais Antiga**.
    
    c. Em **Ação de chamada**, selecione a ação que ocorre quando o limite de excedente é atingido da seguinte forma:
    
   - Para desconectar a chamada após o tempo limite, clique em **Desconectar**.
    
   - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal**e, em seguida, no campo **endereço SIP** , digite um endereço da caixa postal no formato sip: * \<username\>*@ *\<domainname\> * (para Por exemplo, sip:bob@contoso.com).
    
   - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone**e, no campo **endereço SIP** , digite o número de telefone no formato sip: * \<número\>*@ *\<domainname\>* (por exemplo, sip:+14255550121@contoso.com).
    
   - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para endereço SIP**e, em seguida, no campo **endereço SIP** , digite o URI do usuário no formato sip: _ \<username\>_@ _\<domainname\>_.
    
   - Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila**e, em seguida, procure na fila a ser usada.
    
10. Clique em **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Usar Skype para Business Server Management Shell para criar ou modificar uma fila

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
    > [!NOTE]
    > Se você for um dos Gerentes do grupo de resposta designado para um fluxo de trabalho gerenciado, será possível criar grupos de agentes e filas, bem como atribuir grupos de agentes a filas. 
  
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Crie o prompt para que seja reproduzido quando o limite de tempo da fila for atingido e salve-o em um variável. Na linha de comando, execute:
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Por exemplo:
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Para usar um arquivo de áudio no prompt, use o cmdlet **Import-CsRgsAudioFile**. Para obter detalhes, consulte [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Defina a ação que será executada quando o limite de tempo da fila for atingido e salve-o em um variável. Na linha de comando, execute:
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Para obter detalhes sobre ações possíveis e sua sintaxe, consulte [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Por exemplo:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Crie o prompt que será reproduzido quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Por exemplo:
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Para usar um arquivo de áudio no prompt, use o cmdlet **Import-CsRgsAudioFile**. Para obter detalhes, consulte [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Defina a ação que será executada quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:
    
   ```
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Para obter detalhes sobre ações possíveis e sua sintaxe, consulte [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Por exemplo:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Recupere o nome do serviço do Grupo de Resposta e o atribua a uma variável. Na linha de comando, execute:
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Obtenha a identidade do grupo de agente que será atribuído à fila. Na linha de comando, execute:
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Para obter detalhes sobre como criar um grupo de operadores, consulte [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Crie a fila. Na linha de comando, execute:
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Por exemplo:
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Confirme se a fila foi criada. Execute:
    
    ```
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>Confira também

[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
