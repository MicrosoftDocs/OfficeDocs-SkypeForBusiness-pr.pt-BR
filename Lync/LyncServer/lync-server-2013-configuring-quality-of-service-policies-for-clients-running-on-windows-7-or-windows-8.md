---
title: 'Lync Server 2013: Configurando a qualidade de políticas de serviço para clientes em execução no Windows 7 ou Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05835b74f12d5e2d28036b100fd84f207a64e67c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configurando políticas de qualidade de serviço no Lync Server 2013 para clientes que executam o Windows 7 ou Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-03-29_

Além de especificar intervalos de portas para uso pelos seus clientes do Lync, você também deve criar políticas de qualidade de serviço separadas que serão aplicadas aos computadores cliente. (As políticas de qualidade de serviço criadas para servidores de conferência, aplicativo e mediação não devem ser aplicadas aos computadores cliente.) Essas informações se aplicam somente a computadores que executam o cliente Lync 2013 e o Windows 7 ou Windows 8.

O exemplo a seguir usa esse conjunto de intervalos de porta para criar uma política de áudio e uma política de vídeo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de Tráfego do Cliente</th>
<th>Início da Porta</th>
<th>Intervalo da Porta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>508</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativo</p></td>
<td><p>42000</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>508</p></td>
</tr>
</tbody>
</table>


Para criar uma política de áudio de qualidade de serviço para computadores com Windows 7 ou Windows 8, primeiro faça logon em um computador onde o Group Policy Management tenha sido instalado. Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e conclua o procedimento a seguir:

1.  No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores clientes estiverem localizados em uma UO chamada clientes, a nova política deverá ser criada na OU do cliente.

2.  Clique com o botão direito no contêiner adequado e clique em **Criar um GPO neste domínio e fornecer um link para ele aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, **áudio do Lync**) e clique em **OK**.

4.  Clique com o botão direito na política recém criada e depois clique em **Editar**.

5.  No Editor de Gerenciamento de Política de Grupo, expanda **Configuração do computador**, expanda **Políticas**, expanda **Configurações do Windows**, clique com o botão direito em **QoS baseado em política**, e depois clique em **Criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **áudio do Lync**) na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor como **46**. Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.

7. Na próxima página, selecione **somente aplicativos com esse nome executável** e digite o nome **Lync. exe**e clique em **Avançar**. Essa configuração instrui a política a priorizar apenas o tráfego de correspondência do cliente do Lync.

8.  Na terceira página, certifique-se de que ambas as opções **Qualquer endereço IP de origem** e **Qualquer endereço IP de destino** estejam selecionadas e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.

9.  Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.

10. No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**. Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 50020 através de portas 50039 para tráfego de áudio, insira o intervalo de portas usando este formato: **50020:50039**. Clique em **Concluir**.

Depois de criar a política de QoS para o áudio, você deve criar uma segunda política para vídeo. Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **vídeo do Lync**).

  - Defina o valor DSCP para **34** em vez de 46. (Conforme observado anteriormente, não é necessário usar o valor de DSCP 34; você deve apenas atribuir um valor de DSCP diferente daquele usado para áudio.)

  - Use o intervalo de portas configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 58000 a 58019 para vídeo, defina o intervalo de porta como: **58000:58019**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça estas substituições:

  - Use um nome de política diferente (e único) (por exemplo, **Compartilhamento de Aplicativos do Lync Server**).

  - Defina o valor DSCP para **24** em vez de 46. (Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores de DSCP usados para áudio e vídeo.)

  - Use o intervalo de portas configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou as portas de 42000 a 42019 para o compartilhamento de aplicativos, defina o intervalo de porta como: **42000:42019**.

Para uma política de transferência de arquivos:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **transferências de arquivo do Lync Server**).

  - Defina o valor de DSCP para **14**. (Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)

  - Use o intervalo de portas configurado anteriormente para o aplicativo. Por exemplo, se você reservou as portas de 42020 a 42039 para o compartilhamento de aplicativos, defina o intervalo de porta como: **42020:42039**.

As novas políticas criadas não terão efeito até que a política de grupo tenha sido atualizada nos computadores cliente. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:

    Gpudate.exe /force

Este comando pode ser executado em qualquer janela de comando que esteja sendo executada sob as credenciais de administrador. Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**.

Tenha em mente que essas políticas devem ser direcionadas para os computadores clientes. Eles não devem ser aplicados aos servidores que executam o Lync Server.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois de criar a nova chave de registro, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois de criar o novo valor do registro, digite **Não usar NLA** e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Sequência**, digite **1** na caixa **Dados de valor** e clique em **OK**.

7.  Feche o Editor do Registro e reinicie o computador.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurando a qualidade do serviço em computadores com vários adaptadores de rede

Se você tiver um computador que tenha vários adaptadores de rede, ocasionalmente poderá ter problemas nos quais valores de DSCP são mostrados como 0x00, e não o valor configurado. Isso normalmente ocorre em computadores em que um ou mais adaptadores de rede não podem acessar seu domínio do Active Directory (por exemplo, se esses adaptadores são usados para uma rede privada). Em casos como esse, os valores de DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não podem acessar o domínio.

Se quiser marcar valores de DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, será necessário adicionar e configurar um valor ao registro. Isso pode ser feito realizando o procedimento a seguir:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Se você não vir uma chave de registro identificada por **QoS** , clique com o botão direito em **tcpip**, aponte para **novo**e clique em **chave**. Após a criação da nova chave, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois de criar o novo valor do registro, digite **Não usar NLA** e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Sequência**, digite **1** na caixa **Dados de valor** e clique em **OK**.

Após criar e configurar o novo valor do registro, você precisará reiniciar o computador para que as alterações entrem em vigor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

