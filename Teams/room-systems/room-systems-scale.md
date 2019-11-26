---
title: Implantar salas do Microsoft Teams usando o System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Leia este tópico para saber mais sobre a implantação de salas do Microsoft Teams em implantações em grandes escalas.
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
ms.openlocfilehash: d116ea000bc18bf0e9c017b67bfa104dcfa29795
ms.sourcegitcommit: 000957709b841ce55a6813ccc2fbe745b1a9295b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "39218028"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a><span data-ttu-id="f6371-103">Implantar salas do Microsoft Teams usando o System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-103">Deploy Microsoft Teams Rooms by using System Center Configuration Manager</span></span>

<span data-ttu-id="f6371-104">Este artigo fornece todas as informações necessárias para criar suas implantações de salas do Microsoft Teams usando o System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="f6371-105">Com os métodos fáceis de usar fornecidos pelo System Center Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="f6371-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="f6371-106">Use a abordagem ilustrada abaixo para orientá-lo na configuração do Configuration Manager e personalize os exemplos de pacotes e scripts fornecidos nesta orientação, conforme necessário para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6371-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processo de implantação de salas do Microsoft Teams usando o Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="f6371-108">Esta solução foi testada apenas com implantações baseadas em Surface pro.</span><span class="sxs-lookup"><span data-stu-id="f6371-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="f6371-109">Siga as diretrizes do fabricante para configurações que não se baseiam no Surface pro.</span><span class="sxs-lookup"><span data-stu-id="f6371-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="f6371-110">Validar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f6371-110">Validate prerequisites</span></span>

