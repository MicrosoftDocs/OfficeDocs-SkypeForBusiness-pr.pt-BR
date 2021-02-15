---
title: Configurando intervalos de porta e uma Qualidade de Serviço para seus Servidores de Borda
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de porta para Servidores de Borda e como configurar uma política de Qualidade de Serviço para seus Servidores de Borda A/V.
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832901"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="2ab14-103">Configurando intervalos de portas e uma política de Qualidade de Serviço para seus Servidores de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ab14-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="2ab14-104">Este artigo descreve como configurar intervalos de porta para Servidores de Borda e como configurar uma política de Qualidade de Serviço para seus Servidores de Borda A/V.</span><span class="sxs-lookup"><span data-stu-id="2ab14-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="2ab14-105">Configurar intervalos de portas</span><span class="sxs-lookup"><span data-stu-id="2ab14-105">Configure port ranges</span></span>

<span data-ttu-id="2ab14-106">Com os servidores de Borda, você não precisa configurar intervalos de porta separados para compartilhamento de áudio, vídeo e aplicativos; Da mesma forma, os intervalos de porta usados para servidores de Borda não têm que corresponder aos intervalos de porta usados com seus servidores de Conferência, Aplicativo e Mediação.</span><span class="sxs-lookup"><span data-stu-id="2ab14-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="2ab14-107">Antes de prosseguirmos com nosso exemplo, é importante enfatizar que, embora essa opção exista, recomendamos que você não altere os intervalos de porta, pois isso pode afetar adversamente alguns cenários se você sair do intervalo de 50000 portas.</span><span class="sxs-lookup"><span data-stu-id="2ab14-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="2ab14-108">Por exemplo, suponha que você tenha configurado seus servidores de Conferência, Aplicativo e Mediação para usar estes intervalos de porta:</span><span class="sxs-lookup"><span data-stu-id="2ab14-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ab14-109">Tipo de pacote</span><span class="sxs-lookup"><span data-stu-id="2ab14-109">Packet Type</span></span></th>
<th><span data-ttu-id="2ab14-110">Porta inicial</span><span class="sxs-lookup"><span data-stu-id="2ab14-110">Starting Port</span></span></th>
<th><span data-ttu-id="2ab14-111">Número de portas reservadas</span><span class="sxs-lookup"><span data-stu-id="2ab14-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ab14-112">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2ab14-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="2ab14-113">40803</span><span class="sxs-lookup"><span data-stu-id="2ab14-113">40803</span></span></p></td>
<td><p><span data-ttu-id="2ab14-114">8348</span><span class="sxs-lookup"><span data-stu-id="2ab14-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab14-115">Áudio</span><span class="sxs-lookup"><span data-stu-id="2ab14-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="2ab14-116">49152</span><span class="sxs-lookup"><span data-stu-id="2ab14-116">49152</span></span></p></td>
<td><p><span data-ttu-id="2ab14-117">8348</span><span class="sxs-lookup"><span data-stu-id="2ab14-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab14-118">Vídeo</span><span class="sxs-lookup"><span data-stu-id="2ab14-118">Video</span></span></p></td>
<td><p><span data-ttu-id="2ab14-119">57500</span><span class="sxs-lookup"><span data-stu-id="2ab14-119">57500</span></span></p></td>
<td><p><span data-ttu-id="2ab14-120">8034</span><span class="sxs-lookup"><span data-stu-id="2ab14-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab14-121"><strong>Totais</strong></span><span class="sxs-lookup"><span data-stu-id="2ab14-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="2ab14-122">24730</span><span class="sxs-lookup"><span data-stu-id="2ab14-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ab14-123">Como você pode ver, os intervalos de porta para áudio, vídeo e compartilhamento de aplicativos começam na porta 40803 e englobam um total de 24732 portas.</span><span class="sxs-lookup"><span data-stu-id="2ab14-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="2ab14-124">Se preferir, você pode configurar um determinado Servidor de Borda para usar esses valores gerais de porta executando um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="2ab14-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="2ab14-125">Ou use o comando a seguir para configurar simultaneamente todos os servidores de borda na organização:</span><span class="sxs-lookup"><span data-stu-id="2ab14-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="2ab14-126">Você pode verificar as configurações de porta atuais para seus Servidores de Borda usando este comando do Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="2ab14-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="2ab14-127">Novamente, embora forneçamos essas opções, recomendamos que você deixe tudo como estão para a configuração de porta.</span><span class="sxs-lookup"><span data-stu-id="2ab14-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="2ab14-128">Configurar uma política de QoS para seus Servidores de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="2ab14-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="2ab14-129">Além de criar políticas de QoS para seus servidores de Conferências, Aplicativos e Mediação, você também deve criar políticas de áudio e vídeo para o lado interno dos seus servidores de borda de A/V.</span><span class="sxs-lookup"><span data-stu-id="2ab14-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="2ab14-130">No entanto, as políticas usadas em seus servidores de Borda são diferentes das políticas usadas em seus servidores de Conferências, Aplicativos e Mediação.</span><span class="sxs-lookup"><span data-stu-id="2ab14-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="2ab14-131">Para os servidores de Conferência, Aplicativo e Mediação, você especificou um intervalo de porta de origem; com servidores de Borda, você precisa especificar um intervalo de portas de destino.</span><span class="sxs-lookup"><span data-stu-id="2ab14-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="2ab14-132">Por isso, você não pode simplesmente aplicar as políticas de QoS de servidor de Conferência, Aplicativo e Mediação aos seus servidores de Borda: essas políticas simplesmente não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="2ab14-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="2ab14-133">Em vez disso, você deve criar novas políticas e aplicá-las somente aos seus servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="2ab14-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="2ab14-134">O procedimento a seguir descreve o processo para criar objetos de Política de Grupo do Active Directory que podem ser usados para gerenciar a Qualidade de Serviço em Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="2ab14-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="2ab14-135">É possível, é claro, que seus servidores de Borda sejam servidores autônomos que não possuem contas do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ab14-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="2ab14-136">Neste caso, você pode usar uma Política de Grupo local em vez da Política de Grupo do Active Directory: a única diferença é que você deve criar essas políticas locais usando o Editor de Políticas de Grupo Local e deve criar individualmente o mesmo conjunto de políticas em cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2ab14-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="2ab14-137">Para iniciar o Editor de Política de Grupo Local em um servidor de Borda, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2ab14-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="2ab14-138">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="2ab14-139">Na caixa **de** diálogo Executar, digite **gpedit.msc** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="2ab14-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="2ab14-140">Se estiver criando políticas com base no Active Directory, você deve fazer logon em um computador em que o Gerenciamento de Política de Grupo tenha sido instalado.</span><span class="sxs-lookup"><span data-stu-id="2ab14-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="2ab14-141">Nesse caso, abra o Gerenciamento de Política de Grupo (clique em **Iniciar,** aponte para Ferramentas Administrativas e clique em Gerenciamento de Política de **Grupo)** e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2ab14-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="2ab14-142">No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="2ab14-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="2ab14-143">Por exemplo, se todos os computadores do Skype for Business Server estão localizados em uma UO chamada Skype for Business Server, a nova política deve ser criada na UO do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2ab14-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="2ab14-144">Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui.**</span><span class="sxs-lookup"><span data-stu-id="2ab14-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="2ab14-145">Na caixa de diálogo Novo **GPO,** digite um nome  para o novo objeto de Política de Grupo na caixa Nome (por exemplo, Áudio do **Skype for Business Server)** e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="2ab14-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="2ab14-146">Clique com o botão direito do mouse na política recém-criada e clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="2ab14-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="2ab14-147">A partir daqui o processo é idêntico, independente de você estar criando uma política do Active Directory ou uma política local:</span><span class="sxs-lookup"><span data-stu-id="2ab14-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="2ab14-148">No Editor do Gerenciamento de Política de Grupo ou no Editor de Política de Grupo Local, expanda **Configuração do Computador**, **Políticas**, **Configurações do Windows**, clique com o botão direito em **QoS baseada em política** e clique em **Criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="2ab14-149">Na caixa de diálogo **QoS** baseada em política, na página de abertura, digite um nome para a nova política (por exemplo, Áudio do **Skype for Business Server**) na caixa Nome. </span><span class="sxs-lookup"><span data-stu-id="2ab14-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="2ab14-150">Selecione **Especificar valor de DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="2ab14-151">Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="2ab14-152">Na próxima página, certifique-se de que **todos os aplicativos** estão selecionados e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="2ab14-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="2ab14-153">Esta configuração instrui a rede a procurar todos os pacotes com uma marcação de DSCP igual a 46, não somente pacotes criados por um aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="2ab14-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="2ab14-154">Na terceira página, certifique-se de que ambos os **endereços IP** de origem e Qualquer endereço **IP** de destino estão selecionados e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="2ab14-155">Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.</span><span class="sxs-lookup"><span data-stu-id="2ab14-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="2ab14-156">Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="2ab14-157">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype for Business Server e seus aplicativos clientes.</span><span class="sxs-lookup"><span data-stu-id="2ab14-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="2ab14-158">Sob o cabeçalho **Especifique o número da porta de destino**, selecione **A partir desta porta de destino ou intervalo**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="2ab14-159">Na caixa de texto que acompanha, digite o intervalo de portas reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="2ab14-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="2ab14-160">Por exemplo, se você reservou as portas 49152 a 57500 para tráfego de áudio, insira o intervalo de portas usando este formato: **49152:57500.**</span><span class="sxs-lookup"><span data-stu-id="2ab14-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="2ab14-161">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-161">Click **Finish**.</span></span>

