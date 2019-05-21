---
title: Editar a topologia no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Após concluir as perguntas iniciais da entrevista, você poderá editar o nome de domínio totalmente qualificado (FQDN) e o endereço IP do site. Para isso, na página Topologia Global, clique duas vezes no site que deseja editar.
ms.openlocfilehash: 91a7ad51c66d810255fcc3239d25298bd370501f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274286"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="db42b-104">Editar a topologia no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="db42b-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="db42b-p102">Após concluir as perguntas iniciais da entrevista, você poderá editar o nome de domínio totalmente qualificado (FQDN) e o endereço IP do site. Para isso, na página **Topologia Global**, clique duas vezes no site que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="db42b-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="db42b-107">A ferramenta de planejamento exibe a topologia de site para o site selecionado.</span><span class="sxs-lookup"><span data-stu-id="db42b-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="db42b-108">Na parte inferior da página do site, existem quatro guias:</span><span class="sxs-lookup"><span data-stu-id="db42b-108">At the bottom of the site page are four tabs:</span></span>

![Topologia do site da ferramenta de planejamento](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="db42b-110">Topologia de site-a página atualmente exibida com uma visão geral da topologia, conforme recomendado.</span><span class="sxs-lookup"><span data-stu-id="db42b-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="db42b-111">Diagrama de rede de borda – a página de diagrama de rede de borda é onde o designer faz a maior parte do trabalho na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="db42b-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="db42b-112">O diagrama exibe a configuração de rede para uma topologia do Skype for Business Server 2015 recomendada, com entradas editáveis para endereços IP e FQDNs para servidores, pool e balanceadores de carga de hardware e DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="db42b-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="db42b-113">Relatório de administração de borda-o relatório de administração de borda contém um total de quatro relatórios:</span><span class="sxs-lookup"><span data-stu-id="db42b-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Página de relatório de administração de borda](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="db42b-115">Relatório de resumo-um relatório geral de configurações para a configuração de rede de borda.</span><span class="sxs-lookup"><span data-stu-id="db42b-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="db42b-116">Se você editar os valores na página \*\*Diagrama da rede de borda \*\* para a topologia TCP/IP e os valores do FQDN que irão ser usados na implantação atual, tais endereços e nomes serão representados aqui.</span><span class="sxs-lookup"><span data-stu-id="db42b-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="db42b-117">De outro modo, o texto padrão aparecerá.</span><span class="sxs-lookup"><span data-stu-id="db42b-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="db42b-118">Relatório de certificado-o relatório de certificado listará o nome do assunto e os nomes alternativos do assunto para os certificados necessários para a topologia.</span><span class="sxs-lookup"><span data-stu-id="db42b-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="db42b-119">Relatório de firewall-o relatório de firewall lista as informações necessárias para configurar firewalls de perímetro na infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="db42b-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="db42b-120">Isso inclui os endereços IP (seja de valores padrão ou editados), função do servidor, IP e porta de origem, IP e porta de destino, protocolo de transporte, protocolo de aplicativo e notas relevantes.</span><span class="sxs-lookup"><span data-stu-id="db42b-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="db42b-121">Relatório DNS-o relatório DNS lista informações relevantes para as entradas de DNS que você deve criar.</span><span class="sxs-lookup"><span data-stu-id="db42b-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="db42b-122">Estão incluídos o tipo de registro, o FQDN, o endereço IP e os comentários necessários para a operação apropriada.</span><span class="sxs-lookup"><span data-stu-id="db42b-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="db42b-123">Resumo do site – o resumo do site apresenta uma visão geral das seleções que você fez respondendo às perguntas iniciais da entrevista ou preenchendo os valores em **sites de design**.</span><span class="sxs-lookup"><span data-stu-id="db42b-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="db42b-124">A informação de capacidade também é apresentada.</span><span class="sxs-lookup"><span data-stu-id="db42b-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db42b-125">As informações na página do Resumo do site são personalizadas para cada design e podem não conter todas as seções ou informações detalhadas aqui.</span><span class="sxs-lookup"><span data-stu-id="db42b-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="db42b-126">Editar o diagrama de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="db42b-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="db42b-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="db42b-127"></span></span>

<span data-ttu-id="db42b-128">A maior parte do trabalho que um designer faz na ferramenta de planejamento do Skype for Business Server 2015 consiste em definir as entradas dos endereços IP e dos FQDNs (nomes de domínio totalmente qualificados) para as entradas no diagrama de rede.</span><span class="sxs-lookup"><span data-stu-id="db42b-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="db42b-129">As informações inseridas nesta página são fornecidas nos relatórios e outras informações contidas na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="db42b-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Diagrama de rede da ferramenta de planejamento](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="db42b-131">A ferramenta de planejamento cria um diagrama de rede com o texto padrão para endereços IP e FQDNs.</span><span class="sxs-lookup"><span data-stu-id="db42b-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="db42b-132">Para editar os valores de entrada e diagrama de rede:</span><span class="sxs-lookup"><span data-stu-id="db42b-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="db42b-p110">Escolha uma seção da rede para começar o trabalho. Por exemplo, clique duas vezes no texto, \*\*rp01.contoso.net \*\*. Na caixa de diálogo que for aberta, digite o FQDN real do servidor access1.contoso.com e o endereço IP real, substituindo o 131.107.155.3.access1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="db42b-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="db42b-136">Clique em **OK** para salvar as entradas.</span><span class="sxs-lookup"><span data-stu-id="db42b-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="db42b-137">Continue a editar os endereços IP e os FQDNs, fornecendo endereços IP virtuais para balanceadores de carga de hardware ou entradas de servidor para balanceamento de carga do DNS (Sistema de Nome de Domínio) para servidores em pools.</span><span class="sxs-lookup"><span data-stu-id="db42b-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="db42b-p111">Um recurso útil da Ferramenta de Planejamento é que ela pode atribuir incrementalmente um intervalo de endereços IP e nomes de host do servidor, em vez de exigir que o designer edite cada servidor separado em um pool. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="db42b-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="db42b-p112">Clique duas vezes nos Servidores Front-End em pool. Quando a caixa de diálogo for aberta, selecione **Deseja usar os IPs e o FQDN como pontos de partida para todos os servidores equivalentes neste cluster?**.</span><span class="sxs-lookup"><span data-stu-id="db42b-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="db42b-142">Por exemplo, o valor inicial para o primeiro servidor é fe0101.contoso.com e um endereço IP de 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="db42b-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="db42b-143">Digite fe0.contoso.com em  \*\*FQDN do Servidor Front-End \*\*, digite 192.168.21.131 em \*\*Endereço IP do Servidor Front-End \*\* e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="db42b-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="db42b-144">O recurso de incremento automático atualiza todos os servidores no pool para fe01 até fe06 e todos os endereços IP de 192.168.21.131 até 136.</span><span class="sxs-lookup"><span data-stu-id="db42b-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="db42b-145">Após ter concluído todas as edições, salve a topologia completando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="db42b-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="db42b-146">Para salvar o design da ferramenta de planejamento, clique em **arquivo**e, em seguida, clique em **salvar topologia** ou **salvar topologia como**.</span><span class="sxs-lookup"><span data-stu-id="db42b-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="db42b-147">Se uma caixa de diálogo **Salvar Ferramenta de Planejamento como** for exibida, digite um nome para o arquivo em **Nome do arquivo** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="db42b-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="db42b-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="db42b-148">See also</span></span>
<span data-ttu-id="db42b-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="db42b-149"></span></span>

[<span data-ttu-id="db42b-150">Editing the Design</span><span class="sxs-lookup"><span data-stu-id="db42b-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
