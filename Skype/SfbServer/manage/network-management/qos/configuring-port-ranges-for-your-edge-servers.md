---
title: Configurando intervalos de porta e uma qualidade de serviço para seus servidores Edge
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
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
description: Este artigo descreve como configurar intervalos de porta para servidores de borda e como configurar uma política de qualidade de serviço para seus servidores de borda A/V.
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817430"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="4bf6a-103">Configurando intervalos de porta e uma política de qualidade de serviço para seus servidores de borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4bf6a-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="4bf6a-104">Este artigo descreve como configurar intervalos de porta para servidores de borda e como configurar uma política de qualidade de serviço para seus servidores de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="4bf6a-105">Configurar intervalos de porta</span><span class="sxs-lookup"><span data-stu-id="4bf6a-105">Configure port ranges</span></span>

<span data-ttu-id="4bf6a-106">Com os servidores de borda, você não precisa configurar intervalos de porta separados para compartilhamento de áudio, vídeo e aplicativos; da mesma forma, os intervalos de porta usados para servidores de borda não precisam corresponder aos intervalos de porta usados com os servidores de conferência, aplicativo e mediação.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="4bf6a-107">Antes de continuarmos com o nosso exemplo, é importante enfatizar que, enquanto essa opção existe, recomendamos que você não altere os intervalos de porta, pois isso pode afetar negativamente alguns cenários se você sair do intervalo de porta 50000.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="4bf6a-108">Por exemplo, suponha que você tenha configurado seus servidores de conferência, aplicativo e mediação para usar estes intervalos de porta:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bf6a-109">Tipo de pacote</span><span class="sxs-lookup"><span data-stu-id="4bf6a-109">Packet Type</span></span></th>
<th><span data-ttu-id="4bf6a-110">Porta inicial</span><span class="sxs-lookup"><span data-stu-id="4bf6a-110">Starting Port</span></span></th>
<th><span data-ttu-id="4bf6a-111">Número de portas reservadas</span><span class="sxs-lookup"><span data-stu-id="4bf6a-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bf6a-112">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="4bf6a-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="4bf6a-113">40803</span><span class="sxs-lookup"><span data-stu-id="4bf6a-113">40803</span></span></p></td>
<td><p><span data-ttu-id="4bf6a-114">8348</span><span class="sxs-lookup"><span data-stu-id="4bf6a-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf6a-115">Áudio</span><span class="sxs-lookup"><span data-stu-id="4bf6a-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="4bf6a-116">49152</span><span class="sxs-lookup"><span data-stu-id="4bf6a-116">49152</span></span></p></td>
<td><p><span data-ttu-id="4bf6a-117">8348</span><span class="sxs-lookup"><span data-stu-id="4bf6a-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf6a-118">Vídeo</span><span class="sxs-lookup"><span data-stu-id="4bf6a-118">Video</span></span></p></td>
<td><p><span data-ttu-id="4bf6a-119">57500</span><span class="sxs-lookup"><span data-stu-id="4bf6a-119">57500</span></span></p></td>
<td><p><span data-ttu-id="4bf6a-120">8034</span><span class="sxs-lookup"><span data-stu-id="4bf6a-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf6a-121"><strong>Totais</strong></span><span class="sxs-lookup"><span data-stu-id="4bf6a-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="4bf6a-122">24730</span><span class="sxs-lookup"><span data-stu-id="4bf6a-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4bf6a-123">Como você pode ver, os intervalos de portabilidade de áudio, vídeo e compartilhamento de aplicativos começam na porta 40803 e englobam um total de 24732 portas.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="4bf6a-124">Se preferir, você pode configurar um determinado servidor de borda para usar esses valores de porta gerais executando um comando semelhante a este de dentro do Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="4bf6a-125">Ou use o seguinte comando para configurar simultaneamente todos os servidores de borda em sua organização:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="4bf6a-126">Você pode verificar as configurações de porta atuais para seus servidores de borda usando este comando do Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="4bf6a-127">Novamente, enquanto fornecemos essas opções, recomendamos que você deixe as coisas como elas são para a configuração de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="4bf6a-128">Configurar uma política de QoS para seus servidores de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4bf6a-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="4bf6a-129">Além de criar políticas de QoS para seus servidores de conferência, aplicativo e mediação, você também deve criar políticas de áudio e de vídeo para o lado interno dos seus servidores de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="4bf6a-130">No entanto, as políticas usadas em seus servidores de borda são diferentes das políticas usadas em seus servidores de conferência, aplicativo e mediação.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="4bf6a-131">Para os servidores de conferência, aplicativo e mediação, você especificou um intervalo de porta de origem; com os servidores de borda, você precisa especificar um intervalo de porta de destino.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="4bf6a-132">Por isso, você não pode simplesmente aplicar as políticas de QoS de servidor de conferência, aplicativo e mediação aos seus servidores de borda: essas políticas simplesmente não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="4bf6a-133">Em vez disso, você deve criar novas políticas e aplicar essas políticas somente a seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="4bf6a-134">O procedimento a seguir descreve o processo de criação de objetos de política de grupo do Active Directory que podem ser usados para gerenciar a qualidade do serviço em servidores Edge.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="4bf6a-135">É claro que é possível que seus servidores de borda sejam servidores autônomos que não tenham contas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="4bf6a-136">Se esse for o caso, você pode usar a política de grupo local em vez da política de grupo do Active Directory: a única diferença é que você deve criar essas políticas locais usando o editor de política de grupo local e deve criar individualmente o mesmo conjunto de políticas em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="4bf6a-137">Para iniciar o editor de política de grupo local em um servidor de borda, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="4bf6a-138">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="4bf6a-139">Na caixa de diálogo **executar** , digite **gpedit. msc**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="4bf6a-140">Se você estiver criando políticas baseadas no Active Directory, faça logon em um computador onde o gerenciamento de política de grupo foi instalado.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="4bf6a-141">Nesse caso, abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="4bf6a-142">No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="4bf6a-143">Por exemplo, se todos os seus computadores do Skype for Business Server estiverem localizados em uma UO chamada Skype for Business Server, a nova política deve ser criada na OU Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="4bf6a-144">Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="4bf6a-145">Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, o **áudio do Skype for Business Server**) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="4bf6a-146">Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="4bf6a-147">Aqui, o processo é idêntico independentemente de você estar criando uma política do Active Directory ou uma política local:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="4bf6a-148">No editor de gerenciamento de política de grupo ou no editor de política de grupo local, expanda **configuração do computador**, expanda **políticas**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseada em política**e clique em **criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="4bf6a-149">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, o **áudio do Skype for Business Server**) na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="4bf6a-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="4bf6a-150">Selecione **especificar valor DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="4bf6a-151">Deixe **especificar a taxa de aceleração de saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="4bf6a-152">Na página seguinte, verifique se a opção **todos os aplicativos** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="4bf6a-153">Essa configuração instrui a rede a procurar todos os pacotes com uma marcação DSCP de 46, não apenas pacotes criados por um aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="4bf6a-154">Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="4bf6a-155">Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou esses pacotes e qual computador (endereço IP) receberá esses pacotes.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="4bf6a-156">Na página quatro, selecione **TCP e UDP** na lista **Selecione o protocolo que esta política de QoS se aplica à** lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="4bf6a-157">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype for Business Server e seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="4bf6a-158">Em título **especifique o número da porta de destino**, selecione uma **destas portas de destino ou intervalo**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="4bf6a-159">Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="4bf6a-160">Por exemplo, se você reservou portas 49152 pelas portas 57500 para tráfego de áudio, insira o intervalo de porta usando este formato: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="4bf6a-161">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-161">Click **Finish**.</span></span>