<span data-ttu-id="2ab14-162">Depois de criar a política de QoS para tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="2ab14-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="2ab14-163">Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="2ab14-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="2ab14-164">Use um nome de política diferente (e exclusivo) (por exemplo, **Vídeo do Skype for Business Server).**</span><span class="sxs-lookup"><span data-stu-id="2ab14-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="2ab14-p113">Defina o valor do DSCP como **34** em vez de 46 (observe que você não precisa usar o valor 34 para o DSCP. O único requisito é usar para o vídeo um valor de DSCP diferente do valor usado para o áudio).</span><span class="sxs-lookup"><span data-stu-id="2ab14-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="2ab14-168">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="2ab14-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="2ab14-169">Por exemplo, se você reservou as portas 57501 a 65535 para vídeo, de acordo com o intervalo de portas: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="2ab14-170">Novamente, isso deve ser configurado como intervalo de portas de destino.</span><span class="sxs-lookup"><span data-stu-id="2ab14-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="2ab14-171">Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, deverá criar uma terceira política, fazendo as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="2ab14-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="2ab14-172">Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Skype for Business Server).**</span><span class="sxs-lookup"><span data-stu-id="2ab14-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="2ab14-p115">Defina o valor do DSCP como **24** em vez de 46 (novamente, não é necessário usar o valor 24 para o DSCP. O único requisito é usar para o compartilhamento de aplicativos um valor de DSCP diferente do valor usado para áudio e vídeo).</span><span class="sxs-lookup"><span data-stu-id="2ab14-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="2ab14-176">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="2ab14-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="2ab14-177">Por exemplo, se você reservou as portas 40803 a 49151 para compartilhamento de aplicativos, de definir o intervalo de portas como: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="2ab14-p117">As novas políticas criadas não terão efeito até que a Política de Grupo tenha sido atualizada nos servidores de Borda. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="2ab14-p117">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="2ab14-180">Esse comando pode ser executado de dentro do Skype for Business Server ou de qualquer janela de comando que está sendo executado sob credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="2ab14-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="2ab14-181">Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="2ab14-182">Observe que pode ser necessário reiniciar o servidor de Borda mesmo depois de executar o arquivo Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="2ab14-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="2ab14-183">Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="2ab14-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="2ab14-184">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="2ab14-185">Na caixa **de** diálogo Executar, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="2ab14-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="2ab14-186">No Editor do Registro, **expanda HKEY \_ LOCAL \_ MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="2ab14-187">Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="2ab14-188">Depois que a nova chave do Registro for criada, digite **QoS** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="2ab14-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="2ab14-189">Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="2ab14-190">Depois que o novo valor do Registro for criado, digite **Não usar NLA** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="2ab14-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="2ab14-191">Dê um duplo clique em **Não usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="2ab14-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="2ab14-192">Na caixa **de diálogo Editar Cadeia** de Caracteres, digite **1** na caixa **de** dados Valor e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="2ab14-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="2ab14-193">Feche o Editor do Registro e reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="2ab14-193">Close the Registry Editor and reboot your computer.</span></span>
