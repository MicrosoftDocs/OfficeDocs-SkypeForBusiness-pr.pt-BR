---
title: Configurando intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, aplicativo e mediação
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, aplicativo e mediação.
ms.openlocfilehash: 76373407a8087e3646668d7ce9952c83c500af97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817440"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configurando intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, aplicativo e mediação

Este artigo descreve como configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, aplicativo e mediação.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Para implementar a qualidade do serviço, você deve configurar intervalos de porta idênticos para compartilhamento de áudio, vídeo e aplicativos em seus servidores de conferência, aplicativo e mediação; Além disso, esses intervalos de portas não devem ser sobrepostos de maneira alguma. Para usar um exemplo simples, suponha que você use as portas 10000 a 10999 para vídeo em seus servidores de conferência. Isso significa que você também deve reservar as portas de 10000 a 10999 para o vídeo em seus servidores de aplicativo e mediação. Se você não fizer isso, a QoS não funcionará conforme o esperado.

Da mesma forma, suponha que você reserve portas de 10000 a 10999 para vídeo, mas Reserve portas de 10500 a 11999 para áudio. Isso pode criar problemas para a qualidade do serviço, pois os intervalos de porta se sobrepõem. Com o QoS, cada modalidade deve ter um conjunto exclusivo de portas: se você usar as portas 10000 a 10999 para vídeo, será necessário usar um intervalo diferente (por exemplo, 11000 a 11999, para áudio).

Por padrão, os intervalos de porta de áudio e vídeo não se sobrepõem no Skype for Business Server; no entanto, os intervalos de porta atribuídos ao compartilhamento de aplicativos se sobrepõem com os intervalos de porta de áudio e vídeo. (Que, por sua vez, significa que nenhum desses intervalos é exclusivo.) Você pode verificar os intervalos de porta existentes para seus servidores de conferência, aplicativo e mediação executando os três comandos a seguir no Shell de gerenciamento do Skype for Business Server:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Como você pode ver nos comandos anteriores, cada tipo de porta – áudio, vídeo e compartilhamento de aplicativos – recebe dois valores de propriedade separados: o início da porta e a contagem de portabilidade. A porta Start indica a primeira porta usada para essa modalidade; por exemplo, se o início da porta de áudio for igual a 50000, isso significa que a primeira porta usada para tráfego de áudio é a porta 50000. Se o número da porta de áudio for 2 (que não é um valor válido, mas é usado aqui para fins de ilustração), isso significa que apenas duas portas são alocadas para áudio. Se a primeira porta for a porta 50000 e houver um total de duas portas, isso significa que a segunda porta deve ser a porta 50001 (intervalos de porta devem ser contíguos). Como resultado, o intervalo de porta para áudio seria a porta 50000 a 50001, inclusive.<BR><br>Observe que o servidor de aplicativos e o servidor de mediação também dão suporte a QoS para áudio; Você não precisa alterar as portas de vídeo ou de compartilhamento de aplicativos em seus servidores de aplicativos ou servidores de mediação.

Se você executar os três comandos anteriores, verá que os valores de porta padrão para o Skype for Business Server são configurados da seguinte maneira:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriedade</th>
<th>Servidor de conferência</th>
<th>Servidor de aplicativos</th>
<th>Servidor de Mediação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

Conforme observado anteriormente, ao configurar as portas do Skype for Business Server para QoS, certifique-se de que: 1) as configurações da porta de áudio sejam idênticas nos seus servidores de conferência, aplicativos e mediação; e, 2) os intervalos de porta não se sobrepõem. Se você olhar atentamente para a tabela anterior, verá que os intervalos de porta são idênticos nos três tipos de servidor. Por exemplo, a porta de áudio inicial é definida como a porta 49152 em cada tipo de servidor e o número total de portas reservadas para áudio em cada servidor também é idêntica: 8348. No entanto, os intervalos de porta sobrepõem: as portas de áudio começam na porta 49152, mas as portas se reservam para o compartilhamento de aplicativos. Para fazer uso ideal da qualidade do serviço, o compartilhamento de aplicativos deve ser reconfigurado para usar um intervalo de porta exclusivo. Por exemplo, você pode configurar o compartilhamento de aplicativos para iniciar na porta 40803 e para usar as portas do 8348. (Por que 8348 portas? Se você adicionar esses valores juntos--40803 + 8348-------------------------49150 40803-- Como as portas de áudio não começam até a porta 49152, você não terá mais nenhum intervalo de portas sobrepostos.)

