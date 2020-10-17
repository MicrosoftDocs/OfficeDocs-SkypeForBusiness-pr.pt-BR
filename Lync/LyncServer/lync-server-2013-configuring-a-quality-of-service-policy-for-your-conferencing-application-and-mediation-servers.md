---
title: 'Lync Server 2013: Configurando uma política de qualidade de serviço para seus servidores de conferência, aplicativos e mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca1e1e243fe6957fdc5233b248c358d82817516
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508868"
---
# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurando uma política de qualidade de serviço no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-23_

Configurar intervalos de porta facilita o uso da Qualidade de Serviço, garantindo que todo o tráfego de um tipo especificado (por exemplo, todo o tráfego de áudio) percorra o mesmo conjunto de portas. Isso facilita para o sistema identificar e marcar um dado pacote: se a porta 49152 estiver reservada para tráfego de áudio, então qualquer pacote que passar pela porta 49152 poderá ser marcado com um código DSCP indicando que é um pacote de áudio. Por sua vez, isso permite que os roteadores identifiquem o pacote como um pacote de áudio, e forneçam a ele uma prioridade maior que a de pacotes não marcados (como pacotes usados para copiar um arquivo de um servidor a outro).

No entanto, restringir simplesmente um conjunto de portas para um tipo de tráfego específico não faz com que os pacotes que viajam através dessas portas sejam marcados com o código DSCP apropriado. Além de definir o intervalo de portas, é necessário criar políticas de Qualidade de Serviço que especificam que o código DSCP seja associado com cada intervalo de porta. Para o Microsoft Lync Server 2013, isso normalmente significa criar duas políticas: uma para áudio e outra para vídeo.

As políticas de Qualidade de Serviço são criadas e gerenciadas de forma mais fácil usando uma Política de Grupo. (Essas mesmas políticas podem também ser criadas usando políticas de segurança local. No entanto, isso exige que você repita o mesmo procedimento em todos os computadores. O conjunto inicial de políticas de QoS (uma para áudio e outro para vídeo) deve ser aplicado somente aos computadores do Lync Server que executam os serviços servidor de conferência, servidor de aplicativos e/ou servidor de mediação. Se todos esses computadores estiverem localizados no mesmo OU do Active Directory, então você pode simplesmente atribuir um novo objeto de Política de Grupo (GPO) a esse OU. Como alternativa, você pode fazer outro procedimento para abordar a nova política para os computadores especificados; por exemplo, você pode colocar os computadores apropriados em um grupo de segurança, depois usar a filtragem de segurança de Política de Grupo para aplicar a GPO apenas a esse grupo de segurança.

Para criar uma política de Qualidade de Serviço para gerenciar áudio, faça logon em um computador onde o Gerenciamento de Política de Grupo foi instalado. Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e conclua o procedimento a seguir:

1.  No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores Lync Server estiverem localizados em uma UO chamada Lync Server, a nova política deve ser criada na UO Lync Server.

2.  Clique com o botão direito no contêiner adequado e clique em **Criar um GPO neste domínio e fornecer um link para ele aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, **Lync Server QoS**) e clique em **OK**.

4.  Clique com o botão direito na política recém criada e depois clique em **Editar**.

5.  No Editor de Gerenciamento de Política de Grupo, expanda **Configuração do computador**, expanda **Políticas**, expanda **Configurações do Windows**, clique com o botão direito em **QoS baseado em política**, e depois clique em **Criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **Lync Server QoS**) na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor como **46**. Mantenha **Especificar Taxa de Aceleração de Saída** sem selecionar e depois clique em **Avançar**.

7.  Na página seguinte, certifique-se de selecionar **Todos os Aplicativos** e depois clique em **Avançar**. Isso garante que todos os aplicativos compararão os pacotes da porta especificada com o código DSCP especificado.

8.  Na terceira página, certifique-se de que **Qualquer endereço IP de origem e Qualquer endereço IP de destino** estão selecionados e depois clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviar esses pacotes e qual computador (endereço IP) os receberá.

