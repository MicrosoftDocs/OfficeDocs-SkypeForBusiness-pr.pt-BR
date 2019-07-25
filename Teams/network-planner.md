---
title: Usar o planejador de rede para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: Saiba como usar o planejador de rede para determinar os requisitos de rede do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea6a4a5989df0a780f75220ec314439f7dafcbe
ms.sourcegitcommit: 384e123f3b5cf1600ebd5ddd69bd022f9b8ba0f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2019
ms.locfileid: "35861876"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="d2eec-103">Usar o planejador de rede para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d2eec-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="d2eec-104">O planejador de rede é uma nova ferramenta que está disponível no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="d2eec-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="d2eec-105">Ele pode ser encontrado indo para >  **configurações de toda a organização**planejador de**rede**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-105">It can be found by going to **Org-wide settings** > **Network planner**.</span></span> <span data-ttu-id="d2eec-106">Em apenas algumas etapas, o planejador de rede pode ajudá-lo a determinar e organizar os requisitos de rede para a conexão de usuários do Microsoft Teams em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="d2eec-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="d2eec-107">Quando você fornece os detalhes da rede e o uso das equipes, o planejador de rede calcula os requisitos de rede para a implantação de equipes e voz na nuvem nos locais físicos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d2eec-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![Captura de tela do planejador de rede](media/network-planner.png)

<span data-ttu-id="d2eec-109">O planejador de rede permite que você:</span><span class="sxs-lookup"><span data-stu-id="d2eec-109">Network Planner allows you to:</span></span>

- <span data-ttu-id="d2eec-110">Crie representações de sua organização usando sites e as pessoas recomendadas da Microsoft (funcionários do Office, funcionários remotos e sistema da sala de equipe).</span><span class="sxs-lookup"><span data-stu-id="d2eec-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2eec-111">As pessoas mais recomendadas foram desenvolvidas com base nos dados dos melhores cenários de uso e nos padrões de uso típicos do teams.</span><span class="sxs-lookup"><span data-stu-id="d2eec-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="d2eec-112">No entanto, você pode criar até três personas personalizadas, além das três pessoas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="d2eec-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="d2eec-113">Gere relatórios e calcule requisitos de largura de banda para uso do teams.</span><span class="sxs-lookup"><span data-stu-id="d2eec-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="d2eec-114">Para usar o planejador de rede, você deve ser um administrador global, administrador de serviços do teams ou administrador de comunicações do teams.</span><span class="sxs-lookup"><span data-stu-id="d2eec-114">To use Network Planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="d2eec-115">Criar uma pessoa personalizada</span><span class="sxs-lookup"><span data-stu-id="d2eec-115">Create a custom persona</span></span>

<span data-ttu-id="d2eec-116">Siga estas etapas para criar uma pessoa personalizada:</span><span class="sxs-lookup"><span data-stu-id="d2eec-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="d2eec-117">Vá para o planejador de rede no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2eec-117">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="d2eec-118">Na guia **pessoas** , clique em **+ Personalizar pessoa**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="d2eec-119">No painel **novo persona personalizado** , adicione um nome e uma descrição para o novo persona.</span><span class="sxs-lookup"><span data-stu-id="d2eec-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="d2eec-120">Selecione as permissões que esta pessoa usará dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="d2eec-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="d2eec-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="d2eec-122">Crie seu plano</span><span class="sxs-lookup"><span data-stu-id="d2eec-122">Build your plan</span></span>

