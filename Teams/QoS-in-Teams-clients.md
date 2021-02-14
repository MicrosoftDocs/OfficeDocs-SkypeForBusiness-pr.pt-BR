---
title: Implementar QoS (Qualidade de Serviço) em clientes do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba como usar a QoS (Qualidade de Serviço) para otimizar o tráfego de rede para o cliente de área de trabalho do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526398"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="a4d67-103">Implementar QoS (Qualidade de Serviço) em clientes do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a4d67-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="a4d67-104">Você pode usar QoS (Qualidade de Serviço baseado em política) na Política de Grupo para definir o intervalo de porta de origem para o valor DSCP predefinido no cliente teams.</span><span class="sxs-lookup"><span data-stu-id="a4d67-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="a4d67-105">Os intervalos de portas especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a4d67-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="a4d67-106">*Tabela 1. Intervalos de portas iniciais recomendados*</span><span class="sxs-lookup"><span data-stu-id="a4d67-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="a4d67-107">Tipo de tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="a4d67-107">Media traffic type</span></span>| <span data-ttu-id="a4d67-108">Intervalo de portas de origem do cliente </span><span class="sxs-lookup"><span data-stu-id="a4d67-108">Client source port range</span></span> |<span data-ttu-id="a4d67-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="a4d67-109">Protocol</span></span>|<span data-ttu-id="a4d67-110">Valor DSCP</span><span class="sxs-lookup"><span data-stu-id="a4d67-110">DSCP value</span></span>|<span data-ttu-id="a4d67-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="a4d67-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="a4d67-112">Áudio</span><span class="sxs-lookup"><span data-stu-id="a4d67-112">Audio</span></span>| <span data-ttu-id="a4d67-113">50.000–50.019</span><span class="sxs-lookup"><span data-stu-id="a4d67-113">50,000–50,019</span></span>|<span data-ttu-id="a4d67-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a4d67-114">TCP/UDP</span></span>|<span data-ttu-id="a4d67-115">46</span><span class="sxs-lookup"><span data-stu-id="a4d67-115">46</span></span>|<span data-ttu-id="a4d67-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="a4d67-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="a4d67-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="a4d67-117">Video</span></span>| <span data-ttu-id="a4d67-118">50.020–50.039</span><span class="sxs-lookup"><span data-stu-id="a4d67-118">50,020–50,039</span></span>|<span data-ttu-id="a4d67-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a4d67-119">TCP/UDP</span></span>|<span data-ttu-id="a4d67-120">34</span><span class="sxs-lookup"><span data-stu-id="a4d67-120">34</span></span>|<span data-ttu-id="a4d67-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="a4d67-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="a4d67-122">Compartilhamento de tela/aplicativo</span><span class="sxs-lookup"><span data-stu-id="a4d67-122">Application/Screen Sharing</span></span>| <span data-ttu-id="a4d67-123">50.040-50.059</span><span class="sxs-lookup"><span data-stu-id="a4d67-123">50,040–50,059</span></span>|<span data-ttu-id="a4d67-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a4d67-124">TCP/UDP</span></span>|<span data-ttu-id="a4d67-125">18</span><span class="sxs-lookup"><span data-stu-id="a4d67-125">18</span></span>|<span data-ttu-id="a4d67-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="a4d67-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="a4d67-127">Sempre que possível, configure as configurações de QoS baseadas em política dentro de um objeto de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="a4d67-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="a4d67-128">As etapas a seguir são muito semelhantes à Configuração de intervalos de portas e a uma política de Qualidade de Serviço para seus clientes no  [Skype for Business Server,](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)que tem alguns detalhes adicionais que podem não ser necessários.</span><span class="sxs-lookup"><span data-stu-id="a4d67-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="a4d67-129">Para criar uma política de áudio QoS para computadores windows 10 que ingressaram no domínio, primeiro faça logoff em um computador no qual o Gerenciamento de Política de Grupo foi instalado.</span><span class="sxs-lookup"><span data-stu-id="a4d67-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="a4d67-130">Abra o Gerenciamento de Política de Grupo (clique em Iniciar, aponte para Ferramentas Administrativas e, em seguida, clique em Gerenciamento de Política de Grupo) e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a4d67-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="a4d67-131">No Gerenciamento de Política de Grupo, localize o contêiner onde a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="a4d67-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="a4d67-132">Por exemplo, se todos os seus computadores cliente estão localizados em uma UO denominada **Clientes,** a nova política deve ser criada na UO de Clientes.</span><span class="sxs-lookup"><span data-stu-id="a4d67-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="a4d67-133">Clique com o botão direito do mouse no contêiner apropriado e clique em Criar um GPO neste domínio **e vincule-o aqui.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="a4d67-134">Na caixa **de diálogo Novo GPO,** digite um nome  para o novo objeto de Política de Grupo na caixa Nome e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="a4d67-135">Clique com o botão direito do mouse na política recém-criada e clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="a4d67-136">No Editor de Gerenciamento de Política de Grupo, expanda a Configuração do Computador, expanda as Configurações do **Windows,** clique com o botão direito do mouse **em QoS** baseado em política e clique em **Criar nova política.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="a4d67-137">Na caixa **de diálogo QoS** baseado em Política, na página de abertura, digite um nome para a nova política na **caixa** Nome.</span><span class="sxs-lookup"><span data-stu-id="a4d67-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="a4d67-138">Selecione **Especificar Valor DSCP** e de definir o valor como **46.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a4d67-139">Deixe **de especificar a taxa de aceleração de saída** não selecionado e clique em **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="a4d67-140">Na página seguinte, selecione **Somente aplicativos** com esse nome executável, insira o nome **Teams.exe** e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="a4d67-141">Essa configuração instrui a política a priorizar apenas o tráfego correspondente do cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="a4d67-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="a4d67-142">Na terceira página, certifique-se de que qualquer endereço **IP** de origem e qualquer endereço **IP** de destino estão selecionados e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="a4d67-143">Essas duas configurações garantem que os pacotes sejam gerenciados independentemente de qual computador (endereço IP) enviou os pacotes e qual computador (endereço IP) receberá os pacotes.</span><span class="sxs-lookup"><span data-stu-id="a4d67-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="a4d67-144">Na página quatro, selecione **TCP e UDP** na opção Selecionar o protocolo que esta política **QoS aplica** à lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="a4d67-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="a4d67-145">TCP (Protocolo de Controle de Transmissão) e UDP (User Datagram Protocol) são os dois protocolos de rede mais usados.</span><span class="sxs-lookup"><span data-stu-id="a4d67-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="a4d67-146">No título **Especificar o número da porta de origem,** selecione Nesta porta ou intervalo de **origem.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="a4d67-147">Na caixa de texto que acompanha, digite o intervalo de portas reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="a4d67-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a4d67-148">Por exemplo, se você reservou portas 50000 até as portas 50019 para tráfego de áudio, insira o intervalo de portas usando esse formato: **50000:50019.**</span><span class="sxs-lookup"><span data-stu-id="a4d67-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="a4d67-149">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a4d67-149">Click **Finish**.</span></span>

