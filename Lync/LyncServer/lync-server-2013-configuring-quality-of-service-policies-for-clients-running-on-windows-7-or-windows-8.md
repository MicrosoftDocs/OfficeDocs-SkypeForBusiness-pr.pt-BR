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
ms.openlocfilehash: 2cd058e2903160f1c9f4ea06e30959b63953ab01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534968"
---
# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="267f3-102">Configurando políticas de qualidade de serviço no Lync Server 2013 para clientes que executam o Windows 7 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="267f3-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="267f3-103">_**Última modificação do tópico:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="267f3-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="267f3-104">Além de especificar intervalos de portas para uso pelos seus clientes do Lync, você também deve criar políticas de qualidade de serviço separadas que serão aplicadas aos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="267f3-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="267f3-105">(As políticas de qualidade de serviço criadas para servidores de conferência, aplicativo e mediação não devem ser aplicadas aos computadores cliente.) Essas informações se aplicam somente a computadores que executam o cliente Lync 2013 e o Windows 7 ou Windows 8.</span><span class="sxs-lookup"><span data-stu-id="267f3-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="267f3-106">O exemplo a seguir usa esse conjunto de intervalos de porta para criar uma política de áudio e uma política de vídeo:</span><span class="sxs-lookup"><span data-stu-id="267f3-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="267f3-107">Tipo de Tráfego do Cliente</span><span class="sxs-lookup"><span data-stu-id="267f3-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="267f3-108">Início da Porta</span><span class="sxs-lookup"><span data-stu-id="267f3-108">Port Start</span></span></th>
<th><span data-ttu-id="267f3-109">Intervalo da Porta</span><span class="sxs-lookup"><span data-stu-id="267f3-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="267f3-110">Áudio</span><span class="sxs-lookup"><span data-stu-id="267f3-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="267f3-111">50020</span><span class="sxs-lookup"><span data-stu-id="267f3-111">50020</span></span></p></td>
<td><p><span data-ttu-id="267f3-112">508</span><span class="sxs-lookup"><span data-stu-id="267f3-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="267f3-113">Vídeo</span><span class="sxs-lookup"><span data-stu-id="267f3-113">Video</span></span></p></td>
<td><p><span data-ttu-id="267f3-114">58000</span><span class="sxs-lookup"><span data-stu-id="267f3-114">58000</span></span></p></td>
<td><p><span data-ttu-id="267f3-115">508</span><span class="sxs-lookup"><span data-stu-id="267f3-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="267f3-116">Compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="267f3-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="267f3-117">42000</span><span class="sxs-lookup"><span data-stu-id="267f3-117">42000</span></span></p></td>
<td><p><span data-ttu-id="267f3-118">508</span><span class="sxs-lookup"><span data-stu-id="267f3-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="267f3-119">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="267f3-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="267f3-120">42020</span><span class="sxs-lookup"><span data-stu-id="267f3-120">42020</span></span></p></td>
<td><p><span data-ttu-id="267f3-121">508</span><span class="sxs-lookup"><span data-stu-id="267f3-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="267f3-122">Para criar uma política de áudio de qualidade de serviço para computadores com Windows 7 ou Windows 8, primeiro faça logon em um computador onde o Group Policy Management tenha sido instalado.</span><span class="sxs-lookup"><span data-stu-id="267f3-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="267f3-123">Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e conclua o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="267f3-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="267f3-124">No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="267f3-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="267f3-125">Por exemplo, se todos os seus computadores clientes estiverem localizados em uma UO chamada clientes, a nova política deverá ser criada na OU do cliente.</span><span class="sxs-lookup"><span data-stu-id="267f3-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="267f3-126">Clique com o botão direito no contêiner adequado e clique em **Criar um GPO neste domínio e fornecer um link para ele aqui**.</span><span class="sxs-lookup"><span data-stu-id="267f3-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="267f3-127">Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** (por exemplo, **áudio do Lync**) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="267f3-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="267f3-128">Clique com o botão direito na política recém criada e depois clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="267f3-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="267f3-129">No Editor de Gerenciamento de Política de Grupo, expanda **Configuração do computador**, expanda **Políticas**, expanda **Configurações do Windows**, clique com o botão direito em **QoS baseado em política**, e depois clique em **Criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="267f3-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="267f3-130">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **áudio do Lync**) na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="267f3-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="267f3-131">Selecione **Especificar valor de DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="267f3-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="267f3-132">Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="267f3-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="267f3-133">Na próxima página, selecione **somente aplicativos com esse nome executável** e digite o nome **Lync.exe**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="267f3-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="267f3-134">Essa configuração instrui a política a priorizar apenas o tráfego de correspondência do cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="267f3-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="267f3-p106">Na terceira página, certifique-se de que ambas as opções **Qualquer endereço IP de origem** e **Qualquer endereço IP de destino** estejam selecionadas e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.</span><span class="sxs-lookup"><span data-stu-id="267f3-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="267f3-137">Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**.</span><span class="sxs-lookup"><span data-stu-id="267f3-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="267f3-138">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Lync Server e seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="267f3-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="267f3-139">No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**.</span><span class="sxs-lookup"><span data-stu-id="267f3-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="267f3-140">Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="267f3-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="267f3-141">Por exemplo, se você reservou portas 50020 através de portas 50039 para tráfego de áudio, insira o intervalo de portas usando este formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="267f3-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="267f3-142">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="267f3-142">Click **Finish**.</span></span>

