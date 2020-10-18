---
title: Documentação das ferramentas do kit de recursos do Lync Server 2013
description: Documentação das ferramentas do kit de recursos do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6866e04615014daa7e93f7e7f1081b10325d087d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573557"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="42b4a-103">Documentação das ferramentas do kit de recursos do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b4a-103">Lync Server 2013 Resource Kit Tools Documentation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42b4a-104">_**Última modificação do tópico:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="42b4a-104">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="42b4a-105">Este tópico descreve as ferramentas que fazem parte do Lync Server 2013 Resource Kit, incluindo o propósito de cada ferramenta e exemplos de uso. O Lync Server 2013, ferramentas do kit de recursos ajudam a tornar tarefas rotineiras mais fáceis para os administradores de ti que implantam e gerenciam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-105">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="42b4a-106">Por exemplo, a ferramenta **Web conf data** pode ser usada para controlar facilmente os dados que são carregados pelos usuários durante uma reunião online.</span><span class="sxs-lookup"><span data-stu-id="42b4a-106">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="42b4a-107">A ferramenta **SEFAUtil** pode ser usada para configurar o encaminhamento de chamadas de representante e a resposta para usuários.</span><span class="sxs-lookup"><span data-stu-id="42b4a-107">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="42b4a-108">Incentivamos os administradores de ti a usar essas ferramentas para gerenciar com mais eficiência o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-108">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="42b4a-109">Instalação das ferramentas do kit de recursos</span><span class="sxs-lookup"><span data-stu-id="42b4a-109">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="42b4a-110">Para instalar o Lync Server 2013, ferramentas do kit de recursos, **OCSReskit.msi**de download.</span><span class="sxs-lookup"><span data-stu-id="42b4a-110">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="42b4a-111">Você pode baixar o instalador de ferramentas do kit de recursos do centro de download em [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .</span><span class="sxs-lookup"><span data-stu-id="42b4a-111">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="42b4a-112">Execute **OCSResKit.msi** para fazer uma instalação simples.</span><span class="sxs-lookup"><span data-stu-id="42b4a-112">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="42b4a-113">O. msi instala todas as ferramentas no seguinte caminho: **% Program Files% \\ Microsoft Lync Server 2013 \\ reskit**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-113">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="42b4a-114">As ferramentas que são executáveis independentes estão nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-114">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="42b4a-115">As ferramentas que também têm arquivos estão em suas próprias subpastas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-115">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="42b4a-116">Ambientes com suporte</span><span class="sxs-lookup"><span data-stu-id="42b4a-116">Supported Environments</span></span>

<span data-ttu-id="42b4a-117">Para obter o desempenho ideal, o Lync Server 2013, ferramentas do Resource Kit devem ser instalados no mesmo ambiente e com as mesmas especificações necessárias para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="42b4a-118">Visão geral das ferramentas do kit de recursos</span><span class="sxs-lookup"><span data-stu-id="42b4a-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="42b4a-119">A lista a seguir descreve as ferramentas fornecidas no Lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="42b4a-119">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="42b4a-120">Uma descrição de cada ferramenta, incluindo os requisitos e o uso de exemplo, é abordada na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="42b4a-120">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="42b4a-121">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="42b4a-121">ABSConfig</span></span>

  - <span data-ttu-id="42b4a-122">Monitor de serviço de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-122">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="42b4a-123">Analisador de utilização de largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-123">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="42b4a-124">Chamar estacionador chamadas</span><span class="sxs-lookup"><span data-stu-id="42b4a-124">Call Parkometer</span></span>

  - <span data-ttu-id="42b4a-125">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="42b4a-125">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="42b4a-126">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="42b4a-126">DBAnalyze</span></span>

  - <span data-ttu-id="42b4a-127">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="42b4a-127">ImportStorageServiceData</span></span>

  - <span data-ttu-id="42b4a-128">LCSSync</span><span class="sxs-lookup"><span data-stu-id="42b4a-128">LCSSync</span></span>

  - <span data-ttu-id="42b4a-129">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="42b4a-129">LookupUserConsole</span></span>

  - <span data-ttu-id="42b4a-130">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="42b4a-130">MsTurnPing</span></span>

  - <span data-ttu-id="42b4a-131">Visualizador de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-131">Network Configuration Viewer</span></span>

  - <span data-ttu-id="42b4a-132">Agente de grupo de resposta Live</span><span class="sxs-lookup"><span data-stu-id="42b4a-132">Response Group Agent Live</span></span>

  - <span data-ttu-id="42b4a-133">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="42b4a-133">SEFAUtil</span></span>

  - <span data-ttu-id="42b4a-134">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="42b4a-134">SYSPrep.ps1</span></span>

  - <span data-ttu-id="42b4a-135">Migração de comunicados de número não atribuído</span><span class="sxs-lookup"><span data-stu-id="42b4a-135">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="42b4a-136">Dados de conferência da Web</span><span class="sxs-lookup"><span data-stu-id="42b4a-136">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="42b4a-137">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="42b4a-137">ABSConfig</span></span>

<span data-ttu-id="42b4a-138">A ferramenta de configuração do serviço de catálogo de endereços (ABSConfig) é uma ferramenta administrativa que ajuda os administradores a personalizar a configuração do serviço de catálogo de endereços no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-138">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="42b4a-139">Essa ferramenta também permite que os administradores do Lync Server 2013 restaurem as configurações padrão do serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="42b4a-139">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-140">Description</span></span>

<span data-ttu-id="42b4a-141">O ABSConfig é um aplicativo de interface gráfica do usuário que permite que os administradores configurem atributos de serviços de domínio do Active Directory relacionados ao serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="42b4a-141">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="42b4a-142">Os principais cenários da ferramenta são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="42b4a-142">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="42b4a-143">Para permitir que os administradores mapeiem atributos nos serviços de domínio do Active Directory para os atributos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-143">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="42b4a-144">Para permitir que os administradores especifiquem o atributo de serviços de domínio Active Directory a ser incluído ou excluído nos arquivos de serviço do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="42b4a-144">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="42b4a-145">Para permitir que os administradores restaurem as configurações padrão do serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="42b4a-145">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="42b4a-146">A ferramenta ABSConfig pode ser iniciada usando o arquivo absConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="42b4a-146">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="42b4a-147">A ferramenta é aberta para a guia **Configurar atributos** . Esta tabela tem opções para mapear atributos de serviços de domínio do Active Directory para os campos de atributo do Lync Server 2013 e especificar quais usuários serão incluídos ou excluídos nos arquivos de serviço de catálogo de endereços com base em filtros de atributo específicos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-147">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="42b4a-148">Também tem opções para personalizar o valor do número de telefone a ser incluído no arquivo do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="42b4a-148">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="42b4a-149">A opção **Restaurar padrões** permite que os administradores restaurem os valores padrão das configurações do serviço de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="42b4a-149">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="42b4a-150">Alterações do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="42b4a-150">Changes from Lync Server 2010</span></span>

<span data-ttu-id="42b4a-151">Na ferramenta de configuração de ABS do Lync Server 2013, os atributos (linhas) podem ser removidos desmarcando a caixa de seleção "habilitar" para o atributo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-151">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="42b4a-152">Isso tem o mesmo efeito que excluir a linha no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="42b4a-152">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-153">A caixa de seleção Habilitar está na coluna extrema direita; Talvez seja necessário rolar para a direita para ver a coluna</span><span class="sxs-lookup"><span data-stu-id="42b4a-153">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-154">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-154">Output</span></span>

<span data-ttu-id="42b4a-155">ABSConfig armazena a configuração do serviço de catálogo de endereços no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-156">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-156">Purpose</span></span>

<span data-ttu-id="42b4a-157">O ABSConfig fornece uma maneira rápida e fácil de personalizar o serviço de catálogo de endereços do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-157">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-158">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="42b4a-159">Computador</span><span class="sxs-lookup"><span data-stu-id="42b4a-159">Computer</span></span>

<span data-ttu-id="42b4a-160">O ABSConfig pode ser executado apenas de um computador associado ao domínio que tenha o Lync Server 2013 instalado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-160">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="42b4a-161">No caso do Lync Server 2013, Enterprise Edition, essa ferramenta pode ser executada em qualquer servidor front-end que tenha o serviço de catálogo de endereços habilitado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="42b4a-161">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="42b4a-162">Rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-162">Network</span></span>

<span data-ttu-id="42b4a-163">O computador deve poder se conectar ao pool de front-ends e ao banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="42b4a-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="42b4a-164">Software</span><span class="sxs-lookup"><span data-stu-id="42b4a-164">Software</span></span>

<span data-ttu-id="42b4a-165">Os seguintes componentes de software devem ser instalados antes de executar a ferramenta ABSConfig:</span><span class="sxs-lookup"><span data-stu-id="42b4a-165">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="42b4a-166">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b4a-166">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="42b4a-167">Usuários</span><span class="sxs-lookup"><span data-stu-id="42b4a-167">Users</span></span>

<span data-ttu-id="42b4a-168">Administradores que têm as permissões necessárias para atualizar a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-168">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-169">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-169">Examples</span></span>

<span data-ttu-id="42b4a-170">O ABSConfig pode ser iniciado digitando **ABSConfig.exe** em um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="42b4a-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="42b4a-171">Mostrado abaixo é a interface do usuário da ferramenta ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="42b4a-171">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="42b4a-172">![A ferramenta ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "A ferramenta ABSConfig.exe.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-172">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-173">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-173">Summary</span></span>

<span data-ttu-id="42b4a-174">A ferramenta ABSConfig fornece aos administradores uma ferramenta rápida e fácil de usar para personalizar o serviço de catálogo de endereços do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="42b4a-175">Monitor de serviço de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-175">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="42b4a-176">A ferramenta Monitor de serviço de política de largura de banda destina-se a permitir que os administradores exibam uma lista dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="42b4a-176">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="42b4a-177">Todos os serviços de política de largura de banda do Lync Server 2013 (autenticação e núcleo) configurados na topologia</span><span class="sxs-lookup"><span data-stu-id="42b4a-177">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="42b4a-178">As conexões que cada serviço faz para outros serviços de política de largura de banda e para os servidores de borda</span><span class="sxs-lookup"><span data-stu-id="42b4a-178">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="42b4a-179">Todos os links que são configurados no documento de configuração de rede e uso de largura de banda em tempo real conforme relatado por cada um dos serviços de política de largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-179">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-180">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-180">Description</span></span>

<span data-ttu-id="42b4a-181">A ferramenta Monitor de serviço de política de largura de banda é implementada como um aplicativo baseado em GUI.</span><span class="sxs-lookup"><span data-stu-id="42b4a-181">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="42b4a-182">Os administradores iniciam a ferramenta executando o PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="42b4a-182">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="42b4a-183">Quando a ferramenta é iniciada, tenta descobrir a lista de serviços de política de largura de banda na topologia.</span><span class="sxs-lookup"><span data-stu-id="42b4a-183">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="42b4a-184">Depois que a atualização inicial for concluída, o painel à esquerda da janela será preenchido com uma lista de serviços que são agrupados pelos clusters aos quais pertencem.</span><span class="sxs-lookup"><span data-stu-id="42b4a-184">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="42b4a-185">Quando os administradores selecionam um serviço de política de largura de banda específico, o painel à direita exibe as informações sobre esse serviço específico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-185">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="42b4a-186">Esse painel também tem duas guias principais que exibem informações.</span><span class="sxs-lookup"><span data-stu-id="42b4a-186">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="42b4a-187">Guia informações do computador</span><span class="sxs-lookup"><span data-stu-id="42b4a-187">Machine Info Tab</span></span>

<span data-ttu-id="42b4a-188">A guia **informações do computador** mostra os detalhes do serviço de política de largura de banda selecionado e a lista e o estado de todas as conexões feitas pelo serviço de política de largura de banda selecionado para outros serviços.</span><span class="sxs-lookup"><span data-stu-id="42b4a-188">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="42b4a-189">Guia informações de topologia</span><span class="sxs-lookup"><span data-stu-id="42b4a-189">Topology Info Tab</span></span>

<span data-ttu-id="42b4a-190">A guia **informações da topologia** mostra uma lista de todos os links que são configurados nas definições de configuração da rede.</span><span class="sxs-lookup"><span data-stu-id="42b4a-190">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="42b4a-191">Para cada link, a capacidade de largura de banda de áudio e vídeo é exibida.</span><span class="sxs-lookup"><span data-stu-id="42b4a-191">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="42b4a-192">Além disso, a largura de banda atualmente utilizada é exibida, tanto em Kbps quanto como uma porcentagem da capacidade.</span><span class="sxs-lookup"><span data-stu-id="42b4a-192">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="42b4a-193">A ferramenta usa codificação de cores para realçar os links que têm utilização próxima à capacidade, permitindo que os administradores isolem rapidamente esses links.</span><span class="sxs-lookup"><span data-stu-id="42b4a-193">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-194">Se a ferramenta de monitoração do serviço de política de largura de banda apresentar falha ao se conectar a qualquer um dos serviços de política de largura de banda configurados, as informações nas guias informações sobre a <STRONG>máquina</STRONG> e <STRONG>informações de topologia</STRONG> não serão preenchidas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-194">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="42b4a-195">No entanto, é possível que a ferramenta possa se conectar inicialmente, mas, em seguida, perder a conexão com o serviço.</span><span class="sxs-lookup"><span data-stu-id="42b4a-195">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="42b4a-196">Nesses casos, os administradores podem ver informações desatualizadas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-196">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="42b4a-197">Há um carimbo de data/hora <STRONG>atualizado</STRONG> em cada uma das guias que podem permitir que os administradores vejam quando os dados foram atualizados pela última vez para um serviço de política de largura de banda específico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-197">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-198">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-198">Output</span></span>

