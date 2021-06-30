---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Saiba como executar o Microsoft Teams em um ambiente VDI (Infraestrutura de Área de Trabalho Virtualizada).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d498f66241de3edc46a86ae884b615384508b84
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203620"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="a3b94-103">Teams para Infraestrutura de Área de Trabalho Virtualizada</span><span class="sxs-lookup"><span data-stu-id="a3b94-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="a3b94-104">Este artigo descreve os requisitos e limitações para o uso Microsoft Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="a3b94-105">O que é VDI?</span><span class="sxs-lookup"><span data-stu-id="a3b94-105">What is VDI?</span></span>

<span data-ttu-id="a3b94-106">Virtual Desktop Infrastructure (VDI) é uma tecnologia de virtualização que hospeda um sistema operacional da área de trabalho e aplicativos em um servidor centralizado em um data center.</span><span class="sxs-lookup"><span data-stu-id="a3b94-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="a3b94-107">Isso permite uma experiência de área de trabalho totalmente personalizada para usuários com uma fonte centralizada totalmente segura e compatível.</span><span class="sxs-lookup"><span data-stu-id="a3b94-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="a3b94-108">Microsoft Teams em um ambiente virtualizado oferece suporte a chat e colaboração.</span><span class="sxs-lookup"><span data-stu-id="a3b94-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="a3b94-109">Além disso, com Windows de área de trabalho virtual, citrix e plataformas VMware, também há suporte para a funcionalidade de chamada e reunião.</span><span class="sxs-lookup"><span data-stu-id="a3b94-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="a3b94-110">Teams em um ambiente virtualizado oferece suporte a várias configurações.</span><span class="sxs-lookup"><span data-stu-id="a3b94-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="a3b94-111">Elas incluem modos VDI, dedicados, compartilhados, persistentes e não persistentes.</span><span class="sxs-lookup"><span data-stu-id="a3b94-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="a3b94-112">Os recursos estão em desenvolvimento contínuo e são adicionados regularmente, e a funcionalidade será expandida nos próximos meses e anos.</span><span class="sxs-lookup"><span data-stu-id="a3b94-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="a3b94-113">Usar Teams em um ambiente virtualizado pode ser um pouco diferente de usar Teams em um ambiente não virtualizado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="a3b94-114">Por exemplo, alguns recursos avançados podem não estar disponíveis em um ambiente virtualizado, e a resolução de vídeo pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="a3b94-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="a3b94-115">Para garantir uma experiência de usuário ideal, siga as diretrizes neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a3b94-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="a3b94-116">Para obter detalhes sobre Teams VDI em diferentes plataformas, [consulte Teams recursos por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="a3b94-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="a3b94-117">Teams componentes VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-117">Teams on VDI components</span></span>

<span data-ttu-id="a3b94-118">Usar Teams em um ambiente virtualizado requer os seguintes componentes.</span><span class="sxs-lookup"><span data-stu-id="a3b94-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="a3b94-119">**Agente de virtualização**: o gerenciador de recursos e conexões para o provedor de virtualização, como o Azure</span><span class="sxs-lookup"><span data-stu-id="a3b94-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="a3b94-120">**Área de** trabalho virtual : a pilha da máquina virtual (VM) que executa Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3b94-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="a3b94-121">**Cliente fino**: o ponto de extremidade com o que o usuário faz interface física</span><span class="sxs-lookup"><span data-stu-id="a3b94-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="a3b94-122">**Teams da área de** trabalho : o Teams cliente da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="a3b94-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="a3b94-123">Teams requisitos VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="a3b94-124">Requisitos do provedor de virtualização</span><span class="sxs-lookup"><span data-stu-id="a3b94-124">Virtualization provider requirements</span></span>

<span data-ttu-id="a3b94-125">O Teams da área de trabalho foi validado com os principais provedores de soluções de virtualização.</span><span class="sxs-lookup"><span data-stu-id="a3b94-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="a3b94-126">Com vários provedores de mercado, recomendamos que você consulte seu provedor de soluções de virtualização para garantir que você atender aos requisitos mínimos.</span><span class="sxs-lookup"><span data-stu-id="a3b94-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="a3b94-127">Atualmente, Teams na VDI com otimização de áudio/vídeo (AV) é certificada com Windows Área de Trabalho Virtual, Citrix e VMware.</span><span class="sxs-lookup"><span data-stu-id="a3b94-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="a3b94-128">Revise as informações nesta seção para garantir que você atender a todos os requisitos para a funcionalidade adequada.</span><span class="sxs-lookup"><span data-stu-id="a3b94-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="a3b94-129">Plataformas certificadas para Teams</span><span class="sxs-lookup"><span data-stu-id="a3b94-129">Platforms certified for Teams</span></span>

<span data-ttu-id="a3b94-130">As plataformas a seguir têm soluções de infraestrutura de área de trabalho virtual para Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="a3b94-131">Plataforma</span><span class="sxs-lookup"><span data-stu-id="a3b94-131">Platform</span></span>|<span data-ttu-id="a3b94-132">Solução</span><span class="sxs-lookup"><span data-stu-id="a3b94-132">Solution</span></span>|
|----|---|
|![O logotipo que representa a Microsoft](media/microsoft-logo.png)| <span data-ttu-id="a3b94-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Área de trabalho virtual</a></span><span class="sxs-lookup"><span data-stu-id="a3b94-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![O logotipo que representa Citrix](media/citrix-logo.png)| <span data-ttu-id="a3b94-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span><span class="sxs-lookup"><span data-stu-id="a3b94-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![O logotipo que representa a VMware](media/vmware-logo.png)| <span data-ttu-id="a3b94-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="a3b94-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="a3b94-139">Windows Área de trabalho virtual</span><span class="sxs-lookup"><span data-stu-id="a3b94-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="a3b94-140">Windows A Área de Trabalho Virtual fornece otimização av para Teams em VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="a3b94-141">Para saber mais e requisitos e instalação, consulte [Use Teams em Windows Área de Trabalho Virtual](/azure/virtual-desktop/teams-on-wvd).</span><span class="sxs-lookup"><span data-stu-id="a3b94-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="a3b94-142">Requisitos do Citrix Virtual Apps and Desktops</span><span class="sxs-lookup"><span data-stu-id="a3b94-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="a3b94-143">O Citrix Virtual Apps and Desktops (anteriormente conhecido como XenApp e XenDesktop) fornece otimização av para Teams em VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="a3b94-144">Com o Citrix Virtual Apps and Desktops, Teams em VDI oferece suporte à funcionalidade de chamada e reunião, além de chat e colaboração.</span><span class="sxs-lookup"><span data-stu-id="a3b94-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="a3b94-145">Você pode baixar a versão mais recente do Citrix Virtual Apps and Desktops [no site de downloads do Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)</span><span class="sxs-lookup"><span data-stu-id="a3b94-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="a3b94-146">(Você precisará entrar primeiro.) Os componentes necessários são agrupados no [aplicativo CWA (Citrix Workspace)](https://www.citrix.com/downloads/workspace-app/) e no VDA (Virtual Delivery Agent) por padrão.</span><span class="sxs-lookup"><span data-stu-id="a3b94-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="a3b94-147">Não é necessário instalar componentes ou plug-ins adicionais no CWA ou no VDA.</span><span class="sxs-lookup"><span data-stu-id="a3b94-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="a3b94-148">Para saber mais sobre os requisitos de servidor e cliente mais recentes, [consulte este site do Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span><span class="sxs-lookup"><span data-stu-id="a3b94-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="a3b94-149">Requisitos de Espaço de Trabalho e Área de Trabalho do VMware Horizon</span><span class="sxs-lookup"><span data-stu-id="a3b94-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="a3b94-150">O VMware Horizon é uma plataforma moderna para entrega segura de desktops virtuais e aplicativos em toda a nuvem híbrida.</span><span class="sxs-lookup"><span data-stu-id="a3b94-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="a3b94-151">Para oferecer uma ótima experiência do usuário final, o VMware Horizon fornece otimização de mídia para Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="a3b94-152">Essa otimização melhora a produtividade geral em áreas de trabalho virtuais e aplicativos e aprimora a experiência do usuário ao chamar e reunião usando Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="a3b94-153">Você pode baixar a versão mais recente do VMware Horizon na [página Downloads do VMware.](https://my.vmware.com/web/vmware/downloads/#all_products)</span><span class="sxs-lookup"><span data-stu-id="a3b94-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="a3b94-154">Os componentes de otimização de mídia necessários fazem parte do Agente do Horizonte e do Cliente horizon por padrão e não há necessidade de instalar qualquer plug-in adicional para usar o recurso de otimização para Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="a3b94-155">Para obter os requisitos e instruções mais recentes sobre como configurar a otimização de mídia para Teams, consulte [este site VMware](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span><span class="sxs-lookup"><span data-stu-id="a3b94-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="a3b94-156">Instalar ou atualizar o Teams da área de trabalho no VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="a3b94-157">Você pode implantar o Teams desktop para VDI usando uma instalação por máquina ou por usuário usando o pacote MSI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="a3b94-158">Decidir qual abordagem usar depende se você usa uma instalação persistente ou não persistente e as necessidades de funcionalidade associadas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3b94-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="a3b94-159">Para uma instalação persistente dedicada, qualquer abordagem funcionaria.</span><span class="sxs-lookup"><span data-stu-id="a3b94-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="a3b94-160">No entanto, para uma instalação não persistente, o Teams requer uma instalação por máquina para funcionar com eficiência.</span><span class="sxs-lookup"><span data-stu-id="a3b94-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="a3b94-161">Consulte a [seção Configuração não persistente.](#non-persistent-setup)</span><span class="sxs-lookup"><span data-stu-id="a3b94-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="a3b94-162">Com a instalação por máquina, as atualizações automáticas são desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="a3b94-163">Isso significa que, para atualizar o Teams, você deve desinstalar a versão atual para atualizar para uma versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="a3b94-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="a3b94-164">Com a instalação por usuário, as atualizações automáticas são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="a3b94-165">Para a maioria das implantações VDI, recomendamos que você implante Teams usando a instalação por máquina.</span><span class="sxs-lookup"><span data-stu-id="a3b94-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="a3b94-166">Para atualizar para a versão Teams versão mais recente, comece com o procedimento de desinstalação seguido pela implantação Teams versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="a3b94-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="a3b94-167">Para Teams otimização de AV em ambientes VDI funcione corretamente, o ponto de extremidade do cliente fino deve ter acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="a3b94-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="a3b94-168">Se o acesso à Internet não estiver disponível no ponto de extremidade do cliente fino, a inicialização de otimização não será bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="a3b94-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="a3b94-169">Isso significa que o usuário está em um estado de mídia não otimizado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="a3b94-170">Instalação persistente dedicada</span><span class="sxs-lookup"><span data-stu-id="a3b94-170">Dedicated persistent setup</span></span>

<span data-ttu-id="a3b94-171">Em uma instalação persistente dedicada, as alterações do sistema operacional local dos usuários são mantidas após o logoff dos usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="a3b94-172">Para a instalação persistente, Teams oferece suporte à instalação por usuário e por máquina.</span><span class="sxs-lookup"><span data-stu-id="a3b94-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="a3b94-173">A seguir está a configuração mínima de VM recomendada.</span><span class="sxs-lookup"><span data-stu-id="a3b94-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="a3b94-174">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="a3b94-174">Parameter</span></span>  |<span data-ttu-id="a3b94-175">Sistema operacional de estação de trabalho</span><span class="sxs-lookup"><span data-stu-id="a3b94-175">Workstation operating system</span></span>  |<span data-ttu-id="a3b94-176">Sistema operacional do servidor</span><span class="sxs-lookup"><span data-stu-id="a3b94-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a3b94-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="a3b94-177">vCPU</span></span>   |    <span data-ttu-id="a3b94-178">2 núcleos</span><span class="sxs-lookup"><span data-stu-id="a3b94-178">2 cores</span></span>     |  <span data-ttu-id="a3b94-179">4,6 ou 8</span><span class="sxs-lookup"><span data-stu-id="a3b94-179">4,6, or 8</span></span><br><span data-ttu-id="a3b94-180">É importante entender a configuração subjacente de acesso à memória não uniforme (NUMA) e configurar suas VMs de acordo.</span><span class="sxs-lookup"><span data-stu-id="a3b94-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="a3b94-181">RAM</span><span class="sxs-lookup"><span data-stu-id="a3b94-181">RAM</span></span>     |   <span data-ttu-id="a3b94-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="a3b94-182">4 GB</span></span>      | <span data-ttu-id="a3b94-183">512 a 1024 MB por usuário</span><span class="sxs-lookup"><span data-stu-id="a3b94-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="a3b94-184">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="a3b94-184">Storage</span></span>    | <span data-ttu-id="a3b94-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="a3b94-185">8 GB</span></span>        | <span data-ttu-id="a3b94-186">40 a 60 GB</span><span class="sxs-lookup"><span data-stu-id="a3b94-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="a3b94-187">Instalação não persistente</span><span class="sxs-lookup"><span data-stu-id="a3b94-187">Non-persistent setup</span></span>

<span data-ttu-id="a3b94-188">Em uma configuração não persistente, as alterações do sistema operacional local dos usuários não são mantidas depois que os usuários fazem logoff.</span><span class="sxs-lookup"><span data-stu-id="a3b94-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="a3b94-189">Essas configurações são normalmente sessões compartilhadas com vários usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="a3b94-190">A configuração da VM varia com base no número de usuários e nos recursos de caixa física disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a3b94-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="a3b94-191">Para uma configuração não persistente, o Teams da área de trabalho deve ser instalado por máquina na imagem dourada.</span><span class="sxs-lookup"><span data-stu-id="a3b94-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="a3b94-192">(Para saber mais, consulte a seção Instalar ou atualizar o Teams [da área de trabalho na VDI.)](#install-or-update-the-teams-desktop-app-on-vdi) Isso garante um lançamento eficiente do aplicativo Teams durante uma sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="a3b94-193">Usar Teams em uma configuração não persistente também requer um gerenciador de cache de perfil, para uma sincronização de dados Teams tempo de execução eficiente.</span><span class="sxs-lookup"><span data-stu-id="a3b94-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="a3b94-194">A sincronização eficiente de dados garante que as informações específicas do usuário apropriadas (como dados, perfil ou configurações do usuário) são armazenadas em cache durante a sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="a3b94-195">Certifique-se de que os dados nessas duas pastas sejam sincronizados:</span><span class="sxs-lookup"><span data-stu-id="a3b94-195">Make sure data in these two folders are synched:</span></span><br>

- <span data-ttu-id="a3b94-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="a3b94-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="a3b94-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="a3b94-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="a3b94-198">Uma pasta roaming (ou, se você estiver usando redirecionamento de pasta, um gerenciador de cache) é necessária para garantir que o aplicativo Teams tenha os dados e arquivos de tempo de execução necessários para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a3b94-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="a3b94-199">Isso é necessário para atenuar problemas de latência de rede ou falhas de rede, o que poderia causar erros de aplicativo e uma experiência lenta devido a dados e arquivos indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="a3b94-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="a3b94-200">Há uma variedade de soluções de gerenciador de cache disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a3b94-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="a3b94-201">Por exemplo, [FSLogix](/fslogix/overview).</span><span class="sxs-lookup"><span data-stu-id="a3b94-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="a3b94-202">Consulte seu provedor de gerenciador de cache para obter instruções de configuração específicas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="a3b94-203">Teams lista de exclusão de conteúdo em cache para instalação não persistente</span><span class="sxs-lookup"><span data-stu-id="a3b94-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="a3b94-204">Exclua o seguinte da pasta Teams de cache, %appdata%/Microsoft/Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="a3b94-205">Excluir esses itens ajuda a reduzir o tamanho do cache do usuário para otimizar ainda mais sua configuração não persistente.</span><span class="sxs-lookup"><span data-stu-id="a3b94-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="a3b94-206">.txt arquivos</span><span class="sxs-lookup"><span data-stu-id="a3b94-206">.txt files</span></span>
- <span data-ttu-id="a3b94-207">Pasta de pilha de mídia</span><span class="sxs-lookup"><span data-stu-id="a3b94-207">Media-stack folder</span></span>
- <span data-ttu-id="a3b94-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="a3b94-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="a3b94-209">Microsoft 365 Apps para Grandes Empresas considerações</span><span class="sxs-lookup"><span data-stu-id="a3b94-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="a3b94-210">Considere o seguinte ao implantar Teams com Microsoft 365 Apps para Grandes Empresas na VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a3b94-211">Novas implantações de Teams por meio Microsoft 365 Apps para Grandes Empresas</span><span class="sxs-lookup"><span data-stu-id="a3b94-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a3b94-212">Antes de implantar Teams por Microsoft 365 Apps para Grandes Empresas, primeiro desinstale todos os aplicativos de Teams pré-existentes se eles foram implantados usando a instalação por máquina.</span><span class="sxs-lookup"><span data-stu-id="a3b94-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="a3b94-213">Teams por Microsoft 365 Apps para Grandes Empresas é instalado por usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="a3b94-214">Para saber mais, confira [a seção Instalar ou atualizar o Teams desktop na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)</span><span class="sxs-lookup"><span data-stu-id="a3b94-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="a3b94-215">Teams implantações por meio Microsoft 365 Apps para Grandes Empresas atualizações</span><span class="sxs-lookup"><span data-stu-id="a3b94-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="a3b94-216">Teams também está sendo adicionado às instalações existentes de Microsoft 365 Apps para Grandes Empresas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="a3b94-217">Como Microsoft 365 Apps para Grandes Empresas instala somente Teams por usuário, consulte a seção Instalar ou atualizar o Teams da área de trabalho [na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)</span><span class="sxs-lookup"><span data-stu-id="a3b94-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a3b94-218">Usando Teams com instalação por máquina e Microsoft 365 Apps para Grandes Empresas</span><span class="sxs-lookup"><span data-stu-id="a3b94-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a3b94-219">Microsoft 365 Apps para Grandes Empresas não dá suporte a instalações por máquina de Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="a3b94-220">Para usar a instalação por máquina, você deve excluir Teams de Microsoft 365 Apps para Grandes Empresas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="a3b94-221">Consulte [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and How to exclude Teams [deployment through Microsoft 365 Apps para Grandes Empresas](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span><span class="sxs-lookup"><span data-stu-id="a3b94-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a3b94-222">Como excluir Teams implantação por meio Microsoft 365 Apps para Grandes Empresas</span><span class="sxs-lookup"><span data-stu-id="a3b94-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a3b94-223">Para saber mais sobre Teams e Microsoft 365 Apps para Grandes Empresas, consulte Como excluir o Teams de novas instalações do Microsoft 365 Apps para Grandes Empresas e Usar [a](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) Política de Grupo para controlar a instalação do [Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="a3b94-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="a3b94-224">Implantar o Teams da área de trabalho na VM</span><span class="sxs-lookup"><span data-stu-id="a3b94-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="a3b94-225">Baixe o Teams MSI que corresponde ao seu sistema operacional VDI VM usando um dos seguintes links:</span><span class="sxs-lookup"><span data-stu-id="a3b94-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="a3b94-226">Versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="a3b94-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="a3b94-227">Versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="a3b94-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="a3b94-228">Para nuvens do governo, consulte [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span><span class="sxs-lookup"><span data-stu-id="a3b94-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="a3b94-229">A versão mínima do Teams da área de trabalho necessária é a versão 1.3.00.4461.</span><span class="sxs-lookup"><span data-stu-id="a3b94-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="a3b94-230">(A espera PSTN não é suportada em versões anteriores.)</span><span class="sxs-lookup"><span data-stu-id="a3b94-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="a3b94-231">Instale o MSI na VM VDI executando um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a3b94-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="a3b94-232">Instalação por usuário (padrão)</span><span class="sxs-lookup"><span data-stu-id="a3b94-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="a3b94-233">Esse processo é a instalação padrão, que instala Teams na pasta de usuário %AppData%.</span><span class="sxs-lookup"><span data-stu-id="a3b94-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="a3b94-234">Nesse ponto, a configuração da imagem dourada está concluída.</span><span class="sxs-lookup"><span data-stu-id="a3b94-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="a3b94-235">Teams funcionará corretamente com a instalação por usuário em uma instalação não persistente.</span><span class="sxs-lookup"><span data-stu-id="a3b94-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="a3b94-236">Instalação por máquina</span><span class="sxs-lookup"><span data-stu-id="a3b94-236">Per-machine installation</span></span>

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        <span data-ttu-id="a3b94-237">Esse processo adiciona uma chave de registro necessária ao computador que permite que o Teams saiba que é uma instância VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-237">This process adds a required registry key to the machine that lets the Teams installer know it is a VDI instance.</span></span>  <span data-ttu-id="a3b94-238">Sem ele, o instalador falhará, informando: "A instalação falhou.</span><span class="sxs-lookup"><span data-stu-id="a3b94-238">Without it, the installer will error out, stating: "Installation has failed.</span></span>  <span data-ttu-id="a3b94-239">Não é possível instalar para todos os usuários quando um ambiente VDI não é detectado."</span><span class="sxs-lookup"><span data-stu-id="a3b94-239">Cannot install for all users when a VDI environment is not detected."</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="a3b94-240">Esse processo instala Teams na pasta Arquivos de Programas (x86) em um sistema operacional de 64 bits e na pasta Arquivos de Programas em um sistema operacional de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="a3b94-240">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="a3b94-241">Nesse ponto, a configuração da imagem dourada está concluída.</span><span class="sxs-lookup"><span data-stu-id="a3b94-241">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="a3b94-242">A instalação Teams por máquina é necessária para configurações não persistentes.</span><span class="sxs-lookup"><span data-stu-id="a3b94-242">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="a3b94-243">A próxima sessão de logon interativo inicia o Teams e pede credenciais.</span><span class="sxs-lookup"><span data-stu-id="a3b94-243">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a3b94-244">Esses exemplos também usam o **parâmetro ALLUSERS=1.**</span><span class="sxs-lookup"><span data-stu-id="a3b94-244">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="a3b94-245">Quando você define este parâmetro, o Instalador de Todo o Computador do Teams aparece em Programas e recursos no Painel de Controle e em Aplicativos e Recursos nas Configurações do Windows para todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="a3b94-245">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="a3b94-246">Todos os usuários podem desinstalar Teams se eles têm credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="a3b94-246">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="a3b94-247">É importante entender a diferença entre **ALLUSERS=1** e **ALLUSER=1**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-247">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="a3b94-248">O **parâmetro ALLUSERS=1** pode ser usado em ambientes que não sejam VDI e VDI, enquanto o parâmetro **ALLUSER=1** é usado somente em ambientes VDI para especificar uma instalação por máquina.</span><span class="sxs-lookup"><span data-stu-id="a3b94-248">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="a3b94-249">Desinstale o MSI da VM VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-249">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="a3b94-250">Há duas maneiras de desinstalar Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-250">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="a3b94-251">Script do PowerShell: você pode usar esse [script do PowerShell](scripts/powershell-script-deployment-cleanup.md) para desinstalar Teams e remover a pasta Teams para um usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-251">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="a3b94-252">Execute o script para cada perfil de usuário no qual Teams foi instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="a3b94-252">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="a3b94-253">Linha de comando: Execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="a3b94-253">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="a3b94-254">Esse processo desinstala Teams da pasta Arquivos de Programas (x86) ou da pasta Arquivos de Programas, dependendo do ambiente do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="a3b94-254">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="a3b94-255">Teams considerações sobre o desempenho da VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-255">Teams on VDI performance considerations</span></span>

<span data-ttu-id="a3b94-256">Há uma variedade de configurações de configuração virtualizadas, cada uma com um foco diferente para otimização.</span><span class="sxs-lookup"><span data-stu-id="a3b94-256">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="a3b94-257">Por exemplo, uma configuração pode se concentrar na densidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-257">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="a3b94-258">Ao planejar, considere o seguinte para ajudar a otimizar sua instalação com base nas necessidades de carga de trabalho da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3b94-258">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="a3b94-259">Requisito mínimo: Algumas cargas de trabalho podem exigir uma instalação usando recursos que estão acima dos requisitos mínimos.</span><span class="sxs-lookup"><span data-stu-id="a3b94-259">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="a3b94-260">Por exemplo, cargas de trabalho para desenvolvedores que usam aplicativos que exigem mais recursos de computação.</span><span class="sxs-lookup"><span data-stu-id="a3b94-260">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="a3b94-261">Dependências: elas incluem dependências de infraestrutura, carga de trabalho e outras considerações ambientais fora do Teams da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a3b94-261">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="a3b94-262">Recursos desabilitados na VDI: Teams desabilita recursos intensivos de GPU para VDI, o que pode ajudar a melhorar a utilização transitória da CPU.</span><span class="sxs-lookup"><span data-stu-id="a3b94-262">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="a3b94-263">Os seguintes recursos estão desabilitados:</span><span class="sxs-lookup"><span data-stu-id="a3b94-263">The following features are disabled:</span></span>
    - <span data-ttu-id="a3b94-264">Teams Animação CSS</span><span class="sxs-lookup"><span data-stu-id="a3b94-264">Teams CSS animation</span></span>
    - <span data-ttu-id="a3b94-265">Início automático giphy</span><span class="sxs-lookup"><span data-stu-id="a3b94-265">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="a3b94-266">Teams VDI com chamada e reuniões</span><span class="sxs-lookup"><span data-stu-id="a3b94-266">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="a3b94-267">Além de chat e colaboração, o Teams em VDI com chamada e reuniões está disponível com plataformas de provedores de virtualização com suporte.</span><span class="sxs-lookup"><span data-stu-id="a3b94-267">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="a3b94-268">Os recursos suportados são baseados na pilha de mídia WebRTC e na implementação do provedor de virtualização.</span><span class="sxs-lookup"><span data-stu-id="a3b94-268">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="a3b94-269">O diagrama a seguir fornece uma visão geral da arquitetura.</span><span class="sxs-lookup"><span data-stu-id="a3b94-269">The following diagram provides an overview of the architecture.</span></span>

![Diagrama mostrando Teams na arquitetura VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="a3b94-271">Se você atualmente executar o Teams sem otimização de AV na VDI e usar recursos que ainda não são suportados para otimização (como Dar e assumir controle ao compartilhar aplicativos), você terá que definir políticas de provedor de virtualização para desativar Teams redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="a3b94-271">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="a3b94-272">Isso significa que Teams sessões de mídia não serão otimizadas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-272">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="a3b94-273">Para saber mais sobre como definir políticas para desativar Teams redirecionamento, entre em contato com seu provedor de virtualização.</span><span class="sxs-lookup"><span data-stu-id="a3b94-273">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="a3b94-274">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="a3b94-274">Network requirements</span></span>

<span data-ttu-id="a3b94-275">Recomendamos que você avalie seu ambiente para identificar quaisquer riscos e requisitos que possam influenciar sua implantação geral de voz na nuvem e vídeo.</span><span class="sxs-lookup"><span data-stu-id="a3b94-275">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="a3b94-276">Use a [Skype for Business de Avaliação de Rede](https://www.microsoft.com/download/details.aspx?id=53885) para testar se sua rede está pronta para Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-276">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="a3b94-277">Para saber mais sobre como preparar sua rede para Teams, consulte Prepare your [organization's network for Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="a3b94-277">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="a3b94-278">Migrar do Skype for Business VDI para o Teams VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-278">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="a3b94-279">Se você estiver migrando do Skype for Business VDI para o Teams VDI, além das diferenças entre os dois aplicativos, há algumas diferenças quando a VDI também é implementada.</span><span class="sxs-lookup"><span data-stu-id="a3b94-279">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="a3b94-280">Alguns recursos que atualmente não são suportados no Teams VDI que estão no Skype for Business VDI são os seguinte:</span><span class="sxs-lookup"><span data-stu-id="a3b94-280">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="a3b94-281">Política por plataforma para desabilitar alguns recursos av no VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-281">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="a3b94-282">Dar e assumir controle ao compartilhar aplicativos</span><span class="sxs-lookup"><span data-stu-id="a3b94-282">Give and take control when app sharing</span></span>
- <span data-ttu-id="a3b94-283">Compartilhamento de tela do chat sem áudio</span><span class="sxs-lookup"><span data-stu-id="a3b94-283">Screen share from chat without audio</span></span>
- <span data-ttu-id="a3b94-284">Envio e recebimento simultâneos de vídeo e compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="a3b94-284">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="a3b94-285">Teams navegador Chrome versus Teams desktop para VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-285">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="a3b94-286">Teams no navegador Chrome não fornece uma substituição para o aplicativo de área de trabalho Teams para VDI com otimização av.</span><span class="sxs-lookup"><span data-stu-id="a3b94-286">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="a3b94-287">A experiência de chat e colaboração funciona conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-287">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="a3b94-288">Quando a mídia é necessária, há algumas experiências que podem não atender às expectativas do usuário no navegador Chrome:</span><span class="sxs-lookup"><span data-stu-id="a3b94-288">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="a3b94-289">A experiência de streaming de áudio e vídeo pode não ser ideal.</span><span class="sxs-lookup"><span data-stu-id="a3b94-289">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="a3b94-290">Os usuários podem ter atrasos ou qualidade reduzida.</span><span class="sxs-lookup"><span data-stu-id="a3b94-290">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="a3b94-291">As configurações do dispositivo não estão disponíveis nas configurações do navegador.</span><span class="sxs-lookup"><span data-stu-id="a3b94-291">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="a3b94-292">O gerenciamento de dispositivos é manipulado pelo navegador e requer várias configurações nas configurações do site do navegador.</span><span class="sxs-lookup"><span data-stu-id="a3b94-292">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="a3b94-293">As configurações do dispositivo também podem precisar ser definidas no Windows de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a3b94-293">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="a3b94-294">Teams em VDI com chat e colaboração</span><span class="sxs-lookup"><span data-stu-id="a3b94-294">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="a3b94-295">Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você pode definir políticas no nível do usuário para desativar a funcionalidade de chamada e reunião em Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-295">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="a3b94-296">Definir políticas para desativar a funcionalidade de chamada e reunião</span><span class="sxs-lookup"><span data-stu-id="a3b94-296">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="a3b94-297">Você pode definir políticas usando o centro de administração Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3b94-297">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="a3b94-298">Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem.</span><span class="sxs-lookup"><span data-stu-id="a3b94-298">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="a3b94-299">Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-299">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="a3b94-300">[**Políticas de chamada**](teams-calling-policy.md): Teams inclui a política de chamada DisallowCalling interna, na qual todos os recursos de chamada estão desligados.</span><span class="sxs-lookup"><span data-stu-id="a3b94-300">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="a3b94-301">Atribua a política DisallowCalling a todos os usuários da sua organização que usam Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-301">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="a3b94-302">[**Políticas de**](meeting-policies-in-teams.md)reunião : Teams inclui a política de reunião AllOff interna, na qual todos os recursos de reunião estão desligados.</span><span class="sxs-lookup"><span data-stu-id="a3b94-302">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="a3b94-303">Atribua a política AllOff a todos os usuários da sua organização que usam Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-303">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a3b94-304">Atribuir políticas usando o Microsoft Teams de administração</span><span class="sxs-lookup"><span data-stu-id="a3b94-304">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a3b94-305">Para atribuir a política de chamada DisallowCalling e a política de reunião AllOff a um usuário:</span><span class="sxs-lookup"><span data-stu-id="a3b94-305">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="a3b94-306">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-306">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="a3b94-307">Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-307">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a3b94-308">Siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="a3b94-308">Do the following:</span></span>
    1. <span data-ttu-id="a3b94-309">Em **Política de Chamada,** clique **em DisallowCalling**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-309">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2. <span data-ttu-id="a3b94-310">Em **Política de Reunião,** clique **em AllOff**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-310">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="a3b94-311">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-311">Click **Apply**.</span></span>

<span data-ttu-id="a3b94-312">Para atribuir uma política a vários usuários por vez:</span><span class="sxs-lookup"><span data-stu-id="a3b94-312">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="a3b94-313">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="a3b94-313">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="a3b94-314">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-314">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a3b94-315">Para selecionar todos os usuários, clique na (marca de seleção) &#x2713; na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="a3b94-315">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="a3b94-316">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-316">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="a3b94-317">Ou você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a3b94-317">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a3b94-318">Na navegação à esquerda do centro de administração Microsoft Teams, vá para a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="a3b94-318">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="a3b94-319">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a3b94-319">For example:</span></span>
    - <span data-ttu-id="a3b94-320">Vá para **Políticas de Chamada**  >  **de** Voz e clique **em DisallowCalling**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-320">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="a3b94-321">Vá para **Políticas de Reunião** de  >  **Reuniões** e clique em **AllOff**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-321">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="a3b94-322">Selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-322">Select **Manage users**.</span></span>
3. <span data-ttu-id="a3b94-323">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-323">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a3b94-324">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="a3b94-324">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a3b94-325">Quando terminar de adicionar usuários, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-325">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="a3b94-326">Atribuir políticas usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3b94-326">Assign policies using PowerShell</span></span>

<span data-ttu-id="a3b94-327">O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada DisallowCalling a um usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-327">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="a3b94-328">Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamadas, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="a3b94-328">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="a3b94-329">O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOff a um usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-329">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="a3b94-330">Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="a3b94-330">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="a3b94-331">Migrar Teams VDI com chat e colaboração para otimizar Teams com chamada e reuniões</span><span class="sxs-lookup"><span data-stu-id="a3b94-331">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="a3b94-332">Se você tiver uma implementação existente do Teams em VDI com chat e colaboração no qual você definiu políticas no nível do usuário para desativar a funcionalidade de chamada e reunião e está migrando para o Teams com otimização de AV, você deve definir políticas para ativar a funcionalidade de chamada e reunião para esses Teams em usuários VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-332">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="a3b94-333">Definir políticas para ativar a funcionalidade de chamada e reunião</span><span class="sxs-lookup"><span data-stu-id="a3b94-333">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="a3b94-334">Você pode usar o Microsoft Teams de administração ou o PowerShell para definir e atribuir políticas de chamada e reunião aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-334">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="a3b94-335">Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem.</span><span class="sxs-lookup"><span data-stu-id="a3b94-335">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="a3b94-336">Se você não vir alterações para uma determinada conta imediatamente, tente novamente após algumas horas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-336">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="a3b94-337">[**Políticas de chamada:**](teams-calling-policy.md)chamar políticas em Teams controle quais recursos de chamada estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-337">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="a3b94-338">Teams inclui a política interna de chamada AllowCalling, na qual todos os recursos de chamada estão ativas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-338">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="a3b94-339">Para ativar todos os recursos de chamada, atribua a política AllowCalling.</span><span class="sxs-lookup"><span data-stu-id="a3b94-339">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="a3b94-340">Ou crie uma política de chamada personalizada para ativar os recursos de chamada que você deseja e atribuí-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-340">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span>

<span data-ttu-id="a3b94-341">[**Políticas de**](meeting-policies-in-teams.md)reunião : as políticas de reunião em Teams controlam os tipos de reuniões que os usuários podem criar e os recursos que estão disponíveis para os participantes da reunião agendados pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3b94-341">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="a3b94-342">Teams inclui a política de reunião AllOn interna, na qual todos os recursos de reunião estão ativas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-342">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="a3b94-343">Para ativar todos os recursos de reunião, atribua a política AllOn.</span><span class="sxs-lookup"><span data-stu-id="a3b94-343">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="a3b94-344">Ou crie uma política de reunião personalizada para ativar os recursos de reunião que você deseja e atribuí-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-344">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a3b94-345">Atribuir políticas usando o Microsoft Teams de administração</span><span class="sxs-lookup"><span data-stu-id="a3b94-345">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a3b94-346">Para atribuir a política de chamada AllowCalling e a política de reunião AllOn a um usuário:</span><span class="sxs-lookup"><span data-stu-id="a3b94-346">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="a3b94-347">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-347">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="a3b94-348">Selecione o usuário clicando à esquerda do nome de exibição do usuário e clique em **Editar configurações**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-348">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a3b94-349">Siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="a3b94-349">Do the following:</span></span>
    1. <span data-ttu-id="a3b94-350">Em **Política de Chamada,** clique **em AllowCalling**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-350">Under **Calling policy**, click **AllowCalling**.</span></span>
    2. <span data-ttu-id="a3b94-351">Em **Política de Reunião,** clique **em AllOn**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-351">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="a3b94-352">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-352">Click **Apply**.</span></span>

<span data-ttu-id="a3b94-353">Para atribuir uma política a vários usuários por vez:</span><span class="sxs-lookup"><span data-stu-id="a3b94-353">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="a3b94-354">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="a3b94-354">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="a3b94-355">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="a3b94-355">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a3b94-356">Para selecionar todos os usuários, clique na **&#x2713;** (marca de seleção) na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="a3b94-356">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="a3b94-357">Clique em **Editar configurações**, faça as alterações desejadas e, em seguida, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-357">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="a3b94-358">Ou você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a3b94-358">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a3b94-359">Na navegação à esquerda do centro de administração Microsoft Teams, vá para a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="a3b94-359">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="a3b94-360">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a3b94-360">For example:</span></span>
    - <span data-ttu-id="a3b94-361">Vá para **Políticas de Chamada**  >  **de** Voz e clique **em AllowCalling**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-361">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="a3b94-362">Vá para **Políticas de Reunião** de  >  **Reuniões** e clique em **AllOn**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-362">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="a3b94-363">Selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-363">Select **Manage users**.</span></span>
3. <span data-ttu-id="a3b94-364">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-364">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a3b94-365">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="a3b94-365">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a3b94-366">Quando terminar de adicionar usuários, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-366">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="a3b94-367">Atribuir políticas usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3b94-367">Assign policies using PowerShell</span></span>

<span data-ttu-id="a3b94-368">O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada AllowCalling a um usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-368">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="a3b94-369">Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamadas, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="a3b94-369">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="a3b94-370">O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOn a um usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-370">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="a3b94-371">Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="a3b94-371">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="a3b94-372">Controlar o modo de fallback Teams</span><span class="sxs-lookup"><span data-stu-id="a3b94-372">Control fallback mode in Teams</span></span>

<span data-ttu-id="a3b94-373">Quando os usuários se conectam de um ponto de extremidade sem suporte, os usuários estão no modo de fallback, no qual a AV não é otimizada.</span><span class="sxs-lookup"><span data-stu-id="a3b94-373">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="a3b94-374">Você pode desabilitar ou habilitar o modo de fallback definindo um dos seguintes valores DWORD do Registro:</span><span class="sxs-lookup"><span data-stu-id="a3b94-374">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="a3b94-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="a3b94-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="a3b94-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="a3b94-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="a3b94-377">Para desabilitar o modo de fallback, de definir o valor **como 1**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-377">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="a3b94-378">Para habilitar somente áudio, de definir o valor como **2**.</span><span class="sxs-lookup"><span data-stu-id="a3b94-378">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="a3b94-379">Se o valor não estiver presente ou estiver definido como **0** (zero), o modo de fallback será habilitado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-379">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="a3b94-380">Esse recurso está disponível Teams versão 1.3.00.13565 e posterior.</span><span class="sxs-lookup"><span data-stu-id="a3b94-380">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="disable-audio-and-video-settings-for-vdi"></a><span data-ttu-id="a3b94-381">Desabilitar configurações de áudio e vídeo para VDI</span><span class="sxs-lookup"><span data-stu-id="a3b94-381">Disable audio and video settings for VDI</span></span>

<span data-ttu-id="a3b94-382">Teams As políticas VDI estão disponíveis no módulo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-382">Teams VDI policies are available in the Microsoft Teams module.</span></span> <span data-ttu-id="a3b94-383">Essas políticas são ativas e impostas em ambientes VDI não otimizados.</span><span class="sxs-lookup"><span data-stu-id="a3b94-383">These policies are active and enforced on non-optimized VDI environments.</span></span>

- <span data-ttu-id="a3b94-384">New-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="a3b94-384">New-CsTeamsVdiPolicy</span></span>  
- <span data-ttu-id="a3b94-385">Grant-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="a3b94-385">Grant-CsTeamsVdiPolicy</span></span>
- <span data-ttu-id="a3b94-386">Remove-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="a3b94-386">Remove-CsTeamsVdiPolicy</span></span>
- <span data-ttu-id="a3b94-387">Set-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="a3b94-387">Set-CsTeamsVdiPolicy</span></span>

> [!NOTE]
> <span data-ttu-id="a3b94-388">Isso é apenas para ambientes não otimizados.</span><span class="sxs-lookup"><span data-stu-id="a3b94-388">This is only for non-optimized environments.</span></span>

### <a name="update-a-module-name"></a><span data-ttu-id="a3b94-389">Atualizar um nome de módulo</span><span class="sxs-lookup"><span data-stu-id="a3b94-389">Update a module name</span></span>

<span data-ttu-id="a3b94-390">update-Module -Name MicrosoftTeams -AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="a3b94-390">update-Module -Name MicrosoftTeams -AllowPrerelease</span></span>

```PowerShell
<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a><span data-ttu-id="a3b94-391">Definir políticas para limitar recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="a3b94-391">Set policies to limit calling features</span></span>

<span data-ttu-id="a3b94-392">Quando os usuários com essa configuração de Política VDI -DisableCallsAndMeetings $true entrar no Teams no VDI, eles não poderão:</span><span class="sxs-lookup"><span data-stu-id="a3b94-392">When users with this VDI Policy setting -DisableCallsAndMeetings $true to sign in to Teams on VDI, they shouldn't be able to:</span></span>

- <span data-ttu-id="a3b94-393">Fazer chamadas.</span><span class="sxs-lookup"><span data-stu-id="a3b94-393">Make calls.</span></span>
- <span data-ttu-id="a3b94-394">Participe de reuniões.</span><span class="sxs-lookup"><span data-stu-id="a3b94-394">Join meetings.</span></span>
- <span data-ttu-id="a3b94-395">Faça um compartilhamento de tela do chat.</span><span class="sxs-lookup"><span data-stu-id="a3b94-395">Do a screen share from chat.</span></span>

<span data-ttu-id="a3b94-396">Todos os tipos de chamada devem ser desabilitados.</span><span class="sxs-lookup"><span data-stu-id="a3b94-396">All types of calling should be disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="a3b94-397">Isso é apenas para ambientes não otimizados.</span><span class="sxs-lookup"><span data-stu-id="a3b94-397">This is only for non-optimized environments.</span></span>

```PowerShell
#>
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false
<# Assign Policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<#
Show all Policies  
#>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
<#
```

<span data-ttu-id="a3b94-398">Quando os usuários com a configuração de Política VDI -DisableAudioVideoInCallsAndMeetings $true entrar no Teams VDI, eles poderão:</span><span class="sxs-lookup"><span data-stu-id="a3b94-398">When users with the VDI Policy setting -DisableAudioVideoInCallsAndMeetings $true sign in to Teams on VDI, they should be able to:</span></span>

- <span data-ttu-id="a3b94-399">Faça um compartilhamento de tela do chat.</span><span class="sxs-lookup"><span data-stu-id="a3b94-399">Do a screen share from chat.</span></span>
- <span data-ttu-id="a3b94-400">Participe de uma reunião e compartilhe uma tela.</span><span class="sxs-lookup"><span data-stu-id="a3b94-400">Join a meeting and share a screen.</span></span> <span data-ttu-id="a3b94-401">Mova o áudio para um telefone.</span><span class="sxs-lookup"><span data-stu-id="a3b94-401">Move their audio to a phone.</span></span>
- <span data-ttu-id="a3b94-402">Os usuários não devem ser capazes de fazer uma chamada de áudio e vídeo de pessoa para pessoa a partir da VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-402">Users shouldn't be able to do a person-to-person audio and video call from VDI.</span></span>

> [!NOTE]
> <span data-ttu-id="a3b94-403">Isso é apenas para ambientes não otimizados.</span><span class="sxs-lookup"><span data-stu-id="a3b94-403">This is only for non-optimized environments.</span></span>

```powershell
#>
$PolName = "DisableCallsAndMeetingsAV"
New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<# ## Cleanup afterwards #>
$cleanup = $false
if($cleanup){
    "Doing cleanup"
    # de-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
    # remove Policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a><span data-ttu-id="a3b94-404">Problemas conhecidos e limitações</span><span class="sxs-lookup"><span data-stu-id="a3b94-404">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="a3b94-405">Implantação, instalação e instalação do cliente</span><span class="sxs-lookup"><span data-stu-id="a3b94-405">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="a3b94-406">Com a instalação por máquina, Teams na VDI não é atualizada automaticamente da maneira que os clientes que não Teams VDI são.</span><span class="sxs-lookup"><span data-stu-id="a3b94-406">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="a3b94-407">Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção Instalar ou atualizar o Teams da área de trabalho [na VDI.](#install-or-update-the-teams-desktop-app-on-vdi)</span><span class="sxs-lookup"><span data-stu-id="a3b94-407">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="a3b94-408">Você deve desinstalar a versão atual para atualizar para uma versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="a3b94-408">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="a3b94-409">Em ambientes Citrix, se o usuário se desconectar da Máquina Virtual enquanto o Teams está em execução, as atualizações Teams podem fazer com que o usuário esteja em um estado não otimizado para AV quando se reconectar.</span><span class="sxs-lookup"><span data-stu-id="a3b94-409">In Citrix environments, if the user disconnects from the Virtual Machine while Teams is running, Teams updates can result in the user to be in a non-optimized state for AV when they reconnect.</span></span> <span data-ttu-id="a3b94-410">Recomendamos que os usuários Teams antes de se desconectar da Máquina Virtual citrix para evitar esse cenário.</span><span class="sxs-lookup"><span data-stu-id="a3b94-410">We recommend that users quit Teams before they disconnect from Citrix Virtual Machine to avoid this scenario.</span></span>
- <span data-ttu-id="a3b94-411">Teams deve ser implantado por usuário ou por máquina.</span><span class="sxs-lookup"><span data-stu-id="a3b94-411">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="a3b94-412">Não há suporte Teams implantação de Teams para usuários simultâneos e por máquina.</span><span class="sxs-lookup"><span data-stu-id="a3b94-412">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="a3b94-413">Para migrar de cada máquina ou por usuário para um desses modos, siga o procedimento de desinstalação e reimplante para ambos os modos.</span><span class="sxs-lookup"><span data-stu-id="a3b94-413">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="a3b94-414">Windows A Área de Trabalho Virtual não dá suporte a clientes baseados em macOS e Linux no momento.</span><span class="sxs-lookup"><span data-stu-id="a3b94-414">Windows Virtual Desktop doesn't support macOS and Linux-based clients at this time.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="a3b94-415">Chamada e reuniões</span><span class="sxs-lookup"><span data-stu-id="a3b94-415">Calling and meetings</span></span>

<span data-ttu-id="a3b94-416">Os seguintes recursos de chamada e reunião não são suportados:</span><span class="sxs-lookup"><span data-stu-id="a3b94-416">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="a3b94-417">Qualquer funcionalidade de várias janelas, como as novas experiências de reunião ou qualquer funcionalidade que venha com a nova experiência de reunião</span><span class="sxs-lookup"><span data-stu-id="a3b94-417">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="a3b94-418">Serviços de emergência aprimorados</span><span class="sxs-lookup"><span data-stu-id="a3b94-418">Enhanced emergency services</span></span>
- <span data-ttu-id="a3b94-419">Botões HID e controles DE LED entre o aplicativo Teams e dispositivos</span><span class="sxs-lookup"><span data-stu-id="a3b94-419">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="a3b94-420">Desfoque e efeitos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="a3b94-420">Background blur and effects</span></span>
- <span data-ttu-id="a3b94-421">Funções de apresentador e produtor de eventos ao vivo e transmissão</span><span class="sxs-lookup"><span data-stu-id="a3b94-421">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="a3b94-422">Location-Based Roteamento (LBR)</span><span class="sxs-lookup"><span data-stu-id="a3b94-422">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="a3b94-423">Tom de retorno de toque de chamada PSTN</span><span class="sxs-lookup"><span data-stu-id="a3b94-423">PSTN call ringback tone</span></span>
- <span data-ttu-id="a3b94-424">Som de áudio/computador do sistema compartilhado</span><span class="sxs-lookup"><span data-stu-id="a3b94-424">Shared system audio/computer sound</span></span>
- <span data-ttu-id="a3b94-425">Bypass de mídia para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="a3b94-425">Media bypass for Direct Routing</span></span>
- <span data-ttu-id="a3b94-426">Estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="a3b94-426">Call park</span></span>
- <span data-ttu-id="a3b94-427">Controle zoom</span><span class="sxs-lookup"><span data-stu-id="a3b94-427">Zoom control</span></span>

> [!NOTE]
> <span data-ttu-id="a3b94-428">Estamos trabalhando na adição de recursos de chamada e reunião que estão disponíveis apenas em ambientes que não sejam VDI.</span><span class="sxs-lookup"><span data-stu-id="a3b94-428">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="a3b94-429">Isso pode incluir mais controle de administrador sobre qualidade, cenários adicionais de compartilhamento de tela e recursos avançados adicionados recentemente Teams.</span><span class="sxs-lookup"><span data-stu-id="a3b94-429">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="a3b94-430">Entre em contato Teams representante do Teams para saber mais sobre os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="a3b94-430">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="a3b94-431">A seguir estão os problemas conhecidos e limitações de chamada e reuniões:</span><span class="sxs-lookup"><span data-stu-id="a3b94-431">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="a3b94-432">A interoperabilidade com Skype for Business está limitada a chamadas de áudio; não há nenhuma modalidade de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a3b94-432">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="a3b94-433">A resolução de fluxo de vídeo de entrada e saída é limitada à resolução de 720p.</span><span class="sxs-lookup"><span data-stu-id="a3b94-433">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span>
- <span data-ttu-id="a3b94-434">Há suporte para apenas um fluxo de vídeo de uma câmera de entrada ou de um fluxo de compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="a3b94-434">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="a3b94-435">Quando há um compartilhamento de tela de entrada, esse compartilhamento de tela é mostrado, em vez do vídeo do alto-falante dominante.</span><span class="sxs-lookup"><span data-stu-id="a3b94-435">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="a3b94-436">Teams alternar para usar o último dispositivo de áudio que um usuário selecionou, se o dispositivo estiver desconectado e, em seguida, reconectado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-436">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="a3b94-437">Compartilhamento de tela de saída:</span><span class="sxs-lookup"><span data-stu-id="a3b94-437">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="a3b94-438">Não há suporte para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a3b94-438">Application sharing is not supported.</span></span>
- <span data-ttu-id="a3b94-439">Dê controle e controle:</span><span class="sxs-lookup"><span data-stu-id="a3b94-439">Give control and take control:</span></span>
    - <span data-ttu-id="a3b94-440">Não há suporte durante uma sessão de compartilhamento de tela ou de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a3b94-440">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="a3b94-441">Suportado durante uma sessão de PowerPoint de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="a3b94-441">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="a3b94-442">Limitações somente para Citrix</span><span class="sxs-lookup"><span data-stu-id="a3b94-442">Citrix-only limitations</span></span>
    - <span data-ttu-id="a3b94-443">Quando o compartilhamento de tela em uma instalação com vários monitores, apenas o monitor principal é compartilhado.</span><span class="sxs-lookup"><span data-stu-id="a3b94-443">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="a3b94-444">Não há suporte para dimensionamento de DPI alto no CWA.</span><span class="sxs-lookup"><span data-stu-id="a3b94-444">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="a3b94-445">Para Teams problemas conhecidos que não estão relacionados à VDI, consulte [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span><span class="sxs-lookup"><span data-stu-id="a3b94-445">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a3b94-446">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="a3b94-446">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="a3b94-447">Solucionar problemas de componentes do Citrix</span><span class="sxs-lookup"><span data-stu-id="a3b94-447">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="a3b94-448">Teams falha ou a tela de Teams de entrar está em branco</span><span class="sxs-lookup"><span data-stu-id="a3b94-448">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="a3b94-449">Esse é um problema conhecido com o Citrix VDA versões 1906 e 1909.</span><span class="sxs-lookup"><span data-stu-id="a3b94-449">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="a3b94-450">Para resolver esse problema, adicione o seguinte valor DWORD do Registro e desmarca-o como 204 (hexadecimal).</span><span class="sxs-lookup"><span data-stu-id="a3b94-450">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="a3b94-451">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="a3b94-451">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="a3b94-452">Em seguida, reinicie o VDA.</span><span class="sxs-lookup"><span data-stu-id="a3b94-452">Then, restart VDA.</span></span> <span data-ttu-id="a3b94-453">Para saber mais, confira este artigo de suporte do Citrix, [Solucionando problemas de otimização HDX para Teams](https://support.citrix.com/article/CTX253754).</span><span class="sxs-lookup"><span data-stu-id="a3b94-453">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3b94-454">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a3b94-454">Related topics</span></span>

- [<span data-ttu-id="a3b94-455">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="a3b94-455">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="a3b94-456">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="a3b94-456">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a3b94-457">Usar Microsoft Teams em Windows área de trabalho virtual</span><span class="sxs-lookup"><span data-stu-id="a3b94-457">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)