Depois de selecionar o novo intervalo de porta para compartilhamento de aplicativos, você pode fazer a alteração usando o cmdlet Set-CsConferencingServer. Essa alteração não precisa ser feita em seus servidores de aplicativos ou em seus servidores de mediação, pois esses servidores não manipulam o tráfego de compartilhamento de aplicativos. Você só precisa alterar valores de porta nestes servidores se decidir reatribuir as portas usadas para tráfego de áudio.

Para modificar os valores de porta para compartilhamento de aplicativos em um único servidor de conferência, execute um comando semelhante a isso dentro do Shell de gerenciamento do Skype for Business Server:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se você quiser fazer essas alterações em todos os seus servidores de conferência, poderá executar esse comando em vez disso:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Depois de alterar as configurações da porta, você deve parar e reiniciar cada serviço afetado pelas alterações.

Não é obrigatório que seus servidores de conferência, servidores de aplicativos e servidores de mediação compartilhem exatamente o mesmo intervalo de porta; o único requisito verdadeiro é que você se reservasse intervalos de porta exclusivos em todos os seus servidores. No entanto, a administração normalmente será mais fácil se você usar o mesmo conjunto de portas em todos os seus servidores.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurar uma política de qualidade de serviço no Skype for Business Server para seus servidores de conferência, aplicativo e mediação

A configuração de intervalos de porta facilita o uso da qualidade do serviço, garantindo que todo o tráfego de um tipo especificado (por exemplo, todo o tráfego de áudio) Percorra o mesmo conjunto de portas. Isso torna mais fácil para o sistema identificar e marcar um determinado pacote: se a porta 49152 for reservada para o tráfego de áudio, qualquer pacote que viajar pela porta 49152 poderá ser marcado com um código DSCP que indica que esse é um pacote de áudio. Em seguida, isso permite aos roteadores identificar o pacote como um pacote de áudio e dar a ele uma prioridade mais alta do que os pacotes não marcados (como pacotes usados para copiar um arquivo de um servidor para outro).

No entanto, simplesmente restringir um conjunto de portas a um tipo específico de tráfego não resulta em pacotes sendo transmitidos por essas portas sendo marcadas com o código DSCP apropriado. Além de definir intervalos de porta, você também deve criar políticas de qualidade de serviço que especificam o código DSCP a ser associado a cada intervalo de porta. Para o Skype for Business Server, isso geralmente significa criar duas políticas: uma para áudio e outra para vídeo.

As políticas de qualidade de serviço são criadas de forma mais fácil e gerenciadas por meio da política de grupo. Essas mesmas políticas também podem ser criadas usando-se as políticas de segurança local. No entanto, isso exige que você repita o mesmo procedimento em cada computador e em cada computador.) Seu conjunto inicial de políticas de QoS (uma para áudio e outro para vídeo) só deve ser aplicado a computadores com o Skype for Business Server que executam os serviços servidor de conferência, servidor de aplicativos e/ou servidor de mediação. Se todos esses computadores estiverem localizados na mesma UO do Active Directory, você pode simplesmente atribuir o novo objeto de política de grupo (GPO) a essa OU. Você também pode executar outras etapas para direcionar a nova política para os computadores especificados; por exemplo, você pode colocar os computadores apropriados em um grupo de segurança e, em seguida, usar a filtragem de segurança de política de grupo para aplicar o GPO apenas a esse grupo de segurança.

Para criar uma política de qualidade de serviço para o gerenciamento de áudio, faça logon em um computador onde o gerenciamento de política de grupo foi instalado. Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e, em seguida, conclua o seguinte procedimento:

1.  No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores do Skype for Business Server estiverem localizados em uma UO chamada Skype for Business Server, a nova política deve ser criada na OU Skype for Business Server.

2.  Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, **Skype for Business Server QoS**) e, em seguida, clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

