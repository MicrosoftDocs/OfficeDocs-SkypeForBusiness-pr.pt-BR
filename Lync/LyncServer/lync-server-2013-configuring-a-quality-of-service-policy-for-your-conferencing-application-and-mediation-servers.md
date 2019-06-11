---
title: 'Lync Server 2013: Configurando uma política de Qualidade de Serviço para seus servidores de Conferência, de Aplicativo e de Mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a79835fb19f5a30a11eac4859f133aeec5c8cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurando uma política de Qualidade de Serviço no Lync Server 2013 para seus servidores de Conferência, de Aplicativo e de Mediação

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-23_

A configuração de intervalos de porta facilita o uso da qualidade do serviço, garantindo que todo o tráfego de um tipo especificado (por exemplo, todo o tráfego de áudio) Percorra o mesmo conjunto de portas. Isso torna mais fácil para o sistema identificar e marcar um determinado pacote: se a porta 49152 for reservada para o tráfego de áudio, qualquer pacote que viajar pela porta 49152 poderá ser marcado com um código DSCP que indica que esse é um pacote de áudio. Em seguida, isso permite aos roteadores identificar o pacote como um pacote de áudio e dar a ele uma prioridade mais alta do que os pacotes não marcados (como pacotes usados para copiar um arquivo de um servidor para outro).

No entanto, simplesmente restringir um conjunto de portas a um tipo específico de tráfego não resulta em pacotes sendo transmitidos por essas portas sendo marcadas com o código DSCP apropriado. Além de definir intervalos de porta, você também deve criar políticas de qualidade de serviço que especificam o código DSCP a ser associado a cada intervalo de porta. Para o Microsoft Lync Server 2013 que geralmente significa a criação de duas políticas: uma para áudio e outra para vídeo.

As políticas de qualidade de serviço são criadas de forma mais fácil e gerenciadas por meio da política de grupo. Essas mesmas políticas também podem ser criadas usando-se as políticas de segurança local. No entanto, isso exige que você repita o mesmo procedimento em cada computador e em cada computador.) Seu conjunto inicial de políticas de QoS (uma para áudio e outro para vídeo) só deve ser aplicado a computadores do Lync Server que executam o servidor de conferência, servidor de aplicativos e/ou serviços do servidor de mediação. Se todos esses computadores estiverem localizados na mesma UO do Active Directory, você pode simplesmente atribuir o novo objeto de política de grupo (GPO) a essa OU. Você também pode executar outras etapas para direcionar a nova política para os computadores especificados; por exemplo, você pode colocar os computadores apropriados em um grupo de segurança e, em seguida, usar a filtragem de segurança de política de grupo para aplicar o GPO apenas a esse grupo de segurança.

Para criar uma política de qualidade de serviço para o gerenciamento de áudio, faça logon em um computador onde o gerenciamento de política de grupo foi instalado. Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e, em seguida, conclua o seguinte procedimento:

1.  No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores do Lync Server estiverem localizados em uma OU chamada Lync Server, a nova política deve ser criada na OU do Lync Server.

2.  Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, **Lync Server QoS**) e, em seguida, clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

5.  No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **políticas**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseada em política**e clique em **criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **Lync Server QoS**) na caixa **nome** . Selecione **especificar valor DSCP** e defina o valor como **46**. Deixe **especificar a taxa** de aceleração de saída desmarcada e clique em **Avançar**.

7.  Na página seguinte, verifique se a opção **todos os aplicativos** está selecionada e clique em **Avançar**. Isso simplesmente garante que todos os aplicativos corresponderão aos pacotes do intervalo de porta especificado com o código DSCP especificado.

8.  Na terceira página, verifique se **qualquer endereço IP de origem e qualquer endereço IP de destino** estão selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou esses pacotes e qual computador (endereço IP) receberá esses pacotes.

9.  Na página quatro, selecione **TCP e UDP** na lista **Selecione o protocolo que esta política de QoS se aplica à** lista suspensa. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.

10. Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**. Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 49152 pelas portas 57500 para tráfego de áudio, insira o intervalo de porta usando este formato: **49152:57500**. Clique em **Concluir**.

<div>


> [!NOTE]  
> O valor de DSCP de 46 é um pouco arbitrário: embora o DSCP 46 seja usado com frequência para marcar pacotes de áudio, você não precisa usar DSCP 46 para comunicações de áudio. Se você já implementou o QoS e estiver usando um código DSCP diferente para áudio (por exemplo, DSCP 40), deverá configurar sua política de qualidade de serviço para usar esse mesmo código (ou seja, 40 para áudio). Se você estiver agora implementando a qualidade do serviço, é recomendável usar o DSCP 46 para áudio, simplesmente porque esse valor é comumente usado para marcar pacotes de áudio.



</div>

Depois de criar a política de QoS para o tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo (e, opcionalmente, uma terceira política para gerenciar o tráfego de compartilhamento de aplicativos). Para criar uma política de vídeo, siga o mesmo procedimento básico que você seguiu ao criar a política de áudio, como fazer essas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **vídeo do Lync Server**).

  - Defina o valor de DSCP para **34** em vez de 46. (Observe que você não precisa usar um valor de DSCP de 34. O único requisito é que você use um valor DSCP diferente para vídeo do que o usado para áudio.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 57501 a 65535 para vídeo, defina o intervalo de porta como: **57501:65535**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, será necessário criar uma terceira política e fazer as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Lync Server**).

  - Defina o valor de DSCP para **24** em vez de 46. (Novamente, você não precisa usar um valor de DSCP de 24. O único requisito é que você use um valor DSCP diferente para compartilhamento de aplicativos do que usou para áudio ou vídeo.)

  - Use o intervalo de porta configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou portas de 40803 a 49151 para compartilhamento de aplicativos, defina o intervalo de porta como: **40803:49151**.

As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores do Lync Server. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpupdate.exe /force

Esse comando pode ser executado no Shell de gerenciamento do Lync Server ou em qualquer janela de comando que esteja em execução em credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.

Para verificar se as novas políticas de QoS foram aplicadas, faça o seguinte:

1.  Em um computador com o Lync Server, clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite **regedit** e pressione Enter.

3.  No editor do registro, expanda **computador**, expanda a **máquina local\_\_hKey**, expanda **software**, expanda **políticas**, expanda **Microsoft**, expanda **Windows**e clique em **QoS**. Em **QoS** , você verá chaves do registro para cada uma das políticas de QoS que você acabou de criar. Por exemplo, se você tiver criado duas novas políticas (uma chamada de QoS de áudio do Lync Server e outra chamada de QoS de vídeo do Lync Server), deverá ter as entradas de registro do Lync Server Audio QoS e do Lync Server Video QoS.

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