<span data-ttu-id="267f3-143">Depois de criar a política de QoS para o áudio, você deve criar uma segunda política para vídeo.</span><span class="sxs-lookup"><span data-stu-id="267f3-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="267f3-144">Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="267f3-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="267f3-145">Use um nome de política diferente (e exclusivo) (por exemplo, **vídeo do Lync**).</span><span class="sxs-lookup"><span data-stu-id="267f3-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="267f3-146">Defina o valor DSCP para **34** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="267f3-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="267f3-147">(Conforme observado anteriormente, não é necessário usar o valor de DSCP 34; você deve apenas atribuir um valor de DSCP diferente daquele usado para áudio.)</span><span class="sxs-lookup"><span data-stu-id="267f3-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="267f3-148">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="267f3-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="267f3-149">Por exemplo, se você reservou portas de 58000 a 58019 para vídeo, defina o intervalo de porta como: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="267f3-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="267f3-150">Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça estas substituições:</span><span class="sxs-lookup"><span data-stu-id="267f3-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="267f3-151">Use um nome de política diferente (e único) (por exemplo, **Compartilhamento de Aplicativos do Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="267f3-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="267f3-152">Defina o valor DSCP para **24** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="267f3-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="267f3-153">(Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores de DSCP usados para áudio e vídeo.)</span><span class="sxs-lookup"><span data-stu-id="267f3-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="267f3-154">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="267f3-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="267f3-155">Por exemplo, se você reservou as portas de 42000 a 42019 para o compartilhamento de aplicativos, defina o intervalo de porta como: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="267f3-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="267f3-156">Para uma política de transferência de arquivos:</span><span class="sxs-lookup"><span data-stu-id="267f3-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="267f3-157">Use um nome de política diferente (e exclusivo) (por exemplo, **transferências de arquivo do Lync Server**).</span><span class="sxs-lookup"><span data-stu-id="267f3-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="267f3-158">Defina o valor de DSCP para **14**.</span><span class="sxs-lookup"><span data-stu-id="267f3-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="267f3-159">(Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)</span><span class="sxs-lookup"><span data-stu-id="267f3-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="267f3-160">Use o intervalo de portas configurado anteriormente para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="267f3-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="267f3-161">Por exemplo, se você reservou as portas de 42020 a 42039 para o compartilhamento de aplicativos, defina o intervalo de porta como: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="267f3-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="267f3-162">As novas políticas criadas não terão efeito até que a política de grupo tenha sido atualizada nos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="267f3-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="267f3-163">Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="267f3-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="267f3-164">Este comando pode ser executado em qualquer janela de comando que esteja sendo executada sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="267f3-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="267f3-165">Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="267f3-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="267f3-166">Tenha em mente que essas políticas devem ser direcionadas para os computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="267f3-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="267f3-167">Eles não devem ser aplicados aos servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="267f3-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="267f3-168">Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="267f3-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="267f3-169">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="267f3-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="267f3-170">Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="267f3-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="267f3-171">No editor do registro, expanda **HKEY \_ local \_ Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="267f3-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="267f3-p119">Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois de criar a nova chave de registro, digite **QoS** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="267f3-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="267f3-p120">Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois de criar o novo valor do registro, digite **Não usar NLA** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="267f3-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="267f3-176">Clique duas vezes em **não usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="267f3-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="267f3-177">Na caixa de diálogo **Editar Sequência**, digite **1** na caixa **Dados de valor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="267f3-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="267f3-178">Feche o Editor do Registro e reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="267f3-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="267f3-179">Configurando a qualidade do serviço em computadores com vários adaptadores de rede</span><span class="sxs-lookup"><span data-stu-id="267f3-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="267f3-180">Se você tiver um computador que tenha vários adaptadores de rede, ocasionalmente poderá ter problemas nos quais valores de DSCP são mostrados como 0x00, e não o valor configurado.</span><span class="sxs-lookup"><span data-stu-id="267f3-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="267f3-181">Isso normalmente ocorre em computadores em que um ou mais adaptadores de rede não podem acessar seu domínio do Active Directory (por exemplo, se esses adaptadores são usados para uma rede privada).</span><span class="sxs-lookup"><span data-stu-id="267f3-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="267f3-182">Em casos como esse, os valores de DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não podem acessar o domínio.</span><span class="sxs-lookup"><span data-stu-id="267f3-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="267f3-183">Se quiser marcar valores de DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, será necessário adicionar e configurar um valor ao registro.</span><span class="sxs-lookup"><span data-stu-id="267f3-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="267f3-184">Isso pode ser feito realizando o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="267f3-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="267f3-185">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="267f3-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="267f3-186">Na caixa de diálogo **Executar**, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="267f3-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="267f3-187">No editor do registro, expanda **HKEY \_ local \_ Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="267f3-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="267f3-188">Se você não vir uma chave de registro identificada por **QoS** , clique com o botão direito em **tcpip**, aponte para **novo**e clique em **chave**.</span><span class="sxs-lookup"><span data-stu-id="267f3-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="267f3-189">Após a criação da nova chave, digite **QoS** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="267f3-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="267f3-p125">Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois de criar o novo valor do registro, digite **Não usar NLA** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="267f3-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="267f3-192">Clique duas vezes em **não usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="267f3-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="267f3-193">Na caixa de diálogo **Editar Sequência**, digite **1** na caixa **Dados de valor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="267f3-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="267f3-194">Após criar e configurar o novo valor do registro, você precisará reiniciar o computador para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="267f3-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

