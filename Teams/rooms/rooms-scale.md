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
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662416"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="9f66a-103">Implantar salas do Microsoft Teams usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f66a-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="9f66a-104">Este artigo fornece todas as informações necessárias para criar suas implantações de Salas do Microsoft Teams usando o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="9f66a-105">Com os métodos fáceis de usar fornecidos pelo Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="9f66a-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="9f66a-106">Use a abordagem ilustrada abaixo para orientá-lo em sua configuração do Configuration Manager e personalizar os exemplos de pacotes e scripts fornecidos ao longo dessa orientação, conforme necessário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9f66a-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processo de implantação de Salas do Microsoft Teams usando o Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="9f66a-108">Esta solução foi testada apenas com implantações baseadas no Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="9f66a-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="9f66a-109">Siga as diretrizes do fabricante para configurações que não são baseadas no Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="9f66a-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="9f66a-110">Validar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9f66a-110">Validate prerequisites</span></span>

<span data-ttu-id="9f66a-111">Para implantar salas do Microsoft Teams com o Configuration Manager, certifique-se de atender aos seguintes pré-requisitos e requisitos.</span><span class="sxs-lookup"><span data-stu-id="9f66a-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="9f66a-112">Requisitos do Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f66a-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="9f66a-113">A versão do Microsoft Endpoint Configuration Manager deve ser pelo menos 1706 ou superior.</span><span class="sxs-lookup"><span data-stu-id="9f66a-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="9f66a-114">Recomendamos usar o 1710 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9f66a-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="9f66a-115">Confira o [suporte para o Windows 10 no Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões do Windows 10 compatíveis com o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-115">Check out [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="9f66a-116">Uma versão com suporte do ADK (Kit de Avaliação e Implantação) do Windows para Windows 10 deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="9f66a-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="9f66a-117">Veja as versões do [ADK do Windows 10](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com diferentes versões do Configuration Manager e verifique se sua implantação inclui a versão correta.</span><span class="sxs-lookup"><span data-stu-id="9f66a-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="9f66a-118">Os servidores do sistema de site devem ter sido atribuídos a função de ponto de distribuição, e as imagens de inicialização devem estar habilitadas para suporte a [PXE (ambiente](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) de execução pré-inicialização) para habilitar implantações iniciadas pela rede.</span><span class="sxs-lookup"><span data-stu-id="9f66a-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="9f66a-119">Se o suporte PXE não estiver habilitado, você poderá usar mídia [inicial](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.</span><span class="sxs-lookup"><span data-stu-id="9f66a-119">If PXE support isn't enabled, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="9f66a-120">Uma conta de acesso à rede deve ser configurada para dar suporte a novos cenários de implantação de computador (metal nu).</span><span class="sxs-lookup"><span data-stu-id="9f66a-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="9f66a-121">Para saber mais sobre a configuração de uma conta de acesso à rede, consulte [Contas usadas no Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="9f66a-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="9f66a-122">Recomendamos que você habilita o suporte a [multicast,](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)se tiver a probabilidade de implantar a mesma imagem de Salas do Microsoft Teams em várias unidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9f66a-122">We recommend that you enable [multicast support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="9f66a-123">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="9f66a-123">Networking requirements</span></span>

-   <span data-ttu-id="9f66a-124">Sua rede deve ter um servidor DHCP (Dynamic Host Configuration Protocol), configurado para distribuição automática de endereços IP para as sub-redes onde as unidades de Salas do Microsoft Teams serão implantadas.</span><span class="sxs-lookup"><span data-stu-id="9f66a-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9f66a-125">A duração da concessão de DHCP deve ser definida como um valor mais longo do que a duração da implantação da imagem.</span><span class="sxs-lookup"><span data-stu-id="9f66a-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="9f66a-126">Caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="9f66a-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="9f66a-127">Sua rede, incluindo opções e VLANs virtuais, deve ser configurada para dar suporte a PXE.</span><span class="sxs-lookup"><span data-stu-id="9f66a-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="9f66a-128">Consulte seu fornecedor de rede para obter mais informações sobre a configuração do Ip Helper e PXE.</span><span class="sxs-lookup"><span data-stu-id="9f66a-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="9f66a-129">Como alternativa, você pode usar [mídia inicializável](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte PXE não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9f66a-130">Para dispositivos Surface Pro, a inicialização da rede (inicialização PXE) só tem suporte quando você usa um adaptador Ethernet ou uma estação de encaixe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f66a-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="9f66a-131">Adaptadores Ethernet de terceiros não são suportados por inicialização PXE com o Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="9f66a-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="9f66a-132">Consulte [adaptadores Ethernet e a implantação do Surface](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9f66a-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="9f66a-133">Configurar o Microsoft Endpoint Configuration Manager para implantação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9f66a-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="9f66a-134">Este artigo pressuposiciona que você já tem uma implantação saudável do Configuration Manager e não detalha todas as etapas necessárias para implantar e configurar o Configuration Manager do zero.</span><span class="sxs-lookup"><span data-stu-id="9f66a-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="9f66a-135">A [documentação e as diretrizes de](https://docs.microsoft.com/configmgr/) configuração do Microsoft Endpoint Configuration Manager são um ótimo recurso; recomendamos começar com esses recursos se você ainda não implantou o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-135">The [documentation and the configuration guidance](https://docs.microsoft.com/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="9f66a-136">Use as instruções a seguir para verificar se os recursos de implantação do sistema operacional (OSD) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="9f66a-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="9f66a-137">Validar e atualizar o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f66a-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="9f66a-138">No console do Configuration Manager, vá **para Atualizações** de \> **Administração e Manutenção.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="9f66a-139">Verifique o build instalado e as atualizações aplicáveis que ainda não foram instaladas.</span><span class="sxs-lookup"><span data-stu-id="9f66a-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="9f66a-140">Revise [o suporte para o Windows 10 no Configuration Manager;](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) se precisar atualizar sua implantação, selecione a atualização que deseja instalar e, em seguida, selecione **Baixar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-140">Review [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="9f66a-141">Depois que o download for concluído, selecione a atualização e, em seguida, **selecione Instalar Pacote de Atualização.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="9f66a-142">Configurar pontos de distribuição para dar suporte a PXE e multicast</span><span class="sxs-lookup"><span data-stu-id="9f66a-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="9f66a-143">No console do Configuration Manager, vá para **Pontos de** Distribuição \> **da Administração.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="9f66a-144">Selecione o servidor do ponto de distribuição que atenderá à implantação de Salas do Microsoft Teams e, em seguida, selecione **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="9f66a-145">Selecione a **guia PXE** e verifique se as seguintes configurações estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="9f66a-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="9f66a-146">Habilitar o suporte PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="9f66a-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="9f66a-147">Permitir que este ponto de distribuição responda a solicitações PXE de entrada</span><span class="sxs-lookup"><span data-stu-id="9f66a-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="9f66a-148">Habilitar o suporte de computador desconhecido</span><span class="sxs-lookup"><span data-stu-id="9f66a-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="9f66a-149">*Opcional:* Para habilitar o suporte a **multicast,** selecione a guia Multicast e verifique se as seguintes configurações estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="9f66a-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="9f66a-150">Habilitar o multicast para enviar dados simultaneamente para vários clientes</span><span class="sxs-lookup"><span data-stu-id="9f66a-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="9f66a-151">Configurar o intervalo de portas UDP de acordo com a recomendação da equipe de rede</span><span class="sxs-lookup"><span data-stu-id="9f66a-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="9f66a-152">Configurar a Conta de Acesso à Rede</span><span class="sxs-lookup"><span data-stu-id="9f66a-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="9f66a-153">No console do Gerenciador de Configurações, vá para Sites **de** Configuração do Site de Administração \>  \> e selecione o site.</span><span class="sxs-lookup"><span data-stu-id="9f66a-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="9f66a-154">No grupo **Configurações,** selecione Configurar Distribuição de Software **de Componentes** \> **do** Site.</span><span class="sxs-lookup"><span data-stu-id="9f66a-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="9f66a-155">Selecione a **guia Conta de Acesso à** Rede. Configurar uma ou mais contas e, em seguida, selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="9f66a-156">As contas não precisam de direitos especiais, exceto o **Access deste** computador da rede no servidor do ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9f66a-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="9f66a-157">Uma conta de usuário de domínio genérico será apropriada.</span><span class="sxs-lookup"><span data-stu-id="9f66a-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="9f66a-158">Para obter mais informações, consulte [Contas usadas no Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="9f66a-158">For more information, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="9f66a-159">Configurar uma imagem de inicialização</span><span class="sxs-lookup"><span data-stu-id="9f66a-159">Configure a boot image</span></span>

1.  <span data-ttu-id="9f66a-160">No console do Configuration Manager, vá para **Imagens de Inicialização** do Sistema \> **Operacional da Biblioteca de** \> Software.</span><span class="sxs-lookup"><span data-stu-id="9f66a-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="9f66a-161">Selecione **a imagem de inicialização (x64)** e, em seguida, selecione **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="9f66a-162">Selecione a **guia Fonte de** Dados e habilita a implantar esta imagem de inicialização no ponto de distribuição habilitado para **PXE.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="9f66a-163">Selecione a **guia Componentes Opcionais** para instalar os componentes necessários:</span><span class="sxs-lookup"><span data-stu-id="9f66a-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="9f66a-164">Selecione o ícone de estrela e procure **HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="9f66a-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="9f66a-165">Selecione **OK** para adicionar suporte ao aplicativo HTML na imagem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="9f66a-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="9f66a-166">*Opcional:* Para personalizar a experiência de implantação, selecione a **guia Personalização.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="9f66a-167">Habilita o suporte a comandos **(somente teste)** se você quiser ter acesso a um prompt de comando durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="9f66a-168">Quando isso estiver habilitado, você pode iniciar um prompt de comando selecionando **F8** a qualquer momento durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="9f66a-169">Você também pode especificar uma imagem de tela de fundo personalizada a ser exibida durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="9f66a-170">Para definir uma imagem, **habilitar Especificar o arquivo de** imagem de plano de fundo personalizado (caminho UNC e selecionar o plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="9f66a-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="9f66a-171">Quando solicitado, selecione **Sim e** distribua a imagem de inicialização atualizada para seus pontos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9f66a-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="9f66a-172">Para obter mais informações, consulte [Gerenciar imagens de inicialização com o Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)</span><span class="sxs-lookup"><span data-stu-id="9f66a-172">For more information, see [Manage boot images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="9f66a-173">Você pode criar uma mídia USB inicializável para iniciar implantações baseadas em sequência de tarefas do Configuration Manager para ambientes que não têm suporte PXE.</span><span class="sxs-lookup"><span data-stu-id="9f66a-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="9f66a-174">A mídia inicial contém apenas a imagem de inicialização, os comandos de prestart opcionais e seus arquivos necessários, e binários do Configuration Manager para dar suporte à inicialização no Windows PE e à conexão com o Configuration Manager para o restante do processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="9f66a-175">Para obter mais informações, consulte [Criar mídia inicializável.](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)</span><span class="sxs-lookup"><span data-stu-id="9f66a-175">For more information, see [Create bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="9f66a-176">Criar pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f66a-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f66a-177">A versão do sistema operacional necessária para cada versão do instalador SRS muda a cada versão MSI.</span><span class="sxs-lookup"><span data-stu-id="9f66a-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="9f66a-178">Para determinar a melhor versão do sistema operacional para um determinado MSI, execute o script de configuração do console uma vez.</span><span class="sxs-lookup"><span data-stu-id="9f66a-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="9f66a-179">Para saber mais, confira [Implantar Salas do Microsoft Teams usando o Microsoft Endpoint Configuration Manager.](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="9f66a-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="9f66a-180">O Configuration Manager requer vários pacotes para implantar e configurar as unidades de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="9f66a-181">Você precisa criar e configurar os pacotes a seguir e distribuí-los para os sistemas de site do Configuration Manager que tenham sido atribuídos a função de servidor de ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9f66a-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="9f66a-182">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="9f66a-182">**Package name**</span></span>                     | <span data-ttu-id="9f66a-183">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9f66a-183">**Type**</span></span>               | <span data-ttu-id="9f66a-184">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9f66a-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="9f66a-185">SRS v2 - Pacote de Aplicativos SRS</span><span class="sxs-lookup"><span data-stu-id="9f66a-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="9f66a-186">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-186">Software package</span></span>       | <span data-ttu-id="9f66a-187">Pacote para o kit de implantação de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f66a-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="9f66a-188">SRS v2 - Pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="9f66a-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="9f66a-189">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-189">Software package</span></span>       | <span data-ttu-id="9f66a-190">Pacote para o conjunto de Unattended.xml para configurar unidades de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f66a-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="9f66a-191">SRS v2 - Set-SRSComputerName Pacote</span><span class="sxs-lookup"><span data-stu-id="9f66a-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="9f66a-192">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-192">Software package</span></span>       | <span data-ttu-id="9f66a-193">Pacote do aplicativo HTML (HTA) para atribuir um nome de computador durante a implantação</span><span class="sxs-lookup"><span data-stu-id="9f66a-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="9f66a-194">SRS v2 - Configurar Configuração srs</span><span class="sxs-lookup"><span data-stu-id="9f66a-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="9f66a-195">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-195">Software package</span></span>       | <span data-ttu-id="9f66a-196">Pacote para configurar a implantação do aplicativo Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f66a-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="9f66a-197">SRS v2 - Pacote de Atualizações do SISTEMA OPERACIONAL</span><span class="sxs-lookup"><span data-stu-id="9f66a-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="9f66a-198">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-198">Software package</span></span>       | <span data-ttu-id="9f66a-199">Pacote para implantar atualizações obrigatórias do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9f66a-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="9f66a-200">SRS v2 - Pacote de Certificado Raiz</span><span class="sxs-lookup"><span data-stu-id="9f66a-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="9f66a-201">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-201">Software package</span></span>       | <span data-ttu-id="9f66a-202">Opcional - Pacote para implantar o certificado raiz (não necessário para unidades unidas pelo domínio)</span><span class="sxs-lookup"><span data-stu-id="9f66a-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="9f66a-203">SRS v2 - Pacote do Agente de Monitoramento da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9f66a-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="9f66a-204">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-204">Software package</span></span>       | <span data-ttu-id="9f66a-205">Opcional - Pacote para implantar e configurar o agente do Pacote de Gerenciamento de Operações da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9f66a-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="9f66a-206">SRS v2 - Pacote de Plano de Fundo do WinPE</span><span class="sxs-lookup"><span data-stu-id="9f66a-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="9f66a-207">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="9f66a-207">Software package</span></span>       | <span data-ttu-id="9f66a-208">Pacote para a imagem de plano de fundo personalizada a ser usada com imagens de inicialização</span><span class="sxs-lookup"><span data-stu-id="9f66a-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="9f66a-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9f66a-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="9f66a-210">Imagem do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9f66a-210">Operating system image</span></span> | <span data-ttu-id="9f66a-211">Pacote para o arquivo de instalação do sistema operacional (install.wim)</span><span class="sxs-lookup"><span data-stu-id="9f66a-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="9f66a-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="9f66a-212">Surface Pro</span></span>                          | <span data-ttu-id="9f66a-213">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="9f66a-213">Driver package</span></span>         | <span data-ttu-id="9f66a-214">Pacote para os drivers de dispositivo e firmware do Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="9f66a-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="9f66a-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="9f66a-215">Surface Pro 4</span></span>                        | <span data-ttu-id="9f66a-216">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="9f66a-216">Driver package</span></span>         | <span data-ttu-id="9f66a-217">Pacote para os drivers de dispositivo e firmware do Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="9f66a-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="9f66a-218">Para obter mais informações, consulte [Pacotes e programas no Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="9f66a-218">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="9f66a-219">Criar pastas para os arquivos de origem do pacote</span><span class="sxs-lookup"><span data-stu-id="9f66a-219">Create folders for the package source files</span></span>

<span data-ttu-id="9f66a-220">O Configuration Manager exige que os arquivos de origem de pacote sejam organizados em uma estrutura de pastas específica quando eles são criados pela primeira vez e quando são atualizados.</span><span class="sxs-lookup"><span data-stu-id="9f66a-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="9f66a-221">Crie a seguinte estrutura de pastas no site de administração central do Microsoft Endpoint Configuration Manager ou no site principal ou em um compartilhamento de servidor que você está usando para hospedar arquivos de origem de pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="9f66a-222">SRS v2 - Pacote do Agente de Monitoramento da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9f66a-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="9f66a-223">SRS v2 - Pacote de Atualizações do SISTEMA OPERACIONAL</span><span class="sxs-lookup"><span data-stu-id="9f66a-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="9f66a-224">SRS v2 - Pacote de Certificado Raiz</span><span class="sxs-lookup"><span data-stu-id="9f66a-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="9f66a-225">SRS v2 - Set-SRSComputerName Pacote</span><span class="sxs-lookup"><span data-stu-id="9f66a-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="9f66a-226">SRS v2 - Pacote de Aplicativos SRS</span><span class="sxs-lookup"><span data-stu-id="9f66a-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="9f66a-227">SRS v2 - Configurar Configuração srs</span><span class="sxs-lookup"><span data-stu-id="9f66a-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="9f66a-228">SRS v2 - Pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="9f66a-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="9f66a-229">Drivers</span><span class="sxs-lookup"><span data-stu-id="9f66a-229">Drivers</span></span>
    -   <span data-ttu-id="9f66a-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="9f66a-230">Surface Pro</span></span>
    -   <span data-ttu-id="9f66a-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="9f66a-231">Surface Pro 4</span></span>
-   <span data-ttu-id="9f66a-232">Sistemas Operacionais</span><span class="sxs-lookup"><span data-stu-id="9f66a-232">Operating Systems</span></span>
    -   <span data-ttu-id="9f66a-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9f66a-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="9f66a-234">Você também pode [baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pastas dos pacotes, os scripts que você precisa usar e o modelo de sequência de tarefas que você precisa importar.</span><span class="sxs-lookup"><span data-stu-id="9f66a-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="9f66a-235">Criar o pacote do agente de monitoramento</span><span class="sxs-lookup"><span data-stu-id="9f66a-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="9f66a-236">Baixe o agente de monitoramento de <https://go.microsoft.com/fwlink/?LinkId=828603> .</span><span class="sxs-lookup"><span data-stu-id="9f66a-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="9f66a-237">Extraia o pacote na pasta **SRS v2 –** Pacote do Agente de Monitoramento da Microsoft abrindo uma janela do Prompt de Comando e inserindo **MMASetup-AMD64.exe /C:**     no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="9f66a-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="9f66a-238">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e \>  \> selecione **Criar Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="9f66a-239">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="9f66a-240">Nome<strong>: SRS v2 - Pacote do Agente de Monitoramento da Microsoft</strong></span><span class="sxs-lookup"><span data-stu-id="9f66a-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="9f66a-241">Fabricante<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="9f66a-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="9f66a-242">Versão:<strong>8.1.11081.0</strong> (insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="9f66a-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="9f66a-243">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 –** Pacote do Agente de Monitoramento da Microsoft e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="9f66a-244">Selecione **Não criar um programa e,** em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="9f66a-245">Revise a **página Confirmar as configurações** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="9f66a-246">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="9f66a-247">Criar o pacote de atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9f66a-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="9f66a-248">Na pasta **SRS v2 – Pacote de** Atualizações do SISTEMA OPERACIONAL, crie um novo script do PowerShell chamado **Install-SRSv2-OS-Updates.ps1.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="9f66a-249">Copie o script abaixo para o **Install-SRSv2-OS-Updates.ps1** script.</span><span class="sxs-lookup"><span data-stu-id="9f66a-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="9f66a-250">Como alternativa, você pode baixar o Install-SRSv2-OS-Updates.ps1 de texto [a partir daqui.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9f66a-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="9f66a-251">Baixe os pacotes obrigatórios do Windows Update para a mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="9f66a-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9f66a-252">No momento em que este artigo foi publicado, somente [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era obrigatório.</span><span class="sxs-lookup"><span data-stu-id="9f66a-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="9f66a-253">Marque [Configurar um console de Salas do Microsoft Teams](console.md)para ver se outras atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="9f66a-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="9f66a-254">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e \>  \> selecione **Criar Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="9f66a-255">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="9f66a-256">Nome: **SRS v2 – Pacote de Atualizações do SISTEMA OPERACIONAL**</span><span class="sxs-lookup"><span data-stu-id="9f66a-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="9f66a-257">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="9f66a-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="9f66a-258">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="9f66a-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="9f66a-259">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 –** Pacote de Atualizações do SISTEMA OPERACIONAL e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="9f66a-260">Selecione **Não criar um programa e,** em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="9f66a-261">Revise a **página Confirmar as configurações** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="9f66a-262">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="9f66a-263">Criar o pacote de certificado raiz (opcional)</span><span class="sxs-lookup"><span data-stu-id="9f66a-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="9f66a-264">Você cria este pacote para distribuir o certificado raiz para dispositivos que não serão unidos a um domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f66a-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="9f66a-265">Crie este pacote somente se ambas as seguintes condições se aplicarem:</span><span class="sxs-lookup"><span data-stu-id="9f66a-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="9f66a-266">Sua implantação inclui o Lync local ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9f66a-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="9f66a-267">As unidades de Salas do Microsoft Teams estão configuradas para funcionar em um grupo de trabalho em vez de um membro do domínio.</span><span class="sxs-lookup"><span data-stu-id="9f66a-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="9f66a-268">Copie o certificado raiz para a **pasta SRS v2 – Pacote de Certificado** Raiz.</span><span class="sxs-lookup"><span data-stu-id="9f66a-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="9f66a-269">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e \>  \> selecione **Criar Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="9f66a-270">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="9f66a-271">Nome: **SRS v2 – Pacote de Certificado Raiz**</span><span class="sxs-lookup"><span data-stu-id="9f66a-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="9f66a-272">Fabricante: *nome da sua organização*</span><span class="sxs-lookup"><span data-stu-id="9f66a-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="9f66a-273">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="9f66a-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="9f66a-274">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 –** Pacote de Certificado Raiz e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="9f66a-275">Selecione **Não criar um programa e,** em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="9f66a-276">Revise a **página Confirmar as configurações** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="9f66a-277">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="9f66a-278">Criar o pacote de kit de implantação de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f66a-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="9f66a-279">Baixe a versão mais recente do kit de implantação **de Salas do Microsoft Teams** e <https://go.microsoft.com/fwlink/?linkid=851168> instale-o em uma estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9f66a-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="9f66a-280">Copie o conteúdo de C: Kit de Implantação de Arquivos de Programas **\\ (x86) \\** do Skype Room System para a pasta **SRS v2 – Pacote de Aplicativos SRS.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="9f66a-281">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e \>  \> selecione **Criar Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="9f66a-282">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="9f66a-283">Nome: **SRS v2 – Pacote de Aplicativos SRS**</span><span class="sxs-lookup"><span data-stu-id="9f66a-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="9f66a-284">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="9f66a-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="9f66a-285">Versão: **3.1.104.0** (insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="9f66a-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="9f66a-286">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta Pacote de Aplicativo **SRS v2 – SRS e,** em seguida, **selecione Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="9f66a-287">Selecione **Não criar um programa e,** em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="9f66a-288">Revise a **página Confirmar as configurações** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="9f66a-289">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="9f66a-290">Criar o pacote de atribuição de nome de computador</span><span class="sxs-lookup"><span data-stu-id="9f66a-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="9f66a-291">Na pasta **Pacote do SRS v2 - Set-SRSComputerName,** crie um novo aplicativo HTML chamado **Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="9f66a-292">Copie o seguinte script para o **arquivo Set-SRSComputerName.hta.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="9f66a-293">Como alternativa, você pode baixar o arquivo Set-SRSComputerName.hta [daqui.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9f66a-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="9f66a-294">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e \>  \> selecione **Criar Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="9f66a-295">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="9f66a-296">Nome: **SRS v2 - Set-SRSComputerName Pacote**</span><span class="sxs-lookup"><span data-stu-id="9f66a-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="9f66a-297">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="9f66a-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="9f66a-298">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="9f66a-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="9f66a-299">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SrS v2 - Set-SRSComputerName Pacote** e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="9f66a-300">Selecione **Não criar um programa e,** em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="9f66a-301">Revise a **página Confirmar as configurações** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="9f66a-302">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="9f66a-303">Criar o pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="9f66a-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="9f66a-304">Na pasta **Pacote do SRS v2 – Sysprep,** crie um novo arquivo XML chamado **Unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="9f66a-305">Copie o seguinte texto para o **arquivoUnattend.xml** arquivo.</span><span class="sxs-lookup"><span data-stu-id="9f66a-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="9f66a-306">Como alternativa, você pode baixar o arquivo Unattend.xml [aqui.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9f66a-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="9f66a-307">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e \>  \> selecione **Criar Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="9f66a-308">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="9f66a-309">Nome: **SRS v2 - Pacote Sysprep**</span><span class="sxs-lookup"><span data-stu-id="9f66a-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="9f66a-310">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="9f66a-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="9f66a-311">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="9f66a-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="9f66a-312">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta pacote **SRS v2 – Sysprep** e, em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="9f66a-313">Selecione **Não criar um programa e,** em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="9f66a-314">Revise a **página Confirmar as configurações** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="9f66a-315">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="9f66a-316">Criar o pacote do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9f66a-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="9f66a-317">Obtenha uma mídia do Windows 10 Enterprise x64 e copie o arquivo **install.wim** para a pasta Sistemas Operacionais **\\ windows 10 Enterprise.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="9f66a-318">No console do Configuration Manager, vá para **Imagens** do Sistema Operacional da Biblioteca de Software e \>  \> selecione Adicionar **Imagem do Sistema Operacional.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="9f66a-319">Especifique o caminho para o **arquivo install.wim** que você acabou de copiar e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="9f66a-320">Atualize **o campo** Versão para corresponder ao número de build da imagem do Windows 10 Enterprise e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="9f66a-321">Revise a **página Detalhes** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="9f66a-322">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-322">Select **Close**.</span></span>

<span data-ttu-id="9f66a-323">Para obter mais informações, consulte [Gerenciar imagens do sistema operacional com o Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)</span><span class="sxs-lookup"><span data-stu-id="9f66a-323">For more information, see [Manage OS images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="9f66a-324">Criar pacotes de driver de dispositivo do Surface Pro</span><span class="sxs-lookup"><span data-stu-id="9f66a-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="9f66a-325">O Microsoft Teams Rooms tem suporte para Surface Pro e Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="9f66a-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="9f66a-326">Você precisa criar um pacote de driver para cada modelo do Surface Pro que você tem em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="9f66a-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f66a-327">Os drivers devem ser compatíveis com o build do Windows 10 Enterprise e com a versão do kit de implantação de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="9f66a-328">Para obter mais informações, consulte Baixar o firmware e os drivers mais [recentes para dispositivos Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e Configurar um [console.](console.md)</span><span class="sxs-lookup"><span data-stu-id="9f66a-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="9f66a-329">Baixe os drivers e firmware mais recentes.</span><span class="sxs-lookup"><span data-stu-id="9f66a-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="9f66a-330">Para o Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="9f66a-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="9f66a-331">Para o Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="9f66a-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="9f66a-332">Extraia o driver e o firmware baixados.</span><span class="sxs-lookup"><span data-stu-id="9f66a-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="9f66a-333">Abra uma janela do Prompt de Comando e, no prompt de comando, insira um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="9f66a-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="9f66a-334">No console do Configuration Manager, vá para **Drivers** de Sistemas Operacionais da Biblioteca de Software e selecione \>  \>  **Import Driver.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="9f66a-335">Selecione Importar todos os drivers no seguinte caminho de rede **(UNC),** selecione a pasta de origem (por exemplo, C: _Sources Drivers Surface Pro) e selecione \\ \\ \\ **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="9f66a-336">Na página **Especificar os detalhes** para os drivers importados, selecione todos os drivers listados e, em seguida, selecione Habilitar esses drivers e permitir que os computadores os **instalem.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="9f66a-337">Selecione **Categorias,** crie uma nova categoria que corresponde ao modelo do Surface, selecione **OK** e, em seguida, selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="9f66a-338">Selecione **Novo Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="9f66a-339">Especifique o nome do pacote que corresponde ao modelo do Surface Pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver, selecione **OK** e, em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="9f66a-340">Na página **de imagens de inicialização,** certifique-se de que nenhuma imagem de inicialização está selecionada e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="9f66a-341">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-341">Select **Close**.</span></span>

11. <span data-ttu-id="9f66a-342">Vá para **Drivers de** Sistemas Operacionais da Biblioteca de Software, selecione Pasta Criar Pasta e insira um nome de pasta que corresponde ao modelo do Surface Pro para o qual você acabou de \>  \> importar os **\>** drivers.</span><span class="sxs-lookup"><span data-stu-id="9f66a-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="9f66a-343">Mova todos os drivers importados para a pasta recém-criada para facilitar a navegação e a operação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="9f66a-344">Repita as mesmas etapas para outros modelos do Surface Pro que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="9f66a-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="9f66a-345">Para obter mais informações, consulte [Gerenciar drivers no Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)</span><span class="sxs-lookup"><span data-stu-id="9f66a-345">For more information, see [Manage drivers in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="9f66a-346">Criar pacote de configuração de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f66a-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="9f66a-347">No console do Configuration Manager, vá para Pacotes de Gerenciamento de Aplicativos da Biblioteca de **Software** e \>  \> selecione **Criar Pacote.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="9f66a-348">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="9f66a-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="9f66a-349">Nome: **SRS v2 – Configurar Pacote de Configuração do SRS**</span><span class="sxs-lookup"><span data-stu-id="9f66a-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="9f66a-350">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="9f66a-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="9f66a-351">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="9f66a-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="9f66a-352">Marque a **caixa de** seleção Este pacote contém arquivos de origem, insira o caminho para a pasta **SRS v2 –** Configurar Configuração do SRS e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="9f66a-353">Selecione **Não criar um programa e,** em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="9f66a-354">Revise a **página Confirmar as configurações** e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="9f66a-355">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="9f66a-356">Distribuir pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f66a-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="9f66a-357">Todos os pacotes devem ser distribuídos para os servidores que tenham sido atribuídos a função de ponto de distribuição na hierarquia do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="9f66a-358">Siga as instruções abaixo para iniciar a distribuição de pacotes.</span><span class="sxs-lookup"><span data-stu-id="9f66a-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="9f66a-359">Distribuir pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="9f66a-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="9f66a-360">No console do Configuration Manager, vá para Pacotes de Gerenciamento de **Aplicativos da** Biblioteca \> **de** \> Software.</span><span class="sxs-lookup"><span data-stu-id="9f66a-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="9f66a-361">Selecione todos os pacotes de software que você deseja distribuir e selecione **Distribuir Conteúdo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="9f66a-362">Revise a lista de pacotes e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="9f66a-363">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="9f66a-364">Selecione **Próximo** e, em seguida, **selecione Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="9f66a-365">Distribuir pacotes de driver.</span><span class="sxs-lookup"><span data-stu-id="9f66a-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="9f66a-366">No console do Configuration Manager, vá para Pacotes de **Driver** de Sistemas \> **Operacionais da** Biblioteca de \> Software.</span><span class="sxs-lookup"><span data-stu-id="9f66a-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="9f66a-367">Selecione todos os pacotes de driver que você deseja distribuir e selecione **Distribuir Conteúdo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="9f66a-368">Revise a lista de pacotes e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="9f66a-369">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="9f66a-370">Selecione **Próximo** e, em seguida, **selecione Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="9f66a-371">Distribuir pacotes do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9f66a-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="9f66a-372">No console do Configuration Manager, vá para **Imagens** do Sistema Operacional da Biblioteca de \>  \> Software.</span><span class="sxs-lookup"><span data-stu-id="9f66a-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="9f66a-373">Selecione todas as imagens do sistema operacional que você deseja distribuir e selecione **Distribuir Conteúdo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="9f66a-374">Revise a lista de pacotes e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="9f66a-375">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="9f66a-376">Selecione **Próximo** e, em seguida, **selecione Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="9f66a-377">A distribuição de pacotes pode levar algum tempo, dependendo do tamanho do pacote, da hierarquia do Configuration Manager, do número de servidores de pontos de distribuição e da largura de banda disponível na rede.</span><span class="sxs-lookup"><span data-stu-id="9f66a-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="9f66a-378">Todos os pacotes devem ser distribuídos antes que você possa começar a implantar uma unidade de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="9f66a-379">Você pode revisar o status da distribuição do pacote no console do Configuration Manager, indo para **Monitorar o** Status de Conteúdo do \>  \> **Status de Distribuição.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="9f66a-380">Sequências de tarefas do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f66a-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="9f66a-381">Use sequências de tarefas com o Configuration Manager para automatizar as etapas de implantação de uma imagem do sistema operacional em um computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9f66a-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="9f66a-382">Para implantar uma unidade de Salas do Microsoft Teams de forma automatizada, crie uma sequência de tarefas que faz referência à imagem de inicialização usada para iniciar o computador de destino salas do Microsoft Teams, a imagem do sistema operacional Windows 10 Enterprise que você deseja instalar e qualquer outro conteúdo adicional, como outros aplicativos ou atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="9f66a-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="9f66a-383">Importar a sequência de tarefas de exemplo</span><span class="sxs-lookup"><span data-stu-id="9f66a-383">Import the sample task sequence</span></span>

<span data-ttu-id="9f66a-384">Você pode baixar e importar facilmente uma sequência de tarefas de exemplo e personalizá-la para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="9f66a-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="9f66a-385">[**Baixe**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) a sequência de tarefas de exemplo e copie o arquivo zip baixado para um local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="9f66a-386">No console do Gerenciador de Configurações, vá para **Sequências** de Tarefas de Sistemas Operacionais da Biblioteca de Software e \>  \> selecione **Importar Sequência de Tarefas.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="9f66a-387">Selecione **Procurar,** vá para o local da pasta compartilhada que você usou na etapa 1, selecione o arquivo **ZIP (Implantação** de Salas do Microsoft Teams) e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="9f66a-388">De **configurar a** ação para criar **novo** e, em seguida, selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="9f66a-389">Confirme as configurações e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="9f66a-390">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="9f66a-391">Valide se os pacotes de referência estão corretamente vinculados a cada etapa da sequência de tarefas.</span><span class="sxs-lookup"><span data-stu-id="9f66a-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="9f66a-392">Selecione a sequência de tarefas importada e, em seguida, selecione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="9f66a-393">O Editor de Sequência de Tarefas é aberto e exibe cada etapa sequencial que você precisa para implantar e configurar uma unidade de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="9f66a-394">Ande por cada etapa e conclua as atualizações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="9f66a-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="9f66a-395">**Reinicie no Windows PE:** esta etapa reinicia e, em seguida, inicializa o computador no PXE do Windows.</span><span class="sxs-lookup"><span data-stu-id="9f66a-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="9f66a-396">Nenhuma alteração é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="9f66a-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="9f66a-397">**Disco de Partição 0 – UEFI:** esta etapa apaga a configuração de disco e cria partições com base nas configurações configuradas.</span><span class="sxs-lookup"><span data-stu-id="9f66a-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="9f66a-398">Recomendamos que você não faça alterações nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="9f66a-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="9f66a-399">Definir o Nome do Computador **SRS:** esta etapa inclui um aplicativo HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade salas do Microsoft Teams durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="9f66a-400">Essa é uma etapa opcional, mas só pode ser desabilitada se você quiser gerenciar a nomeação do computador por meio de um processo alternativo.</span><span class="sxs-lookup"><span data-stu-id="9f66a-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="9f66a-401">Verifique se o **pacote SRS v2 - Set-SRSComputerName** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="9f66a-402">Se não estiver, navegue até o pacote e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="9f66a-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="9f66a-403">**Aplicar Sistema Operacional:** esta etapa especifica a imagem do sistema operacional a ser implantada e o arquivo de resposta Sysprep autônoma a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="9f66a-404">Verifique se o arquivo de imagem correto do sistema operacional Windows 10 Enterprise está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="9f66a-405">Verifique se o recurso Usar um arquivo de resposta desacompanhado ou **Sysprep** para uma instalação personalizada está habilitado e se o **Pacote SRS v2 – Sysprep** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="9f66a-406">Verifique também se **o Nome do Arquivo** está definido como **unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="9f66a-407">**Aplicar Configurações do Windows:** esta etapa coleta informações sobre a instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9f66a-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="9f66a-408">Forneça informações de licenciamento e registro, incluindo a chave do produto, a senha da conta do administrador local e o fuso horário (dependendo das suas necessidades).</span><span class="sxs-lookup"><span data-stu-id="9f66a-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="9f66a-409">**Aplicar Configurações de Rede:** esta etapa permite especificar um grupo de trabalho ou nome de domínio do Active Directory e uma unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="9f66a-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="9f66a-410">Consulte [as considerações](domain-joining-considerations.md) de junção do domínio do Sistema de Salas do Skype para as ações recomendadas que você precisa tomar na implantação de unidades de Salas do Microsoft Teams como membros de um domínio do Actve Directory.</span><span class="sxs-lookup"><span data-stu-id="9f66a-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="9f66a-411">**Aplicar drivers:** Esta etapa e suas sub-etapas são usadas para implantar drivers de dispositivo e firmware aplicáveis com base no modelo do Surface Pro que você tem.</span><span class="sxs-lookup"><span data-stu-id="9f66a-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="9f66a-412">Atualize cada etapa para especificar o pacote de driver relevante associado a essa implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="9f66a-413">Cada pacote de driver está configurado para aproveitar os filtros WMI (Instrumento de Gerenciamento do Windows) para implantar drivers e firmware relevantes com base na make e no modelo do Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="9f66a-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="9f66a-414">É altamente recomendável que você não altere a configuração desses drivers, caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="9f66a-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="9f66a-415">**Configurar o Windows e o Configuration Manager:** esta etapa implanta e configura o cliente do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="9f66a-416">Atualize esta etapa para especificar o Pacote de Clientes do Configuration Manager integrado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="9f66a-417">**Instalar Certificado Raiz:** esta etapa distribui o certificado raiz para dispositivos que não ingressaram no domínio e, portanto, é opcional e desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="9f66a-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="9f66a-418">Habilita esta etapa se precisar implantar um certificado raiz para as unidades de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="9f66a-419">Se você precisar executar esta etapa, verifique se o **SRS v2 –** Pacote de Certificado Raiz e Desabilitar o redirecionamento do sistema de arquivos de **64** bits está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="9f66a-420">**Instalar e configurar** o Agente de Monitoramento: esta etapa instala a versão de 64 bits do agente do Monitor do Microsoft Azure e configura o agente para se conectar ao seu espaço de trabalho do Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="9f66a-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="9f66a-421">Esta etapa está desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="9f66a-421">This step is disabled by default.</span></span> <span data-ttu-id="9f66a-422">Habilita esta etapa somente se você estiver indo usar o Agente de Monitoramento para monitorar a saúde das suas unidades de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="9f66a-423">Edite esta etapa e atualize os parâmetros de linha de comando para especificar sua **ID** do Espaço de Trabalho e **a Tecla de Espaço de Trabalho.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="9f66a-424">Consulte Configurar dispositivos de teste para [Monitoramento do Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obter mais informações sobre como obter a ID do Espaço de Trabalho do Pacote de Gerenciamento de Operações e a chave primária.</span><span class="sxs-lookup"><span data-stu-id="9f66a-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="9f66a-425">Verifique se o **SRS v2 – Pacote do Agente de Monitoramento** da Microsoft e Desabilitar o redirecionamento do sistema de arquivos de **64** bits está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="9f66a-426">Para saber mais sobre como monitorar a saúde da sua implantação de Salas do Microsoft Teams, consulte Planejar o gerenciamento de Salas do Microsoft Teams com o [Monitor do Azure,](azure-monitor-plan.md)implantar o gerenciamento de salas do Microsoft Teams com o [Monitor do Azure](azure-monitor-deploy.md) e gerenciar dispositivos de salas do Microsoft Teams com o [Monitor do Azure.](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="9f66a-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="9f66a-427">**Copiar arquivos de configuração SRS v2:** esta etapa copia os arquivos de configuração e configuração necessários do kit de implantação de Salas do Microsoft Teams para o disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="9f66a-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="9f66a-428">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="9f66a-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="9f66a-429">Verifique se o **pacote de aplicativos SRS v2 – SRS e** Desabilitar o redirecionamento do sistema de arquivos de **64** bits está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="9f66a-430">**Install-SRSv2-OS-Updates:** esta etapa implanta todas as atualizações obrigatórias do sistema operacional necessárias com a implantação de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="9f66a-431">Siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="9f66a-431">Do the following:</span></span>
       -   <span data-ttu-id="9f66a-432">Marque [Configurar um console de Salas do Microsoft Teams](console.md) para ver quais atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="9f66a-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="9f66a-433">Verifique se o pacote de atualizações do **SRS v2 – OS** inclui todas as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="9f66a-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="9f66a-434">Verifique se o **SRS v2 – Pacote de Atualizações do SISTEMA** OPERACIONAL está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="9f66a-435">Verifique se a política de execução do PowerShell está definida como **Ignorar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="9f66a-436">**Reiniciar Computador:** esta etapa reinicia o computador depois que as atualizações obrigatórias do sistema operacional são instaladas.</span><span class="sxs-lookup"><span data-stu-id="9f66a-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="9f66a-437">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="9f66a-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="9f66a-438">**Configure os Componentes do Windows:** esta etapa configura os recursos necessários do Windows.</span><span class="sxs-lookup"><span data-stu-id="9f66a-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="9f66a-439">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="9f66a-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="9f66a-440">**Reiniciar Computador:** esta etapa reinicia o computador depois que os recursos do Windows estão configurados.</span><span class="sxs-lookup"><span data-stu-id="9f66a-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="9f66a-441">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="9f66a-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="9f66a-442">**Adicionar Usuário Local do Skype:** esta etapa cria a conta local do Skype usada para entrar automaticamente no Windows e iniciar o aplicativo Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="9f66a-443">Esta etapa não tem nenhum pacote de software associado a ele e nenhuma personalização é necessária para ele.</span><span class="sxs-lookup"><span data-stu-id="9f66a-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="9f66a-444">Configurar e configurar o aplicativo **SRS:** esta etapa configura a instalação do aplicativo Salas do Microsoft Teams para a próxima inicialização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9f66a-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="9f66a-445">Verifique se o **SRS v2 – Configurar** Pacote de Configuração do SRS e Desabilitar o redirecionamento do sistema de arquivos de **64** bits está selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f66a-446">É muito importante que as etapas da sequência de tarefas devem estar na ordem fornecida.</span><span class="sxs-lookup"><span data-stu-id="9f66a-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="9f66a-447">Modificar a ordem das etapas ou configurar etapas adicionais pode quebrar a implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="9f66a-448">**Configurar e configurar a etapa do aplicativo SRS** deve ser a última etapa na sequência de tarefas, caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="9f66a-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="9f66a-449">Criar implantação para a sequência de tarefas</span><span class="sxs-lookup"><span data-stu-id="9f66a-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="9f66a-450">Selecione a sequência de tarefas e, em seguida, **selecione Implantar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="9f66a-451">Selecione **Procurar** para selecionar o conjunto de destinos para implantação.</span><span class="sxs-lookup"><span data-stu-id="9f66a-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="9f66a-452">Selecione **Todos os Computadores Desconhecidos** e, em seguida, **selecione OK.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="9f66a-453">Selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-453">Select **Next**.</span></span>

5. <span data-ttu-id="9f66a-454">Selecione **Disponível** na **listada** Finalidade.</span><span class="sxs-lookup"><span data-stu-id="9f66a-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="9f66a-455">Selecione **Somente Mídia e PXE** na lista Disponibilizar para a lista **a** seguir e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="9f66a-456">É muito importante que **a Finalidade** seja definida **como Disponível.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="9f66a-457">Certifique-se de **que a Finalidade** NÃO **está** definida **como Obrigatório.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="9f66a-458">Além disso, certifique-se de selecionar **Somente Mídia e PXE** **na opção Disponibilizar para o seguinte.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="9f66a-459">Definir esses valores para algo diferente pode fazer com que todos os computadores recebam a imagem de implantação de Salas do Microsoft Teams quando inicializadas.</span><span class="sxs-lookup"><span data-stu-id="9f66a-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="9f66a-460">Não especifique nenhum cronograma e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="9f66a-461">Não altere nada na seção Experiência do **Usuário** e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="9f66a-462">Não altere nada na seção **Alertas** e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="9f66a-463">Não altere nada na seção Pontos **de Distribuição** e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="9f66a-464">Confirme as configurações e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="9f66a-465">Selecione **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="9f66a-466">Validar e solucionar problemas da solução</span><span class="sxs-lookup"><span data-stu-id="9f66a-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="9f66a-467">Depois de concluir as sequências de tarefas do Microsoft Endpoint Configuration Manager, você precisará executar uma execução de teste para validar se a sequência de tarefas pode implantar e configurar unidades de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="9f66a-468">Conecte o dispositivo de teste à rede com fio usando um dos adaptadores Ethernet com suporte ou usando o Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="9f66a-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="9f66a-469">Se a funcionalidade de inicialização PXE não tiver sido configurada para seu [](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) ambiente, você poderá usar a imagem de inicialização na unidade flash USB que você criou anteriormente para inicializar a partir de USB e conectar-se ao Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="9f66a-470">Acesse o firmware e inicie a inicialização PXE:</span><span class="sxs-lookup"><span data-stu-id="9f66a-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="9f66a-471">Verifique se o dispositivo Surface está desligado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="9f66a-472">Pressione e segure o **botão Aumentar** Volume.</span><span class="sxs-lookup"><span data-stu-id="9f66a-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="9f66a-473">Pressione e solte o **botão** Ligar/Desligar.</span><span class="sxs-lookup"><span data-stu-id="9f66a-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="9f66a-474">Depois que o dispositivo começar a inicializar, solte o **botão Aumentar** Volume.</span><span class="sxs-lookup"><span data-stu-id="9f66a-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="9f66a-475">Selecione **Configuração de inicialização.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="9f66a-476">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9f66a-476">Do one of the following:</span></span>

        -   <span data-ttu-id="9f66a-477">Selecione **a inicialização PXE** e arraste-a para a parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="9f66a-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="9f66a-478">Como alternativa, você pode deslizar o dedo para a esquerda no adaptador de rede para inicializar o dispositivo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9f66a-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="9f66a-479">Isso não afetará a ordem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="9f66a-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="9f66a-480">Selecione a unidade flash USB que contém a mídia de inicialização.</span><span class="sxs-lookup"><span data-stu-id="9f66a-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="9f66a-481">Selecione **Sair** e, em seguida, selecione **Reiniciar Agora.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="9f66a-482">Quando solicitado, selecione **Enter para o** serviço de inicialização de rede.</span><span class="sxs-lookup"><span data-stu-id="9f66a-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="9f66a-483">O Windows PE será carregado na memória, e o Assistente de Sequência de Tarefas será iniciar.</span><span class="sxs-lookup"><span data-stu-id="9f66a-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="9f66a-484">Selecione **Próximo** para continuar.</span><span class="sxs-lookup"><span data-stu-id="9f66a-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="9f66a-485">Selecione a sequência de tarefas que você importou anteriormente e selecione **Próxima.**</span><span class="sxs-lookup"><span data-stu-id="9f66a-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="9f66a-486">Depois que a configuração de disco for aplicada, você será solicitado a especificar um nome de computador para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9f66a-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="9f66a-487">A interface do usuário exibirá um nome de computador recomendado com base no número de série do dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="9f66a-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="9f66a-488">Você pode aceitar o nome proposto ou especificar um novo.</span><span class="sxs-lookup"><span data-stu-id="9f66a-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="9f66a-489">Siga as instruções na tela de atribuição de nome de computador.</span><span class="sxs-lookup"><span data-stu-id="9f66a-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="9f66a-490">Quando você seleciona **Aceitar,** a implantação começa.</span><span class="sxs-lookup"><span data-stu-id="9f66a-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="9f66a-491">O restante do processo de implantação é automático e não solicita mais nenhuma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="9f66a-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="9f66a-492">Depois que a sequência de tarefas de implantação terminar de configurar o dispositivo, você verá a seguinte tela de configuração que solicita que você configure as configurações do aplicativo Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f66a-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Tela de configuração inicial do aplicativo Salas do Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="9f66a-494">Conecte o Surface Pro ao console salas do Microsoft Teams e configure as configurações do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9f66a-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="9f66a-495">Valide se os recursos listados [nas Salas do Microsoft Teams estão](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funcionando no dispositivo implantado.</span><span class="sxs-lookup"><span data-stu-id="9f66a-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="9f66a-496">Para solucionar problemas de falha na instalação, verifique o **arquivo SMSTS.log,** que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="9f66a-497">O arquivo SMSTS.log é armazenado em um de vários caminhos, dependendo do estágio do processo de com build.</span><span class="sxs-lookup"><span data-stu-id="9f66a-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="9f66a-498">Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="9f66a-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="9f66a-499">**Fase de implantação**</span><span class="sxs-lookup"><span data-stu-id="9f66a-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="9f66a-500">**Caminho de log de sequência de tarefas**</span><span class="sxs-lookup"><span data-stu-id="9f66a-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="9f66a-501">WinPE, antes do formato HDD</span><span class="sxs-lookup"><span data-stu-id="9f66a-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="9f66a-502">X: \\ \\ \\ Smstslog \\ smsts.log do Windows Temp</span><span class="sxs-lookup"><span data-stu-id="9f66a-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="9f66a-503">WinPE, após o formato HDD</span><span class="sxs-lookup"><span data-stu-id="9f66a-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="9f66a-504">C: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="9f66a-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="9f66a-505">Sistema operacional implantado, antes de o agente do Gerenciador de Configuração ser instalado</span><span class="sxs-lookup"><span data-stu-id="9f66a-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="9f66a-506">c: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="9f66a-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="9f66a-507">Sistema operacional e o agente do Gerenciador de Configuração implantado</span><span class="sxs-lookup"><span data-stu-id="9f66a-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="9f66a-508">%windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="9f66a-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="9f66a-509">Execução de sequência de tarefas concluída</span><span class="sxs-lookup"><span data-stu-id="9f66a-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="9f66a-510">%windir% \\ System32 \\ ccm \\ logs \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="9f66a-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="9f66a-511">Você pode selecionar **F8 a** qualquer momento durante a sequência de tarefas para abrir um console de comando e obter acesso ao arquivo SMSTS.log.</span><span class="sxs-lookup"><span data-stu-id="9f66a-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="9f66a-512">Para solucionar problemas de inicialização PXE, verifique os dois arquivos de log no servidor Configuration Manager específicos para ações PXE:</span><span class="sxs-lookup"><span data-stu-id="9f66a-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="9f66a-513">**Pxecontrol.log, localizado** no diretório de logs de instalação do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f66a-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="9f66a-514">**Smspxe.log, localizado** no diretório de logs do Ponto de Gerenciamento do Gerenciador de Configuração (MP)</span><span class="sxs-lookup"><span data-stu-id="9f66a-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="9f66a-515">Para ver uma lista completa dos arquivos de log que você pode usar para solucionar mais problemas de sua instalação do Configuration Manager, consulte a referência de arquivo de [log](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)do Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f66a-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files).</span></span>
