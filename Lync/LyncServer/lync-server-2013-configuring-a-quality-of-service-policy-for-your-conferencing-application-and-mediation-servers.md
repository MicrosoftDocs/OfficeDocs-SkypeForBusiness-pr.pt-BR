---
title: 'Lync Server 2013: Configurando uma política de qualidade de serviço para seus servidores de conferência, aplicativos e mediação'
description: 'Lync Server 2013: Configurando uma política de qualidade de serviço para seus servidores de conferência, aplicativos e mediação.'
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
ms.openlocfilehash: 0ee82c5f1f6b3025c4052b7e27c1013e0624b756
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545637"
---
# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="5fb14-103">Configurando uma política de qualidade de serviço no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação</span><span class="sxs-lookup"><span data-stu-id="5fb14-103">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fb14-104">_**Última modificação do tópico:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="5fb14-104">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="5fb14-p101">Configurar intervalos de porta facilita o uso da Qualidade de Serviço, garantindo que todo o tráfego de um tipo especificado (por exemplo, todo o tráfego de áudio) percorra o mesmo conjunto de portas. Isso facilita para o sistema identificar e marcar um dado pacote: se a porta 49152 estiver reservada para tráfego de áudio, então qualquer pacote que passar pela porta 49152 poderá ser marcado com um código DSCP indicando que é um pacote de áudio. Por sua vez, isso permite que os roteadores identifiquem o pacote como um pacote de áudio, e forneçam a ele uma prioridade maior que a de pacotes não marcados (como pacotes usados para copiar um arquivo de um servidor a outro).</span><span class="sxs-lookup"><span data-stu-id="5fb14-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="5fb14-108">No entanto, restringir simplesmente um conjunto de portas para um tipo de tráfego específico não faz com que os pacotes que viajam através dessas portas sejam marcados com o código DSCP apropriado.</span><span class="sxs-lookup"><span data-stu-id="5fb14-108">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="5fb14-109">Além de definir o intervalo de portas, é necessário criar políticas de Qualidade de Serviço que especificam que o código DSCP seja associado com cada intervalo de porta.</span><span class="sxs-lookup"><span data-stu-id="5fb14-109">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="5fb14-110">Para o Microsoft Lync Server 2013, isso normalmente significa criar duas políticas: uma para áudio e outra para vídeo.</span><span class="sxs-lookup"><span data-stu-id="5fb14-110">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="5fb14-111">As políticas de Qualidade de Serviço são criadas e gerenciadas de forma mais fácil usando uma Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="5fb14-111">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="5fb14-112">(Essas mesmas políticas podem também ser criadas usando políticas de segurança local.</span><span class="sxs-lookup"><span data-stu-id="5fb14-112">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="5fb14-113">No entanto, isso exige que você repita o mesmo procedimento em todos os computadores. O conjunto inicial de políticas de QoS (uma para áudio e outro para vídeo) deve ser aplicado somente aos computadores do Lync Server que executam os serviços servidor de conferência, servidor de aplicativos e/ou servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="5fb14-113">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="5fb14-114">Se todos esses computadores estiverem localizados no mesmo OU do Active Directory, então você pode simplesmente atribuir um novo objeto de Política de Grupo (GPO) a esse OU.</span><span class="sxs-lookup"><span data-stu-id="5fb14-114">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="5fb14-115">Como alternativa, você pode fazer outro procedimento para abordar a nova política para os computadores especificados; por exemplo, você pode colocar os computadores apropriados em um grupo de segurança, depois usar a filtragem de segurança de Política de Grupo para aplicar a GPO apenas a esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="5fb14-115">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="5fb14-116">Para criar uma política de Qualidade de Serviço para gerenciar áudio, faça logon em um computador onde o Gerenciamento de Política de Grupo foi instalado.</span><span class="sxs-lookup"><span data-stu-id="5fb14-116">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="5fb14-117">Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e conclua o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="5fb14-117">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="5fb14-p105">No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores Lync Server estiverem localizados em uma UO chamada Lync Server, a nova política deve ser criada na UO Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p105">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="5fb14-120">Clique com o botão direito no contêiner adequado e clique em **Criar um GPO neste domínio e fornecer um link para ele aqui**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-120">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="5fb14-121">Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, **Lync Server QoS**) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-121">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="5fb14-122">Clique com o botão direito na política recém criada e depois clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-122">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="5fb14-123">No Editor de Gerenciamento de Política de Grupo, expanda **Configuração do computador**, expanda **Políticas**, expanda **Configurações do Windows**, clique com o botão direito em **QoS baseado em política**, e depois clique em **Criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-123">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="5fb14-124">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **Lync Server QoS**) na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="5fb14-124">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="5fb14-125">Selecione **Especificar valor de DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-125">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="5fb14-126">Mantenha **Especificar Taxa de Aceleração de Saída** sem selecionar e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-126">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="5fb14-p107">Na página seguinte, certifique-se de selecionar **Todos os Aplicativos** e depois clique em **Avançar**. Isso garante que todos os aplicativos compararão os pacotes da porta especificada com o código DSCP especificado.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="5fb14-p108">Na terceira página, certifique-se de que **Qualquer endereço IP de origem e Qualquer endereço IP de destino** estão selecionados e depois clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviar esses pacotes e qual computador (endereço IP) os receberá.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="5fb14-131">Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="5fb14-132">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="5fb14-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="5fb14-p110">No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**. Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou as portas de 49152 a 57500 para tráfego de aúdio, insira o intervalo de porta usando esse formato: **49152:57500**. Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5fb14-p111">O valor DSCP de 46 é de certa forma arbitrário: embora DSCP 46 seja usado com frequência para marcar pacotes de áudio, você não precisa usar o DSCP 46 para comunicação de áudio. Se já tiver implementado QoS e estiver usando um código DSCP diferente para áudio (por exemplo, DSCP 40), então você deverá configurar sua política de Qualidade de Serviço para usar o mesmo código (ou seja, 40 para áudio). Se só agora você estiver implementado a Qualidade de Serviço, recomendamos que você use DSCP 46 para áudio, simplesmente porque este valor é o mais comumente usado para marcar pacotes de áudio.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="5fb14-p112">Após criar a política QoS para tráfego de áudio, você deverá criar uma segunda política para tráfego de vídeo (e, opcionalmente, uma terceira para gerenciar tráfego de compartilhamento de aplicativos). Para criar uma política para vídeo, siga o mesmo procedimento básico para criar política de áudio, fazendo essas substituições:</span><span class="sxs-lookup"><span data-stu-id="5fb14-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="5fb14-142">Use um nome de política diferente (e único, por exemplo, **Vídeo do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-142">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="5fb14-p113">Defina o valor DSCP para **34** em vez de 46. (Observe que não é necessário usar um valor DSCP de 34). A única exigência é usar um valor DSCP diferente para vídeo e para áudio).</span><span class="sxs-lookup"><span data-stu-id="5fb14-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="5fb14-p114">Use o intervalo de porta anteriormente configurado para tráfego de vídeo. Por exemplo, se tiver reservado as portas de 57501 a 65535 para vídeo, então defina o intervalo de porta para: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="5fb14-148">Se decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, você deverá criar uma terceira política, fazendo as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="5fb14-148">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="5fb14-149">Use um nome de política diferente (e único) (por exemplo, **Compartilhamento de Aplicativos do Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="5fb14-149">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="5fb14-p115">Defina o valor do DSCP como **24** em vez de 46 (novamente, não é necessário usar o valor 24 para o DSCP. O único requisito é usar para o compartilhamento de aplicativos um valor de DSCP diferente do valor usado para áudio e vídeo).</span><span class="sxs-lookup"><span data-stu-id="5fb14-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="5fb14-p116">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou as portas 40803 a 49151 para o compartilhamento de aplicativos, defina o intervalo de portas como: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="5fb14-155">As novas políticas criadas não terão efeito até que a política de grupo tenha sido atualizada nos computadores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fb14-155">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="5fb14-156">Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="5fb14-156">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="5fb14-157">Este comando pode ser executado de dentro do Shell de gerenciamento do Lync Server ou de qualquer janela de comando que esteja sendo executada sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="5fb14-157">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="5fb14-158">Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de comando**, e depois em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-158">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="5fb14-159">Para verificar se as novas políticas de QoS foram aplicadas, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5fb14-159">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="5fb14-160">Em um computador do Lync Server, clique em **Iniciar** e depois em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-160">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="5fb14-161">Na caixa de diálogo **Executar**, digite **regedit** e depois pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="5fb14-161">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="5fb14-162">No editor do registro, expanda **computador**, expanda \*\* \_ \_ máquina local da hKey\*\*, expanda **software**, expanda **políticas**, expanda **Microsoft**, expanda **Windows**e clique em **QoS**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-162">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="5fb14-163">Em **QoS**, você deverá ver chaves de registro para cada política de QoS criada.</span><span class="sxs-lookup"><span data-stu-id="5fb14-163">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="5fb14-164">Por exemplo, se você criou duas novas políticas (uma chamada de QoS de áudio do Lync Server e outra chamada de QoS de vídeo do Lync Server), deverá ter entradas de registro para o Lync Server Audio QoS e o Lync Server Video QoS.</span><span class="sxs-lookup"><span data-stu-id="5fb14-164">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="5fb14-165">Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="5fb14-165">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="5fb14-166">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-166">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="5fb14-167">Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="5fb14-167">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="5fb14-168">No editor do registro, expanda **HKEY \_ local \_ Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-168">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="5fb14-p120">Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois de criar a nova chave de registro, digite **QoS** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="5fb14-p121">Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois de criar o novo valor do registro, digite **Não usar NLA** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="5fb14-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="5fb14-173">Clique duas vezes em **não usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-173">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="5fb14-174">Na caixa de diálogo **Editar Sequência**, digite **1** na caixa **Dados de valor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fb14-174">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="5fb14-175">Feche o Editor do Registro e reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="5fb14-175">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

