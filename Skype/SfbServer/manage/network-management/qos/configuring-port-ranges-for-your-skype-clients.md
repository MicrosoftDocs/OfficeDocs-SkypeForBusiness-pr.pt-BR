---
title: Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de qualidade de serviço no Skype for Business Server para clientes em execução no Windows 10.
ms.openlocfilehash: ce1690c295f1f5ed991780919370e5dbf5b5d6b1
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35204011"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server

Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de qualidade de serviço no Skype for Business Server para clientes em execução no Windows 10.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Por padrão, os aplicativos cliente do Skype for Business podem usar qualquer porta entre as portas 1024 e 65535 quando envolvidos em uma sessão de comunicação; Isso ocorre porque intervalos de porta específicos não são habilitados automaticamente para clientes. No entanto, para usar a qualidade do serviço, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) a uma série de intervalos de porta exclusivos. Isso pode ser feito usando o cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Os usuários finais não podem fazer essas alterações. As alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.


Você pode determinar quais intervalos de porta atualmente são usados para sessões de comunicação executando o seguinte comando no Shell de gerenciamento do Skype for Business Server:

    Get-CsConferencingConfiguration

Pressupondo que você não fez nenhuma alteração nas configurações de conferência desde que instalou o Skype for Business Server, você deve obter informações que incluam estes valores de propriedade:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se você olhar atentamente a saída anterior, verá duas coisas de importância. Primeiro, a propriedade ClientMediaPortRangeEnabled é definida como false:

    ClientMediaPortRangeEnabled : False

Isso é importante porque, quando essa propriedade é definida como falsa, os clientes do Skype for Business usarão qualquer porta disponível entre as portas 1024 e 65535 quando estiverem envolvidos em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort). Se você quiser restringir o uso para um conjunto de portas especificado (e isso é algo que você deseja fazer se planeja implementar a qualidade de serviço), primeiro você deve habilitar os intervalos de porta de mídia do cliente. Isso pode ser feito usando o seguinte comando do Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, essas configurações também podem ser aplicadas ao escopo do site e/ou ao escopo do serviço (somente para o serviço de servidor de conferência). Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, especifique a identidade desse site ou servidor ao chamar Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Ou, se preferir, você pode usar esse comando para habilitar simultaneamente intervalos de porta para todas as suas definições de configuração de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

O segundo motivo da importância que você observará é que a saída do exemplo mostra que, por padrão, os intervalos de porta de mídia definidos para cada tipo de tráfego de rede são idênticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar a QoS, cada um desses intervalos de portas precisará ser exclusivo. Por exemplo, você pode configurar os intervalos de porta como este:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfego do cliente</th>
<th>Início da porta</th>
<th>Intervalo de porta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>42000</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>cedido</p></td>
</tr>
</tbody>
</table>


Na tabela anterior, intervalos de porta do cliente representam um subconjunto de intervalos de porta configurados para seus servidores. Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores cliente, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019. Isso, também, é feito principalmente para facilitar a administração da QoS: as portas do cliente não precisam representar um subconjunto de portas usadas no servidor. (Por exemplo, nos computadores cliente, você pode configurar o compartilhamento de aplicativos para usar, digamos, portas 10000 a 10019.) No entanto, é recomendável que os intervalos de porta do cliente sejam um subconjunto de intervalos de porta do servidor.

Além disso, você pode ter notado que 8348 portas foram reservadas para o compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram reservadas para o compartilhamento de aplicativos nos clientes. Isso também é recomendado, mas não é uma regra difícil e rápida. Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você tiver portas 100 disponíveis em um intervalo de portabilidade, isso significa que o computador em questão pode participar, no máximo, 100 sessões de comunicação a qualquer momento. Como os servidores provavelmente participarão de muitas mais conversas do que clientes, faz sentido abrir muito mais portas em servidores do que em clientes. A configuração de mais de 20 portas para compartilhamento de aplicativos em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e todos ao mesmo tempo. Isso deve provar suficiente para a grande maioria dos seus usuários.

Para atribuir os intervalos de porta precedentes à sua coleção global de definições de configuração de conferência, você pode usar o seguinte comando do Shell de gerenciamento do Skype for Business Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Ou use este comando para atribuir esses mesmos intervalos de portas para todas as suas configurações de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Usuários individuais devem fazer logoff do Skype for Business e, em seguida, fazer logon novamente para que as alterações realmente entrem em vigor.

> [!NOTE]  
> Você também pode habilitar os intervalos de porta de mídia do cliente e, em seguida, atribuir esses intervalos de porta usando um único comando. Por exemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar políticas de qualidade de serviço para clientes em execução no Windows 10

