---
title: Implementar Qualidade de Serviço nos clientes do Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implementar a QoS (qualidade de serviço) para clientes do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91b761cafa15172ae3fb0126f5059408e1a5f7ca
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246191"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="7298b-103">Definir o QoS em clientes do Windows</span><span class="sxs-lookup"><span data-stu-id="7298b-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="7298b-104">Você pode usar a QoS baseada em política dentro da política de grupo para definir o intervalo de porta de origem para o valor DSCP predefinido no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="7298b-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="7298b-105">Os intervalos de porta especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7298b-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="7298b-106">_Intervalos de portas iniciais recomendados_</span><span class="sxs-lookup"><span data-stu-id="7298b-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="7298b-107">Tipo de tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="7298b-107">Media traffic type</span></span>| <span data-ttu-id="7298b-108">Intervalo de porta de origem do cliente</span><span class="sxs-lookup"><span data-stu-id="7298b-108">Client source port range</span></span> |<span data-ttu-id="7298b-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7298b-109">Protocol</span></span>|<span data-ttu-id="7298b-110">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="7298b-110">DSCP value</span></span>|<span data-ttu-id="7298b-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="7298b-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="7298b-112">Áudio</span><span class="sxs-lookup"><span data-stu-id="7298b-112">Audio</span></span>| <span data-ttu-id="7298b-113">50000 – 50019</span><span class="sxs-lookup"><span data-stu-id="7298b-113">50,000–50,019</span></span>|<span data-ttu-id="7298b-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7298b-114">TCP/UDP</span></span>|<span data-ttu-id="7298b-115">46</span><span class="sxs-lookup"><span data-stu-id="7298b-115">46</span></span>|<span data-ttu-id="7298b-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="7298b-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="7298b-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="7298b-117">Video</span></span>| <span data-ttu-id="7298b-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="7298b-118">50,020–50,039</span></span>|<span data-ttu-id="7298b-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7298b-119">TCP/UDP</span></span>|<span data-ttu-id="7298b-120">34</span><span class="sxs-lookup"><span data-stu-id="7298b-120">34</span></span>|<span data-ttu-id="7298b-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="7298b-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="7298b-122">Compartilhamento de tela/aplicativo</span><span class="sxs-lookup"><span data-stu-id="7298b-122">Application/Screen Sharing</span></span>| <span data-ttu-id="7298b-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="7298b-123">50,040–50,059</span></span>|<span data-ttu-id="7298b-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7298b-124">TCP/UDP</span></span>|<span data-ttu-id="7298b-125">dezoito</span><span class="sxs-lookup"><span data-stu-id="7298b-125">18</span></span>|<span data-ttu-id="7298b-126">Encaminhamento garantido (AF21)</span><span class="sxs-lookup"><span data-stu-id="7298b-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="7298b-127">Sempre que possível, configure as configurações de QoS baseadas em políticas em um objeto de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="7298b-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="7298b-128">As etapas a seguir são muito parecidas com a [configuração de intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tem alguns detalhes adicionais que podem não ser necessários.</span><span class="sxs-lookup"><span data-stu-id="7298b-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="7298b-129">Para criar uma política de áudio QoS para computadores Windows 10 associados a um domínio, primeiro faça logon em um computador no qual o gerenciamento de política de grupo foi instalado.</span><span class="sxs-lookup"><span data-stu-id="7298b-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="7298b-130">Abra gerenciamento de política de grupo (clique em Iniciar, aponte para ferramentas administrativas e clique em gerenciamento de política de grupo) e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7298b-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="7298b-131">No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="7298b-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="7298b-132">Por exemplo, se todos os seus computadores cliente estiverem localizados em uma UO chamada **clientes**, a nova política deve ser criada na UO do cliente.</span><span class="sxs-lookup"><span data-stu-id="7298b-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="7298b-133">Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.</span><span class="sxs-lookup"><span data-stu-id="7298b-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="7298b-134">Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7298b-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="7298b-135">Clique com o botão direito do mouse na política recém-criada e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7298b-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="7298b-136">No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseado em política**e clique em **criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="7298b-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="7298b-137">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="7298b-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="7298b-138">Selecione **especificar valor DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="7298b-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="7298b-139">Deixe **especificar a taxa** de aceleração de saída desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7298b-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="7298b-140">Na próxima página, selecione **apenas aplicativos com esse nome executável** e insira o nome **Teams. exe**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7298b-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="7298b-141">Essa configuração instrui a política a priorizar somente o tráfego de correspondência do cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="7298b-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="7298b-142">Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7298b-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="7298b-143">Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou os pacotes e qual computador (endereço IP) receberá os pacotes.</span><span class="sxs-lookup"><span data-stu-id="7298b-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="7298b-144">Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica** .</span><span class="sxs-lookup"><span data-stu-id="7298b-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="7298b-145">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados.</span><span class="sxs-lookup"><span data-stu-id="7298b-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="7298b-146">Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**.</span><span class="sxs-lookup"><span data-stu-id="7298b-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="7298b-147">Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="7298b-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="7298b-148">Por exemplo, se você reservou portas 50000 pelas portas 50019 para tráfego de áudio, insira o intervalo de porta usando este formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="7298b-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="7298b-149">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="7298b-149">Click **Finish**.</span></span>

