---
title: Instalar a Ferramenta de Planejamento no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de começar a projetar e planejar sua infraestrutura do Skype for Business Server 2015 usando a Ferramenta de Planejamento do Skype for Business Server 2015, você deve primeiro instalar a Ferramenta de Planejamento. A Ferramenta de Planejamento não precisa ser implantada em uma estação de trabalho ou servidor que faz parte do domínio ou da infraestrutura em que você planeja instalar o Skype for Business Server 2015. O arquivo Readme que acompanha a Ferramenta de Planejamento detalha informações importantes sobre como instalar e usar a ferramenta. Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122375"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="8f933-106">Instalar a Ferramenta de Planejamento no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8f933-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="8f933-107">Antes de começar a projetar e planejar sua infraestrutura do Skype for Business Server 2015 usando a Ferramenta de Planejamento do Skype for Business Server 2015, você deve primeiro instalar a Ferramenta de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="8f933-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="8f933-108">A Ferramenta de Planejamento não precisa ser implantada em uma estação de trabalho ou servidor que faz parte do domínio ou da infraestrutura em que você planeja instalar o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8f933-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="8f933-109">O arquivo Readme que acompanha a Ferramenta de Planejamento detalha informações importantes sobre como instalar e usar a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="8f933-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="8f933-110">Algumas das informações no arquivo Leiame estão reproduzidas aqui para esclarecimento.</span><span class="sxs-lookup"><span data-stu-id="8f933-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f933-111">A Ferramenta de Planejamento exige a instalação por um usuário com direitos e permissões de administrador no computador no qual a ferramenta deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="8f933-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="8f933-112">Os sistemas operacionais com suporte para instalação e operação da Ferramenta de Planejamento são:</span><span class="sxs-lookup"><span data-stu-id="8f933-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="8f933-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8f933-113">Windows 10</span></span>

- <span data-ttu-id="8f933-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="8f933-114">Windows 8</span></span>

- <span data-ttu-id="8f933-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8f933-115">Windows 8.1</span></span>

- <span data-ttu-id="8f933-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8f933-116">Windows Server 2012</span></span>

- <span data-ttu-id="8f933-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8f933-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="8f933-118">Windows 7, edição de 32 bits</span><span class="sxs-lookup"><span data-stu-id="8f933-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="8f933-119">Windows 7, edição de 64 bits usando Windows no Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="8f933-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="8f933-120">Windows Server 2008 R2, usando WOW</span><span class="sxs-lookup"><span data-stu-id="8f933-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="8f933-121">Além disso, a Ferramenta de Planejamento requer o Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="8f933-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="8f933-122">Depois que os requisitos de pré-instalação são atendidos, você pode instalar a Ferramenta de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="8f933-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="8f933-123">Para instalar a Ferramenta de Planejamento</span><span class="sxs-lookup"><span data-stu-id="8f933-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="8f933-124">Faça logoff no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="8f933-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="8f933-125">Usando o Windows Explorer ou uma janela de comando, localize o diretório onde você baixou os arquivos de instalação da Ferramenta de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="8f933-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="8f933-126">Localize o SkypeForBusinessPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="8f933-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="8f933-127">No Windows Explorer, clique duas vezes no arquivo.</span><span class="sxs-lookup"><span data-stu-id="8f933-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="8f933-128">Na janela de comando, digite o nome do arquivo e pressione **Enter** para executar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="8f933-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="8f933-129">Na página De boas-vindas do **Skype for Business Server 2015, Assistente** de Instalação da Ferramenta de Planejamento, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="8f933-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="8f933-130">Revise o **Contrato de Licença de Usuário Final**, selecione **Aceito os termos do Contrato de Licença** se você escolher aceitar os termos de uso do contrato de licença e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f933-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="8f933-131">Escolha onde instalar os arquivos da Ferramenta de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="8f933-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="8f933-132">O local padrão é C:\Arquivos de Programas (x86)\Skype for Business Server 2015\Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="8f933-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="8f933-133">Se você quiser alterar o local de instalação, clique em **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="8f933-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="8f933-134">Em **Alterar pasta de destino**, procure ou digite o local para instalar os arquivos, clique em **OK** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f933-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="8f933-135">O instalador agora está pronto para instalar a Ferramenta de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="8f933-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="8f933-136">Clique em **Instalar** para começar o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="8f933-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="8f933-137">A instalação será iniciada e o andamento será exibido.</span><span class="sxs-lookup"><span data-stu-id="8f933-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="8f933-138">Após a conclusão da instalação, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="8f933-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="8f933-139">A Ferramenta de Planejamento está pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="8f933-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="8f933-140">Software opcional</span><span class="sxs-lookup"><span data-stu-id="8f933-140">Optional Software</span></span>
<span data-ttu-id="8f933-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="8f933-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="8f933-142">A Ferramenta de Planejamento do Skype for Business Server 2015 foi projetada para exportar para o Microsoft Excel e o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="8f933-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="8f933-143">Embora esses aplicativos não sejam necessários para a operação da Ferramenta de Planejamento, eles adicionam valor significativo à implantação e documentação do seu design.</span><span class="sxs-lookup"><span data-stu-id="8f933-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="8f933-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8f933-144">Microsoft Excel</span></span>