<span data-ttu-id="4bf6a-162">Depois de criar a política de QoS para o tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="4bf6a-163">Para criar uma política de vídeo, siga o mesmo procedimento básico que você seguiu ao criar a política de áudio, como fazer essas substituições:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="4bf6a-164">Use um nome de política diferente (e exclusivo) (por exemplo, **vídeo do Skype for Business Server**).</span><span class="sxs-lookup"><span data-stu-id="4bf6a-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="4bf6a-165">Defina o valor de DSCP para **34** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="4bf6a-166">(Observe que você não precisa usar um valor de DSCP de 34.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="4bf6a-167">O único requisito é que você use um valor DSCP diferente para vídeo do que o usado para áudio.)</span><span class="sxs-lookup"><span data-stu-id="4bf6a-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="4bf6a-168">Use o intervalo de porta configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="4bf6a-169">Por exemplo, se você reservou portas de 57501 a 65535 para vídeo, defina o intervalo de porta para isso: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="4bf6a-170">Novamente, isso deve ser configurado como o intervalo de porta de destino.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="4bf6a-171">Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, deverá criar uma terceira política, fazer as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="4bf6a-172">Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Skype for Business Server**).</span><span class="sxs-lookup"><span data-stu-id="4bf6a-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="4bf6a-173">Defina o valor de DSCP para **24** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="4bf6a-174">(Novamente, você não precisa usar um valor de DSCP de 24.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="4bf6a-175">O único requisito é que você use um valor DSCP diferente para compartilhamento de aplicativos do que usou para áudio ou vídeo.)</span><span class="sxs-lookup"><span data-stu-id="4bf6a-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="4bf6a-176">Use o intervalo de porta configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="4bf6a-177">Por exemplo, se você reservou portas de 40803 a 49151 para compartilhamento de aplicativos, defina o intervalo de porta como: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="4bf6a-178">As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="4bf6a-179">Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="4bf6a-180">Esse comando pode ser executado no Skype for Business Server ou em qualquer janela de comando que esteja em execução em credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="4bf6a-181">Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="4bf6a-182">Observe que talvez seja necessário reiniciar o servidor de borda, mesmo depois de executar o GPUDATE. exe.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="4bf6a-183">Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador completando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="4bf6a-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="4bf6a-184">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="4bf6a-185">Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="4bf6a-186">No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="4bf6a-187">Clique com o botão direito do mouse em **tcpip**, aponte para **novo**e, em seguida, clique em **tecla**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="4bf6a-188">Após a criação da nova chave do registro, digite **QoS**e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="4bf6a-189">Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="4bf6a-190">Depois que o novo valor do registro for criado, digite não **use NLA**e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="4bf6a-191">Clique duas vezes em **não usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="4bf6a-192">Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="4bf6a-193">Feche o editor do registro e reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-193">Close the Registry Editor and reboot your computer.</span></span>
