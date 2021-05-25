---
title: Skype for Business Server documentação de Ferramentas de Kit de Recursos 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Este artigo descreve as ferramentas no Kit de Recursos Skype for Business Server 2015, incluindo a finalidade de cada ferramenta e exemplos de seu uso. O Skype for Business Server 2015 Resource Kit ajuda a facilitar as tarefas de rotina para os administradores de IT que implantam e gerenciam o Skype for Business Server 2015. Por exemplo, a ferramenta Web Conf Data pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online. A ferramenta SEFAUtil pode ser usada para configurar o encaminhamento de chamada delegada e o atendimento aos usuários. Incentivamos os administradores de IT a usar essas ferramentas para gerenciar com mais eficiência o Skype for Business Server 2015.
ms.openlocfilehash: 6c68a94d331f2ad5f9ffaa169228aa9d64e41293
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629040"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="518db-107">Skype for Business Server documentação de Ferramentas de Kit de Recursos 2015</span><span class="sxs-lookup"><span data-stu-id="518db-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="518db-108">Este artigo descreve as ferramentas no Kit de Recursos Skype for Business Server 2015, incluindo a finalidade de cada ferramenta e exemplos de seu uso.</span><span class="sxs-lookup"><span data-stu-id="518db-108">This article describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="518db-109">O Skype for Business Server 2015 Resource Kit ajuda a facilitar as tarefas de rotina para os administradores de IT que implantam e gerenciam o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="518db-110">Por exemplo, a **ferramenta Web Conf Data** pode ser usada para controlar facilmente os dados carregados pelos usuários durante uma reunião online.</span><span class="sxs-lookup"><span data-stu-id="518db-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="518db-111">A **ferramenta SEFAUtil** pode ser usada para configurar o encaminhamento de chamada delegada e o atendimento aos usuários.</span><span class="sxs-lookup"><span data-stu-id="518db-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="518db-112">Incentivamos os administradores de IT a usar essas ferramentas para gerenciar com mais eficiência o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="518db-113">Instalação das Ferramentas de Kit de Recursos</span><span class="sxs-lookup"><span data-stu-id="518db-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="518db-114">Para instalar o Skype for Business Server 2015 Resource Kit, baixe [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) do Centro de Download.</span><span class="sxs-lookup"><span data-stu-id="518db-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="518db-115">Execute **OCSResKit.msi** para fazer uma instalação simples.</span><span class="sxs-lookup"><span data-stu-id="518db-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="518db-116">O .msi instala todas as ferramentas no seguinte caminho: %Arquivos de **Programas%\Skype for Business Server 2015\ResKit**.</span><span class="sxs-lookup"><span data-stu-id="518db-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="518db-117">As ferramentas que são executáveis autocontivedas estão nesta pasta.</span><span class="sxs-lookup"><span data-stu-id="518db-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="518db-118">As ferramentas que também têm arquivos de suporte estão em suas próprias subpastas.</span><span class="sxs-lookup"><span data-stu-id="518db-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="518db-119">Ambientes com suporte</span><span class="sxs-lookup"><span data-stu-id="518db-119">Supported Environments</span></span>

<span data-ttu-id="518db-120">O Skype for Business Server 2015 Resource Kit deve ser instalado em um servidor que atenda às especificações necessárias para o Skype for Business Server 2015, geralmente um sendo usado para executar o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="518db-121">Visão geral das Ferramentas de Kit de Recursos</span><span class="sxs-lookup"><span data-stu-id="518db-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="518db-122">Veja a seguir uma lista das ferramentas fornecidas no Kit de Recursos Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="518db-123">Uma descrição de cada ferramenta, incluindo os requisitos e o uso de exemplo, é abordada nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="518db-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="518db-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="518db-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="518db-125">Monitor de Serviço de Política de Largura de Banda</span><span class="sxs-lookup"><span data-stu-id="518db-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="518db-126">Analisador de Utilização de Largura de Banda</span><span class="sxs-lookup"><span data-stu-id="518db-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="518db-127">Chamar Parkometer</span><span class="sxs-lookup"><span data-stu-id="518db-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="518db-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="518db-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="518db-129">Importar Armazenamento dados de serviço</span><span class="sxs-lookup"><span data-stu-id="518db-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="518db-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="518db-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="518db-131">Console do usuário de lookup</span><span class="sxs-lookup"><span data-stu-id="518db-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="518db-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="518db-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="518db-133">Visualizador de Configuração de Rede</span><span class="sxs-lookup"><span data-stu-id="518db-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="518db-134">Agente do Grupo de Resposta Ao Vivo</span><span class="sxs-lookup"><span data-stu-id="518db-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="518db-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="518db-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="518db-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="518db-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="518db-137">Migração de anúncios de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="518db-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="518db-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="518db-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="518db-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="518db-139">ABSConfig</span></span>
<span data-ttu-id="518db-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="518db-141">A ferramenta de Configuração do Serviço de Livro de Endereços (ABSConfig) é uma ferramenta administrativa que ajuda os administradores a personalizar a configuração do Serviço de Livro de Endereços no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="518db-142">Essa ferramenta também permite que Skype for Business Server administradores de 2015 restaure as configurações padrão do Serviço de Livro de Endereços.</span><span class="sxs-lookup"><span data-stu-id="518db-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="518db-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-143">Description</span></span>

<span data-ttu-id="518db-144">ABSConfig é um aplicativo de interface gráfica do usuário que permite que os administradores configurem atributos dos Serviços de Domínio do Active Directory relacionados ao Serviço de Livro de Endereços.</span><span class="sxs-lookup"><span data-stu-id="518db-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="518db-145">Os principais cenários da ferramenta são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="518db-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="518db-146">Para permitir que os administradores mapeiem atributos nos Serviços de Domínio do Active Directory para os atributos Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="518db-147">Para permitir que os administradores especifiquem o atributo Serviços de Domínio do Active Directory a serem incluídos ou excluídos nos arquivos do Serviço de Livro de Endereços.</span><span class="sxs-lookup"><span data-stu-id="518db-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="518db-148">Para permitir que os administradores restaurem, configurações padrão do Serviço de Livro de Endereços.</span><span class="sxs-lookup"><span data-stu-id="518db-148">To enable administrators to restore,  default Address Book Service settings.</span></span>

<span data-ttu-id="518db-149">A ferramenta ABSConfig pode ser iniciada usando o arquivo ABSConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="518db-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="518db-150">A ferramenta abre para a guia **Configurar Atributos.** Esta tabela tem opções para mapear atributos dos Serviços de Domínio do Active Directory para os campos de atributos do Skype for Business Server 2015 e especificar quais usuários devem incluir ou excluir em arquivos de Serviço de Livro de Endereços com base em filtros de atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="518db-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="518db-151">Ele também tem opções para personalizar qual valor do número de telefone a ser incluído no arquivo do Livro de Endereços.</span><span class="sxs-lookup"><span data-stu-id="518db-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="518db-152">A **opção Restaurar Padrões** permite que os administradores restaurem as configurações do Serviço do Livro de Endereços para valores padrão.</span><span class="sxs-lookup"><span data-stu-id="518db-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="518db-153">O novo mapeamento de atributos do AD para nomes de campo OC diferentes funcionará apenas para Download de Arquivo do Livro de Endereços e não é suportado pela Consulta Web do Livro de Endereços.</span><span class="sxs-lookup"><span data-stu-id="518db-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="518db-154">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-154">Output</span></span>

<span data-ttu-id="518db-155">ABSConfig armazena a configuração do Serviço de Livro de Endereços no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="518db-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="518db-156">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-156">Purpose</span></span>

<span data-ttu-id="518db-157">ABSConfig fornece uma maneira rápida e fácil de personalizar Skype for Business Server Serviço de Livro de Endereços 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-158">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="518db-159">Computador</span><span class="sxs-lookup"><span data-stu-id="518db-159">Computer</span></span>

<span data-ttu-id="518db-160">ABSConfig só pode ser executado a partir de um computador ingressado em domínio que tenha Skype for Business Server 2015 instalado.</span><span class="sxs-lookup"><span data-stu-id="518db-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="518db-161">No caso do Skype for Business Server 2015, Edição Enterprise, essa ferramenta pode ser executado em todos os servidores Front-End que tenham o Serviço de Livro de Endereços habilitado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="518db-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front-End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="518db-162">Rede</span><span class="sxs-lookup"><span data-stu-id="518db-162">Network</span></span>

<span data-ttu-id="518db-163">O computador deve ser capaz de se conectar ao pool Front-End e banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="518db-163">The computer should be able to connect to the Front-End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="518db-164">Software</span><span class="sxs-lookup"><span data-stu-id="518db-164">Software</span></span>

<span data-ttu-id="518db-165">Os seguintes componentes de software devem ser instalados antes de executar a ferramenta ABSConfig:</span><span class="sxs-lookup"><span data-stu-id="518db-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="518db-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="518db-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="518db-167">Usuários</span><span class="sxs-lookup"><span data-stu-id="518db-167">Users</span></span>

<span data-ttu-id="518db-168">Administradores que têm as permissões necessárias para atualizar a implantação Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-169">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-169">Examples</span></span>

<span data-ttu-id="518db-170">ABSConfig pode ser iniciado digitandoABSConfig.exe **em** um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="518db-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="518db-171">Mostrado abaixo está a interface do usuário da ferramenta ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="518db-171">Shown below is the ABSConfig tool user interface.</span></span>