<span data-ttu-id="42b4a-199">Não há nenhuma saída de linha de comando; a saída do programa está contida na GUI (interface gráfica do usuário) principal.</span><span class="sxs-lookup"><span data-stu-id="42b4a-199">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-200">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-200">Purpose</span></span>

<span data-ttu-id="42b4a-201">O objetivo da ferramenta Monitor de serviço de política de largura de banda é permitir a visibilidade dos administradores no estado de cada um dos serviços de política de largura de banda definidos na topologia.</span><span class="sxs-lookup"><span data-stu-id="42b4a-201">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="42b4a-202">Além disso, os administradores podem ver o uso da largura de banda em tempo real para todos os links definidos no documento de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="42b4a-202">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-203">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-203">Requirements</span></span>

<span data-ttu-id="42b4a-204">A ferramenta Monitor de serviço de política de largura de banda precisa ser executada em um computador que faça parte da topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42b4a-204">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-205">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-205">Summary</span></span>

<span data-ttu-id="42b4a-206">A ferramenta Monitor de serviço de política de largura de banda pode ser um recurso valioso para os administradores para que eles possam inspecionar o estado de todos os serviços de política de largura de banda na topologia, e o mais importante: eles podem obter a utilização de largura de banda em tempo real para os links definidos nas definições de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="42b4a-206">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="42b4a-207">Analisador de utilização de largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-207">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="42b4a-208">O analisador de utilização de largura de banda é uma ferramenta que cria relatórios sobre vários modos de exibição de consumo de largura de banda pelos pontos de extremidade UC nos links WAN na rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="42b4a-208">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="42b4a-209">Esses relatórios podem ser usados para entender o padrão atual de consumo de largura de banda e para ajudar no planejamento da capacidade de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="42b4a-209">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-210">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-210">Description</span></span>

<span data-ttu-id="42b4a-211">O analisador de utilização de largura de banda é implementado como um aplicativo baseado em GUI.</span><span class="sxs-lookup"><span data-stu-id="42b4a-211">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="42b4a-212">Essa ferramenta gera relatórios específicos para a utilização de áudio na rede e ajuda no planejamento da capacidade.</span><span class="sxs-lookup"><span data-stu-id="42b4a-212">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="42b4a-213">Ele também itera na capacidade de largura de banda atribuída a vários links.</span><span class="sxs-lookup"><span data-stu-id="42b4a-213">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-214">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-214">Output</span></span>

<span data-ttu-id="42b4a-215">O analisador de utilização de largura de banda oferece plotagens em formato gráfico Al de capacidade de largura de banda e utilização de áudio para todos os links WAN que são configurados no sistema.</span><span class="sxs-lookup"><span data-stu-id="42b4a-215">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-216">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-216">Purpose</span></span>

<span data-ttu-id="42b4a-217">Em qualquer implantação de voz e vídeo, é fundamental monitorar e entender a tendência da utilização de largura de banda de tráfego de mídia na rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="42b4a-217">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="42b4a-218">A ferramenta Analisador de utilização da largura de banda permite que um administrador realize apenas isso.</span><span class="sxs-lookup"><span data-stu-id="42b4a-218">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="42b4a-219">Esta ferramenta faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="42b4a-219">This tool does the following:</span></span>

  - <span data-ttu-id="42b4a-220">Gera relatórios específicos para a utilização de áudio na rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-220">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="42b4a-221">Ajuda no planejamento de capacidade mais eficaz e na iteração na capacidade de largura de banda atribuída a vários links</span><span class="sxs-lookup"><span data-stu-id="42b4a-221">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="42b4a-222">O analisador de utilização de largura de banda pode gerar gráficos de capacidade de largura de banda e relatórios de utilização; Eles são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="42b4a-222">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="42b4a-223">Todos os links WAN na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="42b4a-223">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="42b4a-224">Filtrado por links WAN selecionados que foram escolhidos</span><span class="sxs-lookup"><span data-stu-id="42b4a-224">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="42b4a-225">Filtrado por links WAN que excederam a capacidade de link</span><span class="sxs-lookup"><span data-stu-id="42b4a-225">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="42b4a-226">Filtrado por links WAN que estão subutilizando a largura de banda provisionada</span><span class="sxs-lookup"><span data-stu-id="42b4a-226">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="42b4a-227">Filtrar por links WAN que atingiram níveis críticos (uma utilização de largura de banda maior que 90% da capacidade de largura de banda do link WAN)</span><span class="sxs-lookup"><span data-stu-id="42b4a-227">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="42b4a-228">Filtrado por tipo de link WAN — links de site de rede, links entre regiões e links em um site</span><span class="sxs-lookup"><span data-stu-id="42b4a-228">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="42b4a-229">Filtrado por região de rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-229">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="42b4a-230">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="42b4a-230">Applications</span></span>

<span data-ttu-id="42b4a-231">O analisador de utilização da largura de banda tem os dois aplicativos a seguir (ferramentas):</span><span class="sxs-lookup"><span data-stu-id="42b4a-231">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="42b4a-232">**WanLinkLogCollector.exe**     Esta ferramenta permite que o usuário insira as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="42b4a-232">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="42b4a-233">**BandwidthUtilizationAnalyzer.xlsm**    Um relatório de software de planilha do Microsoft Excel é iniciado automaticamente pelo WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="42b4a-233">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="42b4a-234">Este aplicativo permite que o usuário Aplique filtros ao relatório, conforme mostrado posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-234">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="42b4a-235">Fases de uso do analisador de utilização de largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-235">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="42b4a-236">Há duas fases ao usar o analisador de utilização da largura de banda:</span><span class="sxs-lookup"><span data-stu-id="42b4a-236">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="42b4a-237">Coletar logs, que é executado usando o WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="42b4a-237">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="42b4a-238">Personalizar relatórios, que é executado usando BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="42b4a-238">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="42b4a-239">É altamente recomendável que BandwidthUtilizationAnalyzer.xlsm não seja iniciado manualmente por usuários finais.</span><span class="sxs-lookup"><span data-stu-id="42b4a-239">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="42b4a-240">Iniciando analisador de utilização da largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-240">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="42b4a-241">Inicie WanLinkLogCollector.exe no prompt de comando ou usando o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="42b4a-241">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="42b4a-242">**Usando WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="42b4a-242">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="42b4a-243">Há três etapas para usar WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="42b4a-243">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="42b4a-244">**Registrar a linha do tempo**     Forneça a linha do tempo para a qual o relatório precisa ser gerado</span><span class="sxs-lookup"><span data-stu-id="42b4a-244">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="42b4a-245">**Especificar os diretórios**     de arquivos Fornecer informações de local de arquivo</span><span class="sxs-lookup"><span data-stu-id="42b4a-245">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="42b4a-246">**Coletar os logs e iniciar o visualizador**    de relatórios Executar o comando para gerar o relatório</span><span class="sxs-lookup"><span data-stu-id="42b4a-246">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="42b4a-247">Etapa 1-registrar a linha do tempo</span><span class="sxs-lookup"><span data-stu-id="42b4a-247">Step 1 - Log the timeline</span></span>

<span data-ttu-id="42b4a-248">O registro da linha do tempo permite que o usuário da ferramenta especifique o seguinte, conforme mostrado na figura abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-248">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="42b4a-249">**Data de início** Esta é a data de início da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 1º de agosto de 2010.</span><span class="sxs-lookup"><span data-stu-id="42b4a-249">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="42b4a-250">**Data de término** Esta é a data de término da linha do tempo para a qual o relatório deve ser gerado; por exemplo, 30 de setembro de 2010.</span><span class="sxs-lookup"><span data-stu-id="42b4a-250">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="42b4a-251">![Datas de início e de término na utilização de largura de banda](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Datas de início e de término na utilização de largura de banda")</span><span class="sxs-lookup"><span data-stu-id="42b4a-251">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="42b4a-252">Etapa 2-especificar os diretórios de arquivo</span><span class="sxs-lookup"><span data-stu-id="42b4a-252">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="42b4a-253">Os seguintes diretórios de arquivos podem ser especificados pelo usuário, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-253">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="42b4a-254">**Local dos arquivos de log do servidor** O local da pasta onde os logs do servidor de política de largura de banda estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-254">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="42b4a-255">Em geral, isso ocorre no \<fileserver\> \\ \<choice of FE\> \\ AppServerFiles \\ PDP.</span><span class="sxs-lookup"><span data-stu-id="42b4a-255">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="42b4a-256">**Local de armazenamento de arquivos temporários** O local do arquivo temporário onde os arquivos intermediários são armazenados enquanto o relatório está sendo gerado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-256">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="42b4a-257">![Diretórios de arquivos no análise de utilização da largura de banda](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Diretórios de arquivos no análise de utilização da largura de banda")</span><span class="sxs-lookup"><span data-stu-id="42b4a-257">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-258">Certifique-se de que o acesso de arquivo suficiente aos logs de servidor e à pasta de repositório de arquivos temporários seja fornecido para o usuário da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-258">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="42b4a-259">Etapa 3: coletar os logs e iniciar o Visualizador de relatórios</span><span class="sxs-lookup"><span data-stu-id="42b4a-259">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="42b4a-260">Para coletar os logs e iniciar o Visualizador de relatórios, clique em **executar** , conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-260">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="42b4a-261">Esta etapa coleta os dados necessários.</span><span class="sxs-lookup"><span data-stu-id="42b4a-261">This step collects the required data.</span></span>

<span data-ttu-id="42b4a-262">![Coletando dados na análise de utilização da largura de banda](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Coletando dados na análise de utilização da largura de banda")</span><span class="sxs-lookup"><span data-stu-id="42b4a-262">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="42b4a-263">Quando a validação de entrada for bem-sucedida, a mensagem mostrada abaixo será exibida.</span><span class="sxs-lookup"><span data-stu-id="42b4a-263">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="42b4a-264">![Registra a notificação coletada no utilitário de largura de banda](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Registra a notificação coletada no utilitário de largura de banda")</span><span class="sxs-lookup"><span data-stu-id="42b4a-264">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="42b4a-265">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-265">Click **OK**.</span></span> <span data-ttu-id="42b4a-266">BandwidthUtilizationAnalyzer.xlsm é iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-266">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="42b4a-267">Siga as instruções na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="42b4a-267">Follow the instructions in the message box.</span></span> <span data-ttu-id="42b4a-268">Para obter detalhes, consulte **usando BandwidthUtilizationAnalyzer.xlsm** na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="42b4a-268">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="42b4a-269">**Usando BandwidthUtilizationAnalyzer.xlsm**</span><span class="sxs-lookup"><span data-stu-id="42b4a-269">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="42b4a-270">Quando BandwidthUtilizationAnalyzer.xlsm for iniciado automaticamente, clique em **Atualizar** , conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-270">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="42b4a-271">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="42b4a-271">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="42b4a-272">Quando uma pasta de arquivos for aberta, selecione consolidated.csv do local especificado na caixa de mensagem, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-272">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="42b4a-273">Também mostra o local como **C: \\ Temp**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-273">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="42b4a-274">![Abrir uma pasta no BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Abrir uma pasta no BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-274">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="42b4a-275">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-275">Click **Import**.</span></span>

4.  <span data-ttu-id="42b4a-276">A plotagem gráfica é gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-276">The graphical plot is automatically generated.</span></span> <span data-ttu-id="42b4a-277">Ela estará disponível quando o ponteiro de trabalho em segundo plano desaparecer.</span><span class="sxs-lookup"><span data-stu-id="42b4a-277">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="42b4a-278">![Aplicando filtros no modo de exibição de relatório.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicando filtros no modo de exibição de relatório.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-278">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="42b4a-279">Aplicando filtros ao modo de exibição de relatório</span><span class="sxs-lookup"><span data-stu-id="42b4a-279">Applying Filters to the Report View</span></span>