Além de especificar intervalos de porta para uso pelos clientes do Skype for Business, você também deve criar políticas de qualidade de serviço separadas que serão aplicadas aos computadores cliente. (As políticas de qualidade de serviço criadas para servidores de conferência, aplicativos e remediação não devem ser aplicadas a computadores cliente.) Essas informações se aplicam apenas a computadores que executam o cliente Skype for Business e o Windows 10.

O exemplo a seguir usa esse conjunto de intervalos de porta para criar uma política de áudio e uma política de vídeo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfego do cliente</th>
<th>Início da porta</th>
<th>Intervalo de porta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>42000</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>cedido</p></td>
</tr>
</tbody>
</table>

Para criar uma política de qualidade de áudio de serviço para computadores com o Windows 10, primeiro faça logon em um computador onde o gerenciamento de política de grupo foi instalado. Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e, em seguida, conclua o seguinte procedimento:

1.  No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores cliente estiverem localizados em uma UO chamada clientes, a nova política deve ser criada na UO do cliente.

2.  Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** e clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

5.  No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseado em política**e clique em **criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** . Selecione **especificar valor DSCP** e defina o valor como **46**. Deixe **especificar a taxa** de aceleração de saída desmarcada e clique em **Avançar**.

7.  Na próxima página, selecione **apenas aplicativos com esse nome executável**, digite **Lync. exe** como o nome e clique em **Avançar**. Essa configuração instrui a política a priorizar somente o tráfego coincidente do cliente Skype for Business.

8.  Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou esses pacotes e qual computador (endereço IP) receberá esses pacotes.

9.  Na página quatro, selecione **TCP e UDP** na lista **Selecione o protocolo que esta política de QoS se aplica à** lista suspensa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype for Business Server e seus aplicativos cliente.

10. Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**. Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 50020 pelas portas 50039 para tráfego de áudio, insira o intervalo de porta usando este formato: **50020:50039**. Clique em **Concluir**.

Depois de criar a política de QoS para o áudio, você deve criar uma segunda política para vídeo. Para criar uma política de vídeo, siga o mesmo procedimento básico que você seguiu ao criar a política de áudio, como fazer essas substituições:

  - Use um nome de política diferente (e exclusivo).

  - Defina o valor de DSCP para **34** em vez de 46. (Conforme observado anteriormente, você não precisa usar o valor de DSCP 34; basta atribuir um valor de DSCP diferente do usado para áudio.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 58000 a 58019 para vídeo, defina o intervalo de porta para isso: **58000:58019**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça essas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Skype for Business Server**).

  - Defina o valor de DSCP para **24** em vez de 46. (Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores de DSCP usados para áudio e vídeo.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 42000 a 42019 para compartilhamento de aplicativos, defina o intervalo de porta como: **42000:42019**.

Para uma política de transferência de arquivos:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **transferências de arquivo do Skype for Business Server**).

  - Defina o valor de DSCP para **14**. (Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)

  - Use o intervalo de portas configurado anteriormente para o aplicativo. Por exemplo, se você reservou portas de 42020 a 42039 para compartilhamento de aplicativos, defina o intervalo de porta como: **42020:42039**.

As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores cliente. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpudate.exe /force

Esse comando pode ser executado em qualquer janela de comando executada com credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.

Lembre-se de que essas políticas devem ser direcionadas para seus computadores cliente. Elas não devem ser aplicadas a servidores que executam o Skype for Business Server.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador completando o seguinte procedimento:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Clique com o botão direito do mouse em **tcpip**, aponte para **novo**e, em seguida, clique em **tecla**. Após a criação da nova chave do registro, digite **QoS**e pressione ENTER para renomear a chave.

5.  Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**. Depois que o novo valor do registro for criado, digite não **use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.

7.  Feche o editor do registro e eboot seu computador.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurar a qualidade do serviço em computadores com vários adaptadores de rede

Se você tiver um computador com vários adaptadores de rede, você pode ocasionalmente executar em problemas nos quais valores de DSCP são mostrados como 0x00, em vez do valor configurado. Isso normalmente ocorrerá em computadores em que um ou mais adaptadores de rede não conseguem acessar o domínio do Active Directory (por exemplo, se esses adaptadores forem usados para uma rede privada). Em casos como esse, os valores de DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não podem acessar o domínio.

Se você quiser marcar valores DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, será necessário adicionar e configurar um valor para o registro. Isso pode ser feito completando o seguinte procedimento:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Se você não vir uma chave do registro rotulada como **QoS** , clique com o botão direito do mouse em **tcpip**, aponte para **novo**e clique em **tecla**. Após a criação da nova chave, digite **QoS**e pressione ENTER para renomear a chave.

5.  Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**. Depois que o novo valor do registro for criado, digite não **use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.

Depois de criar e configurar o novo valor do registro, será necessário reinicializar o computador para que as alterações entrem em vigor.

## <a name="see-also"></a>Confira também

[Criar um objeto de política de grupo no Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