11. <span data-ttu-id="7298b-150">Repita as etapas 5-10 para criar políticas para compartilhamento de aplicativos/aplicativos e vídeo, substituindo os valores apropriados nas etapas 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="7298b-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="7298b-151">As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="7298b-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="7298b-152">Embora a política de grupo seja atualizada periodicamente por conta própria, você pode forçar uma atualização imediata seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7298b-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="7298b-153">Em cada computador para o qual você deseja atualizar a política de grupo, abra um console de comando.</span><span class="sxs-lookup"><span data-stu-id="7298b-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="7298b-154">Verifique se o console de comando está definido como executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="7298b-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="7298b-155">No prompt de comando, insira</span><span class="sxs-lookup"><span data-stu-id="7298b-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="7298b-156">Verificar marcações DSCP no objeto de política de grupo</span><span class="sxs-lookup"><span data-stu-id="7298b-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="7298b-157">Para verificar se os valores do objeto de política de grupo foram definidos, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="7298b-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="7298b-158">Abra um console de comando.</span><span class="sxs-lookup"><span data-stu-id="7298b-158">Open a command console.</span></span> <span data-ttu-id="7298b-159">Verifique se o console de comando está definido como executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="7298b-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="7298b-160">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="7298b-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="7298b-161">Isso irá gerar um relatório e enviá-lo para um arquivo de texto chamado GP. txt.</span><span class="sxs-lookup"><span data-stu-id="7298b-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="7298b-162">Você também pode inserir o seguinte comando para produzir os mesmos dados em um relatório HTML mais legível chamado GP. html:</span><span class="sxs-lookup"><span data-stu-id="7298b-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="7298b-163">![Captura de tela da janela do console executando o comando Gpresult.] (media/Qos-in-Teams-Image3.png "Captura de tela da janela do console executando o comando Gpresult.")</span><span class="sxs-lookup"><span data-stu-id="7298b-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="7298b-164">No arquivo gerado, procure o título objetos de **política de grupo aplicados** e verifique se os nomes dos objetos de política de grupo criados anteriormente estão na lista de políticas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="7298b-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="7298b-165">Abra o editor do registro e acesse:</span><span class="sxs-lookup"><span data-stu-id="7298b-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="7298b-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span><span class="sxs-lookup"><span data-stu-id="7298b-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span></span>\

   <span data-ttu-id="7298b-167">Verifique os valores das entradas do registro listadas na tabela 4.</span><span class="sxs-lookup"><span data-stu-id="7298b-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="7298b-168">_Tabela 4. Valores para entradas do registro do Windows para QoS_</span><span class="sxs-lookup"><span data-stu-id="7298b-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="7298b-169">Nome</span><span class="sxs-lookup"><span data-stu-id="7298b-169">Name</span></span>          |  <span data-ttu-id="7298b-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="7298b-170">Type</span></span>  |    <span data-ttu-id="7298b-171">Dados</span><span class="sxs-lookup"><span data-stu-id="7298b-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="7298b-172">Nome do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="7298b-172">Application Name</span></span>    | <span data-ttu-id="7298b-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-173">REG_SZ</span></span> |  <span data-ttu-id="7298b-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="7298b-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="7298b-175">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="7298b-175">DSCP Value</span></span>       | <span data-ttu-id="7298b-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-176">REG_SZ</span></span> |     <span data-ttu-id="7298b-177">46</span><span class="sxs-lookup"><span data-stu-id="7298b-177">46</span></span>      |
   |        <span data-ttu-id="7298b-178">IP Local</span><span class="sxs-lookup"><span data-stu-id="7298b-178">Local IP</span></span>        | <span data-ttu-id="7298b-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="7298b-180">Comprimento do Prefixo IP Local</span><span class="sxs-lookup"><span data-stu-id="7298b-180">Local IP Prefix Length</span></span> | <span data-ttu-id="7298b-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="7298b-182">Porta Local</span><span class="sxs-lookup"><span data-stu-id="7298b-182">Local Port</span></span>       | <span data-ttu-id="7298b-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-183">REG_SZ</span></span> | <span data-ttu-id="7298b-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="7298b-184">50000-50019</span></span> |
   |        <span data-ttu-id="7298b-185">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7298b-185">Protocol</span></span>        | <span data-ttu-id="7298b-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="7298b-187">IP Remoto</span><span class="sxs-lookup"><span data-stu-id="7298b-187">Remote IP</span></span>        | <span data-ttu-id="7298b-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="7298b-189">Prefixo de IP remoto</span><span class="sxs-lookup"><span data-stu-id="7298b-189">Remote IP Prefix</span></span>    | <span data-ttu-id="7298b-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="7298b-191">Porta Remota</span><span class="sxs-lookup"><span data-stu-id="7298b-191">Remote Port</span></span>       | <span data-ttu-id="7298b-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="7298b-193">Taxa de Aceleração</span><span class="sxs-lookup"><span data-stu-id="7298b-193">Throttle Rate</span></span>      | <span data-ttu-id="7298b-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7298b-194">REG_SZ</span></span> |     <span data-ttu-id="7298b-195">-1</span><span class="sxs-lookup"><span data-stu-id="7298b-195">-1</span></span>      |

5. <span data-ttu-id="7298b-196">Verifique se o valor da entrada do nome do aplicativo está correto para o cliente que você está usando e verifique se as entradas do valor DSCP e da porta local refletem as configurações no objeto de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="7298b-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