5.  No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **políticas**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseada em política**e clique em **criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **Skype for Business Server QoS**) na caixa **nome** . Selecione **especificar valor DSCP** e defina o valor como **46**. Deixe **especificar a taxa de aceleração de saída** desmarcada e clique em **Avançar**.

7.  Na página seguinte, verifique se a opção **todos os aplicativos** está selecionada e clique em **Avançar**. Isso simplesmente garante que todos os aplicativos corresponderão aos pacotes do intervalo de porta especificado com o código DSCP especificado.

8.  Na terceira página, verifique se **qualquer endereço IP de origem e qualquer endereço IP de destino** estão selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou esses pacotes e qual computador (endereço IP) receberá esses pacotes.

9.  Na página quatro, selecione **TCP e UDP** na lista **Selecione o protocolo que esta política de QoS se aplica à** lista suspensa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype for Business Server e seus aplicativos cliente.

10. Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**. Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 49152 pelas portas 57500 para tráfego de áudio, insira o intervalo de porta usando este formato: **49152:57500**. Clique em **Concluir**.

> [!NOTE]  
> O valor de DSCP de 46 é um pouco arbitrário: embora o DSCP 46 seja usado com frequência para marcar pacotes de áudio, você não precisa usar DSCP 46 para comunicações de áudio. Se você já implementou o QoS e estiver usando um código DSCP diferente para áudio (por exemplo, DSCP 40), configure sua política de qualidade de serviço para usar esse mesmo código (ou seja, 40 para áudio). Se você estiver agora implementando a qualidade do serviço, é recomendável usar o DSCP 46 para áudio, simplesmente porque esse valor é comumente usado para marcar pacotes de áudio.

Depois de criar a política de QoS para o tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo (e, opcionalmente, uma terceira política para gerenciar o tráfego de compartilhamento de aplicativos). Para criar uma política de vídeo, siga o mesmo procedimento básico que você seguiu ao criar a política de áudio, como fazer essas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **vídeo do Skype for Business Server**).

  - Defina o valor de DSCP para **34** em vez de 46. (Observe que você não precisa usar um valor de DSCP de 34. O único requisito é que você use um valor DSCP diferente para vídeo do que o usado para áudio.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 57501 a 65535 para vídeo, defina o intervalo de porta para isso: **57501:65535**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, deverá criar uma terceira política, fazer as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Skype for Business Server**).

  - Defina o valor de DSCP para **24** em vez de 46. (Novamente, você não precisa usar um valor de DSCP de 24. O único requisito é que você use um valor DSCP diferente para compartilhamento de aplicativos do que usou para áudio ou vídeo.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 40803 a 49151 para compartilhamento de aplicativos, defina o intervalo de porta como: **40803:49151**.

As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores com o Skype for Business Server. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpupdate.exe /force

Esse comando pode ser executado no Shell de gerenciamento do Skype for Business Server ou em qualquer janela de comando que esteja em execução em credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.

Para verificar se as novas políticas de QoS foram aplicadas, faça o seguinte:

1.  Em um computador com o Skype for Business Server, clique em **Iniciar**e, em seguida, clique em **executar**.

2.  Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.

3.  No editor do registro, expanda **computador**, expanda a **máquina local\_\_hKey**, expanda **software**, expanda **políticas**, expanda **Microsoft**, expanda **Windows**e clique em **QoS**. Em **QoS** , você verá chaves do registro para cada uma das políticas de QoS que você acabou de criar. Por exemplo, se você tiver criado duas novas políticas (uma chamada de QoS de áudio do Skype for Business Server e outra chamada de QoS de vídeo do Skype for Business Server), verá entradas do registro para o QoS de áudio do Skype for Business Server e a QoS de vídeo do Skype for Business Server.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador completando o seguinte procedimento:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Clique com o botão direito do mouse em **tcpip**, aponte para **novo**e, em seguida, clique em **tecla**. Após a criação da nova chave do registro, digite **QoS**e pressione ENTER para renomear a chave.

5.  Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**. Depois que o novo valor do registro for criado, digite não **use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.

7.  Feche o editor do registro e reinicie o computador.