9.  Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.

10. No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**. Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou as portas de 49152 a 57500 para tráfego de aúdio, insira o intervalo de porta usando esse formato: **49152:57500**. Clique em **Concluir**.

<div>


> [!NOTE]  
> O valor DSCP de 46 é de certa forma arbitrário: embora DSCP 46 seja usado com frequência para marcar pacotes de áudio, você não precisa usar o DSCP 46 para comunicação de áudio. Se já tiver implementado QoS e estiver usando um código DSCP diferente para áudio (por exemplo, DSCP 40), então você deverá configurar sua política de Qualidade de Serviço para usar o mesmo código (ou seja, 40 para áudio). Se só agora você estiver implementado a Qualidade de Serviço, recomendamos que você use DSCP 46 para áudio, simplesmente porque este valor é o mais comumente usado para marcar pacotes de áudio.



</div>

Após criar a política QoS para tráfego de áudio, você deverá criar uma segunda política para tráfego de vídeo (e, opcionalmente, uma terceira para gerenciar tráfego de compartilhamento de aplicativos). Para criar uma política para vídeo, siga o mesmo procedimento básico para criar política de áudio, fazendo essas substituições:

  - Use um nome de política diferente (e único, por exemplo, **Vídeo do Lync Server**.

  - Defina o valor DSCP para **34** em vez de 46. (Observe que não é necessário usar um valor DSCP de 34). A única exigência é usar um valor DSCP diferente para vídeo e para áudio).

  - Use o intervalo de porta anteriormente configurado para tráfego de vídeo. Por exemplo, se tiver reservado as portas de 57501 a 65535 para vídeo, então defina o intervalo de porta para: **57501:65535**.

Se decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, você deverá criar uma terceira política, fazendo as seguintes substituições:

  - Use um nome de política diferente (e único) (por exemplo, **Compartilhamento de Aplicativos do Lync Server**).

  - Defina o valor do DSCP como **24** em vez de 46 (novamente, não é necessário usar o valor 24 para o DSCP. O único requisito é usar para o compartilhamento de aplicativos um valor de DSCP diferente do valor usado para áudio e vídeo).

  - Use o intervalo de portas configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou as portas 40803 a 49151 para o compartilhamento de aplicativos, defina o intervalo de portas como: **40803:49151**.

As novas políticas criadas não terão efeito até que a política de grupo tenha sido atualizada nos computadores do Lync Server. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:

    Gpupdate.exe /force

Este comando pode ser executado de dentro do Shell de gerenciamento do Lync Server ou de qualquer janela de comando que esteja sendo executada sob as credenciais de administrador. Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de comando**, e depois em **Executar como administrador**.

Para verificar se as novas políticas de QoS foram aplicadas, faça o seguinte:

1.  Em um computador do Lync Server, clique em **Iniciar** e depois em **Executar**.

2.  Na caixa de diálogo **Executar**, digite **regedit** e depois pressione ENTER.

3.  No editor do registro, expanda **computador**, expanda ** \_ \_ máquina local da hKey**, expanda **software**, expanda **políticas**, expanda **Microsoft**, expanda **Windows**e clique em **QoS**. Em **QoS**, você deverá ver chaves de registro para cada política de QoS criada. Por exemplo, se você criou duas novas políticas (uma chamada de QoS de áudio do Lync Server e outra chamada de QoS de vídeo do Lync Server), deverá ter entradas de registro para o Lync Server Audio QoS e o Lync Server Video QoS.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.

3.  No editor do registro, expanda **HKEY \_ local \_ Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois de criar a nova chave de registro, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois de criar o novo valor do registro, digite **Não usar NLA** e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Sequência**, digite **1** na caixa **Dados de valor** e clique em **OK**.

7.  Feche o Editor do Registro e reinicie o computador.

</div>

<span> </span>

</div>

</div>

</div>

