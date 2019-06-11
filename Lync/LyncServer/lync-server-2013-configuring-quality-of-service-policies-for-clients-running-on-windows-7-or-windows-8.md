---
title: 'Lync Server 2013: Configurando políticas de qualidade de serviço para clientes em execução no Windows 7 ou no Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b36c16056ef378910dc0cd5c885dc7b5d896d860
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configurando políticas de qualidade de serviço no Lync Server 2013 para clientes em execução no Windows 7 ou no Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-03-29_

Além de especificar intervalos de porta para uso por seus clientes do Lync, você também deve criar políticas de qualidade de serviço separadas que serão aplicadas a computadores cliente. (As políticas de qualidade de serviço criadas para servidores de conferência, aplicativos e remediação não devem ser aplicadas a computadores cliente.) Essas informações se aplicam apenas a computadores executando o cliente Lync 2013 e o Windows 7 ou Windows 8.

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


Para criar uma política de áudio de qualidade de serviço para computadores com Windows 7 ou Windows 8, primeiro faça logon em um computador onde o gerenciamento de política de grupo foi instalado. Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e, em seguida, conclua o seguinte procedimento:

1.  No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores cliente estiverem localizados em uma UO chamada clientes, a nova política deve ser criada na UO do cliente.

2.  Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, **áudio do Lync**) e clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

5.  No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **políticas**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseada em política**e clique em **criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **áudio do Lync**) na caixa **nome** . Selecione **especificar valor DSCP** e defina o valor como **46**. Deixe **especificar a taxa** de aceleração de saída desmarcada e clique em **Avançar**.

7.  Na página seguinte, verifique se a opção **todos os aplicativos** está selecionada e clique em **Avançar**. Essa configuração instrui a rede a procurar todos os pacotes com uma marcação DSCP de 46, não apenas pacotes criados por um aplicativo específico.

8.  Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou esses pacotes e qual computador (endereço IP) receberá esses pacotes.

9.  Na página quatro, selecione **TCP e UDP** na lista **Selecione o protocolo que esta política de QoS se aplica à** lista suspensa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.

10. Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**. Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 50020 pelas portas 50039 para tráfego de áudio, insira o intervalo de porta usando este formato: **50020:50039**. Clique em **Concluir**.

Depois de criar a política de QoS para o áudio, você deve criar uma segunda política para vídeo. Para criar uma política de vídeo, siga o mesmo procedimento básico que você seguiu ao criar a política de áudio, como fazer essas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **vídeo do Lync**).

  - Defina o valor de DSCP para **34** em vez de 46. (Conforme observado anteriormente, você não precisa usar o valor de DSCP 34; basta atribuir um valor de DSCP diferente do usado para áudio.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 58000 a 58019 para vídeo, defina o intervalo de porta como: **58000:58019**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça estas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Lync Server**).

  - Defina o valor de DSCP para **24** em vez de 46. (Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores de DSCP usados para áudio e vídeo.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 42000 a 42019 para compartilhamento de aplicativos, defina o intervalo de porta como: **42000:42019**.

Para uma política de transferência de arquivos:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **transferências de arquivo do Lync Server**).

  - Defina o valor de DSCP para **14**. (Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)

  - Use o intervalo de porta configurado anteriormente para o aplicativo. Por exemplo, se você reservou portas de 42020 a 42039 para compartilhamento de aplicativos, defina o intervalo de porta como: **42020:42039**.

As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores cliente. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpudate.exe /force

Esse comando pode ser executado em qualquer janela de comando executada com credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.

Lembre-se de que essas políticas devem ser direcionadas para seus computadores cliente. Elas não devem ser aplicadas a servidores que executam o Lync Server.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador completando o seguinte procedimento:

1.  Clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite **regedit** e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Clique com o botão direito do mouse em **tcpip**, aponte para **novo**e, em seguida, clique em **tecla**. Após a criação da nova chave do registro, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**. Depois que o novo valor do registro for criado, digite não **use NLA** e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.

7.  Feche o editor do registro e reinicie o computador.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurando a qualidade do serviço em computadores com vários adaptadores de rede

Se você tiver um computador com vários adaptadores de rede, ocasionalmente poderá ter problemas nos quais valores de DSCP são mostrados como 0x00, em vez do valor configurado. Isso normalmente ocorrerá em computadores em que um ou mais adaptadores de rede não conseguem acessar o domínio do Active Directory (por exemplo, se esses adaptadores forem usados para uma rede privada). Em casos como esse, os valores de DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não podem acessar o domínio.

Se você quiser marcar valores DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, será necessário adicionar e configurar um valor para o registro. Isso pode ser feito completando o seguinte procedimento:

1.  Clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite **regedit** e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Se você não vir uma chave do registro rotulada como **QoS** , clique com o botão direito do mouse em **tcpip**, aponte para **novo**e clique em **tecla**. Após a criação da nova chave, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**. Depois que o novo valor do registro for criado, digite não **use NLA** e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.

Depois de criar e configurar o novo valor do registro, você precisará reinicializar o computador para que as alterações entrem em vigor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