<span data-ttu-id="42b4a-280">Os filtros que podem ser aplicados ao modo de exibição de relatório, conforme mostrado abaixo, são descritos a seguir:</span><span class="sxs-lookup"><span data-stu-id="42b4a-280">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="42b4a-281">![Aplicando filtros no modo de exibição de relatório.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Aplicando filtros no modo de exibição de relatório.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-281">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="42b4a-282">**Nome** Filtrar por links WAN (o filtro está no lado direito do gráfico). O prefixo indica os seguintes tipos de link; Confira a caixa vertical (azul):</span><span class="sxs-lookup"><span data-stu-id="42b4a-282">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="42b4a-283">**S site** O link WAN de um site de rede para uma região de rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-283">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="42b4a-284">**É entre sites** O link WAN entre dois sites de rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-284">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="42b4a-285">**R inter-Region** O link WAN entre duas regiões de rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-285">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="42b4a-286">**Limite excedido** Filtrar por links WAN cuja utilização de largura de banda é maior do que a capacidade de largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-286">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="42b4a-287">**Níveis críticos** Filtrar por links WAN cuja utilização da largura de banda alcançou 90% ou mais da capacidade da largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-287">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="42b4a-288">**Subutilizado** Filtrar por links WAN cuja utilização da largura de banda tenha sido inferior a 25% da capacidade da largura de banda</span><span class="sxs-lookup"><span data-stu-id="42b4a-288">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="42b4a-289">**Tipo de link** Filtrar pelos seguintes tipos de links de WAN:</span><span class="sxs-lookup"><span data-stu-id="42b4a-289">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="42b4a-290">Tipo de **site de rede**</span><span class="sxs-lookup"><span data-stu-id="42b4a-290">**Network site** type</span></span>
    
      - <span data-ttu-id="42b4a-291">Tipo **entre sites**</span><span class="sxs-lookup"><span data-stu-id="42b4a-291">**Inter-site** type</span></span>
    
      - <span data-ttu-id="42b4a-292">Tipo **de link entre regiões**</span><span class="sxs-lookup"><span data-stu-id="42b4a-292">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="42b4a-293">**Região** Filtrar por região de rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-293">**Region** Filter by network region</span></span>

<span data-ttu-id="42b4a-294">As figuras a seguir mostram os filtros descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-294">The following figures show the previously described filters.</span></span>

<span data-ttu-id="42b4a-295">Filtrar por **nome**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-295">Filter by **Name**.</span></span> <span data-ttu-id="42b4a-296">Selecione a lista de links que precisam ser exibidos no gráfico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-296">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="42b4a-297">![Filtragem por nome no BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtragem por nome no BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-297">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="42b4a-298">Filtrar por **limite excedido**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-298">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="42b4a-299">Selecione **verdadeiro** para impor o filtro.</span><span class="sxs-lookup"><span data-stu-id="42b4a-299">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="42b4a-300">![Filtragem por limite excedido.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtragem por limite excedido.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-300">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="42b4a-301">Filtrar por **níveis críticos**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-301">Filter by **Critical levels**.</span></span> <span data-ttu-id="42b4a-302">Selecione **verdadeiro** para impor o filtro.</span><span class="sxs-lookup"><span data-stu-id="42b4a-302">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="42b4a-303">![Filtragem por níveis críticos.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtragem por níveis críticos.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-303">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="42b4a-304">Filtrar por **subutilizado**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-304">Filter by **Under utilized**.</span></span> <span data-ttu-id="42b4a-305">Selecione **verdadeiro** para impor o filtro.</span><span class="sxs-lookup"><span data-stu-id="42b4a-305">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="42b4a-306">![Filtragem por subutilizado.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtragem por subutilizado.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-306">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="42b4a-307">Filtrar por **tipo de link**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-307">Filter by **Link Type**.</span></span> <span data-ttu-id="42b4a-308">Selecione o tipo ou tipos que precisam ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-308">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="42b4a-309">![Filtragem por tipo de link.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtragem por tipo de link.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-309">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="42b4a-310">Filtrar por **região**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-310">Filter by **Region**.</span></span> <span data-ttu-id="42b4a-311">Selecione uma lista de regiões cujos vínculos precisam ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-311">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="42b4a-312">![Filtragem por região.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtragem por região.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-312">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-313">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-313">Requirements</span></span>

  - <span data-ttu-id="42b4a-314">O .NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="42b4a-314">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="42b4a-315">Microsoft Excel 2010 ou Excel 2007</span><span class="sxs-lookup"><span data-stu-id="42b4a-315">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-316">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-316">Summary</span></span>

<span data-ttu-id="42b4a-317">O analisador de utilização de largura de banda é usado para plotar a utilização de largura de banda de áudio para tráfego UC na rede.</span><span class="sxs-lookup"><span data-stu-id="42b4a-317">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="42b4a-318">Essa ferramenta também pode ser usada para relatar a utilização da largura de banda de vídeo na rede.</span><span class="sxs-lookup"><span data-stu-id="42b4a-318">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="42b4a-319">Chamar estacionador chamadas</span><span class="sxs-lookup"><span data-stu-id="42b4a-319">Call Parkometer</span></span>

<span data-ttu-id="42b4a-320">Call estacionador chamadas é um aplicativo de linha de comando que fornece fácil acesso ao banco de dados de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-320">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-321">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-321">Description</span></span>

<span data-ttu-id="42b4a-322">O estacionador chamadas de chamada é uma ferramenta para rastrear chamadas estacionadas no momento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-322">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="42b4a-323">Ele também coleta estatísticas sobre órbitas e uso do servidor de estacionamento de chamada (CPS).</span><span class="sxs-lookup"><span data-stu-id="42b4a-323">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="42b4a-324">Essa ferramenta de linha de comando fornece acesso de leitura e gravação ao banco de dados do SQL Server do CPS órbita de um computador local ou conectado remotamente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-324">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="42b4a-325">Todas as opções são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-325">All options are mutually exclusive.</span></span> <span data-ttu-id="42b4a-326">A sintaxe da linha de comando é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="42b4a-326">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="42b4a-327">**– o** Parameter — lista todos os intervalos de órbita configurados para este pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-327">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="42b4a-328">**– n** parâmetro — lista todas as órbitas atualmente usadas neste pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-328">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="42b4a-329">As informações exibidas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="42b4a-329">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="42b4a-330">Identificador de recurso uniforme (URI) SIP do estacionamento e do estacionador.</span><span class="sxs-lookup"><span data-stu-id="42b4a-330">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="42b4a-331">Nome do host do CPS onde a chamada está estacionada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-331">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="42b4a-332">Carimbo de data/hora de quando a chamada foi estacionada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-332">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="42b4a-333">**– f** parâmetro — lista o número de órbitas livres no momento no pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-333">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="42b4a-334">\*\*– r \<n\> \*\* parâmetro — lista as \<n\> últimas chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-334">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="42b4a-335">As informações exibidas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="42b4a-335">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="42b4a-336">URI do SIP do estacionamento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-336">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="42b4a-337">Estacionador URI do SIP.</span><span class="sxs-lookup"><span data-stu-id="42b4a-337">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="42b4a-338">Nome do host do CPS onde a chamada foi estacionada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-338">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="42b4a-339">Carimbo de data/hora de quando a chamada foi recuperada ou cancelada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-339">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="42b4a-340">\*\*-t \<n\> \*\* parâmetros-testes reservem uma órbita no banco de dados para mostrar a aleatoriedade dos números de órbita atribuídos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-340">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-341">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-341">Output</span></span>

<span data-ttu-id="42b4a-342">Dependendo dos parâmetros de entrada que são especificados em um prompt de comando, Call estacionador chamadas exibe o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="42b4a-342">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="42b4a-343">Todos os intervalos de órbita configurados para este pool</span><span class="sxs-lookup"><span data-stu-id="42b4a-343">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="42b4a-344">Chamadas estacionadas atualmente</span><span class="sxs-lookup"><span data-stu-id="42b4a-344">Currently parked calls</span></span>

  - <span data-ttu-id="42b4a-345">Número de órbitas livres (disponíveis)</span><span class="sxs-lookup"><span data-stu-id="42b4a-345">Number of free (available) orbits</span></span>

  - <span data-ttu-id="42b4a-346">Chamadas estacionadas recentemente</span><span class="sxs-lookup"><span data-stu-id="42b4a-346">Recently parked calls</span></span>

  - <span data-ttu-id="42b4a-347">Órbitas reservados para testar valores de órbita uniformes e aleatórios</span><span class="sxs-lookup"><span data-stu-id="42b4a-347">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-348">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-348">Purpose</span></span>

<span data-ttu-id="42b4a-349">O objetivo da ferramenta CPS é fornecer acesso de linha de comando para o banco de dados CPS.</span><span class="sxs-lookup"><span data-stu-id="42b4a-349">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="42b4a-350">O administrador pode exibir o uso do CPS e determinar o número de órbitas atribuídas a um pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-350">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-351">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-351">Requirements</span></span>

<span data-ttu-id="42b4a-352">Não há requisitos se essa ferramenta for executada no mesmo computador que está executando o CPS.</span><span class="sxs-lookup"><span data-stu-id="42b4a-352">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="42b4a-353">Se essa ferramenta for executada em um computador remoto, o banco de dados do SQL Server usado pelo Lync Server 2013 deve ser configurado para permitir o acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="42b4a-353">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="42b4a-354">O estacionador chamadas de chamada deve ser configurado com uma cadeia de conexão de banco de dados do SQL Server para se conectar ao SQL Server do pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-354">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="42b4a-355">Esta sequência de conexão de banco de dados do SQL Server está definida no arquivo de configuração **parkometer.exe.config**. Ele deve ser colocado no mesmo diretório onde parkometer.exe está localizado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-355">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="42b4a-356">O arquivo XML a seguir é um exemplo de um parkometer.exe.config. Os parâmetros que devem ser configurados são o nome de usuário (por exemplo, administrador de mydomain \\ ), a senha (por exemplo, mypassword) e o nome do host (por exemplo, meuservidor).</span><span class="sxs-lookup"><span data-stu-id="42b4a-356">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-357">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-357">Examples</span></span>

<span data-ttu-id="42b4a-358">Intervalos de órbita implantados: o parâmetro – o lista todos os intervalos de órbita configurados para este pool, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="42b4a-358">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="42b4a-359">![Intervalos de órbita na chamada estacionador chamadas.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Intervalos de órbita na chamada estacionador chamadas.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-359">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="42b4a-360">Chamadas estacionadas atualmente: o parâmetro – n lista todas as órbitas usadas atualmente neste pool, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="42b4a-360">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="42b4a-361">![Chamadas estacionadas no momento em Call estacionador chamadas.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Chamadas estacionadas no momento em Call estacionador chamadas.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-361">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="42b4a-362">Número de órbitas livres: o parâmetro – f lista o número de órbitas livres no pool, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="42b4a-362">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="42b4a-363">![Órbitas livres no estacionador chamadas de chamada.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Órbitas livres no estacionador chamadas de chamada.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-363">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="42b4a-364">Chamadas estacionadas recentemente: o parâmetro – r \<n\> lista as \<n\> últimas chamadas estacionadas, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="42b4a-364">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="42b4a-365">![Chamadas estacionadas recentemente em Call estacionador chamadas.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Chamadas estacionadas recentemente em Call estacionador chamadas.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-365">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="42b4a-366">Testar reserva de órbita: os testes de parâmetro – t \<n\> reservem uma órbita no banco de dados, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="42b4a-366">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="42b4a-367">![Testar reservas em Call estacionador chamadas.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testar reservas em Call estacionador chamadas.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-367">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-368">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-368">Summary</span></span>

<span data-ttu-id="42b4a-369">Call estacionador chamadas é uma ferramenta de linha de comando que fornece informações detalhadas sobre o servidor de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-369">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="42b4a-370">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="42b4a-370">CleanupStorageServiceData</span></span>

<span data-ttu-id="42b4a-371">A ferramenta CleanupStorageServiceData Resource Kit permite a exclusão de dados órfãos do banco de dados usado pelo serviço de armazenamento do Lync Server (LYSS).</span><span class="sxs-lookup"><span data-stu-id="42b4a-371">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="42b4a-372">Uma função do serviço de armazenamento é armazenar em buffer a comunicação entre o Lync Server e vários pontos de extremidade de armazenamento de dados back-end, como o SQL Server e o Exchange.</span><span class="sxs-lookup"><span data-stu-id="42b4a-372">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-373">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-373">Description</span></span>

<span data-ttu-id="42b4a-374">Para oferecer suporte à alta disponibilidade, o LYSS aceita e salva cópias dos dados em vários servidores front-end no pool temporariamente e remove esses dados depois de serem entregues ao seu local de armazenamento final de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-374">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="42b4a-375">Há situações incomuns que podem ocorrer durante a operação normal, quando um servidor pode falhar ou enfrentar um problema de processamento, e alguns dados podem não ser limpos corretamente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-375">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="42b4a-376">Esses dados são inofensivos, mas eles consomem recursos de processamento limitado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-376">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="42b4a-377">Grande parte da manutenção de dados normal é automatizada, mas essa ferramenta permite a identificação e remoção segura de dados órfãos quando a remoção automatizada não é possível.</span><span class="sxs-lookup"><span data-stu-id="42b4a-377">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="42b4a-378">O uso dessa ferramenta é indicado quando um alerta do System Center Operations Manager (SCOM) de monitoramento de integridade é gerado, solicitando que o administrador remova os dados desnecessários dos bancos de dados do LYSS local no pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-378">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="42b4a-379">Haverá um evento correspondente no log de eventos no front-end que disparou o alerta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-379">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="42b4a-380">Os detalhes do evento conterão informações sobre a quantidade de dados órfãos contidos no front-end e são disparados quando esses dados excedem determinados limites de pré-determinação</span><span class="sxs-lookup"><span data-stu-id="42b4a-380">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-381">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-381">Requirements</span></span>

<span data-ttu-id="42b4a-382">Instale as ferramentas do Lync Server 2013, Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="42b4a-382">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="42b4a-383">A ferramenta é executada em máquinas associadas a um domínio onde o Lync Server e o Shell de gerenciamento do Lync Server 2013 estão instalados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-383">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="42b4a-384">A ferramenta usa um cmdlet do Shell de gerenciamento para identificar todos os servidores front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-384">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="42b4a-385">Em segundo lugar, a ferramenta deve ser executada em um computador no pool que tenha o banco de dados **RtcLocal** instalado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-385">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="42b4a-386">Este banco de dados é usado pela ferramenta CleanupStorageServiceData para obter os detalhes de conexão necessários para se comunicar com o serviço de roteamento do Lync Server. por fim, a conta ou a credencial que invocar a ferramenta deve ter permissão de leitura/gravação para o compartilhamento de arquivo no qual deseja gravar o log de saída. Além disso, essa ferramenta depende do pool estar em um estado estável.</span><span class="sxs-lookup"><span data-stu-id="42b4a-386">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="42b4a-387">Em essência, isso significa que todos os servidores front-end devem ser ativados e em execução, a instância do SQL Server LYNCLOCAL e o banco de dados do LYSS devem estar conectados ao e cada grupo de roteamento deve ter um conjunto completo de 1 servidores front-end primários e dois servidores front-end secundários.</span><span class="sxs-lookup"><span data-stu-id="42b4a-387">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-388">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-388">Examples</span></span>

<span data-ttu-id="42b4a-389">C: \\ arquivos de programa \\ Microsoft Lync Server 2013 \\ reskit \\ StorageService \> ImportStorageServiceData.exe</span><span class="sxs-lookup"><span data-stu-id="42b4a-389">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="42b4a-390">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="42b4a-390">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-391">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-391">Description</span></span>

<span data-ttu-id="42b4a-392">DBAnalyze é uma ferramenta de linha de comando que ajuda os administradores a coletar relatórios de análise sobre os bancos de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-392">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="42b4a-393">O DBAnalyze tem os seguintes modos: diagnóstico, dados do usuário, conferência, MCUs e fragmentação de disco:</span><span class="sxs-lookup"><span data-stu-id="42b4a-393">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="42b4a-394">**Modo**     de diagnóstico Cria um relatório que inclui informações sobre as tabelas (número de registros, fragmentação, tamanho dos dados e tamanho do índice), tamanhos de arquivos de dados e de log o último tempo de backup, distribuição de contatos entre servidores que estão executando o Microsoft Office Communications Server, o número médio de permissões, contatos, contêineres, assinaturas, publicações, pontos de extremidade por usuário, todos os usuários hospedados incorretamente, usuários que não podem ser roteados, o número médio de conferências organizadas por usuário, conferências agendadas, conferências ativas e a versão do banco</span><span class="sxs-lookup"><span data-stu-id="42b4a-394">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42b4a-395">Executar o modo de diagnóstico pode afetar o desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="42b4a-395">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="42b4a-396">Modo de dados do **usuário**   Relata os dados de contato, contêiner, assinatura, publicação, permissão e grupo de contato para um usuário especificado ou para usuários que tenham esse usuário em suas listas de permissões e contatos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-396">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="42b4a-397">Este modo também relata dados de resumo para conferências que um usuário organiza ou é convidado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-397">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="42b4a-398">**Modo**     de conferência Relata dados detalhados para uma conferência específica, incluindo todos os detalhes de tempo de agenda da conferência, a lista de convidados, a lista de tipos de mídia permitidos para a conferência, active MCUs (unidades de controle multiponto), a lista de participantes ativa e o estado de sinalização de cada participante.</span><span class="sxs-lookup"><span data-stu-id="42b4a-398">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="42b4a-399">**Decodificar ID**    da reunião Decodifica uma ID de reunião PSTN (rede telefônica pública comutada) especificada pela opção **/pstnid** , mas não se conecta ao back-end para obter informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-399">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="42b4a-400">**Resolver conferência**     Decodifica uma ID de reunião PSTN especificada pela opção **/pstnid** e exibe informações sobre a conferência indicada pela ID.</span><span class="sxs-lookup"><span data-stu-id="42b4a-400">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="42b4a-401">**Modo MCUs**    Relata a ID, o tipo de mídia, a URL, o status de pulsação, a carga de conferência e a carga de participante de cada MCU no pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-401">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="42b4a-402">Modo de fragmentação de **disco**    Exibe o status de fragmentação de todos os discos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-402">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="42b4a-403">Essa ferramenta pode ser usada para diagnosticar vários problemas ou para ajudar os administradores com o planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="42b4a-403">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="42b4a-404">Por exemplo, se a maioria dos usuários hospedados no servidor A escolher usuários hospedados no servidor B como seus contatos, o administrador pode mover os usuários no servidor A para o servidor B para reduzir o tráfego entre servidores.</span><span class="sxs-lookup"><span data-stu-id="42b4a-404">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-405">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-405">Output</span></span>

<span data-ttu-id="42b4a-406">Esta ferramenta produz relatórios predefinidos sobre o banco de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-406">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="42b4a-407">**Caminho:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ reskit</span><span class="sxs-lookup"><span data-stu-id="42b4a-407">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-408">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-408">Purpose</span></span>

<span data-ttu-id="42b4a-409">Para instalar o Dbanalyze.exe, copie-o para uma pasta local e execute a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-409">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="42b4a-410">Para usar a ferramenta, execute o seguinte comando a partir da linha de comando.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="42b4a-410">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="42b4a-411">As descrições para as opções de linha de comando são mostradas abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-411">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="42b4a-412">![Opções de linha de comando para Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opções de linha de comando para Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-412">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-413">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-413">Requirements</span></span>

<span data-ttu-id="42b4a-414">**Computador** O DBAnalyze pode ser executado apenas de um computador associado ao domínio que tenha o Lync Server 2013 instalado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-414">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="42b4a-415">**Rede** O computador deve poder se conectar ao banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="42b4a-415">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="42b4a-416">**Software** Os componentes de software do Lync Server 2013 devem ser instalados antes de executar o DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="42b4a-416">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="42b4a-417">**Usuários** do A tabela abaixo mostra os administradores que têm as permissões necessárias para acessar os bancos de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-417">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="42b4a-418">![Tabela de permissões para Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabela de permissões para Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-418">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-419">Uma conta de administrador local é necessária para <STRONG>/Report:</STRONG> modo de disco.</span><span class="sxs-lookup"><span data-stu-id="42b4a-419">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-420">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-420">Examples</span></span>

<span data-ttu-id="42b4a-421">Veja a seguir exemplos de comandos válidos do Dbanalyze.exe:</span><span class="sxs-lookup"><span data-stu-id="42b4a-421">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-422">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-422">Summary</span></span>

<span data-ttu-id="42b4a-423">O DBAnalyzer fornece aos administradores uma rápida e fácil análise de bancos de dados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-423">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="42b4a-424">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="42b4a-424">ImportStorageServiceData</span></span>

<span data-ttu-id="42b4a-425">A ferramenta ImportStorageServiceData Resource Kit permite a reimportação da fila e dos dados de ponto de extremidade que foram liberados do serviço de armazenamento (LYSS) de volta para o serviço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-425">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-426">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-426">Description</span></span>

<span data-ttu-id="42b4a-427">Os dados liberados do serviço de armazenamento podem ter sido automáticos (periódicos) com base no status do item da fila ou no tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-427">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="42b4a-428">Isso pode ter acontecido devido à invocação manual do cmdlet de failover do pool ou do cmdlet StorageServiceFullFlush (que o cmdlet de failover do pool invoca).</span><span class="sxs-lookup"><span data-stu-id="42b4a-428">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="42b4a-429">Observe que, preferencialmente, os dados não devem ser importados se qualquer tamanho do banco de dados do serviço de armazenamento (LYSS) no front-ends estiver acima do nível normal, porque isso provavelmente fará com que mais dados sejam exportados de volta. Além disso, qualquer problema que possa ter contribuído com erros que fizeram com que a fila de serviço de armazenamento cresça deve primeiro ser resolvido (por exemplo, erros de ponto de extremidade do Exchange, problemas de rede ou outros problemas).</span><span class="sxs-lookup"><span data-stu-id="42b4a-429">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="42b4a-430">**Cenário 1:** durante o failover do pool, os arquivos podem ser liberados do serviço de armazenamento para cada front-end.</span><span class="sxs-lookup"><span data-stu-id="42b4a-430">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="42b4a-431">Após a conclusão do failover, a ferramenta deve ser executada para reimportar os dados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-431">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="42b4a-432">**Cenário 2:** os dados estão sendo liberados automaticamente todos os dias ou em resposta ao banco de dados do serviço de armazenamento excedendo determinados limites de tamanho (por exemplo, 60%, 80%, 90% completo).</span><span class="sxs-lookup"><span data-stu-id="42b4a-432">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="42b4a-433">Os dados automaticamente liberados devem ser reimportados rotineiramente pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="42b4a-433">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="42b4a-434">Na situação acima, se o pacote SCOM que está sendo monitorado não for implantado, haverá eventos para o serviço de armazenamento do Lync Server relacionado aos dados que estão sendo liberados do serviço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-434">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="42b4a-435">IDs de evento de 32075 (operação de liberação completa iniciada), 32076 (Full flush concluído), 32082 (liberação de nível de manutenção iniciada), 32083 (liberação de nível de manutenção concluída), 32089 (liberação ocorrida devido ao preenchimento de banco de dados).</span><span class="sxs-lookup"><span data-stu-id="42b4a-435">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="42b4a-436">Observação essas IDs de evento correspondem à versão RTM.</span><span class="sxs-lookup"><span data-stu-id="42b4a-436">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="42b4a-437">Quando um administrador vê esses eventos, significa que há arquivos que foram liberados. Esses dados devem ser importados rotineiramente de volta usando essa ferramenta, por exemplo, uma vez por semana.</span><span class="sxs-lookup"><span data-stu-id="42b4a-437">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="42b4a-438">Para a versão de serviço online, se o monitoramento de integridade do SCOM Pack para Lync Server for implantado, há novos alertas que podem ser gerados, o que pede ao administrador para reimportar novamente os dados liberados para o serviço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-438">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="42b4a-439">Haverá um evento correspondente no log de eventos do servidor front-end que disparou o alerta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-439">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="42b4a-440">O evento fornecerá uma descrição do caminho pai no qual os arquivos de dados liberados estão localizados, bem como o número de arquivos que atendem aos critérios de alerta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-440">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="42b4a-441">Os critérios de alerta é que há X ou mais arquivos sob o caminho pai específico, que têm pelo menos Y dias (onde X e Y são predefinidos no StorageService, mas podem ser substituídos alterando o arquivo APPCONFIG.) Dois exemplos de eventos que podem acionar o alerta de integridade são mostrados abaixo, com a diferença que é o caminho pai.</span><span class="sxs-lookup"><span data-stu-id="42b4a-441">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="42b4a-442">Uma possibilidade está no compartilhamento de arquivos do serviço Web, enquanto a outra possibilidade é o diretório de dados do aplicativo local de cada front-end.</span><span class="sxs-lookup"><span data-stu-id="42b4a-442">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="42b4a-443">(por exemplo c: \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService).</span><span class="sxs-lookup"><span data-stu-id="42b4a-443">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="42b4a-444">O administrador executará essa ferramenta reskit.</span><span class="sxs-lookup"><span data-stu-id="42b4a-444">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="42b4a-445">Essa ferramenta aumentará a carga de CPU e de e/s no front-end em que está sendo executado, bem como outros front-ends, na situação em que os dados não são de Propriedade do front-end em que a ferramenta é executada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-445">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="42b4a-446">É recomendável executar esta ferramenta quando os front-ends não estão sob carga intensa de CPU e e/s, por exemplo fora do horário de pico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-446">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="42b4a-447">Em segundo lugar, essa ferramenta pode ser de 2 a 3 minutos para importar um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-447">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="42b4a-448">Tenha isso em mente ao estimar por quanto tempo a ferramenta será executada. O arquivo de log detalhado gerado pela ferramenta será exibido, por padrão, no repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-448">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="42b4a-449">Exclua-o se não houver erros relatados, pois o arquivo de log pode ter dezenas de MB ou mais.</span><span class="sxs-lookup"><span data-stu-id="42b4a-449">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="42b4a-450">![Exemplos de eventos do log de eventos do servidor de armazenamento.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Exemplos de eventos do log de eventos do servidor de armazenamento.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-450">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-451">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-451">Requirements</span></span>

<span data-ttu-id="42b4a-452">Instale as ferramentas do Lync Server 2013, Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="42b4a-452">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="42b4a-453">A ferramenta é executada em máquinas Unidas por domínio onde o Lync Server e o Shell de gerenciamento do Lync Server estão instalados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-453">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="42b4a-454">A ferramenta usa um cmdlet do Shell de gerenciamento para identificar todos os servidores front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-454">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="42b4a-455">Em segundo lugar, a ferramenta deve ser executada em um computador no pool que tenha o banco de dados **RtcLocal** instalado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-455">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="42b4a-456">Este banco de dados é usado pela ferramenta para recuperar o local do compartilhamento de arquivo WEBSERVICE do pool. Além disso, antes de usar a ferramenta, cada servidor front-end deve primeiro habilitar a comunicação remota do Windows PowerShell usando **Enable-PSRemoting** em cada servidor de front-end, bem como a máquina da qual a ferramenta é executada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-456">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="42b4a-457">Caso contrário, os comandos remotos do Windows PowerShell dessa ferramenta falharão.</span><span class="sxs-lookup"><span data-stu-id="42b4a-457">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="42b4a-458">A comunicação remota do Windows PowerShell pode ser desativada em todos os servidores front-end no pool após sua conclusão.</span><span class="sxs-lookup"><span data-stu-id="42b4a-458">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="42b4a-459">Por fim, a conta ou a credencial que invoca a ferramenta deve ter permissão de leitura/gravação no compartilhamento de arquivo WebService para o pool em que eles estão executando essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-459">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="42b4a-460">Caso contrário, a ferramenta irá falhar com erros de permissão de es.</span><span class="sxs-lookup"><span data-stu-id="42b4a-460">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-461">No Windows Server 2012, o Windows PowerShell Remoting é habilitado por padrão, mas não no sistema operacional Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="42b4a-461">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-462">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-462">Examples</span></span>

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="42b4a-463">LCSSync</span><span class="sxs-lookup"><span data-stu-id="42b4a-463">LCSSync</span></span>

<span data-ttu-id="42b4a-464">A ferramenta LCSSync ajuda a implantar o software de comunicação do Lync Server 2013 em um ambiente de várias florestas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-464">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="42b4a-465">Essa ferramenta é usada para sincronizar usuários e grupos de florestas de usuários diferentes como um objeto de contato dos serviços de domínio Active Directory para uma floresta central onde o Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-465">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-466">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-466">Description</span></span>

<span data-ttu-id="42b4a-467">O LCSSync usa os objetos de contato do serviços de domínio do Active Directory sincronizados na floresta central para habilitar usuários para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42b4a-467">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="42b4a-468">Para fornecer logon único, a conta de usuário principal deve ser mapeada para o objeto de contato dos serviços de domínio Active Directory na floresta central do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-468">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="42b4a-469">Essa ferramenta ajuda a executar esse mapeamento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-469">This tool helps perform that mapping.</span></span> <span data-ttu-id="42b4a-470">Esta ferramenta fornece modelos para a criação de agentes de gerenciamento no Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="42b4a-470">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-471">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-471">Summary</span></span>

<span data-ttu-id="42b4a-472">A ferramenta LCSSync ajuda a implantar o Lync Server em um ambiente de várias florestas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-472">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="42b4a-473">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="42b4a-473">LookupUserConsole</span></span>

<span data-ttu-id="42b4a-474">A ferramenta LookupUserConsole exibe informações de roteamento internas do Lync Server sobre usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-474">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="42b4a-475">Essas informações podem ser úteis para o suporte pessoal da Microsoft no diagnóstico de problemas de implantação e roteamento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-475">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-476">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-476">Description</span></span>

<span data-ttu-id="42b4a-477">A execução de LookupUserConsole.exe abrirá um prompt de comando que aceita endereços SIP e tenta exibir informações de roteamento internas do Lync Server relacionadas a eles.</span><span class="sxs-lookup"><span data-stu-id="42b4a-477">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="42b4a-478">Digite **Exit** para sair da ferramenta LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="42b4a-478">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-479">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-479">Requirements</span></span>

<span data-ttu-id="42b4a-480">Instale as ferramentas do Lync Server 2013, Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="42b4a-480">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="42b4a-481">A ferramenta é executada em máquinas Unidas por domínio onde o Lync Server está instalado</span><span class="sxs-lookup"><span data-stu-id="42b4a-481">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-482">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-482">Examples</span></span>

<span data-ttu-id="42b4a-483">C: \\ arquivos de programa \\ Microsoft Lync Server 2013 \\ reskit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="42b4a-483">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="42b4a-484">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="42b4a-484">MsTurnPing</span></span>

<span data-ttu-id="42b4a-485">A ferramenta MSTurnPing permite que um administrador do software de comunicações do Microsoft Lync Server 2013 Verifique o status dos servidores que executam o perímetro de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.</span><span class="sxs-lookup"><span data-stu-id="42b4a-485">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-486">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-486">Description</span></span>

<span data-ttu-id="42b4a-487">A ferramenta MSTurnPing permite que um administrador do software de comunicações do Lync Server 2013 Verifique o status dos servidores que executam o perímetro de áudio/vídeo e os serviços de autenticação de áudio/vídeo, bem como os servidores que estão executando os serviços de política de largura de banda na topologia.</span><span class="sxs-lookup"><span data-stu-id="42b4a-487">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="42b4a-488">A ferramenta permite que o administrador execute os seguintes testes:</span><span class="sxs-lookup"><span data-stu-id="42b4a-488">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="42b4a-489">Teste de servidor de borda a/V: a ferramenta realiza testes em todos os servidores de borda a/V na topologia fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="42b4a-489">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="42b4a-490">Verificar se o serviço de autenticação de áudio/vídeo do Lync Server foi iniciado e se pode emitir credenciais adequadas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-490">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="42b4a-491">Verificando se o serviço de borda de áudio/vídeo do Lync Server foi iniciado e pode alocar os recursos na borda externa com êxito.</span><span class="sxs-lookup"><span data-stu-id="42b4a-491">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="42b4a-492">Teste do serviço de política de largura de banda: a ferramenta realiza testes em todos os servidores que estão executando os serviços de política de largura de banda na topologia fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="42b4a-492">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="42b4a-493">Verificar se o serviço de política de largura de banda (autenticação) do Lync Server foi iniciado e pode emitir credenciais adequadas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-493">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="42b4a-494">Verificando se o serviço de política de largura de banda (núcleo) do Lync Server foi iniciado e pode executar a verificação de largura de banda com êxito.</span><span class="sxs-lookup"><span data-stu-id="42b4a-494">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="42b4a-495">Essa ferramenta deve ser executada em um computador que faça parte da topologia e tenha o repositório local instalado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-495">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-496">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-496">Output</span></span>

<span data-ttu-id="42b4a-497">A ferramenta gera os resultados de cada uma das operações.</span><span class="sxs-lookup"><span data-stu-id="42b4a-497">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="42b4a-498">Se o teste **AudioVideoEdgeServer** for executado, a ferramenta produzirá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="42b4a-498">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="42b4a-499">Os resultados do teste dos computadores que fornecem o serviço de autenticação de áudio/vídeo do Lync Server na topologia</span><span class="sxs-lookup"><span data-stu-id="42b4a-499">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="42b4a-500">Os resultados do teste dos computadores que fornecem o serviço de borda de áudio/vídeo do Lync Server na topologia</span><span class="sxs-lookup"><span data-stu-id="42b4a-500">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="42b4a-501">Se o teste **BandwidthPolicyServer** for executado, a ferramenta produzirá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="42b4a-501">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="42b4a-502">Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda (autenticação) do Lync Server na topologia</span><span class="sxs-lookup"><span data-stu-id="42b4a-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="42b4a-503">Os resultados do teste dos computadores que fornecem o serviço de política de largura de banda (principal) do Lync Server na topologia</span><span class="sxs-lookup"><span data-stu-id="42b4a-503">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-504">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-504">Requirements</span></span>

  - <span data-ttu-id="42b4a-505">Essa ferramenta deve ser executada em um computador que esteja na topologia e que tenha o repositório local.</span><span class="sxs-lookup"><span data-stu-id="42b4a-505">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="42b4a-506">A ferramenta deve ser executada como administrador que tenha acesso ao repositório local.</span><span class="sxs-lookup"><span data-stu-id="42b4a-506">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-507">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-507">Examples</span></span>

<span data-ttu-id="42b4a-508">Veja a seguir um exemplo de entrada da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-508">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-509">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-509">Summary</span></span>

<span data-ttu-id="42b4a-510">Essa ferramenta pode ser um recurso valioso para os administradores do Lync Server 2013 que desejam verificar o status dos servidores que estão executando o áudio/vídeo e serviços de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="42b4a-510">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="42b4a-511">Visualizador de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="42b4a-511">Network Configuration Viewer</span></span>

<span data-ttu-id="42b4a-512">O Visualizador de configuração de rede pode ser usado pelos administradores do software de comunicações do Microsoft Lync Server 2013 para exibir a topologia de rede do controle de admissão de chamadas (CAC) para uma empresa que é configurada para permitir sessões de comunicação em tempo real, como chamadas de voz ou vídeo com base na capacidade de largura de banda especificada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-512">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="42b4a-513">Lync Server 2013 os administradores definem políticas de CAC, que são impostas pelos serviços de política de largura de banda que são instalados com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-513">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-514">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-514">Description</span></span>

<span data-ttu-id="42b4a-515">O Visualizador de configuração de rede (NetworkConfigurationViewer.exe) permite que os administradores realizem as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="42b4a-515">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="42b4a-516">Carregar e exibir a topologia de rede do CAC de uma implantação do Lync Server 2013 em um formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-516">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="42b4a-517">Carregar e exibir a topologia de rede do CAC de um arquivo de log do servidor de política de largura de banda em um formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-517">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="42b4a-518">Salve e armazene a topologia de rede do CAC em um formato XML no disco.</span><span class="sxs-lookup"><span data-stu-id="42b4a-518">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="42b4a-519">Salve e armazene o diagrama de topologia de rede do CAC no formato JPG ou BMP.</span><span class="sxs-lookup"><span data-stu-id="42b4a-519">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="42b4a-520">Exibir dados de configuração da topologia de rede do CAC.</span><span class="sxs-lookup"><span data-stu-id="42b4a-520">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="42b4a-521">Exibir a topologia de rede do CAC em um estilo de exibição de árvore.</span><span class="sxs-lookup"><span data-stu-id="42b4a-521">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="42b4a-522">Definir conectores personalizados para links de topologia de rede do CAC (por exemplo, links de site para região, região para região e site para site).</span><span class="sxs-lookup"><span data-stu-id="42b4a-522">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="42b4a-523">Exibir as informações do site de topologia de rede do CAC, as informações de região e as políticas de largura de banda e os links de rede provisionados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-523">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-524">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-524">Purpose</span></span>

<span data-ttu-id="42b4a-525">Exibir links de topologia de rede do CAC Enterprise em uma interface gráfica.</span><span class="sxs-lookup"><span data-stu-id="42b4a-525">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-526">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-526">Examples</span></span>

<span data-ttu-id="42b4a-527">**Carregar e exibir a topologia de rede do CAC de uma implantação do Lync Server 2013 em um formato gráfico:** Lync Server 2013 os administradores podem carregar e exibir a configuração da topologia de rede do CAC em qualquer computador do Lync Server 2013 usando a opção de **download de configuração de rede** , conforme mostrado na figura abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-527">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="42b4a-528">A ferramenta falhará ao baixar ou exibir essa configuração quando implantada em um computador que não tenha conectividade com o repositório de configuração do Lync.</span><span class="sxs-lookup"><span data-stu-id="42b4a-528">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="42b4a-529">![Baixar a configuração de rede.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Baixar a configuração de rede.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-529">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="42b4a-530">**Carregar e exibir a topologia de rede do CAC de um arquivo de log do servidor de política de largura de banda em um formato gráfico:** Servidores de política de largura de banda do Lync Server 2013 salve a topologia de rede do CAC como parte do mecanismo de log no local de compartilhamento de arquivos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-530">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="42b4a-531">Os administradores do Lync Server podem exibir esse arquivo em um formato gráfico usando a opção **abrir configuração de rede** , conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-531">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="42b4a-532">![Abrir um arquivo de log do servidor de política de largura de banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Abrir um arquivo de log do servidor de política de largura de banda.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-532">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="42b4a-533">Salvar e armazenar a topologia de rede do CAC em um formato XML no disco: os administradores do Lync Server 2013 podem salvar o arquivo de configuração da topologia de rede do CAC em um formato XML usando a opção **salvar uma cópia da configuração de rede** , conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-533">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="42b4a-534">O arquivo de configuração salvo pode ser usado offline para fins de exibição gráfica.</span><span class="sxs-lookup"><span data-stu-id="42b4a-534">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="42b4a-535">![Salvar a configuração de rede como um arquivo XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Salvar a configuração de rede como um arquivo XML.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-535">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="42b4a-536">Salvar e armazenar o diagrama de topologia de rede do CAC no formato JPG ou BMP: os administradores do Lync Server 2013 podem salvar a configuração da topologia de rede do CAC em um formato gráfico (formatos de arquivo JPG e BMP) usando a opção **salvar diagrama de configuração de rede como imagem** , conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-536">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="42b4a-537">![Salvar a configuração de rede como uma imagem.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Salvar a configuração de rede como uma imagem.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-537">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="42b4a-538">**Exibir dados de configuração de topologia de rede do CAC:** Lync Server 2013 os administradores podem exibir dados de configuração de rede relacionados, como regiões de rede, sites de rede, perfis de largura de banda e endereços IP de sub-rede de site em um formato textual, usando a opção Exibir dados de configuração de rede, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-538">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="42b4a-539">![Exibir dados de configuração de rede.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Exibir dados de configuração de rede.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-539">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="42b4a-540">**Exibir a topologia de rede do CAC em um estilo de exibição de árvore:** Lync Server 2013 os administradores podem exibir dados de configuração de rede relacionados em um estilo de exibição de árvore gráfica usando o painel de controle no lado esquerdo da janela da ferramenta, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-540">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="42b4a-541">![Exibir dados de configuração de rede em um modo de exibição de árvore.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Exibir dados de configuração de rede em um modo de exibição de árvore.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-541">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="42b4a-542">**Definir conectores personalizados para links de topologia de rede do CAC (como links de site a região, região para região e site a site):** Lync Server 2013 os administradores podem definir conectores gráficos personalizados para os links WAN de configuração de rede do CAC usando a opção configurações, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-542">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="42b4a-543">Isso ajuda a diferenciar entre vários tipos de links de rede que são provisionados na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="42b4a-543">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="42b4a-544">![Definir conectores personalizados para a topologia de rede do CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definir conectores personalizados para a topologia de rede do CAC")</span><span class="sxs-lookup"><span data-stu-id="42b4a-544">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="42b4a-545">**Exibir as informações do site de topologia de rede do CAC, as informações de região e as políticas de largura de banda provisionadas:** Lync Server 2013 os administradores podem exibir informações de região de rede do CAC relacionadas, informações do site e informações de provisionamento de largura de banda do CAC usando opções mostradas abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-545">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="42b4a-546">(Por exemplo, clique em **informações** em uma região de rede ou em um objeto de site de rede.)</span><span class="sxs-lookup"><span data-stu-id="42b4a-546">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="42b4a-547">![Definir conectores personalizados para sua rede.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definir conectores personalizados para sua rede.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-547">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-548">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-548">Summary</span></span>

<span data-ttu-id="42b4a-549">Essa ferramenta pode ser um recurso valioso para os administradores do Lync Server 2013 que gostariam de exibir a topologia de rede do CAC para sua implantação em um formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-549">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="42b4a-550">Agente de grupo de resposta Live</span><span class="sxs-lookup"><span data-stu-id="42b4a-550">Response Group Agent Live</span></span>

<span data-ttu-id="42b4a-551">O aplicativo grupo de resposta oferece aos agentes a capacidade de acessar informações úteis em tempo real usando seu serviço Web interno.</span><span class="sxs-lookup"><span data-stu-id="42b4a-551">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="42b4a-552">Infelizmente, nenhuma exibição gráfica desses dados está disponível fora do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-552">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="42b4a-553">A ferramenta agente de grupo de resposta Live Resource Kit resolve esse problema fornecendo uma maneira simples e gráfica de acessar essas informações, aprimoradas com informações de software de comunicações do Microsoft Lync 2013 em tempo real, como a presença de outros agentes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-553">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-554">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-554">Description</span></span>

<span data-ttu-id="42b4a-555">Agente de grupo de resposta Live é um aplicativo do Windows que fornece a funcionalidade de entrada e de saída e algumas informações em tempo real (como associação de grupo e número atual de chamadas) para os agentes de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-555">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="42b4a-556">Ele deve ser uma versão avançada da página de grupos de agentes (acessível do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-556">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-557">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-557">Purpose</span></span>

<span data-ttu-id="42b4a-558">O aplicativo grupo de resposta enfileira as chamadas de entrada e roteia-as para os grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-558">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="42b4a-559">Para tomar decisões informadas sobre quais chamadas de serviço, os agentes podem acessar informações em tempo real sobre seus grupos de agentes, como quais outros agentes estão disponíveis e quantas chamadas estão aguardando em cada fila.</span><span class="sxs-lookup"><span data-stu-id="42b4a-559">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="42b4a-560">Essas informações, inicialmente acessíveis apenas através do serviço de grupo de resposta, são disponibilizadas de forma intuitiva por agente de grupo de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-560">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="42b4a-561">Recursos</span><span class="sxs-lookup"><span data-stu-id="42b4a-561">Features</span></span>

<span data-ttu-id="42b4a-562">A ferramenta agente de grupo de resposta do Live é criada no serviço do grupo de resposta e no SDK do Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-562">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="42b4a-563">Ele fornece aos agentes do grupo de resposta as informações e os recursos disponíveis no serviço do grupo de resposta (como associação de grupo, presença de outros agentes e número de chamadas em espera).</span><span class="sxs-lookup"><span data-stu-id="42b4a-563">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="42b4a-564">A figura abaixo ilustra a interface principal do agente do grupo de resposta em tempo real.</span><span class="sxs-lookup"><span data-stu-id="42b4a-564">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="42b4a-565">![A ferramenta agente de grupo de resposta ao vivo.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "A ferramenta agente de grupo de resposta ao vivo.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-565">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="42b4a-566">Os três recursos principais a seguir estão disponíveis para agentes no agente de grupo de resposta em tempo real:</span><span class="sxs-lookup"><span data-stu-id="42b4a-566">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="42b4a-567">**Entrada/saída:** Ao contrário da página de grupos de agentes (acessível no Lync 2013), o agente de grupo de resposta Live permite que somente os agentes entrem ou de todos os grupos de agente ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-567">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="42b4a-568">Este aplicativo fornece três maneiras rápidas para que os agentes entrem ou esgotam:</span><span class="sxs-lookup"><span data-stu-id="42b4a-568">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="42b4a-569">Clique nos botões de entrada/saída (verde e vermelho) no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-569">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="42b4a-570">Clique com o botão direito do mouse no ícone da bandeja do sistema e selecione entrar ou sair.</span><span class="sxs-lookup"><span data-stu-id="42b4a-570">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="42b4a-571">Usando atalhos de teclado configuráveis.</span><span class="sxs-lookup"><span data-stu-id="42b4a-571">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="42b4a-572">**Associação de Grupo:** Quando um grupo de agentes é selecionado, o agente de grupo de resposta Live exibe a lista de agentes desse grupo no painel direito.</span><span class="sxs-lookup"><span data-stu-id="42b4a-572">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="42b4a-573">Se o Lync 2013 estiver em execução no mesmo computador que este aplicativo, as informações de presença e o cartão de visita serão exibidos no agente do grupo de resposta em tempo real.</span><span class="sxs-lookup"><span data-stu-id="42b4a-573">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="42b4a-574">Os agentes podem enviar uma mensagem instantânea ou ligar para outros agentes diretamente de lá.</span><span class="sxs-lookup"><span data-stu-id="42b4a-574">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="42b4a-575">**Estatísticas em tempo real:** Agente de grupo de resposta Live fornece estatísticas em tempo real para todos os grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-575">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="42b4a-576">A frequência de atualização é um minuto.</span><span class="sxs-lookup"><span data-stu-id="42b4a-576">The update frequency is one minute.</span></span> <span data-ttu-id="42b4a-577">Quando uma chamada é atendida por um grupo de resposta, um indicador visual é adicionado ao lado do nome do grupo com o número atual de chamadas em fila.</span><span class="sxs-lookup"><span data-stu-id="42b4a-577">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="42b4a-578">Pausar o ponteiro sobre um grupo também exibe o tempo de espera mais longo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-578">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-579">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-579">Requirements</span></span>

<span data-ttu-id="42b4a-580">O agente de grupo de resposta Live requer o .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="42b4a-580">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="42b4a-581">Além disso, para aproveitar os recursos de cartão de visita e presença, o Lync 2013 deve estar instalado localmente (e estar sendo executado).</span><span class="sxs-lookup"><span data-stu-id="42b4a-581">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="42b4a-582">Configuração</span><span class="sxs-lookup"><span data-stu-id="42b4a-582">Configuration</span></span>

<span data-ttu-id="42b4a-583">O agente de grupo de resposta Live pode ser personalizado para preferências individuais usando a caixa de diálogo opções no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-583">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="42b4a-584">Além disso, o administrador pode definir o endereço de host padrão editando diretamente a propriedade defaultHostAddress do arquivo RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="42b4a-584">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="42b4a-585">A figura abaixo ilustra a caixa de diálogo opções que os agentes podem usar para configurar o endereço do host e as teclas de atalho.</span><span class="sxs-lookup"><span data-stu-id="42b4a-585">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="42b4a-586">Essa caixa de diálogo é acessada clicando-se no botão Opções no canto superior direito da interface principal.</span><span class="sxs-lookup"><span data-stu-id="42b4a-586">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="42b4a-587">![A caixa de diálogo opções do agente de grupo de resposta.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "A caixa de diálogo opções do agente de grupo de resposta.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-587">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="42b4a-588">As três configurações a seguir podem ser personalizadas na configuração do agente de grupo de resposta:</span><span class="sxs-lookup"><span data-stu-id="42b4a-588">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="42b4a-589">Endereço do host: normalmente, esse é o FQDN do pool da Web pertencente ao pool inicial do agente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-589">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="42b4a-590">O endereço do serviço do grupo de resposta exato é automaticamente derivado do plano de fundo nessas informações (acrescentando o caminho correto após o host).</span><span class="sxs-lookup"><span data-stu-id="42b4a-590">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="42b4a-591">Atalhos: os atalhos exatos para entrar/sair podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="42b4a-591">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="42b4a-592">A única limitação é que ambos os atalhos devem conter a chave "logotipo do Windows" (além de pelo menos outra chave).</span><span class="sxs-lookup"><span data-stu-id="42b4a-592">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="42b4a-593">Comece com o Windows: o aplicativo pode ser configurado para iniciar automaticamente com o Windows.</span><span class="sxs-lookup"><span data-stu-id="42b4a-593">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-594">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-594">Examples</span></span>

<span data-ttu-id="42b4a-595">A figura abaixo ilustra como chamar ou enviar uma mensagem instantânea para outro agente clicando com o botão direito do mouse no contato no painel direito.</span><span class="sxs-lookup"><span data-stu-id="42b4a-595">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="42b4a-596">![Fazer uma chamada ou enviar uma mensagem instantânea.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Fazer uma chamada ou enviar uma mensagem instantânea.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-596">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="42b4a-597">A figura abaixo ilustra como o agente de grupo de resposta Live exibe o número atual de chamadas na fila e o tempo de espera mais longo entre todas essas chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-597">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="42b4a-598">![Exibir informações da fila.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Exibir informações da fila.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-598">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-599">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-599">Summary</span></span>

<span data-ttu-id="42b4a-600">Entrada e saída rápidas, associação de grupo e estatísticas básicas em tempo real são recursos interessantes de agente de grupo de resposta que estão disponíveis apenas fora do aplicativo do serviço de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-600">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="42b4a-601">Com a ferramenta de agente de grupo de resposta Live Resource Kit, os administradores do Lync podem fornecer seus agentes com um aplicativo do Windows que permite que eles realizem tarefas de forma mais rápida e gráfica.</span><span class="sxs-lookup"><span data-stu-id="42b4a-601">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="42b4a-602">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="42b4a-602">SEFAUtil</span></span>

<span data-ttu-id="42b4a-603">SEFAUtil (ativação de recurso de extensão secundária) é uma ferramenta de linha de comando que permite que os administradores de software de comunicações e assistência técnica do Microsoft Lync Server 2013 configurem o toque, o encaminhamento de chamada, o toque simultâneo, as configurações de chamada de equipe e o recebimento de chamadas em grupo em nome de um usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-603">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="42b4a-604">A ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico. A ferramenta SEFAUtil permite que o administrador ative/desative/modifique o encaminhamento de chamadas ou tocando simultaneamente em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-604">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="42b4a-605">O administrador pode especificar o destino (na forma de um URI SIP) ou usar um destino que já tenha sido publicado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-605">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="42b4a-606">Essa ferramenta também permite que os administradores adicionem ou removam representantes ou membros do grupo de chamada de equipe em nome do usuário. Essa ferramenta foi criada com o Microsoft Unified Communications Managed API (UCMA) 3,0 e exige que os administradores criem um aplicativo confiável no repositório de gerenciamento central para o SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="42b4a-606">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="42b4a-607">SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Lync Server 2013 e do helpdesk configurem o toque, o encaminhamento de chamada, o toque simultâneo, as configurações de chamada de equipe e o recebimento de chamadas em grupo em nome de um usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-607">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="42b4a-608">Essa ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="42b4a-608">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-609">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-609">Description</span></span>

<span data-ttu-id="42b4a-610">A versão atual do SEFAUtil é apenas uma ferramenta de linha de comando; Não há interface gráfica de usuário de suporte.</span><span class="sxs-lookup"><span data-stu-id="42b4a-610">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="42b4a-611">Essa ferramenta é baseada na API gerenciada de comunicações unificadas da Microsoft (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="42b4a-611">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="42b4a-612">Os recursos desta ferramenta permitem que os administradores e os agentes de assistência técnica façam o seguinte:</span><span class="sxs-lookup"><span data-stu-id="42b4a-612">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="42b4a-613">Exibir todas as configurações de roteamento de chamadas para um usuário (inclui encaminhamento de chamada, delegação, toque simultâneo, chamada de equipe e recebimento de chamadas de grupo)</span><span class="sxs-lookup"><span data-stu-id="42b4a-613">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="42b4a-614">Habilitar/desabilitar/modificar a configuração de encaminhamento de chamadas (inclui destino e timer sem resposta)</span><span class="sxs-lookup"><span data-stu-id="42b4a-614">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="42b4a-615">Habilitar/Desabilitar/Modificar configurações imediatas de encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="42b4a-615">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="42b4a-616">Habilitar/Desabilitar/Modificar configurações de delegação</span><span class="sxs-lookup"><span data-stu-id="42b4a-616">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="42b4a-617">Habilitar/Desabilitar/Modificar configurações do grupo de chamada de equipe</span><span class="sxs-lookup"><span data-stu-id="42b4a-617">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42b4a-618">Novo no Lync Server 2013 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="42b4a-618">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="42b4a-619">Habilitar/Desabilitar/Modificar configurações de toque simultâneo (inclui destino)</span><span class="sxs-lookup"><span data-stu-id="42b4a-619">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42b4a-620">Novo no Lync Server 2013 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="42b4a-620">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="42b4a-621">Habilitar/Desabilitar/Modificar configurações de recebimento de chamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="42b4a-621">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="42b4a-622">Novo no Lync Server 2013 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="42b4a-622">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="42b4a-623">Esta ferramenta tem as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="42b4a-623">This tool has the following limitations:</span></span>

  - <span data-ttu-id="42b4a-624">Suportado somente para usuários hospedados em um pool do Lync Server</span><span class="sxs-lookup"><span data-stu-id="42b4a-624">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="42b4a-625">Não há suporte para a edição em massa das configurações de roteamento de chamadas para vários usuários</span><span class="sxs-lookup"><span data-stu-id="42b4a-625">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-626">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-626">Output</span></span>

<span data-ttu-id="42b4a-627">A versão atual desta ferramenta fornece somente a saída na janela de prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="42b4a-627">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="42b4a-628">Para obter detalhes, consulte a seção exemplos mais adiante neste documento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-628">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-629">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-629">Purpose</span></span>

<span data-ttu-id="42b4a-630">A seguir estão alguns dos principais cenários em que essa ferramenta pode ser usada:</span><span class="sxs-lookup"><span data-stu-id="42b4a-630">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="42b4a-631">Bob é um executivo e foi movido para a telefonia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42b4a-631">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="42b4a-632">Ele tem delegação em seu sistema PBX existente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-632">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="42b4a-633">Como parte da migração para o Lync, o administrador pode configurar o roteamento de Bob para refletir sua configuração de delegação pré-existente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-633">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="42b4a-634">Alice é viajantes e percebe que está esperando uma chamada importante de um de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-634">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="42b4a-635">No entanto, ela está em um hotel e não tem acesso a um computador.</span><span class="sxs-lookup"><span data-stu-id="42b4a-635">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="42b4a-636">Ele chama o helpdesk e solicita que eles encaminhem para seu número de celular todas as chamadas feitas para seu número de trabalho.</span><span class="sxs-lookup"><span data-stu-id="42b4a-636">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="42b4a-637">O pessoal da assistência técnica pode fazer a configuração em seu nome.</span><span class="sxs-lookup"><span data-stu-id="42b4a-637">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="42b4a-638">As chamadas de Joe para seu número de trabalho estão indo para sua caixa postal móvel sempre que estiver trabalhando; no entanto, as coisas parecem estar funcionando corretamente na maioria dos outros locais.</span><span class="sxs-lookup"><span data-stu-id="42b4a-638">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="42b4a-639">O técnico da assistência técnica pode exibir a configuração de roteamento de Joe e descobre que Joe tem o toque simultâneo configurado para seu celular.</span><span class="sxs-lookup"><span data-stu-id="42b4a-639">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="42b4a-640">O técnico faz uma Joe sobre a cobertura móvel em seu escritório e é capaz de determinar que a regra de toque simultâneo é o que está fazendo com que as chamadas vá para a caixa postal móvel de Joe, quando sua cobertura de rede for ruim.</span><span class="sxs-lookup"><span data-stu-id="42b4a-640">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="42b4a-641">Mike é um novo funcionário da Contoso e ele está ingressando em uma nova equipe na qual todos os membros estão configurados para chamada em equipe, quando habilitados para o Microsoft Lync, o administrador pode definir as configurações do grupo de chamada de equipe para incluir todos os membros da equipe, além disso, o administrador adiciona Mike como um membro do grupo de chamada de equipe para cada um dos membros em</span><span class="sxs-lookup"><span data-stu-id="42b4a-641">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="42b4a-642">Uma prática de atendimento ao cliente no departamento de recursos humanos da Contoso é fornecer serviço pessoal para todos os chamadores desde a primeira chamada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-642">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="42b4a-643">Como todos os membros do departamento ficam muito próximos uns dos outros, ter todos os telefones tocando ao mesmo tempo com a chamada de equipe é muito prejudicial para a equipe.</span><span class="sxs-lookup"><span data-stu-id="42b4a-643">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="42b4a-644">Para fornecer o melhor serviço sem interromper os membros da equipe, o administrador do Lync aproveita o recurso de recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-644">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="42b4a-645">O administrador adiciona todos os membros do departamento a um grupo de retirada e se comunica com o número do grupo de recebimento do departamento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-645">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="42b4a-646">Quando Paula estiver ausente da sua mesa, Joe notificará o toque do telefone e continuará a responder à chamada em sua mesa.</span><span class="sxs-lookup"><span data-stu-id="42b4a-646">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-647">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-647">Requirements</span></span>

<span data-ttu-id="42b4a-648">A ferramenta SEFAUtil pode ser executada apenas em um computador que faz parte de um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="42b4a-648">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="42b4a-649">UCMA 3,0 deve ser instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="42b4a-649">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="42b4a-650">Para executar a ferramenta, um novo aplicativo confiável com a ID do aplicativo SEFAUtil deve ser criado nesse pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-650">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="42b4a-651">**Criar um novo aplicativo confiável para a ferramenta SEFAUtil**</span><span class="sxs-lookup"><span data-stu-id="42b4a-651">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="42b4a-652">A ferramenta SEFAUTil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="42b4a-652">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="42b4a-653">Se necessário, a adição de um pool como um novo pool de aplicativos confiáveis pode ser feita por meio do Shell de gerenciamento do Lync Server com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="42b4a-653">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42b4a-654">O UCMA 3,0 deve ser instalado em qualquer computador que será usado para executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="42b4a-654">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="42b4a-655">Um aplicativo confiável precisa ser definido na topologia da ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="42b4a-655">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="42b4a-656">Para definir o SEFAUtil como um novo aplicativo confiável, use o Shell de gerenciamento do Lync Server e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="42b4a-656">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42b4a-657">Uma porta diferente pode ser usada, se necessário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-657">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="42b4a-658">As alterações de topologia precisam ser habilitadas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-658">The topology changes need to be enabled.</span></span> <span data-ttu-id="42b4a-659">Habilitar as alterações de topologia pode ser feito por meio do Shell de gerenciamento do Lync Server executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="42b4a-659">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="42b4a-660">Se necessário, instale as ferramentas do kit de recursos do Lync Server 2013 no servidor que será usado para executar a ferramenta SEFAUtil (o servidor deve fazer parte de um pool de aplicativos confiáveis).</span><span class="sxs-lookup"><span data-stu-id="42b4a-660">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="42b4a-661">Verifique se o SEFAUtil está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-661">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="42b4a-662">Para fazer isso, execute a ferramenta a partir de um prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário na implantação.</span><span class="sxs-lookup"><span data-stu-id="42b4a-662">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="42b4a-663">Por padrão, a ferramenta estará localizada em: "... \\ Arquivos de programa \\ Microsoft Lync Server 2013 \\ reskit ".</span><span class="sxs-lookup"><span data-stu-id="42b4a-663">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="42b4a-664">Para exibir as configurações de encaminhamento de chamadas de um usuário, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="42b4a-664">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="42b4a-665">As configurações de encaminhamento de chamadas do usuário devem ser exibidas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-665">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="42b4a-666">Recebimento de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="42b4a-666">Group Call Pickup</span></span>

<span data-ttu-id="42b4a-667">O recebimento de chamadas de grupo requer configuração adicional no Lync Server para que o recurso seja totalmente habilitado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-667">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="42b4a-668">Antes de atribuir grupos de recebimento aos usuários, consulte a documentação do produto de recebimento de chamadas em grupo para obter as etapas de planejamento e implantação desse recurso.</span><span class="sxs-lookup"><span data-stu-id="42b4a-668">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-669">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-669">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="42b4a-670">Exibir as configurações de tratamento de chamadas atuais</span><span class="sxs-lookup"><span data-stu-id="42b4a-670">Display Current Call Handling Settings</span></span>

<span data-ttu-id="42b4a-671">O comando a seguir exibe o tratamento de chamadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-671">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-672">Este exemplo usa a opção <STRONG>/Server</STRONG> para especificar o Lync Server ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="42b4a-672">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="42b4a-673">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-673">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="42b4a-674">Definir o destino de chamada para encaminhamento/sem resposta</span><span class="sxs-lookup"><span data-stu-id="42b4a-674">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="42b4a-675">Este exemplo define o destino de chamada de encaminhamento/sem resposta e o atraso de anel.</span><span class="sxs-lookup"><span data-stu-id="42b4a-675">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="42b4a-676">Aqui, a opção/Server não é fornecida; O SEFAUtil tenta descobrir a descoberta automática do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42b4a-676">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="42b4a-677">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-677">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="42b4a-678">Habilitar o encaminhamento de chamadas imediatamente</span><span class="sxs-lookup"><span data-stu-id="42b4a-678">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="42b4a-679">Este exemplo habilita imediatamente o encaminhamento de chamada para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-679">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="42b4a-680">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-680">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="42b4a-681">Desabilitar o encaminhamento de chamadas imediatamente</span><span class="sxs-lookup"><span data-stu-id="42b4a-681">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="42b4a-682">Este exemplo desabilita imediatamente o encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-682">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="42b4a-683">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-683">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="42b4a-684">Adicionar um usuário como um representante e configurar o toque simultâneo dos representantes</span><span class="sxs-lookup"><span data-stu-id="42b4a-684">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="42b4a-685">Este exemplo adiciona um usuário como um representante e configura o toque simultâneo dos representantes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-685">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="42b4a-686">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-686">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="42b4a-687">Alterar regra de toque simultâneo dos representantes</span><span class="sxs-lookup"><span data-stu-id="42b4a-687">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="42b4a-688">Este exemplo altera a regra de toque simultâneo definida no exemplo anterior para a regra de toque atrasado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-688">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="42b4a-689">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-689">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="42b4a-690">Remover o representante</span><span class="sxs-lookup"><span data-stu-id="42b4a-690">Remove the Delegate</span></span>

<span data-ttu-id="42b4a-691">Este exemplo remove o representante.</span><span class="sxs-lookup"><span data-stu-id="42b4a-691">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-692">Quando o último representante é removido, o toque de representante é automaticamente desabilitado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-692">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="42b4a-693">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-693">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="42b4a-694">Adicionar um representante e configurar a regra de Call-Forward para representantes</span><span class="sxs-lookup"><span data-stu-id="42b4a-694">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="42b4a-695">Este exemplo adiciona um representante e configura a regra de direcionamento de chamada para representantes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-695">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="42b4a-696">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-696">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="42b4a-697">Habilitar o toque simultâneo e definir um número de destino</span><span class="sxs-lookup"><span data-stu-id="42b4a-697">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="42b4a-698">Este exemplo habilita o toque simultâneo e define um número de destino de toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-698">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-699">Para alterar o número de destino de toque simultâneo de um usuário que já tenha o toque simultâneo habilitado, mantenha o comando com a opção/enablesimulring, caso contrário, o número de destino não será alterado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-699">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="42b4a-700">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-700">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="42b4a-701">Desabilitar toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="42b4a-701">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="42b4a-702">Este exemplo desabilita o toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-702">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="42b4a-703">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-703">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="42b4a-704">Adicionar um membro da equipe para Team-Call e configurar o toque simultâneo para o grupo de membros Team-Call</span><span class="sxs-lookup"><span data-stu-id="42b4a-704">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="42b4a-705">Este exemplo adiciona um membro da equipe ao grupo de chamada de equipe de um usuário e habilita o toque simultâneo para o grupo de chamada de equipe.</span><span class="sxs-lookup"><span data-stu-id="42b4a-705">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-706">A adição de um membro ao grupo de chamada de equipe de um usuário alternará automaticamente a simultâneo de toque simultâneo dos usuários para toque simultâneo o grupo de chamada de equipe.</span><span class="sxs-lookup"><span data-stu-id="42b4a-706">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="42b4a-707">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-707">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="42b4a-708">Remover um membro do grupo de Team-Call</span><span class="sxs-lookup"><span data-stu-id="42b4a-708">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="42b4a-709">Este exemplo remove um membro da equipe do grupo de chamada de equipe de um usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-709">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-710">Se o membro que está sendo removido for o único membro do grupo de chamada de equipe, tocar simultaneamente no grupo de chamada de equipe será automaticamente desabilitado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-710">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="42b4a-711">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-711">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="42b4a-712">Definir o toque atrasado para o grupo de Team-Call</span><span class="sxs-lookup"><span data-stu-id="42b4a-712">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="42b4a-713">Este exemplo altera o anel atrasado para a configuração de tempo do grupo de chamada de equipe.</span><span class="sxs-lookup"><span data-stu-id="42b4a-713">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="42b4a-714">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-714">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="42b4a-715">Habilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="42b4a-715">Enable Team-Call</span></span>

<span data-ttu-id="42b4a-716">Este exemplo habilita a chamada de equipe para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-716">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-717">Se o grupo de chamada de equipe do usuário não tiver membros, a chamada de equipe não será habilitada.</span><span class="sxs-lookup"><span data-stu-id="42b4a-717">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="42b4a-718">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-718">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="42b4a-719">Desabilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="42b4a-719">Disable Team-Call</span></span>

<span data-ttu-id="42b4a-720">Este exemplo desabilita a chamada de equipe para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-720">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="42b4a-721">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-721">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="42b4a-722">Habilitar o recebimento de chamadas em grupo e atribuir um grupo de recebimento a um usuário</span><span class="sxs-lookup"><span data-stu-id="42b4a-722">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="42b4a-723">Este exemplo atribui um grupo de recebimento a um usuário e habilita o recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-723">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="42b4a-724">**Output**</span><span class="sxs-lookup"><span data-stu-id="42b4a-724">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="42b4a-725">Desabilitar o recebimento de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="42b4a-725">Disable Group Call Pickup</span></span>

<span data-ttu-id="42b4a-726">Este exemplo desabilita o recebimento de chamadas em grupo para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-726">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-727">Quando você desabilita o recebimento de chamadas em grupo para um usuário, o número do grupo que foi atribuído ao usuário não é mantido.</span><span class="sxs-lookup"><span data-stu-id="42b4a-727">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="42b4a-728">Se, subsequentemente, você quiser reabilitar o recebimento de chamadas em grupo para esse usuário, você deve atribuir o número de grupo novamente com a opção/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="42b4a-728">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="42b4a-729">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="42b4a-729">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-730">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-730">Description</span></span>

<span data-ttu-id="42b4a-731">SYSPrep.ps1 é um script do Windows PowerShell que instalará os seguintes pré-requisitos do Lync Server 2013 no seu computador do sistema operacional Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="42b4a-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="42b4a-732">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="42b4a-732">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="42b4a-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="42b4a-733">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="42b4a-734">Windows PowerShell versão 3,0</span><span class="sxs-lookup"><span data-stu-id="42b4a-734">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="42b4a-735">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="42b4a-735">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="42b4a-736">Atualizações do Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="42b4a-736">Internet Information Server Updates</span></span>

  - <span data-ttu-id="42b4a-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="42b4a-737">Windows Identity Foundation</span></span>

  - <span data-ttu-id="42b4a-738">Arquivos principais do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b4a-738">Lync Server 2013 Core files</span></span>

<span data-ttu-id="42b4a-739">Embora o nome do script seja semelhante à ferramenta de preparação do sistema para os sistemas operacionais Microsoft Windows, eles são diferentes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="42b4a-740">Este script só instalará os pré-requisitos necessários para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-740">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="42b4a-741">Após a instalação desses pré-requisitos, a ferramenta SYSPrep do Windows pode ser usada para criar uma imagem do servidor.</span><span class="sxs-lookup"><span data-stu-id="42b4a-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-742">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-742">Requirements</span></span>

<span data-ttu-id="42b4a-743">Antes de executar o script SYSPrep.ps1, você deve copiar os arquivos de pré-requisito para uma pasta local no computador do sistema operacional Windows Server 2008 (por exemplo, **D: \\ configuração)**.</span><span class="sxs-lookup"><span data-stu-id="42b4a-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="42b4a-744">Essa pasta também deve incluir uma cópia dos arquivos do Lync Server 2013, especificamente **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="42b4a-744">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="42b4a-745">Os arquivos de pré-requisito podem ser baixados dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="42b4a-745">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42b4a-746">Requisito</span><span class="sxs-lookup"><span data-stu-id="42b4a-746">Prerequisite</span></span></th>
<th><span data-ttu-id="42b4a-747">Local</span><span class="sxs-lookup"><span data-stu-id="42b4a-747">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42b4a-748">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="42b4a-748">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b4a-749">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="42b4a-749">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b4a-750">Windows PowerShell versão 3,0</span><span class="sxs-lookup"><span data-stu-id="42b4a-750">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b4a-751">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="42b4a-751">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b4a-752">Atualizações do Internet Information Server</span><span class="sxs-lookup"><span data-stu-id="42b4a-752">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b4a-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="42b4a-753">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b4a-754">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="42b4a-754">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="42b4a-755">Copiar da mídia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b4a-755">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="42b4a-756">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="42b4a-756">Parameter</span></span>

<span data-ttu-id="42b4a-757">O parâmetro **– SetupFolder** aceita como um argumento o local do diretório dos arquivos de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="42b4a-757">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-758">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-758">Examples</span></span>

<span data-ttu-id="42b4a-759">Para executar o script SYSPrep.ps1 e instalar os pré-requisitos do Lync Server 2013, execute o seguinte comando em um prompt de comando elevado:</span><span class="sxs-lookup"><span data-stu-id="42b4a-759">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="42b4a-760">Migração de comunicados de número não atribuído</span><span class="sxs-lookup"><span data-stu-id="42b4a-760">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="42b4a-761">A ferramenta de migração de comunicados de número não atribuído permite que um administrador do Lync mova a configuração de números não atribuídos que é atendida pelo aplicativo de comunicado de um pool ou servidor do Lync de origem para um servidor ou pool Lync de destino.</span><span class="sxs-lookup"><span data-stu-id="42b4a-761">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-762">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-762">Description</span></span>

<span data-ttu-id="42b4a-763">A ferramenta de migração de comunicados de número não atribuído é um script do Windows PowerShell que move a configuração de números não atribuídos atendida pelo aplicativo de comunicado de um pool ou servidor de origem para um servidor ou pool diferente.</span><span class="sxs-lookup"><span data-stu-id="42b4a-763">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="42b4a-764">Quando executado, o script de migração de comunicados de número não atribuído executará as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="42b4a-764">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="42b4a-765">Mova todos os arquivos de áudio usados pelos comunicados de número não atribuído do aplicativo de comunicado hospedado no servidor ou pool de origem para o repositório de arquivos do pool ou servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="42b4a-765">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42b4a-766">os arquivos de áudio são removidos do pool de origem depois que são copiados para o pool de destino.</span><span class="sxs-lookup"><span data-stu-id="42b4a-766">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="42b4a-767">Mova todos os comunicados de número não atribuídos configurados para o aplicativo de comunicado hospedado no servidor ou pool de origem para o servidor ou pool de destino.</span><span class="sxs-lookup"><span data-stu-id="42b4a-767">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="42b4a-768">Reatribua todos os intervalos de números não atribuídos que são atendidos pelo aplicativo de comunicado hospedado no servidor ou pool de origem para o servidor de destino ou pool.</span><span class="sxs-lookup"><span data-stu-id="42b4a-768">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="42b4a-769">Depois de executar o script com êxito, todos os intervalos de números não atribuídos que foram atendidos pelo aplicativo de anúncio hospedado no servidor de origem ou pool serão agora atendidos com a mesma configuração pelo servidor ou pool de destino.</span><span class="sxs-lookup"><span data-stu-id="42b4a-769">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-770">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-770">Output</span></span>

<span data-ttu-id="42b4a-771">O script **move-CsAnnouncementConfiguration** indica na janela do Shell de gerenciamento do Lync de onde ele é executado com êxito ou falha da operação de migração.</span><span class="sxs-lookup"><span data-stu-id="42b4a-771">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="42b4a-772">Se a execução da operação for interrompida por qualquer erro, os intervalos de números não atribuídos que foram movidos com êxito para o destino permanecerão no destino em um formulário operacional e o restante dos intervalos de números não atribuídos a serem migrados permanecerá na origem também em um formulário operacional.</span><span class="sxs-lookup"><span data-stu-id="42b4a-772">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="42b4a-773">Para migrar completamente o restante da configuração, execute novamente o script após resolver o erro.</span><span class="sxs-lookup"><span data-stu-id="42b4a-773">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="42b4a-774">Finalidade</span><span class="sxs-lookup"><span data-stu-id="42b4a-774">Purpose</span></span>

<span data-ttu-id="42b4a-775">O script de migração de comunicados de número não atribuído pode ser usado nos três cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="42b4a-775">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="42b4a-776">**Migrando definições de configuração para uma nova versão do Lync Server:** A Contoso está em processo de migração para o Lync Server 2013 e como parte do processo de migração o administrador do Lync Server gostaria de mover a configuração de números não atribuídos atendida pelo aplicativo comunicado da implantação do Lync Server 2010 para a nova implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-776">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="42b4a-777">Para mover as definições de configuração, o administrador do Lync Server usa a ferramenta de migração de comunicados de número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="42b4a-777">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="42b4a-778">Reverter **uma implantação do Lync server 2013 para o Lync server 2010:** Fatores de devido inesperados, a contoso tem que reverter a migração para a nova implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42b4a-778">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="42b4a-779">Para minimizar as interrupções do serviço, o administrador do Lync Server usa a ferramenta de migração de comunicados de número não atribuído para reverter a configuração da implantação do Lync Server 2013 para a implantação do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="42b4a-779">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="42b4a-780">**Movimentação de dados entre implantações do Lync:** A Contoso está no processo de substituição de todos os servidores de um pool por servidores mais recentes.</span><span class="sxs-lookup"><span data-stu-id="42b4a-780">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="42b4a-781">Sua estratégia é implantar um novo pool do Lync Server 2013, mover todos os dados do antigo para o novo pool e, em seguida, substituir o pool antigo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-781">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="42b4a-782">Depois que o novo pool é implantado, a ferramenta de migração de comunicados de número não atribuído é usada para mover a configuração do pool antigo para o novo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-782">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-783">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-783">Requirements</span></span>

<span data-ttu-id="42b4a-784">Estes são os principais requisitos necessários para executar a ferramenta com êxito:</span><span class="sxs-lookup"><span data-stu-id="42b4a-784">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="42b4a-785">O script deve ser executado em um computador que tenha o Shell de gerenciamento do Lync Server 2013 instalado.</span><span class="sxs-lookup"><span data-stu-id="42b4a-785">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="42b4a-786">O aplicativo de anúncio deve ser implantado com êxito nos servidores ou pools de origem e destino.</span><span class="sxs-lookup"><span data-stu-id="42b4a-786">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="42b4a-787">Move-CsAnnouncementConfiguration script</span><span class="sxs-lookup"><span data-stu-id="42b4a-787">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="42b4a-788">O script Move-CsAnnouncementConfiguration requer os dois parâmetros descritos na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-788">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="42b4a-789">![Parâmetros move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parâmetros.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-789">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-790">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-790">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="42b4a-791">Mover a configuração de comunicados de número não atribuído de um pool do Lync Server 2010 para um pool do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b4a-791">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="42b4a-792">Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2010) para o pool de destino (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="42b4a-792">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="42b4a-793">Mover a configuração de comunicados de número não atribuído de um pool do Lync Server 2013 para um pool do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="42b4a-793">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="42b4a-794">Este exemplo move os anúncios de número não atribuído do pool de origem (Lync Server 2013) para o pool de destino (Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="42b4a-794">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="42b4a-795">Dados de conferência da Web</span><span class="sxs-lookup"><span data-stu-id="42b4a-795">Web Conf Data</span></span>

<span data-ttu-id="42b4a-796">A ferramenta Web conf data permite que um administrador do software de comunicações do Lync Server 2013 tenha mais controle sobre os dados associados a webconferências do organizador.</span><span class="sxs-lookup"><span data-stu-id="42b4a-796">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="42b4a-797">Os cenários incluem a capacidade de excluir dados de reunião de um usuário específico com base em um critério de carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="42b4a-797">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="42b4a-798">Descrição</span><span class="sxs-lookup"><span data-stu-id="42b4a-798">Description</span></span>

<span data-ttu-id="42b4a-799">Essa ferramenta permite ao administrador executar as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="42b4a-799">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="42b4a-800">Localizar todos os dados de Webconferência associados a um único usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-800">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="42b4a-801">Excluir todos os dados de Webconferência associados a um único usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-801">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="42b4a-802">Excluir todos os dados de Webconferência associados a um único usuário que seja mais antigo do que uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="42b4a-802">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="42b4a-803">Mova todos os dados de Webconferência associados a um único usuário quando esse usuário é movido de um pool para outro.</span><span class="sxs-lookup"><span data-stu-id="42b4a-803">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42b4a-804">As ferramentas do kit de recursos do Lync Server 2010 suportavam a transferência de todos os dados de Webconferência associados a um único usuário quando esse usuário é movido de um pool para outro.</span><span class="sxs-lookup"><span data-stu-id="42b4a-804">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="42b4a-805">Essa funcionalidade foi agora preterida dessa ferramenta em favor do parâmetro <STRONG>MoveConferenceData</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="42b4a-805">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="42b4a-806">Para obter detalhes sobre esse parâmetro, consulte o cmdlet <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">move-CsUser</A> .</span><span class="sxs-lookup"><span data-stu-id="42b4a-806">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="42b4a-807">A ferramenta exclui dados de reunião somente para reuniões que estão inativas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-807">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="42b4a-808">As reuniões ativas (ou reuniões em sessões) não podem ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="42b4a-808">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="42b4a-809">Essa ferramenta deve ser executada em um computador que esteja no mesmo pool do usuário de destino.</span><span class="sxs-lookup"><span data-stu-id="42b4a-809">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="42b4a-810">O usuário cujos dados de conteúdo da reunião estão sendo gerenciados por essa ferramenta deve estar hospedado no mesmo pool de usuários.</span><span class="sxs-lookup"><span data-stu-id="42b4a-810">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="42b4a-811">Saída</span><span class="sxs-lookup"><span data-stu-id="42b4a-811">Output</span></span>

<span data-ttu-id="42b4a-812">Esta ferramenta gera os resultados de cada uma das operações:</span><span class="sxs-lookup"><span data-stu-id="42b4a-812">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="42b4a-813">Se uma consulta for executada, a ferramenta produzirá a lista de todas as pastas de dados de reunião inativas que têm esse usuário como organizador.</span><span class="sxs-lookup"><span data-stu-id="42b4a-813">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="42b4a-814">Se uma exclusão for executada, a ferramenta produzirá a lista de todas as pastas de dados de reunião cujos dados serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-814">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="42b4a-815">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b4a-815">Requirements</span></span>

<span data-ttu-id="42b4a-816">A ferramenta precisa ser executada no mesmo pool em que o organizador está hospedado no momento.</span><span class="sxs-lookup"><span data-stu-id="42b4a-816">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="42b4a-817">A ferramenta deve ser executada usando privilégios de administrador com acesso ao repositório de arquivos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="42b4a-817">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="42b4a-818">Exemplos</span><span class="sxs-lookup"><span data-stu-id="42b4a-818">Examples</span></span>

<span data-ttu-id="42b4a-819">A tabela a seguir descreve os parâmetros, alguns dos quais são usados nos exemplos.</span><span class="sxs-lookup"><span data-stu-id="42b4a-819">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="42b4a-820">![Parâmetros da ferramenta de dados de Webconferência.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parâmetros da ferramenta de dados de Webconferência.")</span><span class="sxs-lookup"><span data-stu-id="42b4a-820">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="42b4a-821">O exemplo anterior mostra como funciona um comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-821">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="42b4a-822">A saída de tal comando seria uma lista de todas as pastas de conteúdo de reunião que seriam afetadas por essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="42b4a-822">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="42b4a-823">O anterior é um exemplo de um comando delete.</span><span class="sxs-lookup"><span data-stu-id="42b4a-823">The preceding is an example of a delete command.</span></span> <span data-ttu-id="42b4a-824">O comando excluir removerá todas as pastas de reunião inativas deste usuário.</span><span class="sxs-lookup"><span data-stu-id="42b4a-824">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="42b4a-825">Resumo</span><span class="sxs-lookup"><span data-stu-id="42b4a-825">Summary</span></span>

<span data-ttu-id="42b4a-826">Essa ferramenta pode ser um recurso valioso para os administradores que precisam de controle mais preciso sobre os dados da reunião de conferência.</span><span class="sxs-lookup"><span data-stu-id="42b4a-826">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
