---
title: Configurando uma política de qualidade de serviço para seus servidores de borda A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Configurando uma política de qualidade de serviço para seus servidores de borda A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Além de criar políticas de QoS para seus servidores de conferência, aplicativo e mediação, você também deve criar políticas de áudio e de vídeo para o lado interno dos seus servidores de borda A/V. No entanto, as políticas usadas em seus servidores de borda são diferentes das políticas usadas em seus servidores de conferência, aplicativo e mediação. Para os servidores de conferência, aplicativo e mediação, você especificou um intervalo de porta de origem; com os servidores de borda, você precisa especificar um intervalo de porta de destino. Por isso você não pode simplesmente aplicar as políticas de QoS do servidor de conferência, aplicativo e mediação a seus servidores de borda: essas políticas simplesmente não funcionarão. Em vez disso, você deve criar novas políticas e aplicar essas políticas somente a seus servidores de borda.

O procedimento a seguir descreve o processo de criação de objetos de política de grupo do Active Directory que podem ser usados para gerenciar a qualidade do serviço em servidores Edge. É claro que é possível que seus servidores de borda sejam servidores autônomos que não tenham contas do Active Directory. Se esse for o caso, você pode usar a política de grupo local em vez da política de grupo do Active Directory: a única diferença é que você deve criar essas políticas locais usando o editor de política de grupo local e deve criar individualmente o mesmo conjunto de políticas em cada servidor de borda. Para iniciar o editor de política de grupo local em um servidor de borda, faça o seguinte:

1.  Clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite **gpedit. msc** e pressione Enter.

Se você estiver criando políticas baseadas no Active Directory, faça logon em um computador onde o gerenciamento de política de grupo foi instalado. Nesse caso, abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e conclua as seguintes etapas:

1.  No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores do Lync Server estiverem localizados em uma OU chamada Lync Server, a nova política deve ser criada na OU do Lync Server.

2.  Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, o **áudio do Lync Server**) e clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

Aqui, o processo é idêntico independentemente de você estar criando uma política do Active Directory ou uma política local:

1.  No editor de gerenciamento de política de grupo ou no editor de política de grupo local, expanda **configuração do computador**, expanda **políticas**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseada em política**e clique em **criar nova política**.

2.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **áudio do Lync Server**) na caixa **nome** . Selecione **especificar valor DSCP** e defina o valor como **46**. Deixe **especificar a taxa** de aceleração de saída desmarcada e clique em **Avançar**.

3.  Na página seguinte, verifique se a opção **todos os aplicativos** está selecionada e clique em **Avançar**. Essa configuração instrui a rede a procurar todos os pacotes com uma marcação DSCP de 46, não apenas pacotes criados por um aplicativo específico.

4.  Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou esses pacotes e qual computador (endereço IP) receberá esses pacotes.

5.  Na página quatro, selecione **TCP e UDP** na lista **Selecione o protocolo que esta política de QoS se aplica à** lista suspensa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.

6.  Em título **especifique o número da porta de destino**, selecione uma **destas portas de destino ou intervalo**. Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 49152 pelas portas 57500 para tráfego de áudio, insira o intervalo de porta usando este formato: **49152:57500**. Clique em **Concluir**.

Depois de criar a política de QoS para o tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo. Para criar uma política de vídeo, siga o mesmo procedimento básico que você seguiu ao criar a política de áudio, como fazer essas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **vídeo do Lync Server**).

  - Defina o valor de DSCP para **34** em vez de 46. (Observe que você não precisa usar um valor de DSCP de 34. O único requisito é que você use um valor DSCP diferente para vídeo do que o usado para áudio.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 57501 a 65535 para vídeo, defina o intervalo de porta como: **57501:65535**. Novamente, isso deve ser configurado como o intervalo de porta de destino.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, será necessário criar uma terceira política e fazer as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Lync Server**).

  - Defina o valor de DSCP para **24** em vez de 46. (Novamente, você não precisa usar um valor de DSCP de 24. O único requisito é que você use um valor DSCP diferente para compartilhamento de aplicativos do que usou para áudio ou vídeo.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 40803 a 49151 para compartilhamento de aplicativos, defina o intervalo de porta como: **40803:49151**.

As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus servidores de borda. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpudate.exe /force

Esse comando pode ser executado no servidor do Lync ou em qualquer janela de comando que esteja em execução em credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**. Observe que talvez seja necessário reiniciar o servidor de borda, mesmo depois de executar o GPUDATE. exe.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador completando o seguinte procedimento:

1.  Clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite **regedit** e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Clique com o botão direito do mouse em **tcpip**, aponte para **novo**e, em seguida, clique em **tecla**. Após a criação da nova chave do registro, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**. Depois que o novo valor do registro for criado, digite não **use NLA** e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.

7.  Feche o editor do registro e reinicie o computador.

</div>

<span> </span>

</div>

</div>

</div>