<span data-ttu-id="8f933-145">Exportar seu design para o Microsoft Excel cria um relatório que exibe sete guias na planilha:</span><span class="sxs-lookup"><span data-stu-id="8f933-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="8f933-146">Resumo - Exibe informações sobre a configuração do site, incluindo contagem de usuários, configurações de capacidade e informações de perfil de servidor.</span><span class="sxs-lookup"><span data-stu-id="8f933-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="8f933-147">Perfil de Hardware - Exibe um relatório sobre as configurações de hardware recomendadas para servidores especificados na topologia, incluindo CPU, memória, disco e interface de rede.</span><span class="sxs-lookup"><span data-stu-id="8f933-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="8f933-148">A quantidade e as especificações recomendadas para os componentes do servidor também estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="8f933-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="8f933-149">Além disso, cada servidor é definido pelo site para fornecer uma representação completa dos requisitos do servidor por site.</span><span class="sxs-lookup"><span data-stu-id="8f933-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="8f933-150">Requisitos de portas - exibe um relatório de todas as portas habilitadas e a associação ao balanceamento de carga do Sistema de Nomes de Domínio (DNS LB) e balanceadores de carga de hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="8f933-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="8f933-151">Você deve usar esse relatório para planejar as configurações de firewall e DNS LB e HLB.</span><span class="sxs-lookup"><span data-stu-id="8f933-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="8f933-152">Relatório de Resumo - Exibe o resumo geral das configurações necessárias para configurar sua rede do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="8f933-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="8f933-153">Relatório de Certificados - Exibe o nome do assunto e os nomes alternativos de assunto necessários para os certificados necessários para que os Servidores de Borda sejam executados.</span><span class="sxs-lookup"><span data-stu-id="8f933-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="8f933-154">Relatório de Firewall - Exibe as portas de origem e destino e endereços IP para interfaces externas e internas.</span><span class="sxs-lookup"><span data-stu-id="8f933-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="8f933-155">Relatório DNS - Exibe o FQDN (nome de domínio totalmente qualificado) e endereços IP/VIP necessários para cada entrada DNS criada.</span><span class="sxs-lookup"><span data-stu-id="8f933-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="8f933-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="8f933-156">Microsoft Visio</span></span>

<span data-ttu-id="8f933-p110">Exportar seu design para o Microsoft Visio cria um diagrama para ser usado com seus objetivos de documentação de sua topologia e infraestrutura configuradas. O diagrama importado pode ser editado e reorganizado a fim de atender às suas necessidades de documentação. O diagrama típico do Visio incluirá:</span><span class="sxs-lookup"><span data-stu-id="8f933-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="8f933-160">Se seu design for grande o suficiente para exigir mais de três Servidores Front-End, uma página adicional será criada para o pool de Front-End, Servidores Front-End, o computador que executa SQL Server, endereços IP e FQDNs.</span><span class="sxs-lookup"><span data-stu-id="8f933-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="8f933-161">Topologia Global - Diagrama de sites configurados do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8f933-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="8f933-162">Guia Nome do Site - Exibe a topologia de configuração do site com Servidor de Borda, firewall, PSTN (rede telefônica pública comutado) com gateways e a implantação interna do servidor.</span><span class="sxs-lookup"><span data-stu-id="8f933-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="8f933-163">A implantação interna consiste em servidores e pools configurados, incluindo os pools de Front-End, servidores baseados em SQL Server, Serviços de Domínio do Active Directory, Diretores, servidores de Unificação de Mensagens do Exchange (UM), Servidores de Caixa de Correio do Exchange, Servidores do Office Web Apps, Servidores de Mediação e Servidores de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="8f933-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="8f933-164">Diagrama de Rede de Borda - Diagrama detalhando a configuração do Servidor de Borda com endereços IP e FQDNs associados.</span><span class="sxs-lookup"><span data-stu-id="8f933-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="8f933-165">Balanceamento de carga de DNS e balanceadores de carga de hardware também estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="8f933-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="8f933-166">Além disso, os Diretores e o Servidor front-end ou pool de front-end são exibidos, com DNS LB ou HLB associado e o endereço IP atribuído (a Ferramenta de Planejamento dá suporte a endereços IPv4 e IPv6) e FQDN.</span><span class="sxs-lookup"><span data-stu-id="8f933-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f933-167">Confira também</span><span class="sxs-lookup"><span data-stu-id="8f933-167">See also</span></span>
<span data-ttu-id="8f933-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="8f933-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="8f933-169">Instalando a ferramenta de planejamento</span><span class="sxs-lookup"><span data-stu-id="8f933-169">Installing the Planning Tool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)