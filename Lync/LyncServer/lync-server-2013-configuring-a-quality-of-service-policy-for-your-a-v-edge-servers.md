---
title: Configurando uma política de qualidade de serviço para seus servidores de borda A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b75e6094fd7d84e086e31bbc4535faf0df84155
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="15e17-102">Configurando uma política de qualidade de serviço para seus servidores de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15e17-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e17-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="15e17-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="15e17-p101">Além de criar políticas de QoS para seus servidores de Conferências, Aplicativos e Mediação, você também deve criar políticas de áudio e vídeo para o lado interno dos seus servidores de borda de A/V. No entanto, as políticas usadas em seus servidores de Borda são diferentes das políticas usadas em seus servidores de Conferências, Aplicativos e Mediação. Para os servidores de Conferências, Aplicativos e Mediação, você especificou um intervalo de portas de origem; com servidores de Borda, é necessário especificar um intervalo de portas de destino. Por isso não é possível simplesmente aplicar as políticas de QoS do servidor de Conferências, Aplicativos e Mediação em seus servidores de Borda: essas políticas simplesmente não funcionarão. Em vez disso, você deve criar novas políticas e aplicá-las somente aos seus servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="15e17-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="15e17-p102">O procedimento a seguir descreve o processo para criar objetos de Política de Grupo do Active Directory que podem ser usados para gerenciar a Qualidade de Serviço em Servidores de Borda. É possível, é claro, que seus servidores de Borda sejam servidores autônomos que não possuem contas do Active Directory. Neste caso, você pode usar uma Política de Grupo local em vez da Política de Grupo do Active Directory: a única diferença é que você deve criar essas políticas locais usando o Editor de Políticas de Grupo Local e deve criar individualmente o mesmo conjunto de políticas em cada Servidor de Borda. Para iniciar o Editor de Políticas de Grupo Local em um servidor de Borda, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="15e17-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="15e17-113">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="15e17-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="15e17-114">Na caixa de diálogo **Executar**, digite **gpedit.msc** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="15e17-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="15e17-p103">Se estiver criando políticas com base no Active Directory, você deve fazer logon em um computador em que o Gerenciamento de Política de Grupo tenha sido instalado. Neste caso, abra o Gerenciamento de Política de Grupo (clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciamento de Política de Grupo**) e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="15e17-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="15e17-p104">No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores Lync Server estiverem localizados em uma UO chamada Lync Server, a nova política deve ser criada na UO Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15e17-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="15e17-119">Clique com o botão direito no contêiner adequado e clique em **Criar um GPO neste domínio e fornecer um link para ele aqui**.</span><span class="sxs-lookup"><span data-stu-id="15e17-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="15e17-120">Na caixa de diálogo **Novo GPO**, digite um nome para o novo objeto de Política de Grupo na caixa **Nome** (por exemplo, **Áudio do Lync Server**) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="15e17-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="15e17-121">Clique com o botão direito na política recém criada e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="15e17-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="15e17-122">A partir daqui o processo é idêntico, independente de você estar criando uma política do Active Directory ou uma política local:</span><span class="sxs-lookup"><span data-stu-id="15e17-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="15e17-123">No Editor do Gerenciamento de Política de Grupo ou no Editor de Política de Grupo Local, expanda **Configuração do Computador**, **Políticas**, **Configurações do Windows**, clique com o botão direito em **QoS baseada em política** e clique em **Criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="15e17-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="15e17-p105">Na caixa de diálogo **QoS baseada em política**, na página inicial, digite um nome para a nova política (por exemplo, **Áudio do Lync Server**) na caixa **Nome**. Selecione **Especificar valor de DSCP** e defina o valor como **46**. Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15e17-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="15e17-p106">Na página seguinte, certifique-se de que a opção **Todos os aplicativos** esteja selecionada e clique em **Avançar**. Esta configuração instrui a rede a procurar todos os pacotes com uma marcação de DSCP igual a 46, não somente pacotes criados por um aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="15e17-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="15e17-p107">Na terceira página, certifique-se de que ambas as opções **Qualquer endereço IP de origem** e **Qualquer endereço IP de destino** estejam selecionadas e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.</span><span class="sxs-lookup"><span data-stu-id="15e17-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="15e17-131">Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**.</span><span class="sxs-lookup"><span data-stu-id="15e17-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="15e17-132">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="15e17-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="15e17-p109">Sob o cabeçalho **Especifique o número da porta de destino**, selecione **A partir desta porta de destino ou intervalo**. Na caixa de texto que acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservou as portas 49152 até as portas 57500 para o tráfego de áudio, insira o intervalo de portas usando este formato: **49152:57500**. Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="15e17-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="15e17-p110">Depois de criar a política de QoS para o tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo. Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="15e17-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="15e17-139">Use um nome de política diferente (e único) (por exemplo, **Vídeo do Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="15e17-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="15e17-p111">Defina o valor do DSCP como **34** em vez de 46 (observe que você não precisa usar o valor 34 para o DSCP. O único requisito é usar para o vídeo um valor de DSCP diferente do valor usado para o áudio).</span><span class="sxs-lookup"><span data-stu-id="15e17-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="15e17-p112">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou as portas 57501 a 65535 para vídeo, defina o intervalo de portas como: **57501:65535**. Novamente, isso deve ser configurado como intervalo de portas de destino.</span><span class="sxs-lookup"><span data-stu-id="15e17-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="15e17-146">Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, deve criar uma terceira política, fazendo as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="15e17-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="15e17-147">Use um nome de política diferente (e único) (por exemplo, **Compartilhamento de Aplicativos do Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="15e17-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="15e17-p113">Defina o valor do DSCP como **24** em vez de 46 (novamente, não é necessário usar o valor 24 para o DSCP. O único requisito é usar para o compartilhamento de aplicativos um valor de DSCP diferente do valor usado para áudio e vídeo).</span><span class="sxs-lookup"><span data-stu-id="15e17-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="15e17-p114">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo. Por exemplo, se você reservou as portas 40803 a 49151 para o compartilhamento de aplicativos, defina o intervalo de portas como: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="15e17-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="15e17-p115">As novas políticas criadas não terão efeito até que a Política de Grupo tenha sido atualizada nos servidores de Borda. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="15e17-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="15e17-155">Este comando pode ser executado no Lync Server ou em qualquer janela de comando que esteja sendo executada sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="15e17-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="15e17-156">Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="15e17-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="15e17-157">Observe que pode ser necessário reiniciar o servidor de Borda mesmo depois de executar o arquivo Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="15e17-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="15e17-158">Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="15e17-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="15e17-159">Clique em **Iniciar** e depois em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="15e17-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="15e17-160">Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="15e17-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="15e17-161">No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="15e17-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="15e17-p117">Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois de criar a nova chave de registro, digite **QoS** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="15e17-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="15e17-p118">Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois de criar o novo valor do registro, digite **Não usar NLA** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="15e17-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="15e17-p119">Dê um duplo clique em **Não usar NLA**. Na caixa de diálogo **Editar Sequência**, digite **1** na caixa **Dados de valor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="15e17-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="15e17-168">Feche o Editor do Registro e reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="15e17-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

