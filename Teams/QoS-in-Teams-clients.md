---
title: Implementar o Quality of Service nos clientes do Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Implemente o Quality of Service (QoS) para clientes do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 157754f38f1304aa0cfe8d48b225b470ec015f4b
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "30211773"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="17682-103">Conjunto de QoS nos clientes do Windows</span><span class="sxs-lookup"><span data-stu-id="17682-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="17682-104">Você pode usar a QoS baseada em diretivas dentro da diretiva de grupo para definir o intervalo de porta de origem para o valor DSCP predefinido no cliente equipes.</span><span class="sxs-lookup"><span data-stu-id="17682-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="17682-105">Os intervalos de porta especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="17682-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="17682-106">_Recomendado de intervalos de porta inicial_</span><span class="sxs-lookup"><span data-stu-id="17682-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="17682-107">Tipo de tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="17682-107">Media traffic type</span></span>| <span data-ttu-id="17682-108">Intervalo de porta de origem do cliente</span><span class="sxs-lookup"><span data-stu-id="17682-108">Client source port range</span></span> |<span data-ttu-id="17682-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="17682-109">Protocol</span></span>|<span data-ttu-id="17682-110">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="17682-110">DSCP value</span></span>|<span data-ttu-id="17682-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="17682-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="17682-112">Áudio</span><span class="sxs-lookup"><span data-stu-id="17682-112">Audio</span></span>| <span data-ttu-id="17682-113">50.000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="17682-113">50,000–50,019</span></span>|<span data-ttu-id="17682-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="17682-114">TCP/UDP</span></span>|<span data-ttu-id="17682-115">46</span><span class="sxs-lookup"><span data-stu-id="17682-115">46</span></span>|<span data-ttu-id="17682-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="17682-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="17682-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="17682-117">Video</span></span>| <span data-ttu-id="17682-118">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="17682-118">50,020–50,039</span></span>|<span data-ttu-id="17682-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="17682-119">TCP/UDP</span></span>|<span data-ttu-id="17682-120">34</span><span class="sxs-lookup"><span data-stu-id="17682-120">34</span></span>|<span data-ttu-id="17682-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="17682-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="17682-122">Compartilhamento de tela do aplicativo</span><span class="sxs-lookup"><span data-stu-id="17682-122">Application/Screen Sharing</span></span>| <span data-ttu-id="17682-123">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="17682-123">50,040–50,059</span></span>|<span data-ttu-id="17682-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="17682-124">TCP/UDP</span></span>|<span data-ttu-id="17682-125">18</span><span class="sxs-lookup"><span data-stu-id="17682-125">18</span></span>|<span data-ttu-id="17682-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="17682-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="17682-127">Sempre que possível, configure as configurações de QoS baseada em diretivas dentro de um objeto de diretiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="17682-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="17682-128">As etapas a seguir serão bastante similares às [Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes em Skype para Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tem alguns detalhes adicionais que talvez não seja necessários.</span><span class="sxs-lookup"><span data-stu-id="17682-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="17682-129">Para criar uma política de QoS de áudio para computadores que ingressaram dominio Windows 10, primeiro faça logon em um computador no qual o gerenciamento de diretiva de grupo tenha sido instalado.</span><span class="sxs-lookup"><span data-stu-id="17682-129">To create a QoS audio policy for domian-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="17682-130">Abra Gerenciamento de diretiva de grupo (clique em Iniciar, aponte para ferramentas administrativas e clique em gerenciamento de diretiva de grupo) e, em seguida, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="17682-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="17682-131">Em gerenciamento de diretiva de grupo, localize o contêiner onde a nova diretiva deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="17682-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="17682-132">Por exemplo, se todos os computadores cliente estão localizados em uma unidade Organizacional denominada **clientes**, a nova diretiva deve ser criada na unidade Organizacional cliente.</span><span class="sxs-lookup"><span data-stu-id="17682-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="17682-133">Com o botão direito do contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.</span><span class="sxs-lookup"><span data-stu-id="17682-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="17682-134">Na caixa de diálogo **Novo GPO** , digite um nome para o novo objeto de diretiva de grupo na caixa **nome** e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="17682-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="17682-135">Clique com o botão a política recém-criada e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="17682-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="17682-136">No Editor de gerenciamento de diretiva de grupo, expanda **Configuração do computador**, expanda **Configurações do Windows**, do mouse em **QoS baseada em política**e clique em **Criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="17682-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="17682-137">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="17682-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="17682-138">Selecione **Especificar valor de DSCP** e defina o valor para **46**.</span><span class="sxs-lookup"><span data-stu-id="17682-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="17682-139">Deixe **Especificar taxa de aceleração saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17682-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="17682-140">Na próxima página, selecione **apenas a aplicativos com este nome executável** e insira o nome **Teams.exe**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17682-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="17682-141">Essa configuração instrui a política priorizar apenas o tráfego do cliente equipes correspondente.</span><span class="sxs-lookup"><span data-stu-id="17682-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="17682-142">Na terceira página, certifique-se de que **qualquer endereço IP de origem** e de **qualquer endereço IP de destino** estão marcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="17682-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="17682-143">Estas duas configurações Certifique-se de que os pacotes serão gerenciados independentemente do computador (endereço IP) enviadas os pacotes e qual computador (endereço IP) receberá os pacotes.</span><span class="sxs-lookup"><span data-stu-id="17682-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="17682-144">Na página quatro, selecione **TCP e UDP** da lista suspensa **, selecione o protocolo que essa política de QoS se aplica** .</span><span class="sxs-lookup"><span data-stu-id="17682-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="17682-145">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados.</span><span class="sxs-lookup"><span data-stu-id="17682-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="17682-146">Sob o título, **Especifique o número da porta de origem**, selecione **este ou intervalo de porta de origem**.</span><span class="sxs-lookup"><span data-stu-id="17682-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="17682-147">Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="17682-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="17682-148">Por exemplo, se você reservadas portas 50000 através de portas 50019 para tráfego de áudio, insira o intervalo de portas usando este formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="17682-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="17682-149">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="17682-149">Click **Finish**.</span></span>

11. <span data-ttu-id="17682-150">Repita as etapas 5 a 10 para criar políticas para vídeo e compartilhamento de aplicativo/área de trabalho, substituindo os valores apropriados nas etapas 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="17682-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="17682-151">As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada em seus computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="17682-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="17682-152">Embora a diretiva de grupo for atualizada periodicamente por si só, você pode forçar uma atualização imediata, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="17682-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="17682-153">Em cada computador para o qual você deseja atualizar a diretiva de grupo, abra um console de comando.</span><span class="sxs-lookup"><span data-stu-id="17682-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="17682-154">Certifique-se de que o console de comando está definido para executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="17682-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="17682-155">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="17682-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="17682-156">Verifique se as marcações de DSCP no objeto de diretiva de grupo</span><span class="sxs-lookup"><span data-stu-id="17682-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="17682-157">Para verificar se os valores do objeto de diretiva de grupo foram definidos, execute as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="17682-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="17682-158">Abra um console de comando.</span><span class="sxs-lookup"><span data-stu-id="17682-158">Open a command console.</span></span> <span data-ttu-id="17682-159">Certifique-se de que o console de comando está definido para executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="17682-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="17682-160">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="17682-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="17682-161">Isso irá gerar um relatório e enviá-la para um arquivo de texto chamado GP. txt.</span><span class="sxs-lookup"><span data-stu-id="17682-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="17682-162">Como alternativa, você pode inserir o seguinte comando para produzir os mesmos dados em um relatório HTML mais legível chamado gp.html:</span><span class="sxs-lookup"><span data-stu-id="17682-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="17682-163">![Captura de tela da janela do console, executando o comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de tela da janela do console, executando o comando gpresult.")</span><span class="sxs-lookup"><span data-stu-id="17682-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="17682-164">No arquivo gerado, procure por título de **Objetos de diretiva de grupo aplicados** e verifique se os nomes dos objetos de diretiva de grupo criados anteriormente estão na lista de diretivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="17682-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="17682-165">Abra o Editor do registro e vá para:</span><span class="sxs-lookup"><span data-stu-id="17682-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="17682-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="17682-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="17682-167">Verifique se os valores para as entradas do Registro listadas na tabela 4.</span><span class="sxs-lookup"><span data-stu-id="17682-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="17682-168">_Tabela 4. Valores para entradas de registro do Windows para QoS_</span><span class="sxs-lookup"><span data-stu-id="17682-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="17682-169">Nome</span><span class="sxs-lookup"><span data-stu-id="17682-169">Name</span></span>          |  <span data-ttu-id="17682-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="17682-170">Type</span></span>  |    <span data-ttu-id="17682-171">Dados</span><span class="sxs-lookup"><span data-stu-id="17682-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="17682-172">Nome do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="17682-172">Application Name</span></span>    | <span data-ttu-id="17682-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-173">REG_SZ</span></span> |  <span data-ttu-id="17682-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="17682-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="17682-175">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="17682-175">DSCP Value</span></span>       | <span data-ttu-id="17682-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-176">REG_SZ</span></span> |     <span data-ttu-id="17682-177">46</span><span class="sxs-lookup"><span data-stu-id="17682-177">46</span></span>      |
   |        <span data-ttu-id="17682-178">IP Local</span><span class="sxs-lookup"><span data-stu-id="17682-178">Local IP</span></span>        | <span data-ttu-id="17682-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="17682-180">Comprimento do Prefixo IP Local</span><span class="sxs-lookup"><span data-stu-id="17682-180">Local IP Prefix Length</span></span> | <span data-ttu-id="17682-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="17682-182">Porta Local</span><span class="sxs-lookup"><span data-stu-id="17682-182">Local Port</span></span>       | <span data-ttu-id="17682-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-183">REG_SZ</span></span> | <span data-ttu-id="17682-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="17682-184">50000-50019</span></span> |
   |        <span data-ttu-id="17682-185">Protocolo</span><span class="sxs-lookup"><span data-stu-id="17682-185">Protocol</span></span>        | <span data-ttu-id="17682-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="17682-187">IP Remoto</span><span class="sxs-lookup"><span data-stu-id="17682-187">Remote IP</span></span>        | <span data-ttu-id="17682-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="17682-189">Prefixo IP remoto</span><span class="sxs-lookup"><span data-stu-id="17682-189">Remote IP Prefix</span></span>    | <span data-ttu-id="17682-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="17682-191">Porta Remota</span><span class="sxs-lookup"><span data-stu-id="17682-191">Remote Port</span></span>       | <span data-ttu-id="17682-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="17682-193">Taxa de Aceleração</span><span class="sxs-lookup"><span data-stu-id="17682-193">Throttle Rate</span></span>      | <span data-ttu-id="17682-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="17682-194">REG_SZ</span></span> |     <span data-ttu-id="17682-195">-1</span><span class="sxs-lookup"><span data-stu-id="17682-195">-1</span></span>      |

5. <span data-ttu-id="17682-196">Verificar se o valor para a entrada de nome do aplicativo está correto para o cliente que você está usando e verificar que o valor DSCP e a porta Local entradas reflitam as configurações no objeto de diretiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="17682-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
