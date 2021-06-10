---
title: Use o planejador de rede para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: O administrador pode aprender a usar o Planejador de Rede para determinar os requisitos de rede para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240474"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="309a9-103">Use o planejador de rede para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="309a9-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="309a9-104">O Planejador de Rede é uma nova ferramenta que está disponível no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="309a9-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="309a9-105">Ele pode ser encontrado indo para **Planning**  >  **Network planner**.</span><span class="sxs-lookup"><span data-stu-id="309a9-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="309a9-106">Em apenas algumas etapas, o Planejador de Rede pode ajudá-lo a determinar e organizar os requisitos de rede para conectar Microsoft Teams usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="309a9-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="309a9-107">Quando você fornece detalhes de sua rede e uso do Teams, o Planejador de Rede calcula seus requisitos de rede para implantar o Teams e o cloud voice nos locais físicos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="309a9-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Captura de tela do planejador de rede](media/network-planner.png)

<span data-ttu-id="309a9-109">O planejador de rede permite que você:</span><span class="sxs-lookup"><span data-stu-id="309a9-109">Network planner allows you to:</span></span>

- <span data-ttu-id="309a9-110">Crie representações da sua organização usando sites e personas recomendadas da Microsoft (funcionários do office, funcionários remotos e Teams de sala).</span><span class="sxs-lookup"><span data-stu-id="309a9-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="309a9-111">As personas recomendadas foram desenvolvidas com base nos dados Teams cenários de melhor uso e padrões de uso típicos.</span><span class="sxs-lookup"><span data-stu-id="309a9-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="309a9-112">No entanto, você pode criar até três personas personalizadas, além das três personas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="309a9-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="309a9-113">Gere relatórios e calcule os requisitos de largura de banda para Teams uso.</span><span class="sxs-lookup"><span data-stu-id="309a9-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="309a9-114">Para usar o Planejador de Rede, você deve ser um Administrador Global, um administrador Teams ou um Teams de Comunicações.</span><span class="sxs-lookup"><span data-stu-id="309a9-114">To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="309a9-115">Criar uma persona personalizada</span><span class="sxs-lookup"><span data-stu-id="309a9-115">Create a custom persona</span></span>

<span data-ttu-id="309a9-116">Siga estas etapas para criar uma persona personalizada:</span><span class="sxs-lookup"><span data-stu-id="309a9-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="309a9-117">Vá para o planejador de rede no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="309a9-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="309a9-118">Na guia **Personas,** clique **em + Persona personalizada.**</span><span class="sxs-lookup"><span data-stu-id="309a9-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="309a9-119">No painel **Nova persona** personalizada, adicione um nome e uma descrição para a nova persona.</span><span class="sxs-lookup"><span data-stu-id="309a9-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="309a9-120">Selecione as permissões que essa persona usará dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="309a9-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="309a9-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="309a9-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="309a9-122">Criar seu plano</span><span class="sxs-lookup"><span data-stu-id="309a9-122">Build your plan</span></span>

<span data-ttu-id="309a9-123">Siga estas etapas para começar a criar seu plano de rede:</span><span class="sxs-lookup"><span data-stu-id="309a9-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="309a9-124">Vá para o planejador de rede no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="309a9-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="309a9-125">Na guia **Plano de Rede,** clique **em Adicionar um plano de rede**.</span><span class="sxs-lookup"><span data-stu-id="309a9-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="309a9-126">Insira um nome e uma descrição para seu plano de rede.</span><span class="sxs-lookup"><span data-stu-id="309a9-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="309a9-127">O plano de rede aparecerá na lista de planos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="309a9-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="309a9-128">Clique no nome do plano para selecionar o novo plano.</span><span class="sxs-lookup"><span data-stu-id="309a9-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="309a9-129">Adicione sites para criar uma representação da configuração de rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="309a9-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="309a9-130">Dependendo da rede da sua organização, talvez você queira usar sites para representar um edifício, um local de escritório ou outra coisa.</span><span class="sxs-lookup"><span data-stu-id="309a9-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="309a9-131">Os sites podem ser conectados por uma WAN para permitir o compartilhamento de conexões de internet e/ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="309a9-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="309a9-132">Para melhores resultados, crie sites com conexões locais antes de criar sites que se conectem remotamente à Internet ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="309a9-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="309a9-133">Para criar um site:</span><span class="sxs-lookup"><span data-stu-id="309a9-133">To create a site:</span></span>

    1. <span data-ttu-id="309a9-134">Adicione um nome e uma descrição para seu site.</span><span class="sxs-lookup"><span data-stu-id="309a9-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="309a9-135">Em **Configurações de rede,** adicione o número de usuários de rede nesse site (necessário).</span><span class="sxs-lookup"><span data-stu-id="309a9-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="309a9-136">Adicione detalhes de rede: capacidade wan habilitada para WAN, saída da Internet (**Local** ou Remota **)** e saída PSTN (nenhuma, local ou remota).</span><span class="sxs-lookup"><span data-stu-id="309a9-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="309a9-137">Você deve adicionar números de capacidade wan e internet para ver recomendações de largura de banda específicas ao gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="309a9-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="309a9-138">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="309a9-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="309a9-139">Criar um relatório</span><span class="sxs-lookup"><span data-stu-id="309a9-139">Create a report</span></span>

<span data-ttu-id="309a9-140">Depois de adicionar todos os sites, você pode criar um relatório, da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="309a9-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="309a9-141">Na guia **Relatórios,** clique em **Iniciar um relatório**.</span><span class="sxs-lookup"><span data-stu-id="309a9-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="309a9-142">Para cada site criado, distribua o número de usuários entre as personas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="309a9-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="309a9-143">Se você usar as personas recomendadas pela Microsoft, o número será distribuído automaticamente (80% de funcionários de escritório e 20% de trabalho remoto).</span><span class="sxs-lookup"><span data-stu-id="309a9-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="309a9-144">Depois de concluir a distribuição, clique em **Gerar relatório**.</span><span class="sxs-lookup"><span data-stu-id="309a9-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="309a9-145">O relatório gerado mostrará os requisitos de largura de banda em várias exibições diferentes para que você possa entender claramente a saída:</span><span class="sxs-lookup"><span data-stu-id="309a9-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="309a9-146">Uma tabela com cálculos individuais exibirá requisitos de largura de banda para cada atividade permitida.</span><span class="sxs-lookup"><span data-stu-id="309a9-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="309a9-147">Uma exibição adicional mostrará as necessidades gerais de largura de banda com recomendações.</span><span class="sxs-lookup"><span data-stu-id="309a9-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="309a9-148">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="309a9-148">Click **Save**.</span></span> <span data-ttu-id="309a9-149">Seu relatório estará disponível na lista de relatórios para exibição posterior.</span><span class="sxs-lookup"><span data-stu-id="309a9-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="309a9-150">Exemplo de cenário</span><span class="sxs-lookup"><span data-stu-id="309a9-150">Example scenario</span></span>

<span data-ttu-id="309a9-151">Para um exemplo de como usar o planejador de rede para configurar um plano de rede e gerar um relatório usando essas etapas, baixe o deck do planejador de rede How-To PowerPoint [(somente](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) em inglês).</span><span class="sxs-lookup"><span data-stu-id="309a9-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
