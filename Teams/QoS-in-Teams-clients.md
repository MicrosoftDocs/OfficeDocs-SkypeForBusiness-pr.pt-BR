---
title: Implementar qoS (Qualidade de Serviço) em clientes do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba como usar a QoS (Qualidade do Serviço) para otimizar o tráfego de rede para o cliente da área de trabalho do Microsoft Teams.
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
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094779"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="7f68e-103">Implementar qoS (Qualidade de Serviço) em clientes do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f68e-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="7f68e-104">Você pode usar a QoS (Qualidade de Serviço baseada em política) na Política de Grupo para definir o intervalo de portas de origem para o valor DSCP predefinido no cliente teams.</span><span class="sxs-lookup"><span data-stu-id="7f68e-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="7f68e-105">Os intervalos de porta especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7f68e-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="7f68e-106">*Tabela 1. Intervalos de portas iniciais recomendados*</span><span class="sxs-lookup"><span data-stu-id="7f68e-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="7f68e-107">Tipo de tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="7f68e-107">Media traffic type</span></span>| <span data-ttu-id="7f68e-108">Intervalo de portas de origem do cliente </span><span class="sxs-lookup"><span data-stu-id="7f68e-108">Client source port range</span></span> |<span data-ttu-id="7f68e-109">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7f68e-109">Protocol</span></span>|<span data-ttu-id="7f68e-110">Valor DSCP</span><span class="sxs-lookup"><span data-stu-id="7f68e-110">DSCP value</span></span>|<span data-ttu-id="7f68e-111">Classe DSCP</span><span class="sxs-lookup"><span data-stu-id="7f68e-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="7f68e-112">Áudio</span><span class="sxs-lookup"><span data-stu-id="7f68e-112">Audio</span></span>| <span data-ttu-id="7f68e-113">50.000–50.019</span><span class="sxs-lookup"><span data-stu-id="7f68e-113">50,000–50,019</span></span>|<span data-ttu-id="7f68e-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7f68e-114">TCP/UDP</span></span>|<span data-ttu-id="7f68e-115">46</span><span class="sxs-lookup"><span data-stu-id="7f68e-115">46</span></span>|<span data-ttu-id="7f68e-116">Expedited Forwarding (EF)</span><span class="sxs-lookup"><span data-stu-id="7f68e-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="7f68e-117">Vídeo</span><span class="sxs-lookup"><span data-stu-id="7f68e-117">Video</span></span>| <span data-ttu-id="7f68e-118">50.020–50.039</span><span class="sxs-lookup"><span data-stu-id="7f68e-118">50,020–50,039</span></span>|<span data-ttu-id="7f68e-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7f68e-119">TCP/UDP</span></span>|<span data-ttu-id="7f68e-120">34</span><span class="sxs-lookup"><span data-stu-id="7f68e-120">34</span></span>|<span data-ttu-id="7f68e-121">Assured Forwarding (AF41)</span><span class="sxs-lookup"><span data-stu-id="7f68e-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="7f68e-122">Compartilhamento de tela/aplicativo</span><span class="sxs-lookup"><span data-stu-id="7f68e-122">Application/Screen Sharing</span></span>| <span data-ttu-id="7f68e-123">50.040-50.059</span><span class="sxs-lookup"><span data-stu-id="7f68e-123">50,040–50,059</span></span>|<span data-ttu-id="7f68e-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7f68e-124">TCP/UDP</span></span>|<span data-ttu-id="7f68e-125">18</span><span class="sxs-lookup"><span data-stu-id="7f68e-125">18</span></span>|<span data-ttu-id="7f68e-126">Assured Forwarding (AF21)</span><span class="sxs-lookup"><span data-stu-id="7f68e-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="7f68e-127">Sempre que possível, configure as configurações de QoS baseadas em política em um objeto de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="7f68e-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="7f68e-128">As etapas a seguir são muito  [semelhantes à](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)Configuração de intervalos de porta e uma política de Qualidade de Serviço para seus clientes no Skype for Business Server , que tem alguns detalhes adicionais que podem não ser necessários.</span><span class="sxs-lookup"><span data-stu-id="7f68e-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="7f68e-129">Para criar uma política de áudio QoS para computadores Windows 10 ingressados no domínio, primeiro faça logoff em um computador no qual o Gerenciamento de Política de Grupo foi instalado.</span><span class="sxs-lookup"><span data-stu-id="7f68e-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="7f68e-130">Abra o Gerenciamento de Política de Grupo (clique em Iniciar, aponte para Ferramentas Administrativas e clique em Gerenciamento de Política de Grupo) e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7f68e-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="7f68e-131">No Gerenciamento de Política de Grupo, localize o contêiner onde a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="7f68e-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="7f68e-132">Por exemplo, se todos os seus computadores clientes estão localizados em uma UO denominada **Clients**, a nova política deve ser criada na UO de Clientes.</span><span class="sxs-lookup"><span data-stu-id="7f68e-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="7f68e-133">Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="7f68e-134">Na caixa de diálogo Novo **GPO,** digite um nome  para o novo objeto de Política de Grupo na caixa Nome e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="7f68e-135">Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="7f68e-136">No Editor de Gerenciamento de Política de Grupo, **expanda** Configuração do **Computador, Configurações** do Windows, clique com o botão direito do mouse em **QoS** baseado em Política e clique em **Criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="7f68e-137">Na caixa **de diálogo QoS** baseada em política, na página de abertura, digite um nome para a nova política na **caixa** Nome.</span><span class="sxs-lookup"><span data-stu-id="7f68e-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="7f68e-138">Selecione **Especificar Valor DSCP** e de definir o valor **como 46**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="7f68e-139">Deixe **Especificar Taxa de Aceleração de Saída** não eleita e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="7f68e-140">Na próxima página, selecione **Somente aplicativos** com esse nome executável e insira o **nome** Teams.exee clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="7f68e-141">Essa configuração instrui a política a priorizar apenas o tráfego correspondente do cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="7f68e-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="7f68e-142">Na terceira página, certifique-se de que qualquer endereço **IP** de origem e qualquer endereço **IP** de destino estão selecionados e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="7f68e-143">Essas duas configurações garantem que os pacotes sejam gerenciados independentemente de qual computador (endereço IP) enviou os pacotes e qual computador (endereço IP) receberá os pacotes.</span><span class="sxs-lookup"><span data-stu-id="7f68e-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="7f68e-144">Na página quatro, selecione **TCP e UDP** na política Selecionar o protocolo que essa **política QoS aplica** à listada.</span><span class="sxs-lookup"><span data-stu-id="7f68e-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="7f68e-145">TCP (Protocolo de Controle de Transmissão) e UDP (User Datagram Protocol) são os dois protocolos de rede mais usados.</span><span class="sxs-lookup"><span data-stu-id="7f68e-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="7f68e-146">Sob o título **Especifique o número da porta de** origem , selecione Nesta porta de **origem ou intervalo**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="7f68e-147">Na caixa de texto que acompanha, digite o intervalo de portas reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="7f68e-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="7f68e-148">Por exemplo, se você reservou as portas 50000 até as portas 50019 para tráfego de áudio, insira o intervalo de portas usando esse formato: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="7f68e-149">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="7f68e-149">Click **Finish**.</span></span>

