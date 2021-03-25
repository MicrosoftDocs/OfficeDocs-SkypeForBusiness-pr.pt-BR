---
title: Implantar salas do Microsoft Teams usando o Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Saiba mais sobre como implantar salas do Microsoft Teams em implantações em grande escala usando o Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: e755a369d3f8aa11d5346c2e5cda9cc84285dc7b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117399"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="691ff-103">Implantar salas do Microsoft Teams usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="691ff-104">Este artigo fornece todas as informações necessárias para criar suas implantações de Salas do Microsoft Teams usando o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="691ff-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="691ff-105">Com os métodos fáceis de usar fornecidos pelo Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="691ff-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="691ff-106">Use a abordagem ilustrada abaixo para orientá-lo através de sua configuração do Configuration Manager e personalizar os pacotes de exemplo e scripts fornecidos ao longo desta orientação, conforme necessário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="691ff-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processo de implantação de Salas do Microsoft Teams usando o Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="691ff-108">Essa solução só foi testada com implantações baseadas no Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="691ff-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="691ff-109">Siga as diretrizes do fabricante para configurações que não se baseiam no Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="691ff-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="691ff-110">Validar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="691ff-110">Validate prerequisites</span></span>

<span data-ttu-id="691ff-111">Para implantar salas do Microsoft Teams com o Configuration Manager, certifique-se de atender aos seguintes pré-requisitos e requisitos.</span><span class="sxs-lookup"><span data-stu-id="691ff-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="691ff-112">Requisitos do Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="691ff-113">A versão do Microsoft Endpoint Configuration Manager deve ter pelo menos 1706 ou mais.</span><span class="sxs-lookup"><span data-stu-id="691ff-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="691ff-114">Recomendamos usar o 1710 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="691ff-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="691ff-115">Confira Suporte [para Windows 10 no Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões do Windows 10 suportadas pelo Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="691ff-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="691ff-116">Uma versão com suporte do ADK (Kit de Avaliação e Implantação do Windows) para Windows 10 deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="691ff-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="691ff-117">Consulte as versões do [ADK do Windows 10](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com versões diferentes do Configuration Manager e certifique-se de que sua implantação inclua a versão correta.</span><span class="sxs-lookup"><span data-stu-id="691ff-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="691ff-118">Os servidores do sistema de site devem ter sido atribuídos à função de ponto de distribuição, e as imagens de inicialização devem estar habilitadas para suporte ao [PXE (ambiente](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) de execução de pré-inicialização) para habilitar implantações iniciadas na rede.</span><span class="sxs-lookup"><span data-stu-id="691ff-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="691ff-119">Se o suporte a PXE não estiver habilitado, você poderá usar mídia [inicializável](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.</span><span class="sxs-lookup"><span data-stu-id="691ff-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="691ff-120">Uma conta de acesso à rede deve ser configurada para dar suporte a novos cenários de implantação do computador (bare metal).</span><span class="sxs-lookup"><span data-stu-id="691ff-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="691ff-121">Para saber mais sobre a configuração de uma conta de acesso à rede, consulte [Contas usadas no Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="691ff-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="691ff-122">Recomendamos que você habilita o suporte a [multicast](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se for provável que você implante a mesma imagem do Microsoft Teams Rooms em várias unidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="691ff-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="691ff-123">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="691ff-123">Networking requirements</span></span>

-   <span data-ttu-id="691ff-124">Sua rede deve ter um servidor DHCP (Dynamic Host Configuration Protocol), configurado para distribuição automática de endereço IP para as sub-redes onde as unidades do Microsoft Teams Rooms serão implantadas.</span><span class="sxs-lookup"><span data-stu-id="691ff-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="691ff-125">A duração do contrato de locação de DHCP deve ser definida como um valor maior do que a duração da implantação da imagem.</span><span class="sxs-lookup"><span data-stu-id="691ff-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="691ff-126">Caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="691ff-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="691ff-127">Sua rede, incluindo comutadores e VLANs virtuais, deve ser configurada para dar suporte a PXE.</span><span class="sxs-lookup"><span data-stu-id="691ff-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="691ff-128">Consulte seu fornecedor de rede para obter mais informações sobre a configuração do Ip Helper e PXE.</span><span class="sxs-lookup"><span data-stu-id="691ff-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="691ff-129">Como alternativa, você pode usar mídia [inicializável](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte PXE não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="691ff-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="691ff-130">Para dispositivos Surface Pro, a inicialização da rede (inicialização PXE) só é suportada quando você usa um adaptador Ethernet ou uma estação de encaixe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="691ff-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="691ff-131">Adaptadores Ethernet de terceiros não suportam inicialização PXE com o Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="691ff-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="691ff-132">Consulte [Adaptadores Ethernet e implantação do Surface](/surface/ethernet-adapters-and-surface-device-deployment) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="691ff-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="691ff-133">Configurar o Microsoft Endpoint Configuration Manager para implantação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="691ff-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="691ff-134">Este artigo supõe que você já tenha uma implantação saudável do Configuration Manager e não detalha todas as etapas necessárias para implantar e configurar o Configuration Manager do zero.</span><span class="sxs-lookup"><span data-stu-id="691ff-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="691ff-135">A [documentação e as diretrizes de](/configmgr/) configuração no Microsoft Endpoint Configuration Manager é um ótimo recurso; recomendamos que você comece com esses recursos se ainda não tiver implantado o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="691ff-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="691ff-136">Use as instruções a seguir para verificar se os recursos de implantação do sistema operacional (OSD) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="691ff-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="691ff-137">Validar e atualizar o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="691ff-138">No console do Configuration Manager, vá para **Atualizações** \> **de Administração e Manutenção.**</span><span class="sxs-lookup"><span data-stu-id="691ff-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="691ff-139">Verifique a com build instalada e as atualizações aplicáveis que ainda não foram instaladas.</span><span class="sxs-lookup"><span data-stu-id="691ff-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="691ff-140">Revisar [o suporte para o Windows 10 no Configuration Manager;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) se você precisar atualizar sua implantação, selecione a atualização que deseja instalar e selecione **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="691ff-141">Depois que o download for concluído, selecione a atualização e selecione **Instalar o Pacote de Atualizações.**</span><span class="sxs-lookup"><span data-stu-id="691ff-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="691ff-142">Configurar pontos de distribuição para dar suporte a PXE e multicast</span><span class="sxs-lookup"><span data-stu-id="691ff-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="691ff-143">No console do Configuration Manager, vá para **Pontos de Distribuição de** \> **Administração**.</span><span class="sxs-lookup"><span data-stu-id="691ff-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="691ff-144">Selecione o servidor de ponto de distribuição que atenderá à implantação de Salas do Microsoft Teams e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="691ff-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="691ff-145">Selecione a **guia PXE** e verifique se as seguintes configurações estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="691ff-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="691ff-146">Habilitar o suporte PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="691ff-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="691ff-147">Permitir que esse ponto de distribuição responda a solicitações PXE de entrada</span><span class="sxs-lookup"><span data-stu-id="691ff-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="691ff-148">Habilitar suporte a computadores desconhecidos</span><span class="sxs-lookup"><span data-stu-id="691ff-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="691ff-149">*Opcional:* Para habilitar o suporte a várioscasts, selecione a guia **Multicast** e verifique se as seguintes configurações estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="691ff-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="691ff-150">Habilitar o multicast para enviar dados simultaneamente a vários clientes</span><span class="sxs-lookup"><span data-stu-id="691ff-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="691ff-151">Configurar o intervalo de portas UDP de acordo com a recomendação da sua equipe de rede</span><span class="sxs-lookup"><span data-stu-id="691ff-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="691ff-152">Configurar a Conta de Acesso à Rede</span><span class="sxs-lookup"><span data-stu-id="691ff-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="691ff-153">No console do Configuration Manager, vá para **Sites** de Configuração do Site de \>  \> Administração e selecione o site.</span><span class="sxs-lookup"><span data-stu-id="691ff-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="691ff-154">No grupo **Configurações,** selecione Configurar Distribuição de Software **de** \> **Componentes de Site**.</span><span class="sxs-lookup"><span data-stu-id="691ff-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="691ff-155">Selecione a **guia Conta de Acesso à** Rede. Configurar uma ou mais contas e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="691ff-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="691ff-156">As contas não precisam de direitos especiais, exceto o **Access this computer** da rede no servidor de ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="691ff-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="691ff-157">Uma conta de usuário de domínio genérico será apropriada.</span><span class="sxs-lookup"><span data-stu-id="691ff-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="691ff-158">Para obter mais informações, consulte [Contas usadas no Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="691ff-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="691ff-159">Configurar uma imagem de inicialização</span><span class="sxs-lookup"><span data-stu-id="691ff-159">Configure a boot image</span></span>

1.  <span data-ttu-id="691ff-160">No console do Configuration Manager, acesse Imagens de **inicialização** do sistema \> **operacional da Biblioteca de** \> Software.</span><span class="sxs-lookup"><span data-stu-id="691ff-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="691ff-161">Selecione **Imagem de inicialização (x64)** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="691ff-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="691ff-162">Selecione a **guia Fonte de** Dados e habilita a Implantação dessa imagem de inicialização do ponto de distribuição habilitado para **PXE.**</span><span class="sxs-lookup"><span data-stu-id="691ff-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="691ff-163">Selecione a **guia Componentes Opcionais** para instalar os componentes necessários:</span><span class="sxs-lookup"><span data-stu-id="691ff-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="691ff-164">Selecione o ícone de estrela e procure **HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="691ff-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="691ff-165">Selecione **OK** para adicionar suporte a aplicativo HTML à imagem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="691ff-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="691ff-166">*Opcional:* Para personalizar a experiência de implantação, selecione a **guia Personalização.**</span><span class="sxs-lookup"><span data-stu-id="691ff-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="691ff-167">Habilita o suporte a comandos **(somente teste)** se você quiser ter acesso a um prompt de comando durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="691ff-168">Quando isso estiver habilitado, você poderá iniciar um prompt de comando selecionando **F8** a qualquer momento durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="691ff-169">Você também pode especificar uma imagem de plano de fundo personalizada a ser exibida durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="691ff-170">Para definir uma imagem, **habilita Especifique o arquivo de imagem de plano** de fundo personalizado (caminho UNC e selecione seu plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="691ff-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="691ff-171">Quando solicitado, selecione **Sim e** distribua a imagem de inicialização atualizada para seus pontos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="691ff-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="691ff-172">Para obter mais informações, consulte [Gerenciar imagens de inicialização com o Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="691ff-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="691ff-173">Você pode criar uma mídia USB inicializável para iniciar implantações baseadas em sequência de tarefas do Configuration Manager para ambientes que não têm suporte para PXE.</span><span class="sxs-lookup"><span data-stu-id="691ff-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="691ff-174">A mídia inicializável contém apenas a imagem de inicialização, comandos de prestart opcionais e seus arquivos necessários e binários do Configuration Manager para dar suporte à inicialização no Windows PE e à conexão com o Configuration Manager para o restante do processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="691ff-175">Para obter mais informações, consulte [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="691ff-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="691ff-176">Criar pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="691ff-177">A versão necessária do sistema operacional para cada versão do instalador SRS é modificada a cada versão MSI.</span><span class="sxs-lookup"><span data-stu-id="691ff-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="691ff-178">Para determinar a melhor versão do sistema operacional para um determinado MSI, execute o script de configuração do console uma vez.</span><span class="sxs-lookup"><span data-stu-id="691ff-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="691ff-179">Para saber mais, consulte [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span><span class="sxs-lookup"><span data-stu-id="691ff-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="691ff-180">O Configuration Manager requer vários pacotes para implantar e configurar as unidades do Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="691ff-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="691ff-181">Você precisa criar e configurar os seguintes pacotes e distribuí-los para os sistemas de site do Configuration Manager que foram atribuídos à função de servidor de ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="691ff-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="691ff-182">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="691ff-182">**Package name**</span></span>                     | <span data-ttu-id="691ff-183">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="691ff-183">**Type**</span></span>               | <span data-ttu-id="691ff-184">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="691ff-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="691ff-185">SRS v2 - Pacote de Aplicativos SRS</span><span class="sxs-lookup"><span data-stu-id="691ff-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="691ff-186">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-186">Software package</span></span>       | <span data-ttu-id="691ff-187">Pacote para o kit de implantação de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="691ff-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="691ff-188">SRS v2 - Pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="691ff-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="691ff-189">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-189">Software package</span></span>       | <span data-ttu-id="691ff-190">Pacote para a Unattended.xml para configurar unidades do Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="691ff-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="691ff-191">SRS v2 - Set-SRSComputerName Pacote</span><span class="sxs-lookup"><span data-stu-id="691ff-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="691ff-192">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-192">Software package</span></span>       | <span data-ttu-id="691ff-193">Pacote para o aplicativo HTML (HTA) para atribuir um nome de computador durante a implantação</span><span class="sxs-lookup"><span data-stu-id="691ff-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="691ff-194">SRS v2 - Configurar a Instalação do SRS</span><span class="sxs-lookup"><span data-stu-id="691ff-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="691ff-195">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-195">Software package</span></span>       | <span data-ttu-id="691ff-196">Pacote para configurar a implantação do aplicativo Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="691ff-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="691ff-197">SRS v2 - Pacote de Atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="691ff-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="691ff-198">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-198">Software package</span></span>       | <span data-ttu-id="691ff-199">Pacote para implantar atualizações obrigatórias do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="691ff-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="691ff-200">SRS v2 - Pacote de Certificado Raiz</span><span class="sxs-lookup"><span data-stu-id="691ff-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="691ff-201">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-201">Software package</span></span>       | <span data-ttu-id="691ff-202">Opcional - Pacote para implantar o certificado raiz (não necessário para unidades ingressadas no domínio)</span><span class="sxs-lookup"><span data-stu-id="691ff-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="691ff-203">SRS v2 - Pacote do Agente de Monitoramento da Microsoft</span><span class="sxs-lookup"><span data-stu-id="691ff-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="691ff-204">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-204">Software package</span></span>       | <span data-ttu-id="691ff-205">Opcional - Pacote para implantar e configurar o agente do Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="691ff-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="691ff-206">SRS v2 - Pacote de Plano de Fundo do WinPE</span><span class="sxs-lookup"><span data-stu-id="691ff-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="691ff-207">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="691ff-207">Software package</span></span>       | <span data-ttu-id="691ff-208">Pacote para a imagem de plano de fundo personalizada a ser usada com imagens de inicialização</span><span class="sxs-lookup"><span data-stu-id="691ff-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="691ff-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="691ff-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="691ff-210">Imagem do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="691ff-210">Operating system image</span></span> | <span data-ttu-id="691ff-211">Pacote para o arquivo de instalação do sistema operacional (install.wim)</span><span class="sxs-lookup"><span data-stu-id="691ff-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="691ff-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="691ff-212">Surface Pro</span></span>                          | <span data-ttu-id="691ff-213">Pacote driver</span><span class="sxs-lookup"><span data-stu-id="691ff-213">Driver package</span></span>         | <span data-ttu-id="691ff-214">Pacote para drivers de dispositivo e firmware do Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="691ff-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="691ff-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="691ff-215">Surface Pro 4</span></span>                        | <span data-ttu-id="691ff-216">Pacote driver</span><span class="sxs-lookup"><span data-stu-id="691ff-216">Driver package</span></span>         | <span data-ttu-id="691ff-217">Pacote para drivers de dispositivo e firmware do Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="691ff-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="691ff-218">Para obter mais informações, consulte [Pacotes e programas no Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="691ff-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="691ff-219">Criar pastas para os arquivos de origem do pacote</span><span class="sxs-lookup"><span data-stu-id="691ff-219">Create folders for the package source files</span></span>

<span data-ttu-id="691ff-220">O Configuration Manager exige que os arquivos de origem do pacote sejam organizados em uma estrutura de pasta específica quando eles são criados pela primeira vez e quando são atualizados.</span><span class="sxs-lookup"><span data-stu-id="691ff-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="691ff-221">Crie a seguinte estrutura de pastas no site da administração central do Microsoft Endpoint Configuration Manager ou no site principal ou em um compartilhamento de servidor que você está usando para hospedar arquivos de origem do pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="691ff-222">SRS v2 - Pacote do Agente de Monitoramento da Microsoft</span><span class="sxs-lookup"><span data-stu-id="691ff-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="691ff-223">SRS v2 - Pacote de Atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="691ff-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="691ff-224">SRS v2 - Pacote de Certificado Raiz</span><span class="sxs-lookup"><span data-stu-id="691ff-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="691ff-225">SRS v2 - Set-SRSComputerName Pacote</span><span class="sxs-lookup"><span data-stu-id="691ff-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="691ff-226">SRS v2 - Pacote de Aplicativos SRS</span><span class="sxs-lookup"><span data-stu-id="691ff-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="691ff-227">SRS v2 - Configurar a Instalação do SRS</span><span class="sxs-lookup"><span data-stu-id="691ff-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="691ff-228">SRS v2 - Pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="691ff-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="691ff-229">Drivers</span><span class="sxs-lookup"><span data-stu-id="691ff-229">Drivers</span></span>
    -   <span data-ttu-id="691ff-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="691ff-230">Surface Pro</span></span>
    -   <span data-ttu-id="691ff-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="691ff-231">Surface Pro 4</span></span>
-   <span data-ttu-id="691ff-232">Sistemas Operacionais</span><span class="sxs-lookup"><span data-stu-id="691ff-232">Operating Systems</span></span>
    -   <span data-ttu-id="691ff-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="691ff-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="691ff-234">Você também pode [baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pastas para os pacotes, os scripts que você precisa usar e o modelo de sequência de tarefas que você precisa importar.</span><span class="sxs-lookup"><span data-stu-id="691ff-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="691ff-235">Criar o pacote do agente de monitoramento</span><span class="sxs-lookup"><span data-stu-id="691ff-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="691ff-236">Baixe o agente de Monitoramento de <https://go.microsoft.com/fwlink/?LinkId=828603> .</span><span class="sxs-lookup"><span data-stu-id="691ff-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="691ff-237">Extraia o pacote na pasta Pacote do Agente de Monitoramento do **SRS v2** abrindo uma janela do Prompt de Comando e inserindoMMASetup-AMD64.exe **/C:**     no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="691ff-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="691ff-238">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="691ff-239">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="691ff-240">Nome<strong>: SRS v2 - Pacote do Agente de Monitoramento da Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="691ff-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="691ff-241">Fabricante<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="691ff-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="691ff-242">Versão<strong>: 8.1.11081.0</strong> (insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="691ff-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="691ff-243">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 - Pacote** do Agente de Monitoramento da Microsoft e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="691ff-244">Selecione **Não criar um programa e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="691ff-245">Revise a **página Confirmar as configurações** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="691ff-246">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="691ff-247">Criar o pacote de atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="691ff-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="691ff-248">Na pasta Pacote de Atualizações do SISTEMA OPERACIONAL do **SRS v2,** crie um novo script do PowerShell chamado **Install-SRSv2-OS-Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="691ff-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="691ff-249">Copie o script abaixo para o **scriptInstall-SRSv2-OS-Updates.ps1** script.</span><span class="sxs-lookup"><span data-stu-id="691ff-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="691ff-250">Como alternativa, você pode baixar o script Install-SRSv2-OS-Updates.ps1 a [partir daqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="691ff-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="691ff-251">Baixe os pacotes obrigatórios do Windows Update na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="691ff-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="691ff-252">No momento em que este artigo foi publicado, apenas [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necessário.</span><span class="sxs-lookup"><span data-stu-id="691ff-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="691ff-253">Verifique [Configurar um console de Salas do Microsoft Teams](console.md)para ver se outras atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="691ff-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="691ff-254">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="691ff-255">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="691ff-256">Nome: **SRS v2 – Pacote de atualizações do sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="691ff-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="691ff-257">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="691ff-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="691ff-258">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="691ff-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="691ff-259">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SrS v2 - Pacote** de Atualizações do sistema operacional e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="691ff-260">Selecione **Não criar um programa e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="691ff-261">Revise a **página Confirmar as configurações** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="691ff-262">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="691ff-263">Criar o pacote de certificado raiz (opcional)</span><span class="sxs-lookup"><span data-stu-id="691ff-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="691ff-264">Você cria esse pacote para distribuir o certificado raiz para dispositivos que não serão ingressados em um domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="691ff-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="691ff-265">Crie este pacote somente se as duas condições a seguir se aplicarem:</span><span class="sxs-lookup"><span data-stu-id="691ff-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="691ff-266">Sua implantação inclui o Lync local ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="691ff-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="691ff-267">As unidades das Salas do Microsoft Teams são configuradas para funcionar em um grupo de trabalho em vez de um membro do domínio.</span><span class="sxs-lookup"><span data-stu-id="691ff-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="691ff-268">Copie o certificado raiz para a pasta **SRS v2 – Pacote de Certificado** Raiz.</span><span class="sxs-lookup"><span data-stu-id="691ff-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="691ff-269">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="691ff-270">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="691ff-271">Nome: **SRS v2 – Pacote de Certificado Raiz**</span><span class="sxs-lookup"><span data-stu-id="691ff-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="691ff-272">Fabricante: *nome da sua organização*</span><span class="sxs-lookup"><span data-stu-id="691ff-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="691ff-273">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="691ff-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="691ff-274">Marque a caixa de seleção **Este pacote contém** arquivos de origem, insira o caminho para a pasta **SRS v2 – Pacote** de Certificado Raiz e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="691ff-275">Selecione **Não criar um programa e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="691ff-276">Revise a **página Confirmar as configurações** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="691ff-277">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="691ff-278">Criar o pacote de kit de implantação do Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="691ff-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="691ff-279">Baixe a versão mais recente do **kit de implantação** do Microsoft Teams Rooms <https://go.microsoft.com/fwlink/?linkid=851168> de , e instale-a em uma estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="691ff-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="691ff-280">Copie o conteúdo de C: Arquivos de **\\ Programas (x86) \\ Skype Room System Deployment Kit** para a pasta **SRS v2 - Pacote de Aplicativos SRS.**</span><span class="sxs-lookup"><span data-stu-id="691ff-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="691ff-281">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="691ff-282">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="691ff-283">Nome: **SRS v2 – Pacote de Aplicativos SRS**</span><span class="sxs-lookup"><span data-stu-id="691ff-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="691ff-284">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="691ff-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="691ff-285">Versão: **3.1.104.0** (insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="691ff-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="691ff-286">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta Pacote de Aplicativos **SRS v2 – SRS** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="691ff-287">Selecione **Não criar um programa e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="691ff-288">Revise a **página Confirmar as configurações** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="691ff-289">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="691ff-290">Criar o pacote de atribuição de nome de computador</span><span class="sxs-lookup"><span data-stu-id="691ff-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="691ff-291">Na pasta **Pacote do SRS v2 - Set-SRSComputerName,** crie um novo aplicativo HTML chamado **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="691ff-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="691ff-292">Copie o seguinte script para o **arquivo Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="691ff-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="691ff-293">Como alternativa, você pode baixar o arquivo Set-SRSComputerName.hta [daqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="691ff-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="691ff-294">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="691ff-295">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="691ff-296">Nome: **SRS v2 - Set-SRSComputerName Pacote**</span><span class="sxs-lookup"><span data-stu-id="691ff-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="691ff-297">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="691ff-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="691ff-298">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="691ff-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="691ff-299">Marque a caixa de seleção Este pacote **contém** arquivos de origem, insira o caminho para a pasta **SRS v2 - Set-SRSComputerName Pacote** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="691ff-300">Selecione **Não criar um programa e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="691ff-301">Revise a **página Confirmar as configurações** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="691ff-302">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="691ff-303">Criar o pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="691ff-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="691ff-304">Na pasta **Pacote do SRS v2 – Sysprep,** crie um novo arquivo XML chamado **Unattend.xml** .</span><span class="sxs-lookup"><span data-stu-id="691ff-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="691ff-305">Copie o seguinte texto para o arquivo **Unattend.xml** arquivo.</span><span class="sxs-lookup"><span data-stu-id="691ff-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="691ff-306">Como alternativa, você pode baixar o arquivo Unattend.xml a [partir daqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="691ff-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="691ff-307">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="691ff-308">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="691ff-309">Nome: **SRS v2 - Pacote Sysprep**</span><span class="sxs-lookup"><span data-stu-id="691ff-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="691ff-310">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="691ff-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="691ff-311">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="691ff-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="691ff-312">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta Pacote **do SRS v2 – Sysprep** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="691ff-313">Selecione **Não criar um programa e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="691ff-314">Revise a **página Confirmar as configurações** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="691ff-315">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="691ff-316">Criar o pacote do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="691ff-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="691ff-317">Obtenha uma mídia x64 do Windows 10 Enterprise e copie o **arquivo install.wim** para a pasta Sistemas Operacionais **windows \\ 10 Enterprise.**</span><span class="sxs-lookup"><span data-stu-id="691ff-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="691ff-318">No console do Configuration Manager, acesse Imagens do Sistema Operacional de Sistemas Operacionais da Biblioteca de **Software** e selecione \>  \> Adicionar **Imagem do Sistema Operacional**.</span><span class="sxs-lookup"><span data-stu-id="691ff-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="691ff-319">Especifique o caminho para **o arquivo install.wim** que você acabou de copiar e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="691ff-320">Atualize **o campo Versão** para corresponder ao número de com build da imagem do Windows 10 Enterprise e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="691ff-321">Revise a **página Detalhes** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="691ff-322">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-322">Select **Close**.</span></span>

<span data-ttu-id="691ff-323">Para obter mais informações, consulte [Gerenciar imagens do sistema operacional com o Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="691ff-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="691ff-324">Criar pacotes de driver de dispositivo do Surface Pro</span><span class="sxs-lookup"><span data-stu-id="691ff-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="691ff-325">As Salas do Microsoft Teams têm suporte para o Surface Pro e o Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="691ff-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="691ff-326">Você precisa criar um pacote de driver para cada modelo do Surface Pro que você tem em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="691ff-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="691ff-327">Os drivers devem ser compatíveis com a com build do Windows 10 Enterprise e a versão do kit de implantação do Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="691ff-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="691ff-328">Para obter mais informações, [consulte Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and Configure a [console](console.md).</span><span class="sxs-lookup"><span data-stu-id="691ff-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="691ff-329">Baixe os drivers e firmware mais recentes.</span><span class="sxs-lookup"><span data-stu-id="691ff-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="691ff-330">Para o Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="691ff-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="691ff-331">Para o Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="691ff-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="691ff-332">Extraia o driver e o firmware baixados.</span><span class="sxs-lookup"><span data-stu-id="691ff-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="691ff-333">Abra uma janela prompt de comando e, no prompt de comando, insira um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="691ff-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="691ff-334">No console do Configuration Manager, vá para **Drivers** de Sistemas \> **Operacionais** da Biblioteca de Software e selecione \>  **Importar Driver**.</span><span class="sxs-lookup"><span data-stu-id="691ff-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="691ff-335">Selecione Importar todos os drivers no seguinte caminho de rede **(UNC),** selecione a pasta de origem (por exemplo, C: \\ _Sources Drivers Surface Pro) e selecione \\ \\ **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="691ff-336">Na página **Especificar os detalhes dos** drivers importados, selecione todos os drivers listados e selecione Habilitar esses drivers e permitir que os computadores os **instalem.**</span><span class="sxs-lookup"><span data-stu-id="691ff-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="691ff-337">Selecione **Categorias**, crie uma nova categoria que corresponde ao modelo Surface, selecione **OK** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="691ff-338">Selecione **Novo Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="691ff-339">Especifique o nome do pacote que corresponde ao modelo do Surface Pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver, selecione **OK** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="691ff-340">Na página **imagens de inicialização,** certifique-se de que nenhuma imagem de inicialização está selecionada e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="691ff-341">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-341">Select **Close**.</span></span>

11. <span data-ttu-id="691ff-342">Vá para **Drivers de Sistemas** Operacionais da Biblioteca de Software, selecione Pasta Criar Pasta e insira um nome de pasta que corresponde ao modelo do Surface Pro para o qual você acabou de \>  \> importar os drivers. **\>**</span><span class="sxs-lookup"><span data-stu-id="691ff-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="691ff-343">Mova todos os drivers importados para a pasta recém-criada para facilitar a navegação e a operação.</span><span class="sxs-lookup"><span data-stu-id="691ff-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="691ff-344">Repita as mesmas etapas para outros modelos do Surface Pro que você pode ter.</span><span class="sxs-lookup"><span data-stu-id="691ff-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="691ff-345">Para obter mais informações, consulte [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="691ff-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="691ff-346">Criar pacote de configuração de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="691ff-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="691ff-347">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e selecione \>  \>  **Criar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="691ff-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="691ff-348">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="691ff-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="691ff-349">Nome: **SRS v2 - Configurar o pacote de instalação do SRS**</span><span class="sxs-lookup"><span data-stu-id="691ff-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="691ff-350">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="691ff-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="691ff-351">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="691ff-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="691ff-352">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 - Configure SRS Setup** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="691ff-353">Selecione **Não criar um programa e** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="691ff-354">Revise a **página Confirmar as configurações** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="691ff-355">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="691ff-356">Distribuir pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="691ff-357">Todos os pacotes devem ser distribuídos para os servidores que foram atribuídos à função de ponto de distribuição na hierarquia do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="691ff-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="691ff-358">Siga as instruções a seguir para iniciar a distribuição do pacote.</span><span class="sxs-lookup"><span data-stu-id="691ff-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="691ff-359">Distribuir pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="691ff-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="691ff-360">No console do Configuration Manager, vá para Pacotes de Gerenciamento de **Aplicativos** da Biblioteca \> **de** \> **Software.**</span><span class="sxs-lookup"><span data-stu-id="691ff-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="691ff-361">Selecione todos os pacotes de software que você deseja distribuir e selecione **Distribuir Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="691ff-362">Revise a lista de pacotes e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="691ff-363">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da hierarquia do Configuration Manager) à lista e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="691ff-364">Selecione **Próximo** e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="691ff-365">Distribuir pacotes de driver.</span><span class="sxs-lookup"><span data-stu-id="691ff-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="691ff-366">No console do Configuration Manager, vá para Pacotes de Driver de **Sistemas** Operacionais da Biblioteca \> **de** \> Software.</span><span class="sxs-lookup"><span data-stu-id="691ff-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="691ff-367">Selecione todos os pacotes de driver que você deseja distribuir e selecione **Distribuir Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="691ff-368">Revise a lista de pacotes e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="691ff-369">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da hierarquia do Configuration Manager) à lista e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="691ff-370">Selecione **Próximo** e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="691ff-371">Distribuir pacotes do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="691ff-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="691ff-372">No console do Configuration Manager, acesse Imagens do Sistema Operacional de **Sistemas** \> **Operacionais da** Biblioteca de \> Software.</span><span class="sxs-lookup"><span data-stu-id="691ff-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="691ff-373">Selecione todas as imagens do sistema operacional que você deseja distribuir e selecione **Distribuir Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="691ff-374">Revise a lista de pacotes e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="691ff-375">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da hierarquia do Configuration Manager) à lista e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="691ff-376">Selecione **Próximo** e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="691ff-377">A distribuição do pacote pode levar algum tempo, dependendo do tamanho do pacote, da hierarquia do Configuration Manager, do número de servidores de ponto de distribuição e da largura de banda disponível em sua rede.</span><span class="sxs-lookup"><span data-stu-id="691ff-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="691ff-378">Todos os pacotes devem ser distribuídos antes de começar a implantar uma unidade do Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="691ff-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="691ff-379">Você pode revisar o status da distribuição do pacote no console do Configuration Manager, indo para **Monitorar o** Status do Conteúdo de Status de \>  \> **Distribuição.**</span><span class="sxs-lookup"><span data-stu-id="691ff-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="691ff-380">Sequências de tarefas do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="691ff-381">Você usa sequências de tarefas com o Configuration Manager para automatizar as etapas para implantar uma imagem do sistema operacional em um computador de destino.</span><span class="sxs-lookup"><span data-stu-id="691ff-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="691ff-382">Para implantar uma unidade do Microsoft Teams Rooms de forma automatizada, crie uma sequência de tarefas que faz referência à imagem de inicialização usada para iniciar o computador de salas do Microsoft Teams de destino, a imagem do sistema operacional Windows 10 Enterprise que você deseja instalar e qualquer outro conteúdo adicional, como outros aplicativos ou atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="691ff-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="691ff-383">Importar a sequência de tarefas de exemplo</span><span class="sxs-lookup"><span data-stu-id="691ff-383">Import the sample task sequence</span></span>

<span data-ttu-id="691ff-384">Você pode baixar e importar facilmente uma sequência de tarefas de exemplo e personalizá-la para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="691ff-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="691ff-385">[**Baixe**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) a sequência de tarefas de exemplo e copie o arquivo zip baixado para um local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="691ff-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="691ff-386">No console do Configuration Manager, vá para **Sequências** de Tarefas de Sistemas Operacionais da Biblioteca de Software e selecione \>  \> Importar Sequência **de Tarefas.**</span><span class="sxs-lookup"><span data-stu-id="691ff-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="691ff-387">Selecione **Procurar**, vá para o local da pasta compartilhada que você usou na etapa 1, selecione o arquivo **EN-US (Implantação** de Salas do Microsoft Teams).zip e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="691ff-388">De **definir Ação** para Criar **Novo** e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="691ff-389">Confirme as configurações e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="691ff-390">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="691ff-391">Valide se os pacotes de referência estão vinculados corretamente a cada etapa de sequência de tarefas.</span><span class="sxs-lookup"><span data-stu-id="691ff-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="691ff-392">Selecione a sequência de tarefas importada e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="691ff-393">O Editor de Sequência de Tarefas abre e exibe cada etapa sequencial que você precisa para implantar e configurar uma unidade de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="691ff-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="691ff-394">Ande por cada etapa e conclua as atualizações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="691ff-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="691ff-395">**Reiniciar no Windows PE**: Esta etapa é reiniciada e inicializa o computador no PXE do Windows.</span><span class="sxs-lookup"><span data-stu-id="691ff-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="691ff-396">Nenhuma alteração é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="691ff-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="691ff-397">**Disco de Partição 0 – UEFI**: Esta etapa apaga a configuração do disco e cria partições com base nas configurações configuradas.</span><span class="sxs-lookup"><span data-stu-id="691ff-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="691ff-398">Recomendamos que você não faça alterações nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="691ff-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="691ff-399">**Definir Nome do Computador SRS**: Esta etapa inclui um aplicativo HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade salas do Microsoft Teams durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="691ff-400">Esta é uma etapa opcional, mas só poderá ser desabilitada se você quiser gerenciar a nomeação do computador por meio de um processo alternativo.</span><span class="sxs-lookup"><span data-stu-id="691ff-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="691ff-401">Verifique se o **pacote SRS v2 - Set-SRSComputerName** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="691ff-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="691ff-402">Se não estiver, navegue até o pacote e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="691ff-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="691ff-403">**Aplicar Sistema Operacional**: esta etapa especifica a imagem do sistema operacional a ser implantada e o arquivo de resposta Sysprep sem supervisão a ser usado.</span><span class="sxs-lookup"><span data-stu-id="691ff-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="691ff-404">Verifique se o arquivo correto de imagem do sistema operacional Windows 10 Enterprise está selecionado.</span><span class="sxs-lookup"><span data-stu-id="691ff-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="691ff-405">Verifique se Usar um arquivo de resposta autônoma ou **Sysprep** para uma instalação personalizada está habilitado e o **Pacote SRS v2 - Sysprep** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="691ff-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="691ff-406">Verifique também se **o Nome do** Arquivo está definido como **unattend.xml**.</span><span class="sxs-lookup"><span data-stu-id="691ff-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="691ff-407">**Aplicar Configurações do Windows**: Esta etapa coleta informações sobre a instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="691ff-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="691ff-408">Forneça informações de licenciamento e registro, incluindo a chave do produto, a senha da conta do administrador local e o fuso horário (dependendo das suas necessidades).</span><span class="sxs-lookup"><span data-stu-id="691ff-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="691ff-409">**Aplicar Configurações de Rede**: Esta etapa permite especificar um grupo de trabalho ou nome de domínio do Active Directory e uma unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="691ff-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="691ff-410">Consulte [Considerações sobre](domain-joining-considerations.md) a junção de domínio do Sistema de Salas do Skype para as ações recomendadas que você precisa tomar na implantação de unidades do Microsoft Teams Rooms como membros de um domínio do Actve Directory.</span><span class="sxs-lookup"><span data-stu-id="691ff-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="691ff-411">**Aplicar drivers:** Esta etapa e suas sub-etapas são usadas para implantar drivers de dispositivo e firmware aplicáveis com base no modelo Surface Pro que você tem.</span><span class="sxs-lookup"><span data-stu-id="691ff-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="691ff-412">Atualize cada etapa para especificar o pacote de driver relevante associado a essa implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="691ff-413">Cada pacote de driver é configurado para aproveitar os filtros WMI (Instrumentação de Gerenciamento do Windows) para implantar drivers e firmware relevantes com base na make e no modelo do Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="691ff-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="691ff-414">É altamente recomendável que você não altere a configuração desses drivers, caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="691ff-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="691ff-415">**Configurar o Windows e o Configuration Manager:** esta etapa implanta e configura o cliente do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="691ff-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="691ff-416">Atualize esta etapa para especificar o Pacote de Cliente do Configuration Manager integrado.</span><span class="sxs-lookup"><span data-stu-id="691ff-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="691ff-417">**Instalar Certificado Raiz**: esta etapa distribui o certificado raiz para dispositivos não ingressados no domínio e, portanto, é opcional e desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="691ff-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="691ff-418">Habilita esta etapa se precisar implantar um certificado raiz nas unidades do Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="691ff-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="691ff-419">Se você precisar executar essa etapa, verifique se o **SRS v2 – Pacote** de Certificado Raiz e Desabilitar o redirecionamento do sistema de arquivos de **64 bits** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="691ff-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="691ff-420">**Instalar e configurar o Agente** de Monitoramento : Esta etapa instala a versão de 64 bits do agente do Microsoft Azure Monitor e configura o agente para se conectar ao seu espaço de trabalho do Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="691ff-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="691ff-421">Esta etapa é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="691ff-421">This step is disabled by default.</span></span> <span data-ttu-id="691ff-422">Habilita esta etapa somente se você for usar o Agente de Monitoramento para monitorar a saúde das unidades de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="691ff-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="691ff-423">Edite esta etapa e atualize os parâmetros de linha de comando para especificar a **ID** do Espaço de Trabalho e **a Chave do Espaço de Trabalho.**</span><span class="sxs-lookup"><span data-stu-id="691ff-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="691ff-424">Consulte [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obter mais informações sobre como obter a ID do Espaço de Trabalho do Pacote de Gerenciamento de Operações e a chave primária.</span><span class="sxs-lookup"><span data-stu-id="691ff-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="691ff-425">Verifique se o **SRS v2 – Pacote do Agente de Monitoramento** da Microsoft e Desabilitar o redirecionamento do sistema de arquivos de **64** bits está selecionado.</span><span class="sxs-lookup"><span data-stu-id="691ff-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="691ff-426">Para obter mais informações sobre como monitorar a saúde da implantação das Salas do Microsoft Teams, consulte Plan Microsoft Teams Rooms [management with Azure Monitor](azure-monitor-plan.md), Deploy Microsoft Teams Rooms management with [Azure Monitor](azure-monitor-deploy.md) and Manage Microsoft Teams Rooms devices with [Azure Monitor](azure-monitor-manage.md).</span><span class="sxs-lookup"><span data-stu-id="691ff-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="691ff-427">**Copiar arquivos de configuração do SRS v2**: Esta etapa copia os arquivos de configuração e configuração necessários do kit de implantação de Salas do Microsoft Teams para o disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="691ff-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="691ff-428">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="691ff-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="691ff-429">Verifique se o **SRS v2 – Pacote de Aplicativos SRS** e Desabilitar o redirecionamento do sistema de arquivos de **64 bits** estão selecionados.</span><span class="sxs-lookup"><span data-stu-id="691ff-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="691ff-430">**Install-SRSv2-OS-Updates**: Esta etapa implanta todas as atualizações obrigatórias do sistema operacional necessárias com a implantação das Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="691ff-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="691ff-431">Siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="691ff-431">Do the following:</span></span>
       -   <span data-ttu-id="691ff-432">Verifique [Configurar um console de Salas do Microsoft Teams](console.md) para ver quais atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="691ff-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="691ff-433">Verifique se o pacote de atualizações do SISTEMA OPERACIONAL do **SRS v2** inclui todas as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="691ff-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="691ff-434">Verifique se o Pacote de Atualizações do SISTEMA OPERACIONAL do **SRS v2** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="691ff-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="691ff-435">Verifique se a política de execução do PowerShell está definida como **Bypass**.</span><span class="sxs-lookup"><span data-stu-id="691ff-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="691ff-436">**Reiniciar Computador**: esta etapa reinicia o computador depois que as atualizações obrigatórias do sistema operacional são instaladas.</span><span class="sxs-lookup"><span data-stu-id="691ff-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="691ff-437">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="691ff-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="691ff-438">**Configurar componentes do Windows:** esta etapa configura os recursos necessários do Windows.</span><span class="sxs-lookup"><span data-stu-id="691ff-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="691ff-439">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="691ff-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="691ff-440">**Reiniciar Computador**: Esta etapa reinicia o computador depois que os recursos do Windows são configurados.</span><span class="sxs-lookup"><span data-stu-id="691ff-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="691ff-441">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="691ff-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="691ff-442">**Adicionar Usuário Local do Skype**: Esta etapa cria a conta local do Skype usada para entrar automaticamente no Windows e iniciar o aplicativo salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="691ff-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="691ff-443">Esta etapa não tem nenhum pacote de software associado a ele e nenhuma personalização é necessária para ele.</span><span class="sxs-lookup"><span data-stu-id="691ff-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="691ff-444">**Configurar e configurar o aplicativo SRS**: Esta etapa configura a instalação do aplicativo salas do Microsoft Teams para a próxima inicialização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="691ff-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="691ff-445">Verifique se o **SRS v2 – Configurar o** Pacote de Instalação do SRS e Desabilitar o redirecionamento do sistema de arquivos de **64** bits está selecionado.</span><span class="sxs-lookup"><span data-stu-id="691ff-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="691ff-446">É muito importante que as etapas da sequência de tarefas devem estar na ordem fornecida.</span><span class="sxs-lookup"><span data-stu-id="691ff-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="691ff-447">Modificar a ordem das etapas ou configurar etapas adicionais pode quebrar a implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="691ff-448">**Configurar e configurar a etapa** do aplicativo SRS deve ser a última etapa da sequência de tarefas, caso contrário, a implantação poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="691ff-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="691ff-449">Criar implantação para a sequência de tarefas</span><span class="sxs-lookup"><span data-stu-id="691ff-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="691ff-450">Selecione a sequência de tarefas e selecione **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="691ff-451">Selecione **Procurar** para selecionar o conjunto de destinos para implantação.</span><span class="sxs-lookup"><span data-stu-id="691ff-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="691ff-452">Selecione **Todos os Computadores Desconhecidos** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="691ff-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="691ff-453">Selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="691ff-453">Select **Next**.</span></span>

5. <span data-ttu-id="691ff-454">Selecione **Disponível** na **listada** Finalidade.</span><span class="sxs-lookup"><span data-stu-id="691ff-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="691ff-455">Selecione **Somente Mídia e PXE** na lista **Disponibilizar** para a lista a seguir e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="691ff-456">É muito importante que **Purpose** seja definido como **Disponível**.</span><span class="sxs-lookup"><span data-stu-id="691ff-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="691ff-457">Certifique-se de **que a Finalidade** NÃO **está** definida **como Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="691ff-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="691ff-458">Além disso, certifique-se de selecionar **Somente Mídia e PXE** no **make available to the following**.</span><span class="sxs-lookup"><span data-stu-id="691ff-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="691ff-459">Definir esses valores para outra coisa pode fazer com que todos os computadores recebam a imagem de implantação do Microsoft Teams Rooms quando inicializadas.</span><span class="sxs-lookup"><span data-stu-id="691ff-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="691ff-460">Não especifique nenhum cronograma e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="691ff-461">Não altere nada na seção Experiência do **Usuário** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="691ff-462">Não altere nada na seção **Alertas** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="691ff-463">Não altere nada na seção **Pontos de Distribuição** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="691ff-464">Confirme as configurações e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="691ff-465">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="691ff-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="691ff-466">Validar e solucionar problemas da solução</span><span class="sxs-lookup"><span data-stu-id="691ff-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="691ff-467">Depois de concluir as sequências de tarefas do Microsoft Endpoint Configuration Manager, você precisará executar uma execução de teste para validar se a sequência de tarefas pode implantar e configurar unidades de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="691ff-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="691ff-468">Conecte o dispositivo de teste à rede com fio usando um dos adaptadores Ethernet com suporte ou usando o encaixe Surface.</span><span class="sxs-lookup"><span data-stu-id="691ff-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="691ff-469">Se a funcionalidade de inicialização PXE não tiver sido configurada para seu [](/configmgr/osd/deploy-use/create-bootable-media) ambiente, você poderá usar a imagem de inicialização na unidade flash USB que você criou anteriormente para inicializar a partir de USB e se conectar ao Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="691ff-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="691ff-470">Acesse o firmware e inicie a inicialização PXE:</span><span class="sxs-lookup"><span data-stu-id="691ff-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="691ff-471">Verifique se o dispositivo Surface está desligado.</span><span class="sxs-lookup"><span data-stu-id="691ff-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="691ff-472">Pressione e segure o **botão Volume Up.**</span><span class="sxs-lookup"><span data-stu-id="691ff-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="691ff-473">Pressione e solte o **botão Ligar.**</span><span class="sxs-lookup"><span data-stu-id="691ff-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="691ff-474">Depois que o dispositivo começar a ser inicializado, solte o **botão Volume Up.**</span><span class="sxs-lookup"><span data-stu-id="691ff-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="691ff-475">Selecione **Configuração de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="691ff-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="691ff-476">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="691ff-476">Do one of the following:</span></span>

        -   <span data-ttu-id="691ff-477">Selecione **inicialização PXE** e arraste-a para a parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="691ff-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="691ff-478">Como alternativa, você pode passar o dedo para a esquerda no adaptador de rede para inicializar o dispositivo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="691ff-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="691ff-479">Isso não afetará a ordem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="691ff-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="691ff-480">Selecione a unidade flash USB que contém a mídia de inicialização.</span><span class="sxs-lookup"><span data-stu-id="691ff-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="691ff-481">Selecione **Sair** e, em seguida, selecione **Reiniciar Agora**.</span><span class="sxs-lookup"><span data-stu-id="691ff-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="691ff-482">Quando solicitado, selecione **Enter for** network boot service.</span><span class="sxs-lookup"><span data-stu-id="691ff-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="691ff-483">O Windows PE será carregado na memória e o Assistente de Sequência de Tarefas será a iniciar.</span><span class="sxs-lookup"><span data-stu-id="691ff-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="691ff-484">Selecione **Próximo** para continuar.</span><span class="sxs-lookup"><span data-stu-id="691ff-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="691ff-485">Selecione a sequência de tarefas que você importou anteriormente e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="691ff-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="691ff-486">Depois que a configuração do disco for aplicada, você será solicitado a especificar um nome de computador para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="691ff-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="691ff-487">A interface do usuário exibirá um nome de computador recomendado com base no número de série do dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="691ff-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="691ff-488">Você pode aceitar o nome proposto ou especificar um novo.</span><span class="sxs-lookup"><span data-stu-id="691ff-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="691ff-489">Siga as instruções na tela de atribuição do nome do computador.</span><span class="sxs-lookup"><span data-stu-id="691ff-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="691ff-490">Quando você seleciona **Aceitar**, a implantação começa.</span><span class="sxs-lookup"><span data-stu-id="691ff-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="691ff-491">O restante do processo de implantação é automático e não solicita mais entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="691ff-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="691ff-492">Depois que a sequência de tarefas de implantação terminar de configurar o dispositivo, você verá a seguinte tela de configuração que solicita que você configure as configurações do aplicativo salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="691ff-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Tela de instalação inicial do aplicativo Salas do Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="691ff-494">Conecte o Surface Pro ao console do Microsoft Teams Rooms e configure as configurações do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="691ff-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="691ff-495">Valide se os recursos listados nas [Salas do Microsoft Teams estão](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funcionando no dispositivo implantado.</span><span class="sxs-lookup"><span data-stu-id="691ff-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="691ff-496">Para solucionar problemas de uma instalação com falha, verifique o **arquivo SMSTS.log,** que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="691ff-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="691ff-497">O arquivo SMSTS.log é armazenado em um de vários caminhos, dependendo do estágio do processo de com build.</span><span class="sxs-lookup"><span data-stu-id="691ff-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="691ff-498">Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="691ff-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="691ff-499">**Fase de implantação**</span><span class="sxs-lookup"><span data-stu-id="691ff-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="691ff-500">**Caminho de log de sequência de tarefas**</span><span class="sxs-lookup"><span data-stu-id="691ff-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="691ff-501">WinPE, antes do formato HDD</span><span class="sxs-lookup"><span data-stu-id="691ff-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="691ff-502">X: \\ \\ \\ Smstslog do Windows Temp \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="691ff-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="691ff-503">WinPE, após o formato HDD</span><span class="sxs-lookup"><span data-stu-id="691ff-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="691ff-504">C: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="691ff-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="691ff-505">Sistema operacional implantado, antes da instalação do agente do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="691ff-506">c: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="691ff-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="691ff-507">Sistema operacional e o agente do Configuration Manager implantado</span><span class="sxs-lookup"><span data-stu-id="691ff-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="691ff-508">%windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="691ff-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="691ff-509">Execução da sequência de tarefas concluída</span><span class="sxs-lookup"><span data-stu-id="691ff-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="691ff-510">%windir% \\ System32 \\ ccm \\ logs \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="691ff-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="691ff-511">Você pode selecionar **F8** a qualquer momento durante a sequência de tarefas para abrir um console de comando e obter acesso ao arquivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="691ff-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="691ff-512">Para solucionar problemas de inicialização PXE, verifique os dois arquivos de log no servidor do Configuration Manager que são específicos das ações PXE:</span><span class="sxs-lookup"><span data-stu-id="691ff-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="691ff-513">**Pxecontrol.log**, localizado no diretório de logs de instalação do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="691ff-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="691ff-514">**Smspxe.log**, localizado no diretório de logs do Ponto de Gerenciamento do Configuration Manager (MP)</span><span class="sxs-lookup"><span data-stu-id="691ff-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="691ff-515">Para uma lista completa dos arquivos de log que você pode usar para solucionar problemas adicionais da instalação do Configuration Manager, consulte a referência de arquivo [de log](/configmgr/core/plan-design/hierarchy/log-files)do Microsoft Endpoint Configuration Manager .</span><span class="sxs-lookup"><span data-stu-id="691ff-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>