1. <span data-ttu-id="a4d67-150">Repita as etapas de 5 a 10 para criar políticas para o Compartilhamento de Vídeo e Aplicativo/Área de Trabalho, substituindo os valores apropriados nas etapas 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="a4d67-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="a4d67-151">As novas políticas criadas não vigorarão até que a Política de Grupo seja atualizada em seus computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="a4d67-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="a4d67-152">Embora a Política de Grupo atualize periodicamente por conta própria, você pode forçar uma atualização imediata seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a4d67-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="a4d67-153">Em cada computador para o qual você deseja atualizar a Política de Grupo, abra um Prompt de Comando como administrador (*Executar como administrador).*</span><span class="sxs-lookup"><span data-stu-id="a4d67-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="a4d67-154">No prompt de comando, insira</span><span class="sxs-lookup"><span data-stu-id="a4d67-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="a4d67-155">Verificar marcações DSCP no objeto Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="a4d67-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="a4d67-156">Para verificar se os valores do objeto de Política de Grupo foram definidos, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a4d67-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="a4d67-157">Abrir um Prompt de Comando como administrador (*Executar como administrador).*</span><span class="sxs-lookup"><span data-stu-id="a4d67-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="a4d67-158">No prompt de comando, insira</span><span class="sxs-lookup"><span data-stu-id="a4d67-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="a4d67-159">Isso gerará um relatório de GPOs aplicados e o enviará para um arquivo de texto chamado *gp.txt.*</span><span class="sxs-lookup"><span data-stu-id="a4d67-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="a4d67-160">Para obter um relatório HTML mais legível chamado *gp.html,* insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a4d67-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="a4d67-161">No arquivo gerado, procure  o título Objetos de Política de Grupo Aplicados e verifique se os nomes dos objetos de Política de Grupo criados anteriormente estão na lista de políticas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="a4d67-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="a4d67-162">Abra o Editor do Registro e vá para</span><span class="sxs-lookup"><span data-stu-id="a4d67-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="a4d67-163">Políticas de \_ software HKEY LOCAL \_ MACHINE Microsoft Windows \\ \\ \\ \\ \\ QoS</span><span class="sxs-lookup"><span data-stu-id="a4d67-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="a4d67-164">Verifique os valores das entradas do registro listadas na Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="a4d67-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="a4d67-165">*Tabela 2. Valores para entradas de registro do Windows para QoS*</span><span class="sxs-lookup"><span data-stu-id="a4d67-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="a4d67-166">Nome</span><span class="sxs-lookup"><span data-stu-id="a4d67-166">Name</span></span>          |  <span data-ttu-id="a4d67-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="a4d67-167">Type</span></span>  |    <span data-ttu-id="a4d67-168">Dados</span><span class="sxs-lookup"><span data-stu-id="a4d67-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="a4d67-169">Nome do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="a4d67-169">Application Name</span></span>    | <span data-ttu-id="a4d67-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-170">REG_SZ</span></span> |  <span data-ttu-id="a4d67-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="a4d67-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="a4d67-172">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="a4d67-172">DSCP Value</span></span>       | <span data-ttu-id="a4d67-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-173">REG_SZ</span></span> |     <span data-ttu-id="a4d67-174">46</span><span class="sxs-lookup"><span data-stu-id="a4d67-174">46</span></span>      |
   |        <span data-ttu-id="a4d67-175">IP Local</span><span class="sxs-lookup"><span data-stu-id="a4d67-175">Local IP</span></span>        | <span data-ttu-id="a4d67-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="a4d67-177">Comprimento do Prefixo IP Local</span><span class="sxs-lookup"><span data-stu-id="a4d67-177">Local IP Prefix Length</span></span> | <span data-ttu-id="a4d67-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="a4d67-179">Porta Local</span><span class="sxs-lookup"><span data-stu-id="a4d67-179">Local Port</span></span>       | <span data-ttu-id="a4d67-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-180">REG_SZ</span></span> | <span data-ttu-id="a4d67-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="a4d67-181">50000-50019</span></span> |
   |        <span data-ttu-id="a4d67-182">Protocolo</span><span class="sxs-lookup"><span data-stu-id="a4d67-182">Protocol</span></span>        | <span data-ttu-id="a4d67-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="a4d67-184">IP Remoto</span><span class="sxs-lookup"><span data-stu-id="a4d67-184">Remote IP</span></span>        | <span data-ttu-id="a4d67-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="a4d67-186">Prefixo IP Remoto</span><span class="sxs-lookup"><span data-stu-id="a4d67-186">Remote IP Prefix</span></span>    | <span data-ttu-id="a4d67-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="a4d67-188">Porta Remota</span><span class="sxs-lookup"><span data-stu-id="a4d67-188">Remote Port</span></span>       | <span data-ttu-id="a4d67-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="a4d67-190">Taxa de Aceleração</span><span class="sxs-lookup"><span data-stu-id="a4d67-190">Throttle Rate</span></span>      | <span data-ttu-id="a4d67-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="a4d67-191">REG_SZ</span></span> |     <span data-ttu-id="a4d67-192">-1</span><span class="sxs-lookup"><span data-stu-id="a4d67-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="a4d67-193">Verifique se o valor da entrada Nome do Aplicativo está correto para o cliente que você está usando e verifique se as entradas Valor DSCP e Porta Local refletem as configurações no objeto Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="a4d67-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a4d67-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a4d67-194">Related topics</span></span>

[<span data-ttu-id="a4d67-195">Implementar qoS (qualidade de serviço) no Teams</span><span class="sxs-lookup"><span data-stu-id="a4d67-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)