<span data-ttu-id="f6371-111">Para implantar salas do Microsoft Teams com o Configuration Manager, verifique se você atende aos seguintes pré-requisitos e requisitos.</span><span class="sxs-lookup"><span data-stu-id="f6371-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="f6371-112">Requisitos do System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="f6371-113">A versão do System Center Configuration Manager deve ser pelo menos 1706 ou superior.</span><span class="sxs-lookup"><span data-stu-id="f6371-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="f6371-114">Recomendamos usar o 1710 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f6371-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="f6371-115">Consulte o [suporte do Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões do Windows 10 compatíveis com o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="f6371-116">É preciso instalar uma versão com suporte do kit de avaliação e implantação do Windows (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f6371-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="f6371-117">Veja as versões do [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com versões diferentes do Configuration Manager e certifique-se de que sua implantação inclui a versão correta.</span><span class="sxs-lookup"><span data-stu-id="f6371-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="f6371-118">Os servidores de sistema de site devem ter sido atribuídos à função de ponto de distribuição, e as imagens de inicialização devem ser habilitadas para [suporte a PXE (ambiente de execução Preboot)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) para habilitar implantações iniciadas pela rede.</span><span class="sxs-lookup"><span data-stu-id="f6371-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="f6371-119">Se o suporte a PXE não estiver habilitado, você poderá usar [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.</span><span class="sxs-lookup"><span data-stu-id="f6371-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="f6371-120">Uma conta de acesso à rede deve ser configurada para dar suporte a novos cenários de implantação de computador (bare metal).</span><span class="sxs-lookup"><span data-stu-id="f6371-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="f6371-121">Para saber mais sobre a configuração de uma conta de acesso à rede, consulte [gerenciar contas para acessar conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="f6371-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="f6371-122">Recomendamos que você habilite o [suporte ao multicast](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se provavelmente você vai implantar a mesma imagem de salas do Microsoft Teams em várias unidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f6371-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="f6371-123">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="f6371-123">Networking requirements</span></span>

-   <span data-ttu-id="f6371-124">Sua rede deve ter um servidor DHCP (protocolo de configuração dinâmica de hosts), configurado para distribuição automática de endereços IP para as sub-redes nas quais as unidades de sala do Microsoft Teams serão implantadas.</span><span class="sxs-lookup"><span data-stu-id="f6371-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6371-125">A duração da concessão DHCP deve ser definida como um valor maior que a duração da implantação da imagem.</span><span class="sxs-lookup"><span data-stu-id="f6371-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="f6371-126">Caso contrário, a implantação poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="f6371-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="f6371-127">Sua rede, incluindo opções e LANs virtuais (VLANs), devem ser configuradas para dar suporte ao PXE.</span><span class="sxs-lookup"><span data-stu-id="f6371-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="f6371-128">Consulte o fornecedor da sua rede para obter mais informações sobre o auxiliar de IP e a configuração PXE.</span><span class="sxs-lookup"><span data-stu-id="f6371-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="f6371-129">Você também pode usar [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte a PXE não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="f6371-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6371-130">Para dispositivos Surface pro, inicializar a partir da rede (inicialização PXE) só tem suporte quando você usa um adaptador Ethernet ou uma docking Station da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f6371-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="f6371-131">Adaptadores Ethernet de terceiros não dão suporte à inicialização PXE com Surface pro.</span><span class="sxs-lookup"><span data-stu-id="f6371-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="f6371-132">Consulte [adaptadores Ethernet e implantação de superfície](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f6371-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="f6371-133">Configurar o System Center Configuration Manager para implantação de sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f6371-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="f6371-134">Este artigo pressupõe que você já tenha uma implantação íntegra do System Center Configuration Manager e não detalha todas as etapas necessárias para implantar e configurar o Configuration Manager do zero.</span><span class="sxs-lookup"><span data-stu-id="f6371-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="f6371-135">A [documentação e as diretrizes de configuração](https://docs.microsoft.com/sccm/) do System Center Configuration Manager são um recurso excelente; Recomendamos que você comece com esses recursos se ainda não tiver implantado o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="f6371-136">Use as instruções a seguir para verificar se os recursos de implantação do sistema operacional (OSD) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="f6371-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="f6371-137">Validar e atualizar o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="f6371-138">No console do Configuration Manager, acesse \*\*\*\* \> **atualizações e serviços**de administração.</span><span class="sxs-lookup"><span data-stu-id="f6371-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="f6371-139">Verifique a compilação instalada e as atualizações aplicáveis que ainda não foram instaladas.</span><span class="sxs-lookup"><span data-stu-id="f6371-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="f6371-140">Revisar o [suporte para Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Se precisar atualizar a implantação, selecione a atualização que você deseja instalar e, em seguida, selecione **baixar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="f6371-141">Após a conclusão do download, selecione a atualização e, em seguida, selecione **instalar pacote de atualização**.</span><span class="sxs-lookup"><span data-stu-id="f6371-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="f6371-142">Configurar pontos de distribuição para dar suporte a PXE e multicast</span><span class="sxs-lookup"><span data-stu-id="f6371-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="f6371-143">No console do Configuration Manager, vá para os **pontos de distribuição**de **Administração** \> .</span><span class="sxs-lookup"><span data-stu-id="f6371-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="f6371-144">Selecione o servidor de ponto de distribuição que servirá a implantação de salas do Microsoft Teams e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f6371-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="f6371-145">Selecione a guia **PXE** e verifique se as seguintes configurações estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="f6371-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="f6371-146">Habilitar o suporte a PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="f6371-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="f6371-147">Permitir que este ponto de distribuição responda a solicitações PXE recebidas</span><span class="sxs-lookup"><span data-stu-id="f6371-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="f6371-148">Habilitar o suporte a computador desconhecido</span><span class="sxs-lookup"><span data-stu-id="f6371-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="f6371-149">*Opcional:* Para habilitar o suporte ao multicast, selecione a guia **multicast** e verifique se as seguintes configurações estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="f6371-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="f6371-150">Habilitar a multicast para enviar dados simultaneamente para vários clientes</span><span class="sxs-lookup"><span data-stu-id="f6371-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="f6371-151">Configurar o intervalo de portas UDP de acordo com a recomendação de sua equipe de rede</span><span class="sxs-lookup"><span data-stu-id="f6371-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="f6371-152">Configurar a conta de acesso à rede</span><span class="sxs-lookup"><span data-stu-id="f6371-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="f6371-153">No console do Configuration Manager, vá para **sites**de **configuração** \> de site de **Administração** \> e selecione o site.</span><span class="sxs-lookup"><span data-stu-id="f6371-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="f6371-154">No grupo **configurações** , selecione **Configurar** \> **distribuição de software**dos componentes do site.</span><span class="sxs-lookup"><span data-stu-id="f6371-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="f6371-155">Selecione a guia **conta de acesso à rede** . configurar uma ou mais contas e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6371-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="f6371-156">As contas não precisam de direitos especiais, exceto para o direito **acesso a este computador pela rede** no servidor de ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f6371-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="f6371-157">Uma conta de usuário de domínio genérico será apropriada.</span><span class="sxs-lookup"><span data-stu-id="f6371-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="f6371-158">Para obter mais informações, consulte [gerenciar contas para acessar conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="f6371-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="f6371-159">Configurar uma imagem de inicialização</span><span class="sxs-lookup"><span data-stu-id="f6371-159">Configure a boot image</span></span>

1.  <span data-ttu-id="f6371-160">No console do Configuration Manager, vá para **imagens de inicialização**do **sistema** \> operacional da **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="f6371-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="f6371-161">Selecione **imagem de inicialização (x64)** e, em seguida, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f6371-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="f6371-162">Selecione a guia **fonte de dados** e habilite **implantar esta imagem de inicialização do ponto de distribuição habilitado para PXE**.</span><span class="sxs-lookup"><span data-stu-id="f6371-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="f6371-163">Selecione a guia **componentes opcionais** para instalar componentes obrigatórios:</span><span class="sxs-lookup"><span data-stu-id="f6371-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="f6371-164">Selecione o ícone estrela e procure por **HTML (WinPE-HTA)**</span><span class="sxs-lookup"><span data-stu-id="f6371-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="f6371-165">Selecione **OK** para adicionar suporte a aplicativo HTML à imagem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="f6371-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="f6371-166">*Opcional:* Para personalizar a experiência de implantação, selecione a guia **personalização** .</span><span class="sxs-lookup"><span data-stu-id="f6371-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="f6371-167">Habilite o **suporte a comandos (somente teste)** se você quiser ter acesso a um prompt de comando durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="f6371-168">Quando essa opção estiver habilitada, você poderá iniciar um prompt de comando selecionando **F8** a qualquer momento durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="f6371-169">Você também pode especificar uma imagem de tela de fundo personalizada a ser exibida durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="f6371-170">Para definir uma imagem, habilite **especificar o arquivo de imagem de tela de fundo personalizada (caminho UNC** e selecione seu plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="f6371-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="f6371-171">Quando for solicitado, selecione **Sim** e distribua a imagem de inicialização atualizada para seus pontos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f6371-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="f6371-172">Para obter mais informações, consulte [gerenciar imagens de inicialização com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="f6371-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="f6371-173">Você pode criar uma mídia USB inicializável para iniciar implantações baseadas em sequência de tarefas do Configuration Manager em ambientes com suporte a PXE.</span><span class="sxs-lookup"><span data-stu-id="f6371-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="f6371-174">A mídia inicializável contém apenas a imagem de inicialização, os comandos prestart opcionais e os arquivos necessários e os binários do Configuration Manager para dar suporte à inicialização no Windows PE e à conexão com o Configuration Manager para o restante do processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="f6371-175">Para obter mais informações, consulte [como criar mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="f6371-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="f6371-176">Criar pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6371-177">A versão do sistema operacional necessária para cada versão do instalador do SRS muda a cada lançamento do MSI.</span><span class="sxs-lookup"><span data-stu-id="f6371-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="f6371-178">Para determinar a melhor versão do sistema operacional para um determinado MSI, execute o script de configuração do console uma vez.</span><span class="sxs-lookup"><span data-stu-id="f6371-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="f6371-179">Para saber mais, consulte [implantar salas do Microsoft Teams usando o System Center Configuration Manager](room-systems-scale.md).</span><span class="sxs-lookup"><span data-stu-id="f6371-179">To learn more, see [Deploy Microsoft Teams Rooms by using System Center Configuration Manager](room-systems-scale.md).</span></span>

<span data-ttu-id="f6371-180">O Configuration Manager requer um número de pacotes para implantar e configurar as unidades de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="f6371-181">Você precisa criar e configurar os seguintes pacotes e, em seguida, distribuí-los aos sistemas de site do Configuration Manager que receberam a função de servidor de ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f6371-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="f6371-182">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="f6371-182">**Package name**</span></span>                     | <span data-ttu-id="f6371-183">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f6371-183">**Type**</span></span>               | <span data-ttu-id="f6371-184">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f6371-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="f6371-185">SRS v2-pacote de aplicativo SRS</span><span class="sxs-lookup"><span data-stu-id="f6371-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="f6371-186">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-186">Software package</span></span>       | <span data-ttu-id="f6371-187">Pacote para o kit de implantação de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6371-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="f6371-188">SRS v2-pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="f6371-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="f6371-189">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-189">Software package</span></span>       | <span data-ttu-id="f6371-190">Pacote para o arquivo Unattended. xml personalizado para configurar as unidades de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6371-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="f6371-191">Pacote SRS v2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="f6371-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="f6371-192">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-192">Software package</span></span>       | <span data-ttu-id="f6371-193">Pacote para o aplicativo HTML (HTA) atribuir um nome de computador durante a implantação</span><span class="sxs-lookup"><span data-stu-id="f6371-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="f6371-194">SRS v2-configurar a configuração do SRS</span><span class="sxs-lookup"><span data-stu-id="f6371-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="f6371-195">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-195">Software package</span></span>       | <span data-ttu-id="f6371-196">Pacote para configurar a implantação do aplicativo salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6371-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="f6371-197">SRS v2-pacote de atualizações do so</span><span class="sxs-lookup"><span data-stu-id="f6371-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="f6371-198">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-198">Software package</span></span>       | <span data-ttu-id="f6371-199">Pacote para implantar atualizações obrigatórias do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f6371-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="f6371-200">SRS v2-pacote de certificado raiz</span><span class="sxs-lookup"><span data-stu-id="f6371-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="f6371-201">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-201">Software package</span></span>       | <span data-ttu-id="f6371-202">Optional – pacote para implantar o certificado raiz (não obrigatório para unidades unidas pelo domínio)</span><span class="sxs-lookup"><span data-stu-id="f6371-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="f6371-203">SRS v2-pacote do Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="f6371-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="f6371-204">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-204">Software package</span></span>       | <span data-ttu-id="f6371-205">Optional-pacote para implantar e configurar o agente do Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="f6371-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="f6371-206">Pacote em segundo plano do SRS v2-WinPE</span><span class="sxs-lookup"><span data-stu-id="f6371-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="f6371-207">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="f6371-207">Software package</span></span>       | <span data-ttu-id="f6371-208">Pacote para a imagem de tela de fundo personalizada a ser usada com imagens de inicialização</span><span class="sxs-lookup"><span data-stu-id="f6371-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="f6371-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f6371-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="f6371-210">Imagem do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f6371-210">Operating system image</span></span> | <span data-ttu-id="f6371-211">Pacote para o arquivo de instalação do sistema operacional (install. wim)</span><span class="sxs-lookup"><span data-stu-id="f6371-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="f6371-212">Surface pro</span><span class="sxs-lookup"><span data-stu-id="f6371-212">Surface Pro</span></span>                          | <span data-ttu-id="f6371-213">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="f6371-213">Driver package</span></span>         | <span data-ttu-id="f6371-214">Pacote para drivers de dispositivo e firmware para Microsoft Surface pro</span><span class="sxs-lookup"><span data-stu-id="f6371-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="f6371-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="f6371-215">Surface Pro 4</span></span>                        | <span data-ttu-id="f6371-216">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="f6371-216">Driver package</span></span>         | <span data-ttu-id="f6371-217">Pacote para drivers de dispositivo e firmware para Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="f6371-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="f6371-218">Para obter mais informações, consulte [pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="f6371-218">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="f6371-219">Criar pastas para os arquivos de origem do pacote</span><span class="sxs-lookup"><span data-stu-id="f6371-219">Create folders for the package source files</span></span>

<span data-ttu-id="f6371-220">O Configuration Manager requer que os arquivos de origem do pacote sejam organizados em uma estrutura de pastas específica quando são criados pela primeira vez e quando são atualizados.</span><span class="sxs-lookup"><span data-stu-id="f6371-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="f6371-221">Crie a seguinte estrutura de pastas no site de administração central do System Center Configuration Manager ou no site primário ou em um compartilhamento de servidor que você está usando para hospedar arquivos de origem do pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-221">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="f6371-222">SRS v2-pacote do Microsoft Monitoring Agent</span><span class="sxs-lookup"><span data-stu-id="f6371-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="f6371-223">SRS v2-pacote de atualizações do so</span><span class="sxs-lookup"><span data-stu-id="f6371-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="f6371-224">SRS v2-pacote de certificado raiz</span><span class="sxs-lookup"><span data-stu-id="f6371-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="f6371-225">Pacote SRS v2-Set-SRSComputerName</span><span class="sxs-lookup"><span data-stu-id="f6371-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="f6371-226">SRS v2-pacote de aplicativo SRS</span><span class="sxs-lookup"><span data-stu-id="f6371-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="f6371-227">SRS v2-configurar a configuração do SRS</span><span class="sxs-lookup"><span data-stu-id="f6371-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="f6371-228">SRS v2-pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="f6371-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="f6371-229">Drivers</span><span class="sxs-lookup"><span data-stu-id="f6371-229">Drivers</span></span>
    -   <span data-ttu-id="f6371-230">Surface pro</span><span class="sxs-lookup"><span data-stu-id="f6371-230">Surface Pro</span></span>
    -   <span data-ttu-id="f6371-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="f6371-231">Surface Pro 4</span></span>
-   <span data-ttu-id="f6371-232">Sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="f6371-232">Operating Systems</span></span>
    -   <span data-ttu-id="f6371-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f6371-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="f6371-234">Você também pode [baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pastas para os pacotes, os scripts que você precisa usar e o modelo sequência de tarefas, que você precisa importar.</span><span class="sxs-lookup"><span data-stu-id="f6371-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="f6371-235">Criar o pacote do agente de monitoramento</span><span class="sxs-lookup"><span data-stu-id="f6371-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="f6371-236">Baixe o agente de monitoramento <https://go.microsoft.com/fwlink/?LinkId=828603>de.</span><span class="sxs-lookup"><span data-stu-id="f6371-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="f6371-237">Extraia o pacote para o **SRS v2-pasta do pacote do Microsoft Monitoring Agent** abrindo uma janela do prompt de comando e digitando **MMASetup-AMD64. exe/c:** no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="f6371-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="f6371-238">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="f6371-239">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="f6371-240">Nome<strong>: SRS v2-pacote do Microsoft Monitoring Agent</strong></span><span class="sxs-lookup"><span data-stu-id="f6371-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="f6371-241">Fabricante<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="f6371-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="f6371-242">Versão<strong>: 8.1.11081.0</strong> (Insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="f6371-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="f6371-243">Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta **SRS v2-Microsoft Monitoring Agent** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="f6371-244">Selecione não **criar um programa**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="f6371-245">Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="f6371-246">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="f6371-247">Criar o pacote de atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f6371-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="f6371-248">Na pasta do **pacote atualizações do SRS v2-so** , crie um novo script do PowerShell chamado **install-SRSv2-os-updates. ps1**.</span><span class="sxs-lookup"><span data-stu-id="f6371-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="f6371-249">Copie o script a seguir para o script **install-SRSv2-os-updates. ps1** .</span><span class="sxs-lookup"><span data-stu-id="f6371-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="f6371-250">Você também pode baixar o script Install-SRSv2-OS-Updates. ps1 [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f6371-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="f6371-251">Baixe os pacotes obrigatórios do Windows Update na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="f6371-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f6371-252">No momento em que este artigo foi publicado, apenas [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necessário.</span><span class="sxs-lookup"><span data-stu-id="f6371-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="f6371-253">Marque [configurar um console de salas do Microsoft Teams](console.md)para ver se outras atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="f6371-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="f6371-254">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="f6371-255">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="f6371-256">Nome: **SRS v2 – pacote de atualizações do so**</span><span class="sxs-lookup"><span data-stu-id="f6371-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="f6371-257">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f6371-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="f6371-258">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f6371-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="f6371-259">Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta do **pacote de atualizações do SRS v2-os** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="f6371-260">Selecione não **criar um programa**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="f6371-261">Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="f6371-262">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="f6371-263">Criar o pacote de certificado raiz (opcional)</span><span class="sxs-lookup"><span data-stu-id="f6371-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="f6371-264">Você cria esse pacote para distribuir o certificado raiz para dispositivos que não ingressam em um domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6371-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="f6371-265">Crie este pacote somente se ambas as condições a seguir forem aplicáveis:</span><span class="sxs-lookup"><span data-stu-id="f6371-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="f6371-266">Sua implantação inclui o Lync local ou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6371-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="f6371-267">As unidades de salas do Microsoft Teams são configuradas para funcionar em um grupo de trabalho em vez de um membro do domínio.</span><span class="sxs-lookup"><span data-stu-id="f6371-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="f6371-268">Copie o certificado raiz para a pasta **SRS v2 – pacote de certificado raiz** .</span><span class="sxs-lookup"><span data-stu-id="f6371-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="f6371-269">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="f6371-270">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="f6371-271">Nome: **SRS v2 – pacote de certificado raiz**</span><span class="sxs-lookup"><span data-stu-id="f6371-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="f6371-272">Fabricante: *o nome da sua organização*</span><span class="sxs-lookup"><span data-stu-id="f6371-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="f6371-273">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f6371-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="f6371-274">Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta **SRS v2 – pacote de certificado raiz** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="f6371-275">Selecione não **criar um programa**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="f6371-276">Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="f6371-277">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="f6371-278">Criar o pacote do kit de implantação de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6371-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="f6371-279">Baixe a versão mais recente <https://go.microsoft.com/fwlink/?linkid=851168>do **Kit de implantação de salas do Microsoft Teams** e instale-a em uma estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6371-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="f6371-280">Copie o conteúdo de **C:\\arquivos de programas (x86\\) kit de implantação do sistema de sala do Skype** para a pasta do **pacote de aplicativos SRS v2-SRS** .</span><span class="sxs-lookup"><span data-stu-id="f6371-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="f6371-281">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="f6371-282">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="f6371-283">Nome: **SRS v2 – pacote do aplicativo SRS**</span><span class="sxs-lookup"><span data-stu-id="f6371-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="f6371-284">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f6371-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="f6371-285">Versão: **3.1.104.0** (Insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="f6371-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="f6371-286">Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta do **pacote de aplicativos SRS v2 – SRS** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="f6371-287">Selecione não **criar um programa**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="f6371-288">Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="f6371-289">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="f6371-290">Criar o pacote de atribuição de nomes de computador</span><span class="sxs-lookup"><span data-stu-id="f6371-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="f6371-291">Na pasta do **pacote SRS v2-Set-SRSComputerName** , crie um novo aplicativo HTML chamado **set-SRSComputerName. hta** .</span><span class="sxs-lookup"><span data-stu-id="f6371-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="f6371-292">Copie o seguinte script para o arquivo **set-SRSComputerName. hta** .</span><span class="sxs-lookup"><span data-stu-id="f6371-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="f6371-293">Você também pode baixar o arquivo Set-SRSComputerName. hta [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f6371-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```
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
3.  <span data-ttu-id="f6371-294">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="f6371-295">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="f6371-296">Nome: **pacote do set-SRSComputerName do SRS v2**</span><span class="sxs-lookup"><span data-stu-id="f6371-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="f6371-297">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f6371-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="f6371-298">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f6371-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="f6371-299">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho para a pasta do **pacote SRS v2-Set-SRSComputerName** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="f6371-300">Selecione não **criar um programa**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="f6371-301">Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="f6371-302">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="f6371-303">Criar o pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="f6371-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="f6371-304">Na pasta **SRS v2 – pacote Sysprep** , crie um novo arquivo XML denominado **Unattend. xml** .</span><span class="sxs-lookup"><span data-stu-id="f6371-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="f6371-305">Copie o seguinte texto para o arquivo **Unattend. xml** .</span><span class="sxs-lookup"><span data-stu-id="f6371-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="f6371-306">Você também pode baixar o arquivo Unattend. XML [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="f6371-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
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
3. <span data-ttu-id="f6371-307">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="f6371-308">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="f6371-309">Nome: **SRS v2-pacote Sysprep**</span><span class="sxs-lookup"><span data-stu-id="f6371-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="f6371-310">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f6371-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="f6371-311">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f6371-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="f6371-312">Marque a caixa de seleção **Este pacote contém arquivos de origem** , digite o caminho para a pasta **SRS v2 – pacote Sysprep** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="f6371-313">Selecione não **criar um programa**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="f6371-314">Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="f6371-315">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="f6371-316">Criar o pacote do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f6371-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="f6371-317">Obtenha uma mídia do Windows 10 Enterprise x64 e copie o arquivo **install. wim** para a pasta **sistemas\\operacionais Windows 10 Enterprise** .</span><span class="sxs-lookup"><span data-stu-id="f6371-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="f6371-318">No console do Configuration Manager, vá para **imagens do sistema**operacional dos **sistemas** \> operacionais da **biblioteca** \> de software e selecione **Adicionar imagem do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="f6371-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="f6371-319">Especifique o caminho para o arquivo **install. wim** que você acabou de copiar e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="f6371-320">Atualize o campo **versão** para corresponder ao número da compilação da imagem do Windows 10 Enterprise e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="f6371-321">Examine a página **detalhes** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="f6371-322">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-322">Select **Close**.</span></span>

<span data-ttu-id="f6371-323">Para obter mais informações, consulte [gerenciar imagens do sistema operacional com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="f6371-323">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="f6371-324">Criar pacotes de driver de dispositivo Surface pro</span><span class="sxs-lookup"><span data-stu-id="f6371-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="f6371-325">As salas do Microsoft Teams são compatíveis com o Surface pro e o Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="f6371-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="f6371-326">Você precisa criar um pacote de driver para cada modelo de Surface pro que você tem em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="f6371-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6371-327">Os drivers devem ser compatíveis com o Windows 10 Enterprise Build e a versão do kit de implantação de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="f6371-328">Para obter mais informações, consulte [baixar o firmware e os drivers mais recentes para os dispositivos Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e [configurar um console](console.md).</span><span class="sxs-lookup"><span data-stu-id="f6371-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="f6371-329">Baixe os drivers e firmware mais recentes.</span><span class="sxs-lookup"><span data-stu-id="f6371-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="f6371-330">Para Surface pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="f6371-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="f6371-331">Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="f6371-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="f6371-332">Extraia o driver e firmware baixados.</span><span class="sxs-lookup"><span data-stu-id="f6371-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="f6371-333">Abra uma janela do prompt de comando e, no prompt de comando, insira um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="f6371-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="f6371-334">No console do Configuration Manager, vá para **drivers**de **sistemas** \> operacionais da **biblioteca** \> de software e selecione **Importar Driver**.</span><span class="sxs-lookup"><span data-stu-id="f6371-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="f6371-335">Selecione **importar todos os drivers no seguinte caminho de rede (UNC)**, selecione a pasta de origem (por exemplo,\\C\\:\\_Sources drivers Surface pro) e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="f6371-336">Na página **especificar os detalhes da página de drivers importados** , selecione todos os drivers listados e, em seguida, selecione **habilitar esses drivers e permitir que os computadores os instalem**.</span><span class="sxs-lookup"><span data-stu-id="f6371-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="f6371-337">Selecione **categorias**, crie uma nova categoria que corresponda ao modelo de superfície, selecione **OK**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="f6371-338">Selecione **novo pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="f6371-339">Especifique o nome do pacote que corresponde ao modelo do Surface pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver em, selecione **OK**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="f6371-340">Na página de **imagens de inicialização** , certifique-se de que nenhuma imagem de inicialização esteja selecionada e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="f6371-341">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-341">Select **Close**.</span></span>

11. <span data-ttu-id="f6371-342">Vá para **drivers**de **sistemas** \> operacionais da **biblioteca** \> de software, selecione pasta \*\* \> criar pasta\*\*e insira um nome de pasta que corresponda ao modelo do Surface pro para o qual você acabou de importar os drivers.</span><span class="sxs-lookup"><span data-stu-id="f6371-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="f6371-343">Mova todos os drivers importados para a pasta recém criada para facilitar a navegação e a operação.</span><span class="sxs-lookup"><span data-stu-id="f6371-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="f6371-344">Repita as mesmas etapas para outros modelos de Surface pro que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="f6371-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="f6371-345">Para obter mais informações, consulte [gerenciar drivers no System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="f6371-345">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="f6371-346">Criar pacote de configuração de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6371-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="f6371-347">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software e selecione **criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="f6371-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="f6371-348">Insira as seguintes informações para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="f6371-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="f6371-349">Nome: **SRS v2-configurar o pacote de configuração do SRS**</span><span class="sxs-lookup"><span data-stu-id="f6371-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="f6371-350">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="f6371-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="f6371-351">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="f6371-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="f6371-352">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho para a pasta **SRS v2-configure SRS setup** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="f6371-353">Selecione não **criar um programa**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="f6371-354">Examine a página **confirmar as configurações** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="f6371-355">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="f6371-356">Distribuir pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="f6371-357">Todos os pacotes devem ser distribuídos para os servidores que foram atribuídos à função de ponto de distribuição na hierarquia do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="f6371-358">Siga as instruções abaixo para iniciar a distribuição de pacote.</span><span class="sxs-lookup"><span data-stu-id="f6371-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="f6371-359">Distribuir pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="f6371-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="f6371-360">No console do Configuration Manager, vá para **pacotes**de **Gerenciamento** \> de aplicativos da **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="f6371-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="f6371-361">Selecione todos os pacotes de software que você deseja distribuir e, em seguida, selecione **distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="f6371-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="f6371-362">Examine a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="f6371-363">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="f6371-364">Selecione **Avançar**e, em seguida, selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="f6371-365">Distribuir pacotes de driver.</span><span class="sxs-lookup"><span data-stu-id="f6371-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="f6371-366">No console do Configuration Manager, vá para **pacotes de driver**de **sistemas** \> operacionais de **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="f6371-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="f6371-367">Selecione todos os pacotes de driver que você deseja distribuir e, em seguida, selecione **distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="f6371-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="f6371-368">Examine a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="f6371-369">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="f6371-370">Selecione **Avançar**e, em seguida, selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="f6371-371">Distribuir pacotes do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f6371-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="f6371-372">No console do Configuration Manager, vá para **imagens do sistema operacional**dos **sistemas** \> operacionais da **biblioteca** \> de software.</span><span class="sxs-lookup"><span data-stu-id="f6371-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="f6371-373">Selecione todas as imagens do sistema operacional que você deseja distribuir e, em seguida, selecione **distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="f6371-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="f6371-374">Examine a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="f6371-375">Adicione todos os servidores de ponto de distribuição (ou grupos de pontos de distribuição, dependendo da sua hierarquia do Configuration Manager) à lista e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="f6371-376">Selecione **Avançar**e, em seguida, selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="f6371-377">A distribuição de pacote pode levar algum tempo, dependendo do tamanho do pacote, da hierarquia do Configuration Manager, do número de servidores de ponto de distribuição e da largura de banda disponível na rede.</span><span class="sxs-lookup"><span data-stu-id="f6371-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="f6371-378">Todos os pacotes devem ser distribuídos para que você possa começar a implantar uma unidade de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="f6371-379">Você pode examinar o status da distribuição do pacote no console do Configuration Manager indo **monitorar** \> \*\*\*\* \> **status do conteúdo**do status da distribuição.</span><span class="sxs-lookup"><span data-stu-id="f6371-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="f6371-380">Sequências de tarefas do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="f6371-381">Você usa sequências de tarefas com o System Center Configuration Manager para automatizar as etapas para implantar uma imagem do sistema operacional em um computador de destino.</span><span class="sxs-lookup"><span data-stu-id="f6371-381">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="f6371-382">Para implantar uma unidade de salas do Microsoft Teams de maneira automatizada, crie uma sequência de tarefas que referencie a imagem de inicialização usada para iniciar o computador de salas de destino do Microsoft Teams, a imagem do sistema operacional Windows 10 Enterprise que você deseja instalar e qualquer outros conteúdos adicionais, como outros aplicativos ou atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="f6371-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="f6371-383">Importar a sequência de tarefas de exemplo</span><span class="sxs-lookup"><span data-stu-id="f6371-383">Import the sample task sequence</span></span>

<span data-ttu-id="f6371-384">Você pode baixar e importar facilmente uma sequência de tarefas de exemplo e personalizá-la para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="f6371-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="f6371-385">[**Baixe**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) a sequência de tarefas de exemplo e copie o arquivo zip baixado para um local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="f6371-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="f6371-386">No console do Configuration Manager, vá para **sequências de tarefas**de **sistemas** \> operacionais da **biblioteca** \> de software e selecione **importar sequência de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="f6371-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="f6371-387">Selecione **procurar**, vá para o local da pasta compartilhada que você usou na etapa 1, selecione o arquivo **. zip da implantação de salas do Microsoft Teams (en-US)** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="f6371-388">Defina **ação** para **criar novo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="f6371-389">Confirme as configurações e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="f6371-390">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="f6371-391">Valide se os pacotes de referência estão vinculados corretamente a cada etapa de sequência de tarefas.</span><span class="sxs-lookup"><span data-stu-id="f6371-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="f6371-392">Selecione a sequência de tarefas importada e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="f6371-393">O editor de sequência de tarefas abre e exibe cada etapa sequencial que você precisa para implantar e configurar uma unidade de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="f6371-394">Percorra cada etapa e conclua as atualizações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="f6371-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="f6371-395">**Reinicie no Windows PE**: essa etapa reinicia e inicializa o computador no Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="f6371-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="f6371-396">Nenhuma alteração é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f6371-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="f6371-397">**Partition Disk 0 – UEFI**: esta etapa apaga a configuração do disco e cria partições com base nas configurações definidas.</span><span class="sxs-lookup"><span data-stu-id="f6371-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="f6371-398">Recomendamos que você não faça nenhuma alteração nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="f6371-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="f6371-399">**Definir o nome do computador SRS**: esta etapa inclui um aplicativo HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade de salas do Microsoft Teams durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="f6371-400">Esta etapa é opcional, mas só poderá ser desabilitada se você quiser gerenciar o nome do computador por meio de um processo alternativo.</span><span class="sxs-lookup"><span data-stu-id="f6371-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="f6371-401">Verifique se o pacote **SRS v2-Set-SRSComputerName** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="f6371-402">Se não estiver, navegue até o pacote e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="f6371-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="f6371-403">**Aplicar sistema operacional**: esta etapa especifica a imagem do sistema operacional a ser implantada e o arquivo de resposta do Sysprep autônomo a ser usado.</span><span class="sxs-lookup"><span data-stu-id="f6371-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="f6371-404">Verifique se o arquivo de imagem correto do sistema operacional Windows 10 Enterprise está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="f6371-405">Verifique se o uso de um **arquivo de resposta autônomo ou Sysprep para uma instalação personalizada** está habilitado e se o **pacote SRS v2-Sysprep** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="f6371-406">Além disso, certifique-se de que o **nome do arquivo** esteja definido como Unattend **. xml**.</span><span class="sxs-lookup"><span data-stu-id="f6371-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="f6371-407">**Aplicar configurações do Windows**: esta etapa coleta informações sobre a instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="f6371-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="f6371-408">Forneça informações de licenciamento e registro, incluindo a chave do produto, a senha da conta de administrador local e o fuso horário (dependendo das suas necessidades).</span><span class="sxs-lookup"><span data-stu-id="f6371-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="f6371-409">**Aplicar configurações de rede**: esta etapa permite que você especifique um grupo de trabalho ou um nome de domínio e uma unidade organizacional do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6371-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="f6371-410">Consulte [domínio do sistema de sala da Skype considerações sobre](domain-joining-considerations.md) as ações recomendadas para a implantação de unidades de sala do Microsoft Teams como membros de um domínio do diretório actve.</span><span class="sxs-lookup"><span data-stu-id="f6371-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="f6371-411">**Aplicar drivers:** Esta etapa e suas subetapas são usadas para implantar drivers de dispositivo e firmware aplicáveis com base no modelo do Surface pro que você tem.</span><span class="sxs-lookup"><span data-stu-id="f6371-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="f6371-412">Atualize cada etapa para especificar o pacote de driver apropriado associado a essa implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="f6371-413">Cada pacote de driver é configurado para aproveitar os filtros de instrumentação de gerenciamento do Windows (WMI) para implantar drivers relevantes e firmware com base na marca e no modelo do Surface pro.</span><span class="sxs-lookup"><span data-stu-id="f6371-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="f6371-414">É altamente recomendável que você não altere a configuração desses drivers, caso contrário, a implantação poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="f6371-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="f6371-415">**Configurar o Windows e o Gerenciador de configurações**: esta etapa implanta e configura o cliente do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="f6371-416">Atualize esta etapa para especificar o pacote interno do cliente do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="f6371-417">**Instalar certificado raiz**: esta etapa distribui o certificado raiz para dispositivos não associados ao domínio e, portanto, é opcional e desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f6371-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="f6371-418">Habilite esta etapa se você precisar implantar um certificado raiz nas unidades de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="f6371-419">Se você precisar executar esta etapa, verifique se o pacote de **certificado raiz do SRS v2** e **desabilite o redirecionamento do sistema de arquivos de 64** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="f6371-420">**Instalar e configurar o agente de monitoramento**: esta etapa instala a versão de 64 bits do agente de monitor do Microsoft Azure e configura o agente para se conectar ao espaço de trabalho de análise de log.</span><span class="sxs-lookup"><span data-stu-id="f6371-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="f6371-421">Esta etapa é desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="f6371-421">This step is disabled by default.</span></span> <span data-ttu-id="f6371-422">Habilite essa etapa somente se você for usar o agente de monitoramento para monitorar a integridade de suas unidades de sala de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="f6371-423">Edite esta etapa e atualize os parâmetros de linha de comando para especificar a **ID do espaço de trabalho** e a chave do espaço de **trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f6371-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="f6371-424">Consulte [configurar dispositivos de teste para monitoramento do Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) para obter mais informações sobre como obter a ID do espaço de trabalho do Operations Management Suite e a chave primária.</span><span class="sxs-lookup"><span data-stu-id="f6371-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="f6371-425">Verifique se o **pacote SRS v2 – Microsoft Monitoring Agent** e **desabilite o redirecionamento do sistema de arquivos de 64-bit** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="f6371-426">Para obter mais informações sobre como monitorar a integridade da implantação de salas do Microsoft Teams, consulte planejar o gerenciamento de salas do Microsoft [Teams com o Azure monitor](azure-monitor-plan.md), [implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md) e [gerenciar dispositivos de salas do Microsoft Teams com o Azure monitor](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="f6371-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="f6371-427">**Copiar os arquivos de configuração do SRS v2**: esta etapa copia os arquivos de configuração e configuração necessários do kit de implantação de salas do Microsoft Teams para o disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="f6371-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="f6371-428">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f6371-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="f6371-429">Verifique se o **pacote do aplicativo SRS v2 – SRS** e **desabilite o redirecionamento do sistema de arquivos do 64-bit** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="f6371-430">**Install-SRSv2-os-so-updates**: esta etapa implanta todas as atualizações obrigatórias do sistema operacional necessárias para a implantação de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="f6371-431">Do the following:</span><span class="sxs-lookup"><span data-stu-id="f6371-431">Do the following:</span></span>
       -   <span data-ttu-id="f6371-432">Marque [configurar um console de salas do Microsoft Teams](console.md) para ver quais atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="f6371-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="f6371-433">Verifique se o **pacote de atualizações do SRS v2 – so** inclui todas as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="f6371-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="f6371-434">Verifique se o **SRS v2 – pacote de atualizações do so** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="f6371-435">Verifique se a política de execução do PowerShell está definida como **ignorar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="f6371-436">**Reiniciar computador**: esta etapa reinicializa o computador após a instalação das atualizações obrigatórias do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f6371-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="f6371-437">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f6371-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="f6371-438">**Configurar componentes do Windows**: esta etapa configura os recursos necessários do Windows.</span><span class="sxs-lookup"><span data-stu-id="f6371-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="f6371-439">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f6371-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="f6371-440">**Reiniciar computador**: esta etapa reinicializa o computador após a configuração dos recursos do Windows.</span><span class="sxs-lookup"><span data-stu-id="f6371-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="f6371-441">Nenhuma personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f6371-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="f6371-442">**Adicionar usuário local do Skype**: esta etapa cria a conta do Skype local usada para entrar automaticamente no Windows e iniciar o aplicativo salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="f6371-443">Esta etapa não tem nenhum pacote de software associado a ele, e nenhuma personalização é necessária para ele.</span><span class="sxs-lookup"><span data-stu-id="f6371-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="f6371-444">**Configurar e configurar o aplicativo SRS**: esta etapa configura a instalação do aplicativo salas do Microsoft Teams para a próxima inicialização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f6371-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="f6371-445">Verifique se o **SRS v2 – configurar o pacote de configuração do SRS** e **desativar o redirecionamento do sistema de arquivos de 64 bits** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6371-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6371-446">É muito importante que as etapas da sequência de tarefas devem estar na ordem fornecida.</span><span class="sxs-lookup"><span data-stu-id="f6371-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="f6371-447">Modificar a ordem das etapas ou configurar etapas adicionais pode interromper a implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="f6371-448">**Configurar e configurar o aplicativo SRS** a etapa deve ser a última etapa na sequência de tarefas, caso contrário, a implantação poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="f6371-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="f6371-449">Criar implantação para a sequência de tarefas</span><span class="sxs-lookup"><span data-stu-id="f6371-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="f6371-450">Selecione a sequência de tarefas e, em seguida, selecione **implantar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="f6371-451">Selecione **procurar** para selecionar a coleção de destino para implantação.</span><span class="sxs-lookup"><span data-stu-id="f6371-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="f6371-452">Selecione **todos os computadores desconhecidos** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6371-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="f6371-453">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-453">Select **Next**.</span></span>

5. <span data-ttu-id="f6371-454">Selecione **disponível** na lista suspensa **finalidade** .</span><span class="sxs-lookup"><span data-stu-id="f6371-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="f6371-455">Selecione **somente mídia e PXE** na lista **fazer disponível para a lista a seguir** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="f6371-456">É muito importante que a **finalidade** seja definida como **disponível**.</span><span class="sxs-lookup"><span data-stu-id="f6371-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="f6371-457">Verifique se a **finalidade** **não** está definida como **obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="f6371-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="f6371-458">Além disso, certifique-se de selecionar **somente mídia e PXE** na opção disponibilizar **para o seguinte**.</span><span class="sxs-lookup"><span data-stu-id="f6371-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="f6371-459">Configurar esses valores para algo mais pode fazer com que todos os computadores obtenham a imagem de implantação de salas do Microsoft Teams quando inicializados.</span><span class="sxs-lookup"><span data-stu-id="f6371-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="f6371-460">Não especifique nenhum agendamento e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="f6371-461">Não altere nada na seção **experiência do usuário** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="f6371-462">Não altere nada na seção **alertas** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="f6371-463">Não altere nada na seção **pontos de distribuição** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="f6371-464">Confirme as configurações e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="f6371-465">Selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="f6371-466">Validar e solucionar problemas com a solução</span><span class="sxs-lookup"><span data-stu-id="f6371-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="f6371-467">Depois de concluir as sequências de tarefas do System Center Configuration Manager, você precisará executar uma execução de teste para validar que a sequência de tarefas pode implantar e configurar unidades de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-467">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="f6371-468">Conecte o dispositivo de teste à rede com fio usando um dos adaptadores Ethernet compatíveis ou usando o Dock Dock.</span><span class="sxs-lookup"><span data-stu-id="f6371-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="f6371-469">Se a funcionalidade de inicialização PXE não tiver sido configurada para o seu ambiente, você poderá usar a imagem de inicialização na unidade flash USB [que você criou anteriormente](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) para inicializar a partir do USB e conectar-se ao Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="f6371-470">Acesse o firmware e inicie a inicialização PXE:</span><span class="sxs-lookup"><span data-stu-id="f6371-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="f6371-471">Verifique se o dispositivo de Surface está desligado.</span><span class="sxs-lookup"><span data-stu-id="f6371-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="f6371-472">Pressione e mantenha pressionado o botão **aumentar volume** .</span><span class="sxs-lookup"><span data-stu-id="f6371-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="f6371-473">Pressione e libere o botão de **energia** .</span><span class="sxs-lookup"><span data-stu-id="f6371-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="f6371-474">Depois que o dispositivo começar a inicializar, solte o botão **aumentar volume** .</span><span class="sxs-lookup"><span data-stu-id="f6371-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="f6371-475">Selecione **configuração de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="f6371-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="f6371-476">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f6371-476">Do one of the following:</span></span>

        -   <span data-ttu-id="f6371-477">Selecione **inicialização PXE**e arraste-o para a parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="f6371-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="f6371-478">Você também pode passar o dedo para a esquerda no adaptador de rede para inicializar o dispositivo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f6371-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="f6371-479">Isso não afetará a ordem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="f6371-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="f6371-480">Selecione a unidade flash USB que contém a mídia de inicialização.</span><span class="sxs-lookup"><span data-stu-id="f6371-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="f6371-481">Selecione **sair**e, em seguida, selecione **reiniciar agora**.</span><span class="sxs-lookup"><span data-stu-id="f6371-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="f6371-482">Quando solicitado, selecione **Enter** for Network boot Service.</span><span class="sxs-lookup"><span data-stu-id="f6371-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="f6371-483">O Windows PE será carregado na memória, e o assistente de sequência de tarefas será iniciado.</span><span class="sxs-lookup"><span data-stu-id="f6371-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="f6371-484">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="f6371-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="f6371-485">Selecione a sequência de tarefas que você importou anteriormente e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6371-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="f6371-486">Após a aplicação da configuração do disco, você será solicitado a especificar um nome de computador para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f6371-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="f6371-487">A interface do usuário exibirá um nome de computador recomendado com base no número de série do dispositivo do Surface pro.</span><span class="sxs-lookup"><span data-stu-id="f6371-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="f6371-488">Você pode aceitar o nome proposto ou especificar um novo.</span><span class="sxs-lookup"><span data-stu-id="f6371-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="f6371-489">Siga as instruções na tela atribuição de nome do computador.</span><span class="sxs-lookup"><span data-stu-id="f6371-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="f6371-490">Quando você selecionar **aceitar**, a implantação começará.</span><span class="sxs-lookup"><span data-stu-id="f6371-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="f6371-491">O restante do processo de implantação é automático e não solicita mais entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6371-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="f6371-492">Depois que a sequência de tarefas de implantação terminar de configurar o dispositivo, você verá a seguinte tela de configuração que solicita que você defina as configurações do aplicativo salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6371-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Tela inicial de configuração do aplicativo salas do Microsoft Teams](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="f6371-494">Conecte o Surface pro ao console de salas do Microsoft Teams e defina as configurações do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f6371-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="f6371-495">Valide se os recursos listados na [ajuda das salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estão trabalhando no dispositivo implantado.</span><span class="sxs-lookup"><span data-stu-id="f6371-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="f6371-496">Para solucionar uma falha na instalação, verifique o arquivo **SMSTS. log** , que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6371-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="f6371-497">O arquivo SMSTS. log está armazenado em um de vários caminhos, dependendo do estágio do processo de compilação.</span><span class="sxs-lookup"><span data-stu-id="f6371-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="f6371-498">Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="f6371-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="f6371-499">**Fase de implantação**</span><span class="sxs-lookup"><span data-stu-id="f6371-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="f6371-500">**Caminho do log da sequência de tarefas**</span><span class="sxs-lookup"><span data-stu-id="f6371-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="f6371-501">WinPE, antes do formato do HDD</span><span class="sxs-lookup"><span data-stu-id="f6371-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="f6371-502">X:\\Windows\\temp\\smstslog\\SMSTS. log</span><span class="sxs-lookup"><span data-stu-id="f6371-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="f6371-503">WinPE, após o formato do HDD</span><span class="sxs-lookup"><span data-stu-id="f6371-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="f6371-504">C:\\_SMSTaskSequence\\registra\\-\\se Smstslog SMSTS. log</span><span class="sxs-lookup"><span data-stu-id="f6371-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="f6371-505">Sistema operacional implantado antes da instalação do agente do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="f6371-506">c:\\_SMSTaskSequence\\registra\\-\\se Smstslog SMSTS. log</span><span class="sxs-lookup"><span data-stu-id="f6371-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="f6371-507">Sistema operacional e o agente do Configuration Manager implantado</span><span class="sxs-lookup"><span data-stu-id="f6371-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="f6371-508">% WINDIR%\\system32\\CCM\\logs\\Smstslog\\SMSTS. log</span><span class="sxs-lookup"><span data-stu-id="f6371-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="f6371-509">Execução da sequência de tarefas concluída</span><span class="sxs-lookup"><span data-stu-id="f6371-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="f6371-510">% WINDIR%\\system32\\CCM\\registra\\SMSTS. log</span><span class="sxs-lookup"><span data-stu-id="f6371-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="f6371-511">Você pode selecionar **F8** a qualquer momento durante a sequência de tarefas para abrir um console de comando e, em seguida, obter acesso ao arquivo SMSTS. log.</span><span class="sxs-lookup"><span data-stu-id="f6371-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="f6371-512">Para solucionar problemas de inicialização PXE, verifique os dois arquivos de log no servidor do Configuration Manager que são específicos para ações PXE:</span><span class="sxs-lookup"><span data-stu-id="f6371-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="f6371-513">**Pxecontrol. log**, localizado no diretório de logs de instalação do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6371-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="f6371-514">**Smspxe. log**, localizado no diretório de logs do ponto de gerenciamento do Configuration Manager (MP)</span><span class="sxs-lookup"><span data-stu-id="f6371-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="f6371-515">Para obter uma lista completa dos arquivos de log que você pode usar para solucionar problemas com a instalação do Configuration Manager, consulte [arquivos de log no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="f6371-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