![A ABSConfig.exe ferramenta.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="518db-173">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-173">Summary</span></span>

<span data-ttu-id="518db-174">A ferramenta ABSConfig fornece aos administradores uma ferramenta rápida e fácil de usar para personalizar Skype for Business Server Serviço de Livro de Endereços 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="518db-175">Monitor de Serviço de Política de Largura de Banda</span><span class="sxs-lookup"><span data-stu-id="518db-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="518db-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="518db-177">A ferramenta Monitor do Serviço de Política de Largura de Banda destina-se a permitir que os administradores exibirem uma lista dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="518db-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="518db-178">Todos os serviços de Política de Largura de Banda Skype for Business Server 2015 (Autenticação e Núcleo) configurados na topologia</span><span class="sxs-lookup"><span data-stu-id="518db-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="518db-179">As conexões que cada serviço faz com outros serviços de Política de Largura de Banda e com os servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="518db-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="518db-180">Todos os links configurados no documento de configuração de rede e no uso da largura de banda em tempo real, conforme relatado por cada um dos serviços de Política de Largura de Banda</span><span class="sxs-lookup"><span data-stu-id="518db-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="518db-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-181">Description</span></span>

<span data-ttu-id="518db-182">A ferramenta Monitor do Serviço de Política de Largura de Banda é implementada como um aplicativo baseado em GUI.</span><span class="sxs-lookup"><span data-stu-id="518db-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="518db-183">Os administradores iniciam a ferramenta executando PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="518db-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="518db-184">Quando a ferramenta é iniciada, ela tenta descobrir a lista de serviços de Política de Largura de Banda na topologia.</span><span class="sxs-lookup"><span data-stu-id="518db-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="518db-185">Depois que a atualização inicial é feita, o painel à esquerda da janela é preenchido com uma lista de serviços agrupados pelos clusters aos quais pertencem.</span><span class="sxs-lookup"><span data-stu-id="518db-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="518db-186">Quando os administradores selecionam um determinado Serviço de Política de Largura de Banda, o painel à direita exibe as informações sobre esse serviço específico.</span><span class="sxs-lookup"><span data-stu-id="518db-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="518db-187">Esse painel também tem duas guias principais que exibem informações.</span><span class="sxs-lookup"><span data-stu-id="518db-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="518db-188">Guia Informações do Computador</span><span class="sxs-lookup"><span data-stu-id="518db-188">Machine Info Tab</span></span>

<span data-ttu-id="518db-189">A **guia Informações do** Computador mostra os detalhes do Serviço de Política de Largura de Banda selecionado e a lista e o estado de todas as conexões que são feitas pelo Serviço de Política de Largura de Banda selecionado para outros serviços.</span><span class="sxs-lookup"><span data-stu-id="518db-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="518db-190">Guia Informações de Topologia</span><span class="sxs-lookup"><span data-stu-id="518db-190">Topology Info Tab</span></span>

<span data-ttu-id="518db-191">A **guia Informações de Topologia** mostra uma lista de todos os links configurados nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="518db-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="518db-192">Para cada link, a capacidade de largura de banda de áudio e vídeo é exibida.</span><span class="sxs-lookup"><span data-stu-id="518db-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="518db-193">Além disso, a largura de banda atualmente utilizada é exibida, tanto em Kbps quanto como uma porcentagem da capacidade.</span><span class="sxs-lookup"><span data-stu-id="518db-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="518db-194">A ferramenta usa codificação de cores para realçar links que têm utilização próxima à capacidade, o que permite que os administradores isolem rapidamente esses links.</span><span class="sxs-lookup"><span data-stu-id="518db-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="518db-195">Se a ferramenta Monitor do Serviço de Política de Largura de Banda tiver falhas quando se conectar a qualquer um dos serviços de Política de Largura de Banda configurados, as informações nas guias **Informações** do Computador e Informações de **Topologia** não serão preenchidas.</span><span class="sxs-lookup"><span data-stu-id="518db-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="518db-196">No entanto, é possível que a ferramenta possa se conectar inicialmente, mas, posteriormente, perder sua conexão com o serviço.</span><span class="sxs-lookup"><span data-stu-id="518db-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="518db-197">Nesses casos, os administradores podem ver informações desatualizadas.</span><span class="sxs-lookup"><span data-stu-id="518db-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="518db-198">Há um carimbo **de** hora Última Atualização em cada uma das guias que podem permitir que os administradores vejam quando os dados foram atualizados pela última vez para um determinado Serviço de Política de Largura de Banda.</span><span class="sxs-lookup"><span data-stu-id="518db-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="518db-199">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-199">Output</span></span>

<span data-ttu-id="518db-200">Não há saída de linha de comando; a saída do programa está contida na interface do usuário gráfica principal (GUI).</span><span class="sxs-lookup"><span data-stu-id="518db-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-201">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-201">Purpose</span></span>

<span data-ttu-id="518db-202">O objetivo da ferramenta Monitor de Serviço de Política de Largura de Banda é permitir que os administradores visibilidade do estado de cada um dos serviços de Política de Largura de Banda definidos na topologia.</span><span class="sxs-lookup"><span data-stu-id="518db-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="518db-203">Além disso, os administradores podem ver o uso de largura de banda em tempo real para todos os links definidos no documento de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="518db-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-204">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-204">Requirements</span></span>

<span data-ttu-id="518db-205">A ferramenta Monitor de Serviço de Política de Largura de Banda precisa ser executado em um computador que faz parte da topologia Skype for Business Server de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="518db-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="518db-206">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-206">Summary</span></span>

<span data-ttu-id="518db-207">A ferramenta Monitor de Serviço de Política de Largura de Banda pode ser um recurso valioso para os administradores para que eles possam inspecionar o estado de todos os serviços de Política de Largura de Banda na topologia e, o mais importante, eles podem obter utilização de largura de banda em tempo real para os links definidos nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="518db-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="518db-208">Analisador de Utilização de Largura de Banda</span><span class="sxs-lookup"><span data-stu-id="518db-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="518db-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-209"><a name="bua"> </a></span></span>

<span data-ttu-id="518db-210">O Analisador de Utilização de Largura de Banda é uma ferramenta que cria relatórios sobre várias exibições de consumo de largura de banda pelos pontos de extremidade da UC em links WAN na rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="518db-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="518db-211">Esses relatórios podem ser usados para entender o padrão de consumo de largura de banda atual e para ajudar no planejamento da capacidade de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="518db-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="518db-212">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-212">Description</span></span>

<span data-ttu-id="518db-213">O Analisador de Utilização de Largura de Banda é implementado como um aplicativo baseado em GUI.</span><span class="sxs-lookup"><span data-stu-id="518db-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="518db-214">Essa ferramenta gera relatórios especificamente para utilização de áudio em toda a rede e ajuda no planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="518db-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="518db-215">Ele também itera na capacidade de largura de banda atribuída a vários links.</span><span class="sxs-lookup"><span data-stu-id="518db-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="518db-216">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-216">Output</span></span>

<span data-ttu-id="518db-217">O Analisador de Utilização de Largura de Banda fornece plotações gráficas de capacidade de largura de banda e utilização de áudio para todos os links WAN configurados no sistema.</span><span class="sxs-lookup"><span data-stu-id="518db-217">Bandwidth Utilization Analyzer provides graphical plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-218">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-218">Purpose</span></span>

<span data-ttu-id="518db-219">Em qualquer implantação de voz e vídeo, é fundamental monitorar e entender a tendência de utilização de largura de banda do tráfego de mídia em toda a rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="518db-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="518db-220">A ferramenta Analisador de Utilização de Largura de Banda permite que um administrador alcance exatamente isso.</span><span class="sxs-lookup"><span data-stu-id="518db-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="518db-221">Esta ferramenta faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-221">This tool does the following:</span></span>

- <span data-ttu-id="518db-222">Gera relatórios específicos para utilização de áudio em toda a rede</span><span class="sxs-lookup"><span data-stu-id="518db-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="518db-223">Ajuda com o planejamento e a iteração de capacidade mais eficazes na capacidade de largura de banda atribuída a vários links</span><span class="sxs-lookup"><span data-stu-id="518db-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="518db-224">O Analisador de Utilização de Largura de Banda pode gerar plotagens gráficas de relatórios de capacidade de largura de banda e utilização; eles são os seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="518db-225">Todos os links WAN na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="518db-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="518db-226">Filtrado por links WAN selecionados que foram escolhidos</span><span class="sxs-lookup"><span data-stu-id="518db-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="518db-227">Filtrado por links WAN que excederam a capacidade de link</span><span class="sxs-lookup"><span data-stu-id="518db-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="518db-228">Filtrado por links WAN que estão sub-utilizando a largura de banda provisionada</span><span class="sxs-lookup"><span data-stu-id="518db-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="518db-229">Filtrar por links WAN que tenham atingido níveis críticos (uma utilização de largura de banda maior que 90% da capacidade de largura de banda do link WAN)</span><span class="sxs-lookup"><span data-stu-id="518db-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="518db-230">Filtrado por tipo de link WAN — links de site de rede, links interregionais e links em um site</span><span class="sxs-lookup"><span data-stu-id="518db-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="518db-231">Filtrada por região de rede</span><span class="sxs-lookup"><span data-stu-id="518db-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="518db-232">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="518db-232">Applications</span></span>

<span data-ttu-id="518db-233">O Analisador de Utilização de Largura de Banda tem os dois aplicativos a seguir (ferramentas):</span><span class="sxs-lookup"><span data-stu-id="518db-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="518db-234">**WanLinkLogCollector.exe** Essa ferramenta permite que seu usuário inser as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="518db-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="518db-235">**BandwidthUtilizationAnalyzer.xlsm** Um Microsoft Excel de software de planilha é automaticamente WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="518db-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="518db-236">Esse aplicativo permite que o usuário aplique filtros ao relatório, conforme mostrado posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="518db-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="518db-237">Fases do Uso do Analisador de Utilização de Largura de Banda</span><span class="sxs-lookup"><span data-stu-id="518db-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="518db-238">Há duas fases ao usar o Analisador de Utilização de Largura de Banda:</span><span class="sxs-lookup"><span data-stu-id="518db-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="518db-239">Coletar logs, que são executados usando WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="518db-239">Collect logs, which are performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="518db-240">Personalizar relatórios, que são executados usando BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="518db-240">Customize reports, which are performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="518db-241">É recomendável que BandwidthUtilizationAnalyzer.xlsseja lançado manualmente pelos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="518db-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="518db-242">Iniciando o Analisador de Utilização de Largura de Banda</span><span class="sxs-lookup"><span data-stu-id="518db-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="518db-243">Inicie WanLinkLogCollector.exe no prompt de comando ou usando Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="518db-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="518db-244">**Usando WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="518db-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="518db-245">Há três etapas para usar WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="518db-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="518db-246">**Registrar a linha do tempo** Forneça a linha do tempo para a que o relatório precisa ser gerado</span><span class="sxs-lookup"><span data-stu-id="518db-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="518db-247">**Especificar os diretórios de arquivos** Fornecer informações sobre o local do arquivo</span><span class="sxs-lookup"><span data-stu-id="518db-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="518db-248">**Coletar os logs e iniciar o visualizador de relatórios** Execute o comando para gerar o relatório</span><span class="sxs-lookup"><span data-stu-id="518db-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="518db-249">Etapa 1 - Registrar a linha do tempo</span><span class="sxs-lookup"><span data-stu-id="518db-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="518db-250">Registrar a linha do tempo permite que o usuário da ferramenta especifique o seguinte, conforme mostrado na figura abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="518db-251">**Data de início** Esta é a data de início da linha do tempo para a quais o relatório deve ser gerado; por exemplo, 1º de agosto de 2010.</span><span class="sxs-lookup"><span data-stu-id="518db-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="518db-252">**Data de término** Esta é a data de término da linha do tempo para a quais o relatório deve ser gerado; por exemplo, 30 de setembro de 2010.</span><span class="sxs-lookup"><span data-stu-id="518db-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Datas de início e término na Utilização de Largura de Banda A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="518db-254">Etapa 2 - Especificar os diretórios de arquivos</span><span class="sxs-lookup"><span data-stu-id="518db-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="518db-255">Os diretórios de arquivos a seguir podem ser especificados pelo usuário, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="518db-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="518db-256">**Local dos arquivos de log do servidor** O local da pasta onde os logs do servidor de política de largura de banda são armazenados.</span><span class="sxs-lookup"><span data-stu-id="518db-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="518db-257">Isso normalmente está na \<fileserver\> \\<fe \> \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="518db-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="518db-258">**Local de armazenamento de arquivo temporário** O local do arquivo temporário onde arquivos intermediários são armazenados enquanto o relatório está sendo gerado.</span><span class="sxs-lookup"><span data-stu-id="518db-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Diretórios de arquivos no Anal de Utilização de Largura de Banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="518db-260">Certifique-se de que o acesso de arquivo suficiente aos logs do servidor e à pasta de armazenamento de arquivos temporários seja fornecido ao usuário da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="518db-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="518db-261">Etapa 3 - Coletar os logs e iniciar o visualizador de relatórios</span><span class="sxs-lookup"><span data-stu-id="518db-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="518db-262">Para coletar os logs e iniciar o visualizador de relatórios, clique em **Executar** conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="518db-263">Esta etapa coleta os dados necessários.</span><span class="sxs-lookup"><span data-stu-id="518db-263">This step collects the required data.</span></span>

![Coletando dados na Análise de Utilização de Largura de Banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="518db-265">Quando a validação de entrada é bem-sucedida, a mensagem mostrada abaixo é exibida.</span><span class="sxs-lookup"><span data-stu-id="518db-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Logs coletados notificação no Utili de Largura de Banda](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="518db-267">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="518db-267">Click **OK**.</span></span> <span data-ttu-id="518db-268">BandwidthUtilizationAnalyzer.xlsm é iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="518db-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="518db-269">Siga as instruções na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="518db-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="518db-270">Para obter detalhes, **consulte Using BandwidthUtilizationAnalyzer.xlsm** na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="518db-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="518db-271">Usando BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="518db-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="518db-272">Quando BandwidthUtilizationAnalyzer.xlsm é iniciado automaticamente, clique **em Atualizar,** conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="518db-274">Quando uma pasta de arquivo for aberta, selecione consolidated.csv do local especificado na caixa de mensagem, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="518db-275">Ele também mostra o local como **C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="518db-275">It also shows the location as **C:\Temp**.</span></span>

     ![Abrindo uma pasta em BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="518db-277">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="518db-277">Click **Import**.</span></span>

4. <span data-ttu-id="518db-278">O plot gráfico é gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="518db-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="518db-279">Ele está disponível quando o ponteiro de trabalho no plano de fundo desaparece.</span><span class="sxs-lookup"><span data-stu-id="518db-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Aplicando filtros no Report View.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="518db-281">Aplicando filtros à exibição de relatório</span><span class="sxs-lookup"><span data-stu-id="518db-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="518db-282">Os filtros que podem ser aplicados à exibição de relatório, conforme mostrado abaixo, são descritos da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="518db-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Aplicando filtros no Report View.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="518db-284">**Nome** Filtrar por links WAN (o filtro está no lado direito do gráfico).</span><span class="sxs-lookup"><span data-stu-id="518db-284">**Name** Filter by WAN links (the filter is on the right side of the graph).</span></span> <span data-ttu-id="518db-285">O prefixo indica os seguintes tipos de link; consulte a caixa vertical (azul):</span><span class="sxs-lookup"><span data-stu-id="518db-285">The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="518db-286">**S Site** O link WAN de um site de rede para uma região de rede</span><span class="sxs-lookup"><span data-stu-id="518db-286">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="518db-287">**IS Inter-Site** O link WAN entre dois sites de rede</span><span class="sxs-lookup"><span data-stu-id="518db-287">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="518db-288">**R Inter-Região** O link WAN entre duas regiões de rede</span><span class="sxs-lookup"><span data-stu-id="518db-288">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="518db-289">**Limite excedido** Filtrar por links WAN cuja utilização de largura de banda é maior do que a capacidade de largura de banda</span><span class="sxs-lookup"><span data-stu-id="518db-289">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="518db-290">**Níveis críticos** Filtrar por links WAN cuja utilização de largura de banda atingiu 90% ou mais do que a capacidade de largura de banda</span><span class="sxs-lookup"><span data-stu-id="518db-290">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="518db-291">**Subutilizou** Filtrar por links WAN cuja utilização de largura de banda tenha sido inferior a 25% da capacidade de largura de banda</span><span class="sxs-lookup"><span data-stu-id="518db-291">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="518db-292">**Tipo de link** Filtrar pelos seguintes tipos de links WAN:</span><span class="sxs-lookup"><span data-stu-id="518db-292">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="518db-293">**Tipo de site de** rede</span><span class="sxs-lookup"><span data-stu-id="518db-293">**Network site** type</span></span>

   - <span data-ttu-id="518db-294">**Tipo entre sites**</span><span class="sxs-lookup"><span data-stu-id="518db-294">**Inter-site** type</span></span>

   - <span data-ttu-id="518db-295">**Tipo de link entre regiões**</span><span class="sxs-lookup"><span data-stu-id="518db-295">**Inter-Region link** type</span></span>

6. <span data-ttu-id="518db-296">**Região** Filtrar por região de rede</span><span class="sxs-lookup"><span data-stu-id="518db-296">**Region** Filter by network region</span></span>

<span data-ttu-id="518db-297">As figuras a seguir mostram os filtros descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="518db-297">The following figures show the previously described filters.</span></span>

<span data-ttu-id="518db-298">Filtrar por **Nome**.</span><span class="sxs-lookup"><span data-stu-id="518db-298">Filter by **Name**.</span></span> <span data-ttu-id="518db-299">Selecione a lista de links que precisam ser exibidos no gráfico.</span><span class="sxs-lookup"><span data-stu-id="518db-299">Select the list of links that need to be displayed in the graph.</span></span>

![Filtragem por Nome em BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="518db-301">Filtrar **por limite excedido**.</span><span class="sxs-lookup"><span data-stu-id="518db-301">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="518db-302">Selecione **True** para impor o filtro.</span><span class="sxs-lookup"><span data-stu-id="518db-302">Select **True** to enforce the filter.</span></span>

![Filtragem por Limite Excedido.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="518db-304">Filtrar por **níveis críticos**.</span><span class="sxs-lookup"><span data-stu-id="518db-304">Filter by **Critical levels**.</span></span> <span data-ttu-id="518db-305">Selecione **True** para impor o filtro.</span><span class="sxs-lookup"><span data-stu-id="518db-305">Select **True** to enforce the filter.</span></span>

![Filtragem por níveis críticos.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="518db-307">Filtrar **por Subutilizou**.</span><span class="sxs-lookup"><span data-stu-id="518db-307">Filter by **Under utilized**.</span></span> <span data-ttu-id="518db-308">Selecione **True** para impor o filtro.</span><span class="sxs-lookup"><span data-stu-id="518db-308">Select **True** to enforce the filter.</span></span>

![Filtragem por Subutilizou.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="518db-310">Filtrar por **Tipo de Link**.</span><span class="sxs-lookup"><span data-stu-id="518db-310">Filter by **Link Type**.</span></span> <span data-ttu-id="518db-311">Selecione o tipo ou os tipos que precisam ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="518db-311">Select the type or types that need to be displayed.</span></span>

![Filtragem por Tipo de Link.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="518db-313">Filtrar por **Região**.</span><span class="sxs-lookup"><span data-stu-id="518db-313">Filter by **Region**.</span></span> <span data-ttu-id="518db-314">Selecione uma lista de regiões cujos links precisam ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="518db-314">Select a list of regions whose links need to be displayed.</span></span>

![Filtragem por Região.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="518db-316">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-316">Requirements</span></span>

- <span data-ttu-id="518db-317">O .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="518db-317">The .NET Framework 3.5</span></span>

- <span data-ttu-id="518db-318">Microsoft Excel 2010 ou Excel 2007</span><span class="sxs-lookup"><span data-stu-id="518db-318">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="518db-319">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-319">Summary</span></span>

<span data-ttu-id="518db-320">O Analisador de Utilização de Largura de Banda é usado para plotar a utilização de largura de banda de áudio para o tráfego de UC na rede.</span><span class="sxs-lookup"><span data-stu-id="518db-320">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="518db-321">Essa ferramenta também pode ser usada para relatar a utilização da largura de banda de vídeo na rede.</span><span class="sxs-lookup"><span data-stu-id="518db-321">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="518db-322">Chamar Parkometer</span><span class="sxs-lookup"><span data-stu-id="518db-322">Call Parkometer</span></span>
<span data-ttu-id="518db-323"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-323"><a name="callpark"> </a></span></span>

<span data-ttu-id="518db-324">Call Parkometer é um aplicativo de linha de comando que fornece acesso fácil ao banco de dados de órbita do Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="518db-324">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="518db-325">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-325">Description</span></span>

<span data-ttu-id="518db-326">Call Parkometer é uma ferramenta para rastrear chamadas estacionadas no momento.</span><span class="sxs-lookup"><span data-stu-id="518db-326">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="518db-327">Ele também coleta estatísticas sobre órbitas e uso do Servidor de Estacionamento de Chamada (CPS).</span><span class="sxs-lookup"><span data-stu-id="518db-327">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="518db-328">Essa ferramenta de linha de comando fornece acesso de leitura e gravação à órbita cps SQL Server banco de dados de um computador local ou conectado remotamente.</span><span class="sxs-lookup"><span data-stu-id="518db-328">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="518db-329">Todas as opções são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="518db-329">All options are mutually exclusive.</span></span> <span data-ttu-id="518db-330">A sintaxe de linha de comando é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-330">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="518db-331">**-o** parameter — lista todos os intervalos de órbita configurados para esse pool.</span><span class="sxs-lookup"><span data-stu-id="518db-331">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="518db-332">**-n** parameter — lista todas as órbitas usadas no momento neste pool.</span><span class="sxs-lookup"><span data-stu-id="518db-332">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="518db-333">As informações exibidas são as seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-333">The information displayed is as follows:</span></span>

  - <span data-ttu-id="518db-334">URI (Identificador de Recurso Uniforme SIP) do parkee e do parker.</span><span class="sxs-lookup"><span data-stu-id="518db-334">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="518db-335">Nome do host do CPS onde a chamada está estacionada.</span><span class="sxs-lookup"><span data-stu-id="518db-335">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="518db-336">Carimbo de data/hora de quando a chamada foi estacionada.</span><span class="sxs-lookup"><span data-stu-id="518db-336">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="518db-337">**-f** parameter — lista o número de órbitas atualmente livres no pool.</span><span class="sxs-lookup"><span data-stu-id="518db-337">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="518db-338">**-r \<n\>** parameter — lista as \<n\> últimas chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="518db-338">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="518db-339">As informações exibidas são as seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-339">The information displayed is as follows:</span></span>

  - <span data-ttu-id="518db-340">URI SIP parkee.</span><span class="sxs-lookup"><span data-stu-id="518db-340">Parkee SIP URI.</span></span>

  - <span data-ttu-id="518db-341">URI SIP do Parker.</span><span class="sxs-lookup"><span data-stu-id="518db-341">Parker SIP URI.</span></span>

  - <span data-ttu-id="518db-342">Nome do host do CPS onde a chamada foi estacionada.</span><span class="sxs-lookup"><span data-stu-id="518db-342">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="518db-343">Carimbo de data/hora de quando a chamada foi recuperada ou retirada.</span><span class="sxs-lookup"><span data-stu-id="518db-343">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="518db-344">**-t \<n\>** parameter - testa a reserva de uma órbita no banco de dados para mostrar a aleatoriedade dos números de órbita atribuídos.</span><span class="sxs-lookup"><span data-stu-id="518db-344">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="518db-345">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-345">Output</span></span>

<span data-ttu-id="518db-346">Dependendo dos parâmetros de entrada especificados em um prompt de comando, o Estacionamento de Chamada exibe a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="518db-346">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="518db-347">Todos os intervalos de órbita configurados para este pool</span><span class="sxs-lookup"><span data-stu-id="518db-347">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="518db-348">Chamadas estacionadas no momento</span><span class="sxs-lookup"><span data-stu-id="518db-348">Currently parked calls</span></span>

- <span data-ttu-id="518db-349">Número de órbitas livres (disponíveis)</span><span class="sxs-lookup"><span data-stu-id="518db-349">Number of free (available) orbits</span></span>

- <span data-ttu-id="518db-350">Chamadas estacionadas recentemente</span><span class="sxs-lookup"><span data-stu-id="518db-350">Recently parked calls</span></span>

- <span data-ttu-id="518db-351">Órbitas reservadas para testar valores de órbita uniforme e aleatória</span><span class="sxs-lookup"><span data-stu-id="518db-351">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-352">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-352">Purpose</span></span>

<span data-ttu-id="518db-353">O objetivo da ferramenta CPS é fornecer acesso de linha de comando ao banco de dados CPS.</span><span class="sxs-lookup"><span data-stu-id="518db-353">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="518db-354">O administrador pode exibir o uso do CPS e determinar o número de órbitas atribuídas a um pool.</span><span class="sxs-lookup"><span data-stu-id="518db-354">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-355">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-355">Requirements</span></span>

<span data-ttu-id="518db-356">Não há requisitos se essa ferramenta for executado no mesmo computador que está executando CPS.</span><span class="sxs-lookup"><span data-stu-id="518db-356">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="518db-357">Se essa ferramenta for executado em um computador remoto, o banco de dados SQL Server usado pelo Skype for Business Server 2015 deve ser configurado para permitir o acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="518db-357">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="518db-358">O Parkometer de chamada deve ser configurado com uma cadeia de SQL Server de conexão de banco de dados para se conectar ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="518db-358">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="518db-359">Essa SQL Server de conexão de banco de dados é definida no arquivo de configuração, **parkometer.exe.config**. Ele deve ser colocado no mesmo diretório onde parkometer.exe está localizado.</span><span class="sxs-lookup"><span data-stu-id="518db-359">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="518db-360">O arquivo XML a seguir é um exemplo de um parkometer.exe.config. Os parâmetros que devem ser configurados são nome de usuário (por exemplo, mydomain\Administrator), senha (por exemplo, mypassword) e nome do host (por exemplo, myserver).</span><span class="sxs-lookup"><span data-stu-id="518db-360">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="518db-361">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-361">Examples</span></span>

<span data-ttu-id="518db-362">Intervalos de órbita implantados: o parâmetro -o lista todos os intervalos de órbita configurados para esse pool, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="518db-362">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Intervalos de órbita no Estacionamento de Chamada.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="518db-364">Chamadas estacionadas no momento: o parâmetro -n lista todas as órbitas usadas no momento neste pool, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="518db-364">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Chamadas estacionadas no estacionamento de chamadas.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="518db-366">Número de órbitas livres: o parâmetro -f lista o número de órbitas atualmente livres no pool, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="518db-366">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Órbitas livres no Estacionamento de Chamada.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="518db-368">Chamadas estacionadas recentemente: o parâmetro -r \<n\> lista as últimas chamadas \<n\> estacionadas, conforme mostrado</span><span class="sxs-lookup"><span data-stu-id="518db-368">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Chamadas estacionadas recentemente no Estacionamento de Chamadas.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="518db-370">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span><span class="sxs-lookup"><span data-stu-id="518db-370">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testar reservas de órbita no Estacionamento de Chamada.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="518db-372">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-372">Summary</span></span>

<span data-ttu-id="518db-373">Call Parkometer é uma ferramenta de linha de comando que fornece informações detalhadas sobre o Servidor de Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="518db-373">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="518db-374">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="518db-374">DBAnalyze</span></span>
<span data-ttu-id="518db-375"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-375"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="518db-376">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-376">Description</span></span>

<span data-ttu-id="518db-377">DBAnalyze é uma ferramenta de linha de comando que ajuda os administradores a coletar relatórios de análise sobre os bancos de dados Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-377">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="518db-378">DBAnalyze tem os seguintes modos: diagnóstico, dados do usuário, conferência, MCUs e fragmentação de disco:</span><span class="sxs-lookup"><span data-stu-id="518db-378">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="518db-379">**Modo de diagnóstico** Cria um relatório que inclui informações sobre tabelas (número de registros, fragmentação, tamanho dos dados e tamanho do índice), tamanhos de arquivos de dados e log, o último tempo de back-up, distribuição de contatos entre servidores que estão executando o servidor de comunicações do Microsoft Office, o número médio de permissões, contatos, contêineres, assinaturas, publicações, pontos de extremidade por usuário, usuários que não podem ser roteados, o número médio de conferências organizadas por usuário, conferências agendadas, conferências ativas e a versão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="518db-379">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="518db-380">Executar o modo de diagnóstico pode afetar o desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="518db-380">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="518db-381">**Modo de dados do usuário** Relata dados de contato, contêiner, assinatura, publicação, permissão e grupo de contatos para um usuário especificado ou para usuários que têm esse usuário em suas listas de contatos e permissões.</span><span class="sxs-lookup"><span data-stu-id="518db-381">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="518db-382">Esse modo também relata dados de resumo para conferências que um usuário organiza ou é convidado.</span><span class="sxs-lookup"><span data-stu-id="518db-382">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="518db-383">**Modo de conferência** Relata dados detalhados para uma conferência específica, incluindo todos os detalhes de tempo de agendamento para a conferência, a lista de convidados, a lista de tipos de mídia permitidos para a conferência, MCUs ativos (unidades de controle de vários pontos), a lista de participantes ativos e o estado de sinalização de cada participante.</span><span class="sxs-lookup"><span data-stu-id="518db-383">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="518db-384">**Decodificar a ID da Reunião** Decodifica uma ID de reunião PSTN (rede telefônica pública comutado) especificada pela opção **/pstnid,** mas que não se conecta ao back-end para obter informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="518db-384">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="518db-385">**Resolver conferência** Decodifica uma ID de reunião PSTN especificada pela opção **/pstnid** e exibe informações sobre a conferência indicada pela ID.</span><span class="sxs-lookup"><span data-stu-id="518db-385">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="518db-386">**Modo MCUs** Relata a ID, o tipo de mídia, a URL, o status da pulsação, a carga de conferência e a carga do participante para cada MCU no pool.</span><span class="sxs-lookup"><span data-stu-id="518db-386">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="518db-387">**Modo de fragmentação de disco** Exibe o status de fragmentação de todos os discos.</span><span class="sxs-lookup"><span data-stu-id="518db-387">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="518db-388">Essa ferramenta pode ser usada para diagnosticar vários problemas ou para ajudar os administradores com o planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="518db-388">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="518db-389">Por exemplo, se a maioria dos usuários que estão no servidor A escolher usuários no servidor B como seus contatos, o administrador poderá mover os usuários no servidor A para o servidor B para reduzir o tráfego entre servidores.</span><span class="sxs-lookup"><span data-stu-id="518db-389">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="518db-390">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-390">Output</span></span>

<span data-ttu-id="518db-391">Esta ferramenta saídas de relatórios predefinidos sobre o banco de dados Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-391">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="518db-392">**Caminho**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="518db-392">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-393">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-393">Purpose</span></span>

<span data-ttu-id="518db-394">Para instalar Dbanalyze.exe, copie-o para uma pasta local e execute a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="518db-394">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="518db-395">Para usar a ferramenta, execute o seguinte comando na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="518db-395">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="518db-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` As descrições das opções de linha de comando são mostradas abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Opções de linha de comando para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="518db-398">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-398">Requirements</span></span>

 <span data-ttu-id="518db-399">**Computador** DBAnalyze só pode ser executado a partir de um computador ingressado em domínio que tenha Skype for Business Server 2015 instalado.</span><span class="sxs-lookup"><span data-stu-id="518db-399">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="518db-400">**Rede** O computador deve ser capaz de se conectar ao banco de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="518db-400">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="518db-401">**Os** Skype for Business Server de software 2015 devem ser instalados antes de executar o DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="518db-401">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="518db-402">**Usuários** A tabela a seguir mostra os administradores que têm as permissões necessárias para acessar Skype for Business Server bancos de dados 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-402">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Tabela permissões para Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="518db-404">Uma conta de administrador local é necessária para **o modo /report:disk.**</span><span class="sxs-lookup"><span data-stu-id="518db-404">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-405">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-405">Examples</span></span>

<span data-ttu-id="518db-406">Veja a seguir exemplos de comandos Dbanalyze.exe válidos:</span><span class="sxs-lookup"><span data-stu-id="518db-406">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="518db-407">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-407">Summary</span></span>

<span data-ttu-id="518db-408">O DBAnalyzer fornece aos administradores uma análise rápida e fácil Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-408">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="518db-409">Importar Armazenamento dados de serviço</span><span class="sxs-lookup"><span data-stu-id="518db-409">Import Storage Service Data</span></span>
<span data-ttu-id="518db-410"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-410"><a name="Issd"> </a></span></span>

<span data-ttu-id="518db-411">A ferramenta de kit de recursos ImportStorageServiceData permite a reportação de dados de Fila e Ponto de Extremidade que foram liberados do LYSS (serviço de Armazenamento) de volta para o serviço Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="518db-411">The ImportStorageServiceData resource kit tool allows for reimporting Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="518db-412">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-412">Description</span></span>

<span data-ttu-id="518db-413">Os dados liberados do serviço Armazenamento podem ter sido automáticos (periódicos) com base no status do Item da Fila ou no tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="518db-413">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="518db-414">Isso pode ter ocorrido devido à invocação manual do cmdlet de failover do pool ou do cmdlet StorageServiceFullFlush (que o cmdlet de failover do pool invoca).</span><span class="sxs-lookup"><span data-stu-id="518db-414">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="518db-415">Observe que o ideal é que os dados não sejam reemportados se qualquer um dos tamanhos de banco de dados do LYSS (Serviço de Armazenamento) nas extremidades front-ends estiver acima do nível normal, pois isso provavelmente fará com que mais dados sejam exportados de volta. Além disso, quaisquer problemas que poderiam ter contribuído para erros que causaram o crescimento da Fila de Serviços Armazenamento do Armazenamento primeiro devem ser resolvidos Exchange (por exemplo, erros de ponto de extremidade, problemas de rede ou outros problemas).</span><span class="sxs-lookup"><span data-stu-id="518db-415">Note that data should ideally not be reimported if any of the Storage Service (LYSS ) database sizes on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems that could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="518db-416">**Cenário 1: durante** o failover do pool, os arquivos podem ser liberados do serviço de armazenamento para cada front-end.</span><span class="sxs-lookup"><span data-stu-id="518db-416">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="518db-417">Depois que o failover for concluído, a ferramenta deverá ser executado para reaportar os dados.</span><span class="sxs-lookup"><span data-stu-id="518db-417">After failover is completed, the tool should be run to reimport the data.</span></span>

 <span data-ttu-id="518db-418">**Cenário 2:** os dados são liberados automaticamente todos os dias ou em resposta ao banco de dados do serviço Armazenamento excedendo determinados limites de tamanho (por exemplo, 60%, 80%, 90% completo).</span><span class="sxs-lookup"><span data-stu-id="518db-418">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds (for example 60%, 80%, 90% full).</span></span> <span data-ttu-id="518db-419">Esses dados liberados automaticamente devem ser reemportados rotineiramente pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="518db-419">This automatically flushed data should be reimported routinely by the administrator.</span></span> <span data-ttu-id="518db-420">Na situação acima, se o pacote SCOM de monitoramento não for implantado, haverá eventos para o serviço Skype for Business Server Armazenamento relacionados aos dados que estão sendo liberados do serviço Armazenamento de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="518db-420">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="518db-421">IDs de evento de 32075 (operação de liberação total iniciada), 32076 (liberação total concluída), 32082 (liberação de nível de manutenção iniciada), 32083 (liberação de nível de manutenção concluída), 32089 (flush ocorreu devido ao preenchimento do banco de dados).</span><span class="sxs-lookup"><span data-stu-id="518db-421">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="518db-422">Observe que essas IDs de evento correspondem à versão RTM.</span><span class="sxs-lookup"><span data-stu-id="518db-422">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="518db-423">Quando um administrador vê esses eventos, significa que há arquivos que foram liberados. Esses dados devem ser importados rotineiramente usando essa ferramenta, por exemplo, uma vez por semana.</span><span class="sxs-lookup"><span data-stu-id="518db-423">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="518db-424">Para a versão do Serviço Online, se o pacote SCOM de monitoramento de saúde para Skype for Business Server for implantado, haverá novos alertas que podem ser acionados que solicitam que o administrador reporte os dados liberados de volta para o serviço Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="518db-424">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts that may be raised which ask the administrator to reimport the flushed data back into Storage Service.</span></span> <span data-ttu-id="518db-425">Haverá um evento correspondente no log de eventos no servidor Front-End que disparou o alerta.</span><span class="sxs-lookup"><span data-stu-id="518db-425">There will be a corresponding event in the event log on the Front-End server that triggered the alert.</span></span> <span data-ttu-id="518db-426">O evento dará uma descrição do caminho Pai no qual os arquivos de dados liberados estão localizados e quantos arquivos há que atendem aos critérios de alerta.</span><span class="sxs-lookup"><span data-stu-id="518db-426">The event will give a description of the Parent path under which the flushed data files are located, and how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="518db-427">O critério de alerta é que há X ou mais arquivos no caminho pai específico que têm pelo menos dias Y (onde X e Y são predefinidos no StorageService, mas podem ser substituídos alterando o arquivo APPCONFIG.) Dois exemplos de eventos que podem disparar o alerta de saúde são mostrados abaixo, com a diferença sendo seu caminho pai.</span><span class="sxs-lookup"><span data-stu-id="518db-427">The alert criteria is that there are X or more files under the particular parent path that are at least Y days old (where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events that can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="518db-428">Uma possibilidade está em compartilhamento de arquivos de serviço Web, enquanto a outra possibilidade é o diretório de Dados de Aplicativo local de cada front-end.</span><span class="sxs-lookup"><span data-stu-id="518db-428">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="518db-429">(por exemplo, c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService).</span><span class="sxs-lookup"><span data-stu-id="518db-429">(for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService).</span></span> <span data-ttu-id="518db-430">Em seguida, o administrador executará essa ferramenta de reskit.</span><span class="sxs-lookup"><span data-stu-id="518db-430">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="518db-431">Essa ferramenta aumentará a carga de CPU e E/S no front-end em que está sendo executada e em outros front-ends, na situação em que os dados não são de propriedade do front-end em que a ferramenta é executada.</span><span class="sxs-lookup"><span data-stu-id="518db-431">This tool will increase CPU and IO load on the front end it is running on, and other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="518db-432">Recomendamos executar essa ferramenta quando as front ends não estão sob carga pesada de CPU e E/S, por exemplo, fora do horário de pico.</span><span class="sxs-lookup"><span data-stu-id="518db-432">We recommend running this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="518db-433">Em segundo lugar, essa ferramenta pode de 2 a 3 minutos para importar um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="518db-433">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="518db-434">Lembre-se disso ao estimar por quanto tempo a ferramenta estará em execução.</span><span class="sxs-lookup"><span data-stu-id="518db-434">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="518db-435">O arquivo de log detalhado gerado pela ferramenta será exibido por padrão no Arquivo Store.</span><span class="sxs-lookup"><span data-stu-id="518db-435">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="518db-436">Exclua-o se não houver erros relatados, pois o arquivo de log pode ter dezenas de MB ou mais.</span><span class="sxs-lookup"><span data-stu-id="518db-436">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Exemplo Armazenamento log de eventos do Servidor.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="518db-438">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-438">Requirements</span></span>

<span data-ttu-id="518db-439">Instale as ferramentas Skype for Business Server Kit de Recursos 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-439">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="518db-440">A ferramenta é executado em máquinas ingressadas no domínio em que Skype for Business Server e Skype for Business Server Shell de Gerenciamento estão instalados.</span><span class="sxs-lookup"><span data-stu-id="518db-440">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="518db-441">A ferramenta usa um cmdlet do shell de gerenciamento para identificar todos os servidores Front-End no pool.</span><span class="sxs-lookup"><span data-stu-id="518db-441">The tool uses a cmdlet from the management shell to identify all the Front-End servers in the pool.</span></span> <span data-ttu-id="518db-442">Em segundo lugar, a ferramenta deve ser executada de um computador no pool que tenha o banco de **dados RtcLocal** instalado.</span><span class="sxs-lookup"><span data-stu-id="518db-442">Secondly, the tool must be executed from a machine in the pool that has the **RtcLocal** database installed.</span></span> <span data-ttu-id="518db-443">Esse banco de dados é usado pela ferramenta para recuperar o local do compartilhamento de arquivos WEBSERVICE para o pool.</span><span class="sxs-lookup"><span data-stu-id="518db-443">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="518db-444">Além disso, antes de usar Front-End ferramenta, cada servidor Front-End deve primeiro habilitar o Windows PowerShell Remoting usando **Enable-PSRemoting** em cada servidor Front-End e o computador de onde a ferramenta é executada.</span><span class="sxs-lookup"><span data-stu-id="518db-444">Additionally, before using the tool, each Front-End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front-End server, and the machine that the tool is executed from.</span></span> <span data-ttu-id="518db-445">Caso contrário, Windows PowerShell comandos remotos desta ferramenta falharão.</span><span class="sxs-lookup"><span data-stu-id="518db-445">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="518db-446">Windows PowerShell O remoting pode ser desligado em todos os Front-End no pool depois que ele for concluído.</span><span class="sxs-lookup"><span data-stu-id="518db-446">Windows PowerShell Remoting can be turned off on all Front-End servers in the pool after it is finished.</span></span> <span data-ttu-id="518db-447">Por fim, a conta ou a credencial que invoca a ferramenta deve ter permissão de leitura/gravação para o compartilhamento de arquivos do webservice para o pool em que está executando essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="518db-447">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="518db-448">Caso contrário, a ferramenta falhará com erros de Permissão de E/S.</span><span class="sxs-lookup"><span data-stu-id="518db-448">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="518db-449">No Windows Server 2012, Windows PowerShell Remoting está habilitado por padrão, mas não no sistema operacional Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="518db-449">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-450">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-450">Examples</span></span>

```console
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
```

## <a name="lcssync"></a><span data-ttu-id="518db-451">LCSSync</span><span class="sxs-lookup"><span data-stu-id="518db-451">LCSSync</span></span>
<span data-ttu-id="518db-452"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-452"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="518db-453">A ferramenta LCSSync ajuda a implantar Skype for Business Server software de comunicação 2015 em um ambiente de várias florestas.</span><span class="sxs-lookup"><span data-stu-id="518db-453">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="518db-454">Essa ferramenta é usada para sincronizar usuários e grupos de diferentes florestas de usuários como um objeto de contato dos Serviços de Domínio do Active Directory para uma floresta central onde o Skype for Business Server 2015 está instalado.</span><span class="sxs-lookup"><span data-stu-id="518db-454">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="518db-455">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-455">Description</span></span>

 <span data-ttu-id="518db-456">O LCSSync usa os objetos de contato sincronizados dos Serviços de Domínio do Active Directory na floresta central para habilitar os usuários para Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="518db-456">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="518db-457">Para fornecer uma única assinatura, a conta de usuário principal deve ser mapeada para o objeto de contato serviços de domínio do Active Directory na floresta central para Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-457">To provide single sign in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="518db-458">Essa ferramenta ajuda a executar esse mapeamento.</span><span class="sxs-lookup"><span data-stu-id="518db-458">This tool helps perform that mapping.</span></span> <span data-ttu-id="518db-459">Esta ferramenta fornece modelos para a criação de Agentes de Gerenciamento no Servidor de Integração de Identidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="518db-459">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="518db-460">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-460">Summary</span></span>

<span data-ttu-id="518db-461">A ferramenta LCSSync ajuda a implantar o Skype for Business Server 2015 em um ambiente de várias florestas.</span><span class="sxs-lookup"><span data-stu-id="518db-461">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="518db-462">Console do usuário de lookup</span><span class="sxs-lookup"><span data-stu-id="518db-462">Lookup User Console</span></span>
<span data-ttu-id="518db-463"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-463"><a name="LUC"> </a></span></span>

<span data-ttu-id="518db-464">A ferramenta LookupUserConsole exibe informações de roteamento Skype for Business Server internas sobre usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="518db-464">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="518db-465">Essas informações podem ser úteis para o suporte pessoal da Microsoft no diagnóstico de problemas de implantação e roteamento.</span><span class="sxs-lookup"><span data-stu-id="518db-465">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="518db-466">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-466">Description</span></span>

 <span data-ttu-id="518db-467">A execução LookupUserConsole.exe abrirá um prompt de comando que aceita endereços SIP e tenta exibir informações de roteamento Skype for Business Server internas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="518db-467">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="518db-468">Digite **exit** para sair da ferramenta LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="518db-468">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-469">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-469">Requirements</span></span>

<span data-ttu-id="518db-470">Instale o Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="518db-470">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="518db-471">A ferramenta é executado em máquinas ingressadas no domínio onde Skype for Business Server está instalada.</span><span class="sxs-lookup"><span data-stu-id="518db-471">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-472">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-472">Examples</span></span>

<span data-ttu-id="518db-473">C:\Program Files\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="518db-473">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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
```

## <a name="msturnping"></a><span data-ttu-id="518db-474">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="518db-474">MsTurnPing</span></span>
<span data-ttu-id="518db-475"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-475"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="518db-476">A ferramenta MSTurnPing permite que um administrador do software de comunicações Skype for Business Server 2015 verifique o status dos servidores que executam a Borda de Áudio/Vídeo, os serviços de Autenticação de Áudio/Vídeo e os servidores que executam os Serviços de Política de Largura de Banda na topologia.</span><span class="sxs-lookup"><span data-stu-id="518db-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="518db-477">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-477">Description</span></span>

<span data-ttu-id="518db-478">A ferramenta MSTurnPing permite que um administrador do software de comunicações Skype for Business Server 2015 verifique o status dos servidores que executam a Borda de Áudio/Vídeo, os serviços de Autenticação de Áudio/Vídeo e os servidores que executam os Serviços de Política de Largura de Banda na topologia.</span><span class="sxs-lookup"><span data-stu-id="518db-478">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="518db-479">A ferramenta permite que o administrador execute os seguintes testes:</span><span class="sxs-lookup"><span data-stu-id="518db-479">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="518db-480">Teste do Servidor de Borda A/V: a ferramenta realiza testes em todos os Servidores de Borda A/V na topologia, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-480">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="518db-481">Verificar se o serviço Skype for Business Server autenticação de áudio/vídeo foi iniciado e pode emitir credenciais adequadas.</span><span class="sxs-lookup"><span data-stu-id="518db-481">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="518db-482">Verificar se o serviço Skype for Business Server de Borda de Áudio/Vídeo foi iniciado e pode alocar os recursos na borda externa com êxito.</span><span class="sxs-lookup"><span data-stu-id="518db-482">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="518db-483">Teste do Serviço de Política de Largura de Banda: a ferramenta realiza testes em todos os servidores que executam os Serviços de Política de Largura de Banda na topologia, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-483">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="518db-484">Verificar se o Serviço Skype for Business Server de Política de Largura de Banda (Autenticação) está iniciado e pode emitir credenciais adequadas.</span><span class="sxs-lookup"><span data-stu-id="518db-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="518db-485">Verificar se o Serviço Skype for Business Server de Política de Largura de Banda (Core) foi iniciado e pode executar a verificação de largura de banda com êxito.</span><span class="sxs-lookup"><span data-stu-id="518db-485">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="518db-486">Essa ferramenta deve ser executado de um computador que faz parte da topologia e tem o armazenamento local instalado.</span><span class="sxs-lookup"><span data-stu-id="518db-486">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="518db-487">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-487">Output</span></span>

<span data-ttu-id="518db-488">A ferramenta resulta nos resultados de cada uma das operações.</span><span class="sxs-lookup"><span data-stu-id="518db-488">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="518db-489">Se o **teste AudioVideoEdgeServer** for executado, as saídas da ferramenta serão as seguintes:</span><span class="sxs-lookup"><span data-stu-id="518db-489">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="518db-490">Os resultados de teste dos computadores que fornecem o serviço Skype for Business Server autenticação de áudio/vídeo 2015 na topologia</span><span class="sxs-lookup"><span data-stu-id="518db-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="518db-491">Os resultados de teste dos computadores que fornecem o serviço de Borda de Áudio/Vídeo Skype for Business Server 2015 na topologia</span><span class="sxs-lookup"><span data-stu-id="518db-491">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="518db-492">Se o **teste BandwidthPolicyServer** for executado, as saídas da ferramenta serão as seguintes:</span><span class="sxs-lookup"><span data-stu-id="518db-492">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="518db-493">Os resultados de teste dos computadores que fornecem o Serviço de Política de Largura de Banda (Authentication) Skype for Business Server 2015 na topologia</span><span class="sxs-lookup"><span data-stu-id="518db-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="518db-494">Os resultados de teste dos computadores que fornecem o Serviço de Política de Largura de Banda (Core) Skype for Business Server 2015 na topologia</span><span class="sxs-lookup"><span data-stu-id="518db-494">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-495">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-495">Requirements</span></span>

- <span data-ttu-id="518db-496">Essa ferramenta deve ser executado a partir de um computador que está na topologia e que tenha o armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="518db-496">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="518db-497">A ferramenta deve ser executado como um administrador que tenha acesso ao armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="518db-497">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-498">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-498">Examples</span></span>

<span data-ttu-id="518db-499">A seguir, um exemplo da entrada da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="518db-499">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="518db-500">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-500">Summary</span></span>

<span data-ttu-id="518db-501">Essa ferramenta pode ser um recurso valioso para Skype for Business Server administradores de 2015 que querem verificar o status dos servidores que estão executando serviços de política de áudio/vídeo e largura de banda.</span><span class="sxs-lookup"><span data-stu-id="518db-501">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="518db-502">Visualizador de Configuração de Rede</span><span class="sxs-lookup"><span data-stu-id="518db-502">Network Configuration Viewer</span></span>
<span data-ttu-id="518db-503"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-503"><a name="NCV"> </a></span></span>

<span data-ttu-id="518db-504">O Visualizador de Configuração de Rede pode ser usado pelos administradores de software de comunicação 2015 para exibir a topologia de rede cac (controle de admissão de chamada) para uma empresa provisionada para permitir sessões de comunicação em tempo real, como chamadas de voz ou vídeo com base na capacidade de largura de banda especificada. Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="518db-504">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="518db-505">Skype for Business Server administradores de 2015 definem políticas de CAC, que são impostas pelos serviços de Política de Largura de Banda instalados com o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-505">Skype for Business Server 2015 administrators defines CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="518db-506">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-506">Description</span></span>

<span data-ttu-id="518db-507">O Visualizador de Configuração de Rede (NetworkConfigurationViewer.exe) permite que os administradores executem as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="518db-507">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="518db-508">Carregar e exibir a topologia de rede cac de uma implantação Skype for Business Server 2015 em um formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="518db-508">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="518db-509">Carregar e exibir a topologia de rede cac a partir de um arquivo de log do Servidor de Política de Largura de Banda em um formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="518db-509">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="518db-510">Salve e armazene a topologia de rede CAC em um formato XML no disco.</span><span class="sxs-lookup"><span data-stu-id="518db-510">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="518db-511">Salvar e armazenar o diagrama de topologia de rede cac no formato JPG ou BMP.</span><span class="sxs-lookup"><span data-stu-id="518db-511">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="518db-512">Exibir dados de configuração de topologia de rede cac.</span><span class="sxs-lookup"><span data-stu-id="518db-512">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="518db-513">Exibir a topologia de rede cac em um estilo de exibição de árvore.</span><span class="sxs-lookup"><span data-stu-id="518db-513">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="518db-514">Defina conectores personalizados para links de topologia de rede cac (por exemplo, links de site para região, região para região e site para site).</span><span class="sxs-lookup"><span data-stu-id="518db-514">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="518db-515">Exibir informações do site de topologia de rede cac, informações da região e políticas de largura de banda provisionadas e links de rede.</span><span class="sxs-lookup"><span data-stu-id="518db-515">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-516">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-516">Purpose</span></span>

<span data-ttu-id="518db-517">Exibir links de topologia de rede CAC corporativos em uma interface gráfica.</span><span class="sxs-lookup"><span data-stu-id="518db-517">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-518">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-518">Examples</span></span>

 <span data-ttu-id="518db-519">Carregar e exibir a topologia de rede cac a partir de uma implantação do **Skype for Business Server 2015** em um formato gráfico : os administradores do Skype for Business Server 2015 podem carregar e exibir a configuração de topologia de rede cac em qualquer computador Skype for Business Server 2015 usando a opção **Baixar** Configuração de Rede, conforme mostrado na figura abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-519">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="518db-520">A ferramenta falhará ao baixar ou exibir essa configuração quando implantada em um computador que não tenha conectividade com o armazenamento de configuração Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-520">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Baixando a configuração de rede.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="518db-522">Carregar e exibir a topologia de rede cac de um arquivo de log do servidor de Política de Largura de Banda em um formato **gráfico:** os servidores de Política de Largura de Banda do Skype for Business Server 2015 salvam a topologia de rede cac como parte do mecanismo de registro em log no local de compartilhamento de arquivos Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-522">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers saves the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="518db-523">Skype for Business Server administradores de 2015 podem exibir esse arquivo em um formato gráfico usando a opção **Configuração** de Rede Aberta, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-523">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Abrindo um arquivo de log do Servidor de Política de Largura de Banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="518db-525">Salve e armazene a topologia de rede CAC em um formato XML no disco: os administradores do Skype for Business Server 2015 podem salvar o arquivo de configuração de topologia de rede CAC em um formato XML usando a opção Salvar **uma** cópia da Configuração de Rede, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-525">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="518db-526">O arquivo de configuração salvo pode ser usado offline para fins de exibição gráfica.</span><span class="sxs-lookup"><span data-stu-id="518db-526">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Salvar a configuração de rede como um arquivo XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="518db-528">Salvar e armazenar diagrama de topologia de rede CAC no formato JPG ou BMP: os administradores do Skype for Business Server 2015 podem salvar a configuração de topologia de rede cac em um formato gráfico (formatos de arquivo JPG e BMP) usando o diagrama **Salvar Configuração** de Rede como opção de imagem, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-528">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Salvar a configuração de rede como uma imagem.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="518db-530">Exibir dados de configuração de topologia de rede do <strong>CAC:</strong>os administradores do Skype for Business Server 2015 podem exibir dados relacionados de configuração de rede, como regiões de rede, sites de rede, perfis de largura de banda e endereços IP da sub-rede do site em um formato textual usando a opção Exibir dados de Configuração de Rede, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-530"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Exibindo dados de configuração de rede.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="518db-532">Exibir a topologia de rede cac em um estilo de exibição de **árvore:** os administradores do Skype for Business Server 2015 podem exibir dados relacionados de configuração de rede em um estilo de exibição de árvore gráfica usando o painel de controle no lado esquerdo da janela da ferramenta, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-532">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Exibindo dados de configuração de rede em uma exibição em árvore.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="518db-534">**Definir conectores personalizados** para links de topologia de rede cac (como links de WAN de site para região, região para região e site para site): os administradores do Skype for Business Server 2015 podem definir conectores gráficos personalizados para links WAN de configuração de rede do CAC usando a opção Configurações como mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-534">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="518db-535">Isso ajuda a diferenciar entre vários tipos de links de rede provisionados na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="518db-535">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Ferramentas](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="518db-537">Exibir informações de site de topologia de rede **cac,** informações de região e políticas de largura de banda provisionadas: os administradores do Skype for Business Server 2015 podem exibir informações relacionadas da região de rede cac, informações de site e informações de provisionamento de largura de banda cac usando opções mostradas abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-537">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="518db-538">(Por exemplo, clique **em Informações em** uma região de rede ou em um objeto de site de rede.)</span><span class="sxs-lookup"><span data-stu-id="518db-538">(For example, click **Info** in a network region or network site object.)</span></span>

![Definindo conectores personalizados para sua rede.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="518db-540">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-540">Summary</span></span>

<span data-ttu-id="518db-541">Essa ferramenta pode ser um recurso valioso para Skype for Business Server administradores 2015 que gostaria de exibir a topologia de rede cac para sua implantação em um formato gráfico.</span><span class="sxs-lookup"><span data-stu-id="518db-541">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="518db-542">Agente do Grupo de Resposta Ao Vivo</span><span class="sxs-lookup"><span data-stu-id="518db-542">Response Group Agent Live</span></span>
<span data-ttu-id="518db-543"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-543"><a name="RGAL"> </a></span></span>

<span data-ttu-id="518db-544">O aplicativo grupo de resposta oferece aos agentes a capacidade de acessar informações úteis em tempo real usando seu serviço Web interno.</span><span class="sxs-lookup"><span data-stu-id="518db-544">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="518db-545">Infelizmente, nenhuma exibição gráfica desses dados está disponível fora do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="518db-545">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="518db-546">A ferramenta Kit de Recursos ao Vivo do Agente de Grupo de Resposta resolve esse problema fornecendo uma maneira simples e gráfica de acessar essas informações, aprimorada com informações de software de comunicações em tempo Skype for Business real, como a presença de outros agentes.</span><span class="sxs-lookup"><span data-stu-id="518db-546">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="518db-547">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-547">Description</span></span>

<span data-ttu-id="518db-548">O Agente do Grupo de Resposta Live é um aplicativo Windows que fornece funcionalidade de entrada e saída e algumas informações em tempo real (como associação ao grupo e número atual de chamadas) aos agentes do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="518db-548">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="518db-549">Ele deve ser uma versão aprimorada da página Grupos de Agentes (acessível Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="518db-549">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-550">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-550">Purpose</span></span>

<span data-ttu-id="518db-551">O aplicativo grupo de resposta faz filas de chamadas de entrada e as encaminha para grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="518db-551">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="518db-552">Para tomar decisões informadas sobre quais chamadas para o serviço, os agentes podem acessar informações em tempo real sobre seus grupos de agentes, como quais outros agentes estão disponíveis e quantas chamadas estão aguardando em cada fila.</span><span class="sxs-lookup"><span data-stu-id="518db-552">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="518db-553">Essas informações, inicialmente acessíveis somente por meio do serviço grupo de resposta, são disponibilizadas de forma intuitiva pelo Agente de Grupo de Resposta Live.</span><span class="sxs-lookup"><span data-stu-id="518db-553">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="518db-554">Recursos</span><span class="sxs-lookup"><span data-stu-id="518db-554">Features</span></span>

<span data-ttu-id="518db-555">A ferramenta Agente do Grupo de Resposta Live é criada no serviço grupo de resposta e no SDK Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-555">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="518db-556">Ele fornece aos agentes do Grupo de Resposta as informações e os recursos disponíveis no serviço grupo de resposta (como associação ao grupo, presença de outros agentes e número de chamadas de espera).</span><span class="sxs-lookup"><span data-stu-id="518db-556">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="518db-557">A figura a seguir ilustra a interface principal do Agente de Grupo de Resposta Ao Vivo.</span><span class="sxs-lookup"><span data-stu-id="518db-557">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![A ferramenta Agente do Grupo de Resposta Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="518db-559">Os três principais recursos a seguir estão disponíveis para agentes no Response Group Agent Live:</span><span class="sxs-lookup"><span data-stu-id="518db-559">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="518db-560">**Entrar/sair:** Ao contrário da página Grupos de Agentes (acessível a partir do Skype for Business Server 2015), o Agente do Grupo de Resposta Live permite que apenas agentes entre ou saia de todos os grupos de agentes de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="518db-560">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign in or out of all agent groups at once.</span></span> <span data-ttu-id="518db-561">Este aplicativo fornece três maneiras rápidas para os agentes entrarem ou sairem:</span><span class="sxs-lookup"><span data-stu-id="518db-561">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="518db-562">Clique nos botões Entrar/Sair (verde e vermelho) dentro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="518db-562">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="518db-563">Clique com o botão direito do mouse no ícone da bandeja do sistema e selecione entrar ou sair.</span><span class="sxs-lookup"><span data-stu-id="518db-563">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="518db-564">Usando atalhos de teclado configuráveis.</span><span class="sxs-lookup"><span data-stu-id="518db-564">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="518db-565">**Associação ao grupo:** Quando um grupo de agentes é selecionado, o Agente de Grupo de Resposta Ao Vivo exibe a lista de agentes neste grupo no painel direito.</span><span class="sxs-lookup"><span data-stu-id="518db-565">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="518db-566">Se Skype for Business Server 2015 estiver sendo executado no mesmo computador que este aplicativo, as informações de presença e o cartão de visita serão exibidas no Agente do Grupo de Resposta Ao Vivo.</span><span class="sxs-lookup"><span data-stu-id="518db-566">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="518db-567">Os agentes podem enviar um IM ou chamar outros agentes diretamente a partir daí.</span><span class="sxs-lookup"><span data-stu-id="518db-567">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="518db-568">**Estatísticas em tempo real:** O Agente do Grupo de Resposta Live fornece estatísticas em tempo real para todos os grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="518db-568">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="518db-569">A frequência de atualização é de um minuto.</span><span class="sxs-lookup"><span data-stu-id="518db-569">The update frequency is one minute.</span></span> <span data-ttu-id="518db-570">Quando uma chamada é atendida por um Grupo de Resposta, um indicador visual é adicionado ao lado do nome do grupo com o número atual de chamadas em fila.</span><span class="sxs-lookup"><span data-stu-id="518db-570">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="518db-571">Pausar o ponteiro sobre um grupo também exibe o tempo de espera mais longo.</span><span class="sxs-lookup"><span data-stu-id="518db-571">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-572">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-572">Requirements</span></span>

<span data-ttu-id="518db-573">O Agente do Grupo de Resposta Live requer .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="518db-573">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="518db-574">Além disso, para aproveitar os recursos de cartão de visita e presença, Skype for Business deve ser instalado localmente (e estar em execução).</span><span class="sxs-lookup"><span data-stu-id="518db-574">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="518db-575">Configuração</span><span class="sxs-lookup"><span data-stu-id="518db-575">Configuration</span></span>

<span data-ttu-id="518db-576">O Agente do Grupo de Resposta Live pode ser personalizado para preferências individuais usando a caixa de diálogo Opções no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="518db-576">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="518db-577">Além disso, o administrador pode definir o endereço de host padrão editando diretamente a propriedade defaultHostAddress do arquivo RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="518db-577">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="518db-578">A figura a seguir ilustra a caixa de diálogo Opções que os agentes podem usar para configurar o endereço do host e as teclas de atalho.</span><span class="sxs-lookup"><span data-stu-id="518db-578">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="518db-579">Essa caixa de diálogo é acessada clicando no botão Opções na parte superior direita da interface principal.</span><span class="sxs-lookup"><span data-stu-id="518db-579">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![A caixa de diálogo Opções ao Vivo do Agente de Grupo de Resposta.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="518db-581">As três configurações diferentes a seguir podem ser personalizadas na configuração do Agente de Grupo de Resposta Live:</span><span class="sxs-lookup"><span data-stu-id="518db-581">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="518db-582">Endereço do host: normalmente é o FQDN do pool da Web pertencente ao pool residencial do agente.</span><span class="sxs-lookup"><span data-stu-id="518db-582">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="518db-583">O endereço de serviço exato do Grupo de Resposta é derivado automaticamente em segundo plano a partir dessa informação (acrescentando o caminho certo após o host).</span><span class="sxs-lookup"><span data-stu-id="518db-583">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="518db-584">Atalhos: os atalhos exatos para entrar/sair podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="518db-584">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="518db-585">A única limitação é que ambos os atalhos devem conter a tecla "Windows Logo" (além de pelo menos outra chave).</span><span class="sxs-lookup"><span data-stu-id="518db-585">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="518db-586">Comece com Windows: o aplicativo pode ser configurado para iniciar automaticamente com Windows.</span><span class="sxs-lookup"><span data-stu-id="518db-586">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-587">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-587">Examples</span></span>

<span data-ttu-id="518db-588">A figura a seguir ilustra como chamar ou enviar um IM para outro agente clicando com o botão direito do mouse no contato no painel direito.</span><span class="sxs-lookup"><span data-stu-id="518db-588">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Fazer uma chamada ou enviar um IM.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="518db-590">A figura a seguir ilustra como o Agente de Grupo de Resposta Live exibe o número atual de chamadas na fila e o tempo de espera mais longo entre todas essas chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="518db-590">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Exibindo informações da fila.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="518db-592">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-592">Summary</span></span>

<span data-ttu-id="518db-593">Entrar e sair rapidamente, associação ao grupo e estatísticas básicas em tempo real são recursos interessantes do agente do Grupo de Resposta que estão disponíveis apenas fora do aplicativo do serviço grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="518db-593">Fast sign in and sign out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="518db-594">Com a ferramenta Kit de Recursos ao Vivo do Agente de Grupo de Resposta, os administradores do Skype for Business Server 2015 podem fornecer aos seus agentes um aplicativo Windows que permite que eles executem tarefas de maneira mais rápida e gráfica.</span><span class="sxs-lookup"><span data-stu-id="518db-594">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="518db-595">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="518db-595">SEFAUtil</span></span>
<span data-ttu-id="518db-596"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-596"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="518db-597">SEFAUtil (ativação de recurso de extensão secundária) é uma ferramenta de linha de comando que permite que os administradores de software de comunicações do Skype for Business Server 2015 e agentes auxiliares configurem toque de representante, encaminhamento de chamada, toque simultâneo, configurações de chamada de equipe e retirada de chamada de grupo em nome de um usuário do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-597">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="518db-598">A ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="518db-598">The tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="518db-599">A ferramenta SEFAUtil permite que o administrador habilita/desabilite/modifique o encaminhamento de chamada ou toque simultâneo em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-599">The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="518db-600">O administrador pode especificar o destino (na forma de um URI SIP) ou usar um destino que já foi publicado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-600">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="518db-601">Essa ferramenta também permite que os administradores adicionem ou removam representantes ou membros do grupo de chamada de equipe em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-601">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.</span></span> <span data-ttu-id="518db-602">Essa ferramenta é criada com base na UCMA (Microsoft Unified Communications Managed API) 3.0 e exige que os administradores criem um aplicativo confiável no armazenamento de Gerenciamento Central para SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="518db-602">This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="518db-603">O SEFAUtil (ativação de recurso de extensão secundária) permite que os administradores do Skype for Business Server 2015 e agentes auxiliares configurem toque de representante, encaminhamento de chamada, toque simultâneo, configurações de chamada de equipe e retirada de chamada de grupo em nome de um usuário do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-603">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="518db-604">Essa ferramenta também permite que os administradores consultem as configurações de roteamento de chamadas publicadas para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="518db-604">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="518db-605">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-605">Description</span></span>

<span data-ttu-id="518db-606">A versão atual do SEFAUtil é apenas uma ferramenta de linha de comando; não há suporte para interface gráfica do usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-606">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="518db-607">Essa ferramenta se baseia na UCMA (Microsoft Unified Communications Managed API) 3.0.</span><span class="sxs-lookup"><span data-stu-id="518db-607">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="518db-608">Os recursos nesta ferramenta permitem que os administradores e agentes do helpdesk faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="518db-608">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="518db-609">Exibir todas as configurações de roteamento de chamadas para um usuário (inclui encaminhamento de chamadas, delegação, toque simultâneo, chamada de equipe e retirada de chamada de grupo)</span><span class="sxs-lookup"><span data-stu-id="518db-609">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call, and group call pickup)</span></span>

- <span data-ttu-id="518db-610">Habilitar/desabilitar/modificar a configuração de encaminhamento de chamada (inclui o timer de destino e sem resposta)</span><span class="sxs-lookup"><span data-stu-id="518db-610">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="518db-611">Habilitar/desabilitar/modificar configurações imediatas de encaminhamento de chamada</span><span class="sxs-lookup"><span data-stu-id="518db-611">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="518db-612">Habilitar/desabilitar/modificar configurações de delegação</span><span class="sxs-lookup"><span data-stu-id="518db-612">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="518db-613">Habilitar/desabilitar/modificar configurações de grupo de chamada de equipe</span><span class="sxs-lookup"><span data-stu-id="518db-613">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="518db-614">Novo na Skype for Business Server 2015 ferramenta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="518db-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="518db-615">Habilitar/desabilitar/modificar configurações simultâneas de toque (inclui destino)</span><span class="sxs-lookup"><span data-stu-id="518db-615">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="518db-616">Novo na Skype for Business Server 2015 ferramenta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="518db-616">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="518db-617">Habilitar/desabilitar/modificar configurações de retirada de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="518db-617">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="518db-618">Novo na Skype for Business Server 2015 ferramenta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="518db-618">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="518db-619">Esta ferramenta tem as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="518db-619">This tool has the following limitations:</span></span>

- <span data-ttu-id="518db-620">Com suporte apenas para usuários que estão em um pool Skype for Business Server usuário</span><span class="sxs-lookup"><span data-stu-id="518db-620">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="518db-621">Não há suporte para edição em massa de configurações de roteamento de chamadas para vários usuários</span><span class="sxs-lookup"><span data-stu-id="518db-621">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="518db-622">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-622">Output</span></span>

<span data-ttu-id="518db-623">A versão atual desta ferramenta fornece saída somente na janela Prompt de Comando.</span><span class="sxs-lookup"><span data-stu-id="518db-623">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="518db-624">Para obter detalhes, consulte a seção Exemplos posteriormente neste documento.</span><span class="sxs-lookup"><span data-stu-id="518db-624">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-625">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-625">Purpose</span></span>

<span data-ttu-id="518db-626">A seguir estão alguns dos principais cenários em que essa ferramenta pode ser usada:</span><span class="sxs-lookup"><span data-stu-id="518db-626">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="518db-627">Bob é um executivo e foi movido para Skype for Business Server telefonia.</span><span class="sxs-lookup"><span data-stu-id="518db-627">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="518db-628">Ele tem delegação em seu sistema PBX existente.</span><span class="sxs-lookup"><span data-stu-id="518db-628">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="518db-629">Como parte da mudança para Skype for Business Server 2015, o administrador é capaz de configurar o roteamento de Bob para refletir sua configuração de delegação pré-existente.</span><span class="sxs-lookup"><span data-stu-id="518db-629">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="518db-630">Alice está viajando e percebe que está esperando uma chamada importante de um de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="518db-630">Alice is traveling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="518db-631">No entanto, ela está em um hotel e não tem acesso a um computador.</span><span class="sxs-lookup"><span data-stu-id="518db-631">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="518db-632">Ela chama o helpdesk e solicita que eles encaminhem para seu número de celular todas as chamadas feitas para seu número de trabalho.</span><span class="sxs-lookup"><span data-stu-id="518db-632">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="518db-633">A equipe de ajuda é capaz de fazer a configuração em nome dela.</span><span class="sxs-lookup"><span data-stu-id="518db-633">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="518db-634">As chamadas de Joe para seu número de trabalho estão indo para sua caixa postal móvel sempre que ele está no trabalho; no entanto, as coisas parecem estar funcionando corretamente na maioria dos outros locais.</span><span class="sxs-lookup"><span data-stu-id="518db-634">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="518db-635">O técnico do helpdesk é capaz de exibir a configuração de roteamento de Joe e descobre que Joe tem toque simultâneo configurado para seu telefone celular.</span><span class="sxs-lookup"><span data-stu-id="518db-635">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="518db-636">O técnico pergunta a Joe sobre a cobertura móvel em seu escritório e é capaz de determinar que a regra de toque simultâneo é o que está fazendo com que as chamadas acessem a caixa postal móvel de Joe quando sua cobertura de rede é ruim.</span><span class="sxs-lookup"><span data-stu-id="518db-636">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="518db-637">Mike é um novo funcionário da Contoso e está in juntando uma nova equipe na qual todos os membros estão configurados para chamada de equipe, ao ser habilitado para o Skype for Business Server 2015, o administrador é capaz de definir suas configurações de grupo de chamada de equipe para incluir todos os novos membros da equipe, além disso, o administrador adiciona Mike como membro do grupo de chamada de equipe para cada um dos membros em sua equipe.</span><span class="sxs-lookup"><span data-stu-id="518db-637">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="518db-638">Uma prática de atendimento ao cliente no departamento de recursos humanos da Contoso é fornecer serviço pessoal para todos os chamadores desde a primeira chamada.</span><span class="sxs-lookup"><span data-stu-id="518db-638">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="518db-639">Como todos os membros do departamento ficam muito próximos uns dos outros, ter todos os telefones tocando ao mesmo tempo com a chamada de equipe é prejudicial para a equipe.</span><span class="sxs-lookup"><span data-stu-id="518db-639">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is disruptive for the team.</span></span> <span data-ttu-id="518db-640">Para fornecer o melhor serviço sem interromper os membros da equipe, o administrador Skype for Business Server 2015 aproveita o recurso de Retirada de Chamada de Grupo.</span><span class="sxs-lookup"><span data-stu-id="518db-640">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="518db-641">O administrador adiciona todos os membros do departamento a um grupo de retirada e comunica ao departamento o número do grupo de retirada.</span><span class="sxs-lookup"><span data-stu-id="518db-641">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="518db-642">Quando Samantha está ausente de sua mesa, Joe nota seu telefone tocando e ele continua a atender a chamada de sua mesa.</span><span class="sxs-lookup"><span data-stu-id="518db-642">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-643">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-643">Requirements</span></span>

<span data-ttu-id="518db-644">A ferramenta SEFAUtil só pode ser executado em um computador que faz parte de um Pool de Aplicativos Confiáveis.</span><span class="sxs-lookup"><span data-stu-id="518db-644">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="518db-645">O UCMA 3.0 deve ser instalado nesse computador.</span><span class="sxs-lookup"><span data-stu-id="518db-645">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="518db-646">Para executar a ferramenta, um novo Aplicativo Confiável com a ID do aplicativo SEFAUtil deve ser criado nesse pool.</span><span class="sxs-lookup"><span data-stu-id="518db-646">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="518db-647">Criando um novo aplicativo confiável para a ferramenta SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="518db-647">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="518db-648">A ferramenta SEFAUTil só pode ser executado em um computador que faz parte de um pool de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="518db-648">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="518db-649">Se necessário, a adição de um pool como um novo pool de aplicativos confiáveis pode ser feita por meio do Shell de Gerenciamento Skype for Business Server com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="518db-649">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="518db-650">O UCMA 3.0 deve ser instalado em qualquer computador que será usado para executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="518db-650">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="518db-651">Um aplicativo confiável precisa ser definido na topologia da ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="518db-651">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="518db-652">Para definir SEFAUtil como um novo aplicativo confiável, use o Shell de Gerenciamento Skype for Business Server e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="518db-652">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="518db-653">Uma porta diferente pode ser usada, se necessário.</span><span class="sxs-lookup"><span data-stu-id="518db-653">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="518db-654">FQDN do Pool: O FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um servidor Skype for Business de front-end > ou pool).</span><span class="sxs-lookup"><span data-stu-id="518db-654">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="518db-655">FQDN do Registrador de Pool: O FQDN do servidor Skype for Business ou pool de front-end associado a esse pool de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="518db-655">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="518db-656">Site do Pool: A ID do Site do site no qual esse pool está.</span><span class="sxs-lookup"><span data-stu-id="518db-656">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="518db-657">As alterações de topologia precisam ser habilitadas.</span><span class="sxs-lookup"><span data-stu-id="518db-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="518db-658">A habilitação das alterações de topologia pode ser feita por meio do Shell de Gerenciamento Skype for Business Server executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="518db-658">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="518db-659">Se necessário, instale as Ferramentas de Kit de Recursos do Skype for Business Server 2015 no servidor que será usada para executar a ferramenta SEFAUtil (o servidor deve fazer parte de um pool de aplicativos confiáveis).</span><span class="sxs-lookup"><span data-stu-id="518db-659">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="518db-660">Verifique se SEFAUtil está em execução corretamente.</span><span class="sxs-lookup"><span data-stu-id="518db-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="518db-661">Para fazer isso, execute a ferramenta de um prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário na implantação.</span><span class="sxs-lookup"><span data-stu-id="518db-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="518db-662">Por padrão, a ferramenta estará localizada em: "...\Arquivos de Programas\Skype for Business Server 2015\Reskit".</span><span class="sxs-lookup"><span data-stu-id="518db-662">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="518db-663">Para exibir as configurações de encaminhamento de chamada de um usuário, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="518db-663">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="518db-664">As configurações de encaminhamento de chamada do usuário devem ser exibidas.</span><span class="sxs-lookup"><span data-stu-id="518db-664">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="518db-665">Recebimento de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="518db-665">Group Call Pickup</span></span>

<span data-ttu-id="518db-666">A Retirada de Chamada de Grupo requer configuração adicional Skype for Business Server 2015 para que a funcionalidade seja totalmente habilitada.</span><span class="sxs-lookup"><span data-stu-id="518db-666">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="518db-667">Antes de atribuir grupos de retirada aos usuários, consulte a documentação do produto de Retirada de Chamada de Grupo para as etapas de planejamento e implantação desse recurso.</span><span class="sxs-lookup"><span data-stu-id="518db-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-668">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-668">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="518db-669">Exibir o tratamento de chamada atual Configurações</span><span class="sxs-lookup"><span data-stu-id="518db-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="518db-670">O comando a seguir exibe o tratamento de chamada para o usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-670">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="518db-671">Este exemplo usa a **opção /server** para especificar o Skype for Business Server para se conectar.</span><span class="sxs-lookup"><span data-stu-id="518db-671">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="518db-672">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-672">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="518db-673">Definir o destino de encaminhamento/sem resposta de chamada</span><span class="sxs-lookup"><span data-stu-id="518db-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="518db-674">Este exemplo define o destino de encaminhamento/sem resposta da chamada e o atraso do anel.</span><span class="sxs-lookup"><span data-stu-id="518db-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="518db-675">Aqui, a opção /server não é fornecida; SEFAUtil tenta descobrir automaticamente o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="518db-676">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="518db-677">Habilitar o encaminhamento de chamada imediatamente</span><span class="sxs-lookup"><span data-stu-id="518db-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="518db-678">Este exemplo habilita imediatamente o encaminhamento de chamada para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-678">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="518db-679">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="518db-680">Desabilitar o encaminhamento de chamada imediatamente</span><span class="sxs-lookup"><span data-stu-id="518db-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="518db-681">Este exemplo desabilita imediatamente o encaminhamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="518db-681">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="518db-682">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="518db-683">Adicionar um usuário como representante e configurar toque simultâneo de representantes</span><span class="sxs-lookup"><span data-stu-id="518db-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="518db-684">Este exemplo adiciona um usuário como representante e configura toque simultâneo de representantes.</span><span class="sxs-lookup"><span data-stu-id="518db-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="518db-685">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="518db-686">Alterar a regra de toque simultâneo dos representantes</span><span class="sxs-lookup"><span data-stu-id="518db-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="518db-687">Este exemplo altera a regra de toque simultâneo definida no exemplo anterior para a regra de toque atrasada.</span><span class="sxs-lookup"><span data-stu-id="518db-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="518db-688">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-688">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="518db-689">Remover o Representante</span><span class="sxs-lookup"><span data-stu-id="518db-689">Remove the Delegate</span></span>

<span data-ttu-id="518db-690">Este exemplo remove o representante.</span><span class="sxs-lookup"><span data-stu-id="518db-690">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="518db-691">Quando o último representante é removido, o toque do representante é desabilitado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="518db-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="518db-692">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="518db-693">Adicionar um Representante e Configurar o Call-Forward a Regra de Representantes</span><span class="sxs-lookup"><span data-stu-id="518db-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="518db-694">Este exemplo adiciona um representante e configura a regra de encaminhamento de chamada para representantes.</span><span class="sxs-lookup"><span data-stu-id="518db-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="518db-695">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-695">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="518db-696">Habilitar toque simultâneo e definir um número de destino</span><span class="sxs-lookup"><span data-stu-id="518db-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="518db-697">Este exemplo habilita toque simultâneo e define um número de destino de toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="518db-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="518db-698">Para alterar o número de destino de toque simultâneo de um usuário que já tenha toque simultâneo habilitado, mantenha o comando com a opção /enablesimulring, caso contrário, o número de destino não será alterado.</span><span class="sxs-lookup"><span data-stu-id="518db-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="518db-699">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="518db-700">Desabilitar toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="518db-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="518db-701">Este exemplo desabilita o toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="518db-701">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="518db-702">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-702">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="518db-703">Adicionar um membro da equipe para Team-Call e configurar toque simultâneo ao grupo Team-Call membros</span><span class="sxs-lookup"><span data-stu-id="518db-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="518db-704">Este exemplo adiciona um membro da equipe ao grupo de chamada de equipe de um usuário e habilita toque simultâneo ao grupo de chamada de equipe.</span><span class="sxs-lookup"><span data-stu-id="518db-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="518db-705">Adicionar um membro ao grupo de chamada de equipe de um usuário alterna automaticamente os settigs de toque simultâneos dos usuários para tocar simultaneamente no grupo de chamada de equipe.</span><span class="sxs-lookup"><span data-stu-id="518db-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simultaneous ring his team-call group.</span></span>

 <span data-ttu-id="518db-706">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-706">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="518db-707">Remover um membro do grupo Team-Call</span><span class="sxs-lookup"><span data-stu-id="518db-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="518db-708">Este exemplo remove um membro da equipe do grupo de chamada de equipe de um usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-708">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="518db-709">Se o membro que está sendo removido for o único membro do grupo de chamada de equipe, o toque simultâneo para o grupo de chamada de equipe será desabilitado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="518db-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="518db-710">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="518db-711">Definir o Anel Atrasado como o Team-Call Grupo</span><span class="sxs-lookup"><span data-stu-id="518db-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="518db-712">Este exemplo altera o anel atrasado para a configuração de hora do grupo de chamada de equipe.</span><span class="sxs-lookup"><span data-stu-id="518db-712">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="518db-713">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-713">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="518db-714">Habilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="518db-714">Enable Team-Call</span></span>

<span data-ttu-id="518db-715">Este exemplo habilita a chamada de equipe para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-715">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="518db-716">Se o grupo de chamada de equipe do usuário não tiver membros, a chamada de equipe não será habilitada.</span><span class="sxs-lookup"><span data-stu-id="518db-716">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="518db-717">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-717">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="518db-718">Desabilitar Team-Call</span><span class="sxs-lookup"><span data-stu-id="518db-718">Disable Team-Call</span></span>

<span data-ttu-id="518db-719">Este exemplo desabilita a chamada de equipe para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-719">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="518db-720">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="518db-721">Habilitar a coleta de chamada de grupo e atribuir um grupo de retirada a um usuário</span><span class="sxs-lookup"><span data-stu-id="518db-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="518db-722">Este exemplo atribui um grupo de retirada a um usuário e habilita o Atendimento de Chamada de Grupo.</span><span class="sxs-lookup"><span data-stu-id="518db-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="518db-723">**Output**</span><span class="sxs-lookup"><span data-stu-id="518db-723">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="518db-724">Desabilitar a coleta de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="518db-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="518db-725">Este exemplo desabilita a Coleta de Chamada de Grupo para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-725">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="518db-726">Quando você desabilita a Coleta de Chamada de Grupo para um usuário, o número de grupo atribuído ao usuário não é mantido.</span><span class="sxs-lookup"><span data-stu-id="518db-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="518db-727">Se você quiser reabilitar a Coleta de Chamada de Grupo para esse usuário, deverá atribuir o número do grupo novamente com a opção /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="518db-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="518db-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="518db-728">SYSPrep.ps1</span></span>
<span data-ttu-id="518db-729"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-729"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="518db-730">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-730">Description</span></span>

<span data-ttu-id="518db-731">SYSPrep.ps1 é um script Windows PowerShell que instalará os seguintes pré-requisitos do Skype for Business Server 2015 em sua máquina do sistema operacional Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="518db-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="518db-732">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="518db-732">Microsoft .NET Framework 4.5</span></span>

- <span data-ttu-id="518db-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="518db-733">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="518db-734">Windows PowerShell versão 3.0</span><span class="sxs-lookup"><span data-stu-id="518db-734">Windows PowerShell version 3.0</span></span>

- <span data-ttu-id="518db-735">Visual C++ 2010 Redistribuível</span><span class="sxs-lookup"><span data-stu-id="518db-735">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="518db-736">Atualizações do Servidor de Informações da Internet</span><span class="sxs-lookup"><span data-stu-id="518db-736">Internet Information Server Updates</span></span>

- <span data-ttu-id="518db-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="518db-737">Windows Identity Foundation</span></span>

- <span data-ttu-id="518db-738">Skype for Business Server arquivos Core 2015</span><span class="sxs-lookup"><span data-stu-id="518db-738">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="518db-739">Embora o nome do script seja semelhante à Ferramenta de Preparação do Sistema para os sistemas operacionais microsoft Windows, eles são diferentes.</span><span class="sxs-lookup"><span data-stu-id="518db-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="518db-740">Esse script só instalará os pré-requisitos necessários para Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-740">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="518db-741">Depois que esses pré-requisitos são instalados, a ferramenta Windows SYSPrep pode ser usada para criar uma imagem do servidor.</span><span class="sxs-lookup"><span data-stu-id="518db-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-742">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-742">Requirements</span></span>

<span data-ttu-id="518db-743">Antes de executar o script SYSPrep.ps1, você deve copiar os arquivos de pré-requisito para uma pasta local na máquina do sistema operacional Windows Server 2008 (por **exemplo, D:\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="518db-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="518db-744">Essa pasta também deve incluir uma cópia dos arquivos Skype for Business Server 2015, especificamente **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="518db-744">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="518db-745">Os arquivos de pré-requisito podem ser baixados nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="518db-745">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="518db-746">**Pré-requisito**</span><span class="sxs-lookup"><span data-stu-id="518db-746">**Prerequisite**</span></span>                                | <span data-ttu-id="518db-747">**Location**</span><span class="sxs-lookup"><span data-stu-id="518db-747">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="518db-748">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="518db-748">Microsoft .NET Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="518db-749">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="518db-749">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="518db-750">Windows PowerShell versão 3.0</span><span class="sxs-lookup"><span data-stu-id="518db-750">Windows PowerShell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="518db-751">Visual C++ 2010 Redistribuível</span><span class="sxs-lookup"><span data-stu-id="518db-751">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="518db-752">Atualizações do Servidor de Informações da Internet</span><span class="sxs-lookup"><span data-stu-id="518db-752">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="518db-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="518db-753">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="518db-754">Skype for Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="518db-754">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="518db-755">Copiar da mídia Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="518db-755">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="518db-756">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="518db-756">Parameter</span></span>

<span data-ttu-id="518db-757">O **parâmetro -SetupFolder** assume como argumento o local do diretório dos arquivos de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="518db-757">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="518db-758">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-758">Examples</span></span>

<span data-ttu-id="518db-759">Para executar o script SYSPrep.ps1 e instalar os pré-requisitos do Skype for Business Server 2015, execute o seguinte comando de um prompt de comando elevado:</span><span class="sxs-lookup"><span data-stu-id="518db-759">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="518db-760">Migração de anúncios de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="518db-760">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="518db-761"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-761"><a name="UNAM"> </a></span></span>

<span data-ttu-id="518db-762">A ferramenta Migração de Comunicados de Número Não Atribuído permite que um administrador do Skype for Business Server 2015 mova a configuração de números não atribuídos que é a serviço pelo aplicativo de anúncio de um Skype for Business Server ou Pool de origem para um destino Skype for Business Server ou Pool.</span><span class="sxs-lookup"><span data-stu-id="518db-762">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="518db-763">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-763">Description</span></span>

<span data-ttu-id="518db-764">A ferramenta De migração de anúncios de números não atribuídos é um script Windows PowerShell que move a configuração de números não atribuídos a serviço pelo aplicativo de anúncio de um servidor de origem ou pool para um servidor ou pool diferente.</span><span class="sxs-lookup"><span data-stu-id="518db-764">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="518db-765">Quando executado, o script de Migração de Anúncios de Números Não Atribuídos executará as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="518db-765">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="518db-766">Mova todos os arquivos de áudio usados pelos comunicados de número não atribuídos do aplicativo de anúncio hospedado no servidor de origem ou pool para o armazenamento de arquivos do servidor de destino ou pool.</span><span class="sxs-lookup"><span data-stu-id="518db-766">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="518db-767">Os arquivos de áudio são removidos do pool de origem depois de copiados para o pool de destino.</span><span class="sxs-lookup"><span data-stu-id="518db-767">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="518db-768">Mova todos os comunicados de número não atribuídos configurados para o aplicativo de comunicado hospedado no servidor de origem ou pool para o servidor ou pool de destino.</span><span class="sxs-lookup"><span data-stu-id="518db-768">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="518db-769">Reatribua todos os intervalos de números não atribuídos que são atendidos pelo aplicativo de anúncio hospedado no servidor de origem ou pool para o servidor ou pool de destino.</span><span class="sxs-lookup"><span data-stu-id="518db-769">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="518db-770">Depois de executar com êxito o script, todos os intervalos de números não atribuídos que foram atendidos pelo aplicativo de anúncio hospedado no servidor de origem ou pool agora serão atendidos com a mesma configuração pelo servidor de destino ou pool.</span><span class="sxs-lookup"><span data-stu-id="518db-770">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="518db-771">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-771">Output</span></span>

<span data-ttu-id="518db-772">O **script Move-CsAnnouncementConfiguration** indica na janela do Shell de Gerenciamento Skype for Business Server de onde ele executou o sucesso ou falha da operação de migração.</span><span class="sxs-lookup"><span data-stu-id="518db-772">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="518db-773">Se a execução da operação for interrompida por qualquer erro, os intervalos de números não atribuídos que foram movidos com êxito para o destino permanecerão no destino em uma forma operacional e o restante dos intervalos de números não atribuídos a serem migrados permanecerá na origem também em um formulário operacional.</span><span class="sxs-lookup"><span data-stu-id="518db-773">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="518db-774">Para migrar totalmente o restante da configuração, reprise o script após endereçamento do erro.</span><span class="sxs-lookup"><span data-stu-id="518db-774">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="518db-775">Objetivo</span><span class="sxs-lookup"><span data-stu-id="518db-775">Purpose</span></span>

<span data-ttu-id="518db-776">O script migração de anúncios de números não atribuídos pode ser usado nos três cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="518db-776">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="518db-777">**Migrando configurações para uma nova versão do Skype for Business Server:** A Contoso está em processo de migração para o Skype for Business Server 2015 e como parte do processo de migração, o administrador do Skype for Business Server gostaria de mover a configuração de números não atribuídos a serviço pelo aplicativo de anúncio da implantação do Lync Server 2013 para a nova implantação do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-777">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="518db-778">Para mover as configurações, o administrador Skype for Business Server usa a ferramenta Migração de Anúncios de Números Não Atribuídos.</span><span class="sxs-lookup"><span data-stu-id="518db-778">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="518db-779">**Reverter uma implantação do Skype for Business Server 2015 para o Lync Server 2013:** Devido a fatores inesperados, a Contoso precisa reverter a migração para a nova implantação Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="518db-779">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="518db-780">Para minimizar as interrupções no serviço, o administrador Skype for Business Server usa a ferramenta Migração de Comunicados de Número Não Atribuído para reverter a configuração da implantação do Skype for Business Server 2015 para a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="518db-780">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="518db-781">**Mover dados entre implantações:** A Contoso está em processo de substituição de todos os servidores de um pool por servidores mais novos.</span><span class="sxs-lookup"><span data-stu-id="518db-781">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="518db-782">Sua estratégia é implantar um novo pool Skype for Business Server 2015, mover todos os dados do antigo para o novo pool e, em seguida, depreende o pool antigo.</span><span class="sxs-lookup"><span data-stu-id="518db-782">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="518db-783">Depois que o novo pool é implantado, a ferramenta Migração de Anúncios de Número Não Atribuído é usada para mover a configuração do pool antigo para o novo.</span><span class="sxs-lookup"><span data-stu-id="518db-783">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="518db-784">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-784">Requirements</span></span>

<span data-ttu-id="518db-785">Veja a seguir os principais requisitos necessários para executar com êxito a ferramenta:</span><span class="sxs-lookup"><span data-stu-id="518db-785">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="518db-786">O script deve ser executado de um computador que tenha Skype for Business Server Shell de Gerenciamento instalado.</span><span class="sxs-lookup"><span data-stu-id="518db-786">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="518db-787">O aplicativo de comunicado deve ser implantado com êxito na origem e destino Skype for Business Servidores ou Pools.</span><span class="sxs-lookup"><span data-stu-id="518db-787">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="518db-788">Move-CsAnnouncementConfiguration script</span><span class="sxs-lookup"><span data-stu-id="518db-788">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="518db-789">O Move-CsAnnouncementConfiguration script requer os dois parâmetros descritos na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="518db-789">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration parâmetros.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="518db-791">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-791">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="518db-792">Movendo a Configuração de Comunicados de Número Não Atribuído de um Pool do Lync Server 2013 para um pool Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="518db-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="518db-793">Este exemplo move os comunicados de número não atribuídos do pool de origem (Lync Server 2013) para o pool de destino (Skype for Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="518db-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="518db-794">Mover a Configuração de Comunicados de Número Não Atribuído de um pool Skype for Business Server 2015 para um Pool do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="518db-794">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="518db-795">Este exemplo move os comunicados de número não atribuídos do pool de origem (Skype for Business Server 2015) para o pool de destino (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="518db-795">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="518db-796">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="518db-796">Web Conf Data</span></span>
<span data-ttu-id="518db-797"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="518db-797"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="518db-798">A Ferramenta de Dados web Conf permite que um administrador do software de comunicações Skype for Business Server 2015 tenha mais controle sobre os dados associados a conferências Web de um organizador.</span><span class="sxs-lookup"><span data-stu-id="518db-798">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="518db-799">Os cenários incluem a capacidade de excluir dados de reunião de um usuário específico com base em um critério de carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="518db-799">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="518db-800">Descrição</span><span class="sxs-lookup"><span data-stu-id="518db-800">Description</span></span>

<span data-ttu-id="518db-801">Esta ferramenta permite que o administrador execute as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="518db-801">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="518db-802">Encontre todos os dados de Webconferência associados a um único usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-802">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="518db-803">Exclua todos os dados de webconferência associados a um único usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-803">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="518db-804">Exclua todos os dados de webconferência associados a um único usuário que seja mais antigo do que uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="518db-804">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="518db-805">Mova todos os dados de Webconferência associados a um único usuário quando esse usuário for movido de um pool para outro.</span><span class="sxs-lookup"><span data-stu-id="518db-805">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="518db-806">As Ferramentas de Kit de Recursos do Lync Server 2010 suportam mover todos os dados de Webconferência associados a um único usuário quando esse usuário é movido de um pool para outro.</span><span class="sxs-lookup"><span data-stu-id="518db-806">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="518db-807">Essa funcionalidade agora é preterida dessa ferramenta em favor do **parâmetro MoveConferenceData.**</span><span class="sxs-lookup"><span data-stu-id="518db-807">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="518db-808">Para obter detalhes sobre esse parâmetro, consulte o cmdlet [Move-CsUser.](/powershell/module/skype/move-csuser?)</span><span class="sxs-lookup"><span data-stu-id="518db-808">For details about this parameter, see the [Move-CsUser](/powershell/module/skype/move-csuser?) cmdlet.</span></span>

<span data-ttu-id="518db-809">A ferramenta exclui dados de reunião somente para reuniões inativas.</span><span class="sxs-lookup"><span data-stu-id="518db-809">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="518db-810">Reuniões ativas (ou reuniões em sessões) não podem ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="518db-810">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="518db-811">Essa ferramenta deve ser executado de um computador que está no mesmo pool que o usuário de destino.</span><span class="sxs-lookup"><span data-stu-id="518db-811">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="518db-812">O usuário cujos dados de conteúdo de reunião estão sendo gerenciados por essa ferramenta deve estar no mesmo pool de usuários.</span><span class="sxs-lookup"><span data-stu-id="518db-812">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="518db-813">Saída</span><span class="sxs-lookup"><span data-stu-id="518db-813">Output</span></span>

<span data-ttu-id="518db-814">Esta ferramenta resulta nos resultados de cada uma das operações:</span><span class="sxs-lookup"><span data-stu-id="518db-814">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="518db-815">Se uma consulta for realizada, a ferramenta será saída da lista de todas as pastas de dados de reunião inativas que têm esse usuário como organizador.</span><span class="sxs-lookup"><span data-stu-id="518db-815">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="518db-816">Se uma exclusão for executada, a ferramenta será saída da lista de todas as pastas de dados de reunião cujos dados serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="518db-816">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="518db-817">Requirements</span><span class="sxs-lookup"><span data-stu-id="518db-817">Requirements</span></span>

<span data-ttu-id="518db-818">A ferramenta precisa ser executado no mesmo pool em que o organizador está no momento.</span><span class="sxs-lookup"><span data-stu-id="518db-818">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="518db-819">A ferramenta deve ser executado usando privilégios de administrador com acesso ao Armazenamento de Arquivos de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="518db-819">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="518db-820">Exemplos</span><span class="sxs-lookup"><span data-stu-id="518db-820">Examples</span></span>

<span data-ttu-id="518db-821">A tabela a seguir descreve os parâmetros, alguns dos quais são usados nos exemplos.</span><span class="sxs-lookup"><span data-stu-id="518db-821">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parâmetros da Ferramenta de Dados web Conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="518db-823">O exemplo anterior mostra como um comando de consulta funcionaria.</span><span class="sxs-lookup"><span data-stu-id="518db-823">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="518db-824">A saída desse comando seria uma lista de todas as pastas de conteúdo de reunião que seriam afetadas por essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="518db-824">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="518db-825">O anterior é um exemplo de um comando delete.</span><span class="sxs-lookup"><span data-stu-id="518db-825">The preceding is an example of a delete command.</span></span> <span data-ttu-id="518db-826">O comando delete removerá todas as pastas de reunião inativas desse usuário.</span><span class="sxs-lookup"><span data-stu-id="518db-826">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="518db-827">Resumo</span><span class="sxs-lookup"><span data-stu-id="518db-827">Summary</span></span>

<span data-ttu-id="518db-828">Essa ferramenta pode ser um recurso valioso para administradores que precisam de controle mais preciso sobre dados de reunião de conferência.</span><span class="sxs-lookup"><span data-stu-id="518db-828">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>
