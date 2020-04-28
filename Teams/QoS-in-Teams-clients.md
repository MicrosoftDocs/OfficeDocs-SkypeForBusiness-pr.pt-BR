---
title: Implementar a qualidade de serviço em clientes do teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Saiba como preparar a rede para sua organização para a QoS (qualidade de serviço) no Microsoft Teams.
ms.custom: seo-marvel-mar2020
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81c10ce415c0ed0db670a81b896289b23cb39218
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904556"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="69b2f-103">Definir o QoS em clientes do Windows</span><span class="sxs-lookup"><span data-stu-id="69b2f-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="69b2f-104">Você pode usar a QoS baseada em política dentro da política de grupo para definir o intervalo de porta de origem para o valor DSCP predefinido no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="69b2f-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="69b2f-105">Os intervalos de porta especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="69b2f-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="69b2f-106">*Tabela 1. Intervalos de portas iniciais recomendados*</span><span class="sxs-lookup"><span data-stu-id="69b2f-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="69b2f-107">Tipo de tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="69b2f-107">Media traffic type</span></span>| <span data-ttu-id="69b2f-108">Intervalo de portas de origem do cliente </span><span class="sxs-lookup"><span data-stu-id="69b2f-108">Client source port range</span></span> |<span data-ttu-id="69b2f-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="69b2f-109">Protocol</span></span>|<span data-ttu-id="69b2f-110">Valor DSCP</span><span class="sxs-lookup"><span data-stu-id="69b2f-110">DSCP value</span></span>|<span data-ttu-id="69b2f-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="69b2f-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="69b2f-112">Áudio</span><span class="sxs-lookup"><span data-stu-id="69b2f-112">Audio</span></span>| <span data-ttu-id="69b2f-113">50.000–50.019</span><span class="sxs-lookup"><span data-stu-id="69b2f-113">50,000–50,019</span></span>|<span data-ttu-id="69b2f-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="69b2f-114">TCP/UDP</span></span>|<span data-ttu-id="69b2f-115">46</span><span class="sxs-lookup"><span data-stu-id="69b2f-115">46</span></span>|<span data-ttu-id="69b2f-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="69b2f-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="69b2f-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="69b2f-117">Video</span></span>| <span data-ttu-id="69b2f-118">50.020–50.039</span><span class="sxs-lookup"><span data-stu-id="69b2f-118">50,020–50,039</span></span>|<span data-ttu-id="69b2f-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="69b2f-119">TCP/UDP</span></span>|<span data-ttu-id="69b2f-120">34</span><span class="sxs-lookup"><span data-stu-id="69b2f-120">34</span></span>|<span data-ttu-id="69b2f-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="69b2f-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="69b2f-122">Compartilhamento de tela/aplicativo</span><span class="sxs-lookup"><span data-stu-id="69b2f-122">Application/Screen Sharing</span></span>| <span data-ttu-id="69b2f-123">50.040-50.059</span><span class="sxs-lookup"><span data-stu-id="69b2f-123">50,040–50,059</span></span>|<span data-ttu-id="69b2f-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="69b2f-124">TCP/UDP</span></span>|<span data-ttu-id="69b2f-125">dezoito</span><span class="sxs-lookup"><span data-stu-id="69b2f-125">18</span></span>|<span data-ttu-id="69b2f-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="69b2f-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="69b2f-127">Sempre que possível, configure as configurações de QoS baseadas em políticas em um objeto de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="69b2f-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="69b2f-128">As etapas a seguir são muito parecidas com a [configuração de intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tem alguns detalhes adicionais que podem não ser necessários.</span><span class="sxs-lookup"><span data-stu-id="69b2f-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="69b2f-129">Para criar uma política de áudio QoS para computadores Windows 10 associados a um domínio, primeiro faça logon em um computador no qual o gerenciamento de política de grupo foi instalado.</span><span class="sxs-lookup"><span data-stu-id="69b2f-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="69b2f-130">Abra gerenciamento de política de grupo (clique em Iniciar, aponte para ferramentas administrativas e clique em gerenciamento de política de grupo) e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="69b2f-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="69b2f-131">No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="69b2f-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="69b2f-132">Por exemplo, se todos os seus computadores cliente estiverem localizados em uma UO chamada **clientes**, a nova política deve ser criada na ou clientes.</span><span class="sxs-lookup"><span data-stu-id="69b2f-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="69b2f-133">Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="69b2f-134">Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="69b2f-135">Clique com o botão direito do mouse na política recém-criada e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="69b2f-136">No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseado em política**e clique em **criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="69b2f-137">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="69b2f-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="69b2f-138">Selecione **especificar valor DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="69b2f-139">Deixe **especificar a taxa de aceleração de saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="69b2f-140">Na próxima página, selecione **apenas aplicativos com esse nome executável** e insira o nome **Teams. exe**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="69b2f-141">Essa configuração instrui a política a priorizar somente o tráfego de correspondência do cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="69b2f-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="69b2f-142">Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="69b2f-143">Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou os pacotes e qual computador (endereço IP) receberá os pacotes.</span><span class="sxs-lookup"><span data-stu-id="69b2f-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="69b2f-144">Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica** .</span><span class="sxs-lookup"><span data-stu-id="69b2f-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="69b2f-145">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados.</span><span class="sxs-lookup"><span data-stu-id="69b2f-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="69b2f-146">Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="69b2f-147">Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="69b2f-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="69b2f-148">Por exemplo, se você reservou portas 50000 pelas portas 50019 para tráfego de áudio, insira o intervalo de porta usando este formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="69b2f-149">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="69b2f-149">Click **Finish**.</span></span>