1. <span data-ttu-id="7f68e-150">Repita as etapas 5 a 10 para criar políticas para Compartilhamento de Vídeo e Aplicativo/Área de Trabalho, substituindo os valores apropriados nas etapas 6 e 10.</span><span class="sxs-lookup"><span data-stu-id="7f68e-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="7f68e-151">As novas políticas criadas não vigorarão até que a Política de Grupo seja atualizada em seus computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="7f68e-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="7f68e-152">Embora a Política de Grupo atualize periodicamente por conta própria, você pode forçar uma atualização imediata seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7f68e-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="7f68e-153">Em cada computador para o qual você deseja atualizar a Política de Grupo, abra um Prompt de Comando como administrador (*Execute como administrador*).</span><span class="sxs-lookup"><span data-stu-id="7f68e-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="7f68e-154">No prompt de comando, digite</span><span class="sxs-lookup"><span data-stu-id="7f68e-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="7f68e-155">Verificar marcações DSCP no objeto Diretiva de Grupo</span><span class="sxs-lookup"><span data-stu-id="7f68e-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="7f68e-156">Para verificar se os valores do objeto Diretiva de Grupo foram definidos, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7f68e-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="7f68e-157">Abra um Prompt de Comando como administrador (*Execute como administrador*).</span><span class="sxs-lookup"><span data-stu-id="7f68e-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="7f68e-158">No prompt de comando, digite</span><span class="sxs-lookup"><span data-stu-id="7f68e-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="7f68e-159">Isso gerará um relatório de GPOs aplicados e o enviará para um arquivo de texto chamado *gp.txt*.</span><span class="sxs-lookup"><span data-stu-id="7f68e-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="7f68e-160">Para um relatório HTML mais legível chamado *gp.html*, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7f68e-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="7f68e-161">No arquivo gerado, procure o título **Objetos** de Política de Grupo Aplicados e verifique se os nomes dos objetos de Política de Grupo criados anteriormente estão na lista de políticas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="7f68e-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="7f68e-162">Abra o Editor do Registro e vá para</span><span class="sxs-lookup"><span data-stu-id="7f68e-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="7f68e-163">HKEY \_ LOCAL \_ MACHINE \\ Software \\ Policies \\ Microsoft \\ Windows \\ QoS</span><span class="sxs-lookup"><span data-stu-id="7f68e-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="7f68e-164">Verifique os valores das entradas do Registro listadas na Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="7f68e-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="7f68e-165">*Tabela 2. Valores para entradas do Registro do Windows para QoS*</span><span class="sxs-lookup"><span data-stu-id="7f68e-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="7f68e-166">Nome</span><span class="sxs-lookup"><span data-stu-id="7f68e-166">Name</span></span>          |  <span data-ttu-id="7f68e-167">Tipo</span><span class="sxs-lookup"><span data-stu-id="7f68e-167">Type</span></span>  |    <span data-ttu-id="7f68e-168">Dados</span><span class="sxs-lookup"><span data-stu-id="7f68e-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="7f68e-169">Nome do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="7f68e-169">Application Name</span></span>    | <span data-ttu-id="7f68e-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-170">REG_SZ</span></span> |  <span data-ttu-id="7f68e-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="7f68e-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="7f68e-172">Valor de DSCP</span><span class="sxs-lookup"><span data-stu-id="7f68e-172">DSCP Value</span></span>       | <span data-ttu-id="7f68e-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-173">REG_SZ</span></span> |     <span data-ttu-id="7f68e-174">46</span><span class="sxs-lookup"><span data-stu-id="7f68e-174">46</span></span>      |
   |        <span data-ttu-id="7f68e-175">IP Local</span><span class="sxs-lookup"><span data-stu-id="7f68e-175">Local IP</span></span>        | <span data-ttu-id="7f68e-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="7f68e-177">Comprimento do Prefixo IP Local</span><span class="sxs-lookup"><span data-stu-id="7f68e-177">Local IP Prefix Length</span></span> | <span data-ttu-id="7f68e-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="7f68e-179">Porta Local</span><span class="sxs-lookup"><span data-stu-id="7f68e-179">Local Port</span></span>       | <span data-ttu-id="7f68e-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-180">REG_SZ</span></span> | <span data-ttu-id="7f68e-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="7f68e-181">50000-50019</span></span> |
   |        <span data-ttu-id="7f68e-182">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7f68e-182">Protocol</span></span>        | <span data-ttu-id="7f68e-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="7f68e-184">IP Remoto</span><span class="sxs-lookup"><span data-stu-id="7f68e-184">Remote IP</span></span>        | <span data-ttu-id="7f68e-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="7f68e-186">Prefixo IP remoto</span><span class="sxs-lookup"><span data-stu-id="7f68e-186">Remote IP Prefix</span></span>    | <span data-ttu-id="7f68e-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="7f68e-188">Porta Remota</span><span class="sxs-lookup"><span data-stu-id="7f68e-188">Remote Port</span></span>       | <span data-ttu-id="7f68e-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="7f68e-190">Taxa de Aceleração</span><span class="sxs-lookup"><span data-stu-id="7f68e-190">Throttle Rate</span></span>      | <span data-ttu-id="7f68e-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7f68e-191">REG_SZ</span></span> |     <span data-ttu-id="7f68e-192">-1</span><span class="sxs-lookup"><span data-stu-id="7f68e-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="7f68e-193">Verifique se o valor da entrada Nome do Aplicativo está correto para o cliente que você está usando e verifique se as entradas Valor DSCP e Porta Local refletem as configurações no objeto Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="7f68e-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7f68e-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7f68e-194">Related topics</span></span>

[<span data-ttu-id="7f68e-195">Implementar qoS (qualidade de serviço) no Teams</span><span class="sxs-lookup"><span data-stu-id="7f68e-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)