<span data-ttu-id="d2eec-123">Siga estas etapas para começar a criar seu plano de rede:</span><span class="sxs-lookup"><span data-stu-id="d2eec-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="d2eec-124">Vá para o planejador de rede no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2eec-124">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="d2eec-125">Na guia **plano de rede** , clique em **Adicionar um plano de rede**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="d2eec-126">Insira um nome e uma descrição para o plano de rede.</span><span class="sxs-lookup"><span data-stu-id="d2eec-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="d2eec-127">O plano de rede será exibido na lista de planos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d2eec-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="d2eec-128">Clique no nome do plano para selecionar o novo plano.</span><span class="sxs-lookup"><span data-stu-id="d2eec-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="d2eec-129">Adicione sites para criar uma representação da configuração de rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d2eec-129">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="d2eec-130">Dependendo da rede da sua organização, talvez você queira usar sites para representar um edifício, um local de escritório ou outra coisa.</span><span class="sxs-lookup"><span data-stu-id="d2eec-130">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="d2eec-131">Os sites podem ser conectados por uma WAN para permitir o compartilhamento de conexões de Internet e/ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2eec-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="d2eec-132">Para obter melhores resultados, crie sites com conexões locais antes de criar sites que se conectam remotamente à Internet ou à PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2eec-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="d2eec-133">Para criar um site:</span><span class="sxs-lookup"><span data-stu-id="d2eec-133">To create a site:</span></span>

    1. <span data-ttu-id="d2eec-134">Adicione um nome e uma descrição para o seu site.</span><span class="sxs-lookup"><span data-stu-id="d2eec-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="d2eec-135">Em **configurações de rede**, adicione o número de usuários da rede nesse site (obrigatório).</span><span class="sxs-lookup"><span data-stu-id="d2eec-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="d2eec-136">Adicionar detalhes de rede: habilitados para WAN, capacidade WAN, egresso de Internet (**local** ou **remota**) e egresso PSTN (nenhum, local ou remota).</span><span class="sxs-lookup"><span data-stu-id="d2eec-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2eec-137">Você deve adicionar números de capacidade de Internet e WAN para ver recomendações específicas de largura de banda ao gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="d2eec-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="d2eec-138">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="d2eec-139">Criar um relatório</span><span class="sxs-lookup"><span data-stu-id="d2eec-139">Create a report</span></span>

<span data-ttu-id="d2eec-140">Depois de adicionar todos os sites, você pode criar um relatório da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="d2eec-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="d2eec-141">Na guia **relatórios** , clique em **Iniciar um relatório**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="d2eec-142">Para cada site que você criar, distribua o número de usuários nas pessoas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d2eec-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="d2eec-143">Se você usar as pessoas recomendadas pela Microsoft, o número será distribuído automaticamente (80% de trabalho do Office e 20% de trabalho remoto).</span><span class="sxs-lookup"><span data-stu-id="d2eec-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="d2eec-144">Depois de concluir a distribuição, clique em **gerar relatório**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="d2eec-145">O relatório gerado mostrará os requisitos de largura de banda em vários modos de exibição diferentes para que você possa entender claramente a saída:</span><span class="sxs-lookup"><span data-stu-id="d2eec-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="d2eec-146">Uma tabela com cálculos individuais mostrará requisitos de largura de banda para cada atividade permitida.</span><span class="sxs-lookup"><span data-stu-id="d2eec-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="d2eec-147">Um modo de exibição adicional mostrará as necessidades gerais de largura de banda com recomendações.</span><span class="sxs-lookup"><span data-stu-id="d2eec-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="d2eec-148">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2eec-148">Click **Save**.</span></span> <span data-ttu-id="d2eec-149">Seu relatório estará disponível na lista relatórios para exibição posterior.</span><span class="sxs-lookup"><span data-stu-id="d2eec-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="d2eec-150">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="d2eec-150">Example scenario</span></span>

<span data-ttu-id="d2eec-151">Para obter um exemplo de como usar o planejador de rede para configurar um plano de rede e gerar um relatório usando essas etapas, baixe o conjunto do [PowerPoint de instruções](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) do planejador de rede (somente em inglês).</span><span class="sxs-lookup"><span data-stu-id="d2eec-151">For an example of how to use the Network Planner to set up a network plan and generate a report using these steps, download the [Network Planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