1. <span data-ttu-id="69b2f-150">Repita as etapas 5-10 para criar políticas para compartilhamento de aplicativos/aplicativos e vídeo, substituindo os valores apropriados nas etapas 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="69b2f-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="69b2f-151">As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="69b2f-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="69b2f-152">Embora a política de grupo seja atualizada periodicamente por conta própria, você pode forçar uma atualização imediata seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="69b2f-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="69b2f-153">Em cada computador para o qual você deseja atualizar a política de grupo, abra um prompt de comando como administrador (*Executar como administrador*).</span><span class="sxs-lookup"><span data-stu-id="69b2f-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="69b2f-154">No prompt de comando, insira</span><span class="sxs-lookup"><span data-stu-id="69b2f-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="69b2f-155">Verificar marcações DSCP no objeto de política de grupo</span><span class="sxs-lookup"><span data-stu-id="69b2f-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="69b2f-156">Para verificar se os valores do objeto de política de grupo foram definidos, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="69b2f-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="69b2f-157">Abra um prompt de comando como administrador (*Executar como administrador*).</span><span class="sxs-lookup"><span data-stu-id="69b2f-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="69b2f-158">No prompt de comando, insira</span><span class="sxs-lookup"><span data-stu-id="69b2f-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="69b2f-159">Isso irá gerar um relatório de GPOs aplicados e enviá-lo a um arquivo de texto chamado *GP. txt*.</span><span class="sxs-lookup"><span data-stu-id="69b2f-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="69b2f-160">Para obter um relatório HTML mais legível chamado *GP. html*, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="69b2f-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="69b2f-161">No arquivo gerado, procure o título objetos de **política de grupo aplicados** e verifique se os nomes dos objetos de política de grupo criados anteriormente estão na lista de políticas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="69b2f-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="69b2f-162">Abra o editor do registro e vá para</span><span class="sxs-lookup"><span data-stu-id="69b2f-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="69b2f-163">HKEY\_local\_Machine\\software\\\\Policies\\Microsoft\\Windows QoS</span><span class="sxs-lookup"><span data-stu-id="69b2f-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="69b2f-164">Verifique os valores das entradas do registro listadas na tabela 2.</span><span class="sxs-lookup"><span data-stu-id="69b2f-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="69b2f-165">*Tabela 2. Valores para entradas do registro do Windows para QoS*</span><span class="sxs-lookup"><span data-stu-id="69b2f-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="69b2f-166">Nome</span><span class="sxs-lookup"><span data-stu-id="69b2f-166">Name</span></span>          |  <span data-ttu-id="69b2f-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="69b2f-167">Type</span></span>  |    <span data-ttu-id="69b2f-168">Dados</span><span class="sxs-lookup"><span data-stu-id="69b2f-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="69b2f-169">Nome do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="69b2f-169">Application Name</span></span>    | <span data-ttu-id="69b2f-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-170">REG_SZ</span></span> |  <span data-ttu-id="69b2f-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="69b2f-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="69b2f-172">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="69b2f-172">DSCP Value</span></span>       | <span data-ttu-id="69b2f-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-173">REG_SZ</span></span> |     <span data-ttu-id="69b2f-174">46</span><span class="sxs-lookup"><span data-stu-id="69b2f-174">46</span></span>      |
   |        <span data-ttu-id="69b2f-175">IP Local</span><span class="sxs-lookup"><span data-stu-id="69b2f-175">Local IP</span></span>        | <span data-ttu-id="69b2f-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="69b2f-177">Comprimento do Prefixo IP Local</span><span class="sxs-lookup"><span data-stu-id="69b2f-177">Local IP Prefix Length</span></span> | <span data-ttu-id="69b2f-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="69b2f-179">Porta Local</span><span class="sxs-lookup"><span data-stu-id="69b2f-179">Local Port</span></span>       | <span data-ttu-id="69b2f-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-180">REG_SZ</span></span> | <span data-ttu-id="69b2f-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="69b2f-181">50000-50019</span></span> |
   |        <span data-ttu-id="69b2f-182">Protocolo</span><span class="sxs-lookup"><span data-stu-id="69b2f-182">Protocol</span></span>        | <span data-ttu-id="69b2f-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="69b2f-184">IP Remoto</span><span class="sxs-lookup"><span data-stu-id="69b2f-184">Remote IP</span></span>        | <span data-ttu-id="69b2f-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="69b2f-186">Prefixo de IP remoto</span><span class="sxs-lookup"><span data-stu-id="69b2f-186">Remote IP Prefix</span></span>    | <span data-ttu-id="69b2f-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="69b2f-188">Porta Remota</span><span class="sxs-lookup"><span data-stu-id="69b2f-188">Remote Port</span></span>       | <span data-ttu-id="69b2f-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="69b2f-190">Taxa de Aceleração</span><span class="sxs-lookup"><span data-stu-id="69b2f-190">Throttle Rate</span></span>      | <span data-ttu-id="69b2f-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="69b2f-191">REG_SZ</span></span> |     <span data-ttu-id="69b2f-192">-1</span><span class="sxs-lookup"><span data-stu-id="69b2f-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="69b2f-193">Verifique se o valor da entrada do nome do aplicativo está correto para o cliente que você está usando e verifique se as entradas do valor DSCP e da porta local refletem as configurações no objeto de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="69b2f-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
