---
title: Implantar sistemas de sala Skype usando o System Center Configuration Manager
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este tópico para saber mais sobre como implantar sistemas de sala Skype v2 em implantações de grande escala.
ms.openlocfilehash: 3602422779a405376893a3a7e6663520ed6a4a4c
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "30210870"
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a><span data-ttu-id="0bdec-103">Implantar sistemas de sala Skype v2 usando o System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bdec-103">Deploy Skype Room Systems v2 by using System Center Configuration Manager</span></span>

<span data-ttu-id="0bdec-104">Este artigo fornece todas as informações necessárias para criar suas implantações do Skype sala sistemas v2 usando o System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0bdec-104">This article gives you all the necessary information to create your Skype Room Systems v2 deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="0bdec-105">Com os métodos de fácil utilização fornecidos pelo System Center Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="0bdec-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="0bdec-106">Usar a abordagem ilustrada abaixo para orientá-lo a configuração do Configuration Manager e personalize os pacotes de amostra e os scripts fornecidos no decorrer deste guia, conforme necessário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="0bdec-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processo de implantação do Skype sala sistemas v2 usando o Configuration Manager](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="0bdec-108">Essa solução foi testada apenas com implantações baseadas em Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="0bdec-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="0bdec-109">Siga as diretrizes do fabricante para configurações que não são baseadas em Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="0bdec-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="0bdec-110">Valide os pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0bdec-110">Validate prerequisites</span></span>

<span data-ttu-id="0bdec-111">Para implantar sistemas de sala Skype v2 com o Configuration Manager, certifique-se de que você atende os seguintes pré-requisitos e requisitos.</span><span class="sxs-lookup"><span data-stu-id="0bdec-111">To deploy Skype Room Systems v2 with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="0bdec-112">Requisitos do System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bdec-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="0bdec-113">Versão do System Center Configuration Manager deve ser de pelo menos 1706 ou acima.</span><span class="sxs-lookup"><span data-stu-id="0bdec-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="0bdec-114">É recomendável usar 1710 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0bdec-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="0bdec-115">Confira o [suporte para o Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões do Windows 10 Configuration Manager oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="0bdec-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="0bdec-116">Uma versão compatível do Windows Assessment e Kit de implantação (ADK) para Windows 10 deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="0bdec-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="0bdec-117">Consulte as versões do [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com diferentes versões do Configuration Manager e certifique-se de que sua implantação incluir a versão correta.</span><span class="sxs-lookup"><span data-stu-id="0bdec-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="0bdec-118">Os servidores de sistema do site devem ser atribuídos a função de ponto de distribuição e as imagens de inicialização devem ser habilitadas para [preboot suporte do ambiente (PXE) de execução](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) habilitar implantações iniciadas de rede.</span><span class="sxs-lookup"><span data-stu-id="0bdec-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="0bdec-119">Se o suporte a PXE não estiver habilitado, você pode usar a [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.</span><span class="sxs-lookup"><span data-stu-id="0bdec-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="0bdec-120">Uma conta de acesso de rede deve ser configurada para oferecer suporte a novos cenários de implantação de computador (bare metal).</span><span class="sxs-lookup"><span data-stu-id="0bdec-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="0bdec-121">Para saber mais sobre a configuração de uma conta de acesso de rede, consulte [Gerenciar contas para acessar o conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="0bdec-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="0bdec-122">Recomendamos que você habilite o [suporte ao multicast](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se você provavelmente precisará implantar a imagem de v2 Skype sala sistemas mesma várias unidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0bdec-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Skype Room Systems v2 image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="0bdec-123">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="0bdec-123">Networking requirements</span></span>

-   <span data-ttu-id="0bdec-124">Sua rede deve ter um servidor Dynamic Host Configuration Protocol (DHCP), configurado para distribuição automática de endereço IP para as sub-redes onde unidades do Skype sala sistemas v2 serão implantadas.</span><span class="sxs-lookup"><span data-stu-id="0bdec-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Skype Room Systems v2 units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0bdec-125">Duração de concessão DHCP deve ser definida como um valor maior que a duração de implantação de imagem.</span><span class="sxs-lookup"><span data-stu-id="0bdec-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="0bdec-126">Caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="0bdec-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="0bdec-127">Sua rede, incluindo comutadores e LANs virtuais (VLANs), deve ser configurado para oferecer suporte a PXE.</span><span class="sxs-lookup"><span data-stu-id="0bdec-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="0bdec-128">Consulte seu fornecedor de rede para obter mais informações sobre a configuração IP Helper e PXE.</span><span class="sxs-lookup"><span data-stu-id="0bdec-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="0bdec-129">Como alternativa, você pode usar [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte PXE não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0bdec-130">Para Surface Pro dispositivos, inicialização a partir da rede (inicialização PXE) só são suportados quando você usa um adaptador de Ethernet ou estação de encaixe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bdec-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="0bdec-131">Adaptadores de Ethernet de terceiros não oferecem suporte a inicialização PXE com Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="0bdec-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="0bdec-132">Para obter mais informações, consulte [implantação de superfície e adaptadores Ethernet](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="0bdec-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="0bdec-133">Configurar o System Center Configuration Manager para implantação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="0bdec-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="0bdec-134">Este artigo pressupõe que você já possui uma implantação do System Center Configuration Manager íntegro e não detalhes de todas as etapas necessárias para implantar e configurar o Gerenciador de configuração do zero.</span><span class="sxs-lookup"><span data-stu-id="0bdec-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="0bdec-135">A [documentação e as diretrizes de configuração](https://docs.microsoft.com/sccm/) no System Center Configuration Manager é um ótimo recurso; Recomendamos que você comece com esses recursos, se você ainda não tenha implantado o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0bdec-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="0bdec-136">Use as instruções a seguir para verificar se os recursos de implantação (OSD) do sistema operacional estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="0bdec-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="0bdec-137">Validar e atualizar o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bdec-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="0bdec-138">No console do Configuration Manager, vá para **Administração** \> **atualizações e manutenção**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="0bdec-139">Verifique a compilação instalada e atualizações aplicáveis que ainda não tenham sido instaladas.</span><span class="sxs-lookup"><span data-stu-id="0bdec-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="0bdec-140">Revise o [suporte para Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Se você precisar atualizar a implantação, selecione a atualização que você deseja instalar e, em seguida, selecione **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="0bdec-141">Quando o download for concluído, selecione a atualização e, em seguida, selecione **Instalar o pacote de atualização**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="0bdec-142">Configurar os pontos de distribuição para oferecer suporte a PXE e multicast</span><span class="sxs-lookup"><span data-stu-id="0bdec-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="0bdec-143">No console do Configuration Manager, vá para **Administração** \> **Pontos de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="0bdec-144">Selecione o servidor de ponto de distribuição que atender a implantação do Skype sala sistemas v2 e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-144">Select the distribution point server that will serve the Skype Room Systems v2 deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="0bdec-145">Selecione a guia **PXE** e certifique-se de que as configurações a seguir estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="0bdec-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="0bdec-146">Habilitar o suporte a PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="0bdec-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="0bdec-147">Permitir que esse ponto de distribuição responder às solicitações de entrada PXE</span><span class="sxs-lookup"><span data-stu-id="0bdec-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="0bdec-148">Habilitar o suporte de computador desconhecido</span><span class="sxs-lookup"><span data-stu-id="0bdec-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="0bdec-149">*Opcional:* Para habilitar o suporte ao multicast, selecione a guia **Multicast** e certifique-se de que as configurações a seguir estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="0bdec-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="0bdec-150">Habilitar multicast simultaneamente enviar dados para vários clientes</span><span class="sxs-lookup"><span data-stu-id="0bdec-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="0bdec-151">Configurar o intervalo de portas UDP conforme recomendação da sua equipe de rede</span><span class="sxs-lookup"><span data-stu-id="0bdec-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="0bdec-152">Configurar a conta de acesso de rede</span><span class="sxs-lookup"><span data-stu-id="0bdec-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="0bdec-153">No console do Configuration Manager, vá para **Administração** \> **Configuração de Site** \> **Sites**e selecione o site.</span><span class="sxs-lookup"><span data-stu-id="0bdec-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="0bdec-154">No grupo **configurações** , selecione **Configurar componentes de Site** \> **A distribuição de Software**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="0bdec-155">Selecione a guia de **Conta de acesso de rede** Set up uma ou mais contas e selecione **Okey**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="0bdec-156">As contas não precisam quaisquer direitos especiais, exceto para o **acesso a este computador a partir da rede** diretamente no servidor de ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0bdec-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="0bdec-157">Uma conta de usuário de domínio genérico será apropriada.</span><span class="sxs-lookup"><span data-stu-id="0bdec-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="0bdec-158">Para obter mais informações, consulte [Gerenciar contas para acessar o conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="0bdec-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="0bdec-159">Configurar uma imagem de inicialização</span><span class="sxs-lookup"><span data-stu-id="0bdec-159">Configure a boot image</span></span>

1.  <span data-ttu-id="0bdec-160">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistema operacional** \> **Imagens de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="0bdec-161">Selecione a **imagem de inicialização (x64)** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="0bdec-162">Selecione a guia **Fonte de dados** e habilite **implantar essa imagem de inicialização do ponto de distribuição habilitado para PXE**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="0bdec-163">Selecione a guia **Componentes opcionais** para instalar os componentes necessários:</span><span class="sxs-lookup"><span data-stu-id="0bdec-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="0bdec-164">Selecione o ícone de estrela e procurar **HTML (HTA WinPE)**</span><span class="sxs-lookup"><span data-stu-id="0bdec-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="0bdec-165">Selecione **Okey** para adicionar suporte a aplicativos em HTML para a imagem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="0bdec-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="0bdec-166">*Opcional:* Para personalizar a experiência de implantação, selecione a guia de **personalização** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="0bdec-167">Habilite o **comando suporte (somente para teste)** se você deseja que tenham acesso a um prompt de comando durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="0bdec-168">Quando esta opção estiver ativada, você pode iniciar um prompt de comando, selecionando **F8** a qualquer momento durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="0bdec-169">Você também pode especificar uma imagem de plano de fundo personalizado a ser exibida durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="0bdec-170">Para definir uma imagem, habilitar **especificar o arquivo de imagem de plano de fundo personalizado (caminho UNC** e selecione seu plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="0bdec-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="0bdec-171">Quando solicitado, selecione **Sim** e distribuir a imagem de inicialização atualizada para seus pontos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0bdec-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="0bdec-172">Para obter mais informações, consulte [imagens de inicialização de gerenciar com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="0bdec-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="0bdec-173">Você pode criar uma mídia USB inicializável para lançar implantações de baseadas em sequência de tarefa Configuration Manager para ambientes que não oferece suporte a PXE.</span><span class="sxs-lookup"><span data-stu-id="0bdec-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="0bdec-174">A mídia inicializável contém apenas a imagem de inicialização, comandos prestart opcionais e seus arquivos necessários e binários do Configuration Manager para oferecer suporte à inicialização no Windows PE e conectando-se ao Gerenciador de configuração para o restante do processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="0bdec-175">Para obter mais informações, consulte [como criar uma mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="0bdec-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="0bdec-176">Crie pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bdec-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="0bdec-177">Gerenciador de configuração requer um número de pacotes para implantar e configurar as unidades do sistema de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="0bdec-177">Configuration Manager requires a number of packages to deploy and configure the Skype Room System v2 units.</span></span>

<span data-ttu-id="0bdec-178">Você precisa criar e configurar os pacotes a seguir e, em seguida, distribuí-las para os sistemas de site do Configuration Manager que tiverem sido atribuídos a função de servidor do ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="0bdec-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="0bdec-179">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="0bdec-179">**Package name**</span></span>                     | <span data-ttu-id="0bdec-180">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0bdec-180">**Type**</span></span>               | <span data-ttu-id="0bdec-181">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0bdec-181">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="0bdec-182">SRS v2 - SRS pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0bdec-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="0bdec-183">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-183">Software package</span></span>       | <span data-ttu-id="0bdec-184">Pacote para o kit de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="0bdec-184">Package for the Skype Room Systems v2 deployment kit</span></span>                                      |
| <span data-ttu-id="0bdec-185">SRS v2 - pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="0bdec-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="0bdec-186">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-186">Software package</span></span>       | <span data-ttu-id="0bdec-187">Pacote para o Unattended.xml personalizado configurar unidades de v2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="0bdec-187">Package for the custom Unattended.xml to configure Skype Room Systems v2 units</span></span>            |
| <span data-ttu-id="0bdec-188">SRS v2 - Set-SRSComputerName pacote</span><span class="sxs-lookup"><span data-stu-id="0bdec-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="0bdec-189">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-189">Software package</span></span>       | <span data-ttu-id="0bdec-190">Pacote para o aplicativo HTML (HTA) atribuir um nome de computador durante a implantação</span><span class="sxs-lookup"><span data-stu-id="0bdec-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="0bdec-191">SRS v2 - configurar a instalação do SRS</span><span class="sxs-lookup"><span data-stu-id="0bdec-191">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="0bdec-192">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-192">Software package</span></span>       | <span data-ttu-id="0bdec-193">Pacote para configurar a implantação do aplicativo v2 sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="0bdec-193">Package to configure deployment of the Skype Room Systems v2 app</span></span>                          |
| <span data-ttu-id="0bdec-194">SRS v2 - pacote de atualizações de sistema operacional</span><span class="sxs-lookup"><span data-stu-id="0bdec-194">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="0bdec-195">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-195">Software package</span></span>       | <span data-ttu-id="0bdec-196">Pacote para implantar as atualizações obrigatórias do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="0bdec-196">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="0bdec-197">SRS v2 - pacote do certificado raiz</span><span class="sxs-lookup"><span data-stu-id="0bdec-197">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="0bdec-198">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-198">Software package</span></span>       | <span data-ttu-id="0bdec-199">Opcional - pacote para implantar o certificado raiz (não é necessário para unidades de domínio)</span><span class="sxs-lookup"><span data-stu-id="0bdec-199">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="0bdec-200">SRS v2 - pacote do Microsoft OMS agente</span><span class="sxs-lookup"><span data-stu-id="0bdec-200">SRS v2 - Microsoft OMS Agent Package</span></span> | <span data-ttu-id="0bdec-201">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-201">Software package</span></span>       | <span data-ttu-id="0bdec-202">Opcional - pacote para implantar e configurar o agente do pacote de gerenciamento de operações do Microsoft</span><span class="sxs-lookup"><span data-stu-id="0bdec-202">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="0bdec-203">SRS v2 - pacote de plano de fundo do WinPE</span><span class="sxs-lookup"><span data-stu-id="0bdec-203">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="0bdec-204">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="0bdec-204">Software package</span></span>       | <span data-ttu-id="0bdec-205">Pacote para a imagem de plano de fundo personalizado a ser usada com imagens de inicialização</span><span class="sxs-lookup"><span data-stu-id="0bdec-205">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="0bdec-206">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0bdec-206">Windows 10 Enterprise</span></span>                | <span data-ttu-id="0bdec-207">Imagem do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="0bdec-207">Operating system image</span></span> | <span data-ttu-id="0bdec-208">Pacote para o arquivo de instalação do sistema operacional (WIM)</span><span class="sxs-lookup"><span data-stu-id="0bdec-208">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="0bdec-209">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="0bdec-209">Surface Pro</span></span>                          | <span data-ttu-id="0bdec-210">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="0bdec-210">Driver package</span></span>         | <span data-ttu-id="0bdec-211">Pacote para drivers de dispositivo e firmware Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="0bdec-211">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="0bdec-212">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="0bdec-212">Surface Pro 4</span></span>                        | <span data-ttu-id="0bdec-213">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="0bdec-213">Driver package</span></span>         | <span data-ttu-id="0bdec-214">Pacote para drivers de dispositivo e firmware para 4 do Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="0bdec-214">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="0bdec-215">Para obter mais informações, consulte [pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="0bdec-215">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="0bdec-216">Criar arquivos de origem de pastas para o pacote</span><span class="sxs-lookup"><span data-stu-id="0bdec-216">Create folders for the package source files</span></span>

<span data-ttu-id="0bdec-217">Gerenciador de configuração requer os arquivos de origem de pacote para ser organizados em uma estrutura de pasta específica, eles são criados pela primeira vez e quando os campos são atualizados.</span><span class="sxs-lookup"><span data-stu-id="0bdec-217">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="0bdec-218">Crie a seguinte estrutura de pasta no site de administração central do System Center Configuration Manager ou sites primário ou em um compartilhamento de servidor que você está usando para arquivos de origem do pacote de host:</span><span class="sxs-lookup"><span data-stu-id="0bdec-218">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="0bdec-219">SRS v2 - pacote do Microsoft OMS agente</span><span class="sxs-lookup"><span data-stu-id="0bdec-219">SRS v2 - Microsoft OMS Agent Package</span></span>
-   <span data-ttu-id="0bdec-220">SRS v2 - pacote de atualizações de sistema operacional</span><span class="sxs-lookup"><span data-stu-id="0bdec-220">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="0bdec-221">SRS v2 - pacote do certificado raiz</span><span class="sxs-lookup"><span data-stu-id="0bdec-221">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="0bdec-222">SRS v2 - Set-SRSComputerName pacote</span><span class="sxs-lookup"><span data-stu-id="0bdec-222">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="0bdec-223">SRS v2 - SRS pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0bdec-223">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="0bdec-224">SRS v2 - configurar a instalação do SRS</span><span class="sxs-lookup"><span data-stu-id="0bdec-224">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="0bdec-225">SRS v2 - pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="0bdec-225">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="0bdec-226">Drivers</span><span class="sxs-lookup"><span data-stu-id="0bdec-226">Drivers</span></span>
    -   <span data-ttu-id="0bdec-227">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="0bdec-227">Surface Pro</span></span>
    -   <span data-ttu-id="0bdec-228">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="0bdec-228">Surface Pro 4</span></span>
-   <span data-ttu-id="0bdec-229">Sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="0bdec-229">Operating Systems</span></span>
    -   <span data-ttu-id="0bdec-230">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0bdec-230">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="0bdec-231">Você também pode [Baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pasta para os pacotes e os scripts que você precisará usar o modelo de sequência de tarefa, que você precisa importar.</span><span class="sxs-lookup"><span data-stu-id="0bdec-231">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a><span data-ttu-id="0bdec-232">Crie o pacote do pacote de gerenciamento de operações do Microsoft agent</span><span class="sxs-lookup"><span data-stu-id="0bdec-232">Create the Microsoft Operations Management Suite agent package</span></span>

1. <span data-ttu-id="0bdec-233">Baixe o agente do pacote de gerenciamento de operações X-64 contra <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="0bdec-233">Download the Operations Management Suite X-64 agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="0bdec-234">Extraia o pacote para a pasta **SRS v2 - pacote do Microsoft OMS agente** abrindo uma janela de Prompt de comando e inserindo **/c de MMASetup-AMD64.exe:** no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="0bdec-234">Extract the package into the **SRS v2 - Microsoft OMS Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="0bdec-235">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-235">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="0bdec-236">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="0bdec-236">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="0bdec-237">Nome<strong>: SRS v2 - pacote do Microsoft OMS agente</strong></span><span class="sxs-lookup"><span data-stu-id="0bdec-237">Name<strong>: SRS v2 - Microsoft OMS Agent Package</strong></span></span>

   - <span data-ttu-id="0bdec-238">Fabricante<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="0bdec-238">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="0bdec-239">Versão<strong>: 8.1.11081.0</strong> (Insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="0bdec-239">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="0bdec-240">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - pacote do Microsoft OMS agente** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-240">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft OMS Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="0bdec-241">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-241">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="0bdec-242">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-242">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="0bdec-243">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-243">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="0bdec-244">Crie o pacote de atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="0bdec-244">Create the operating system updates package</span></span>

1. <span data-ttu-id="0bdec-245">Na pasta **SRS v2 - pacote de atualizações do sistema operacional** , crie um novo script do PowerShell chamado **Install-SRSv2 SO Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-245">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="0bdec-246">Copie o script abaixo para o script **Install-SRSv2 SO Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-246">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="0bdec-247">Como alternativa, você pode baixar o script Install-SRSv2 SO Updates.ps1 [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="0bdec-247">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="0bdec-248">Baixe os pacotes do Windows Update obrigatórios para a mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="0bdec-248">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0bdec-249">No momento em que este artigo foi publicado, [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necessária.</span><span class="sxs-lookup"><span data-stu-id="0bdec-249">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="0bdec-250">Verifique se [Configure um console do Skype sala sistemas v2](console.md), para ver se quaisquer outras atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="0bdec-250">Check [Configure a Skype Room Systems v2 console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="0bdec-251">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-251">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="0bdec-252">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="0bdec-252">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="0bdec-253">Nome: **SRS v2 – SO atualiza o pacote**</span><span class="sxs-lookup"><span data-stu-id="0bdec-253">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="0bdec-254">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="0bdec-254">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="0bdec-255">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="0bdec-255">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="0bdec-256">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - pacote de atualizações do sistema operacional** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-256">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="0bdec-257">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-257">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="0bdec-258">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-258">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="0bdec-259">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-259">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="0bdec-260">Criar o pacote do certificado raiz (opcional)</span><span class="sxs-lookup"><span data-stu-id="0bdec-260">Create the root certificate package (optional)</span></span>

<span data-ttu-id="0bdec-261">Você criar este pacote para distribuir o certificado raiz para dispositivos que não estar associado a um domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0bdec-261">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="0bdec-262">Crie este pacote somente se as seguintes condições se aplicam:</span><span class="sxs-lookup"><span data-stu-id="0bdec-262">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="0bdec-263">Sua implantação incluir local Lync ou Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0bdec-263">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="0bdec-264">Unidades de v2 Skype sala sistemas são configuradas para trabalhar em um grupo de trabalho em vez de um membro do domínio.</span><span class="sxs-lookup"><span data-stu-id="0bdec-264">Skype Room Systems v2 units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="0bdec-265">Copie o certificado raiz para a pasta **SRS v2 – pacote do certificado raiz** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-265">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="0bdec-266">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-266">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="0bdec-267">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="0bdec-267">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="0bdec-268">Nome: **SRS v2 – pacote do certificado raiz**</span><span class="sxs-lookup"><span data-stu-id="0bdec-268">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="0bdec-269">Fabricante: *nome da sua organização*</span><span class="sxs-lookup"><span data-stu-id="0bdec-269">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="0bdec-270">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="0bdec-270">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="0bdec-271">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – pacote do certificado raiz** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-271">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="0bdec-272">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-272">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="0bdec-273">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-273">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="0bdec-274">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-274">Select **Close**.</span></span>

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a><span data-ttu-id="0bdec-275">Criar um pacote do kit de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="0bdec-275">Create the Skype Room Systems v2 deployment kit package</span></span>

1.  <span data-ttu-id="0bdec-276">Baixe a versão mais recente do **kit de implantação do Skype sala sistemas v2** de <https://go.microsoft.com/fwlink/?linkid=851168>e instalá-lo a uma estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0bdec-276">Download the latest version of the **Skype Room Systems v2 deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="0bdec-277">Copiar o conteúdo de **c:\\arquivos de programa (x86)\\Kit de implantação do sistema do Skype sala** para a pasta **SRS v2 - SRS pacote de aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-277">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="0bdec-278">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-278">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="0bdec-279">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="0bdec-279">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="0bdec-280">Nome: **SRS v2 – SRS pacote de aplicativos**</span><span class="sxs-lookup"><span data-stu-id="0bdec-280">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="0bdec-281">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="0bdec-281">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="0bdec-282">Versão: **3.1.104.0** (Insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="0bdec-282">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="0bdec-283">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – SRS pacote de aplicativos** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-283">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="0bdec-284">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-284">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="0bdec-285">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-285">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="0bdec-286">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-286">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="0bdec-287">Crie o pacote de atribuição de nome de computador</span><span class="sxs-lookup"><span data-stu-id="0bdec-287">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="0bdec-288">Na pasta **SRS v2 - Set-SRSComputerName pacote** , crie um novo aplicativo de HTML chamado **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-288">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="0bdec-289">Copie o script a seguir para o arquivo de **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-289">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="0bdec-290">Como alternativa, você pode baixar o arquivo Set-SRSComputerName.hta [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="0bdec-290">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="0bdec-291">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-291">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="0bdec-292">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="0bdec-292">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="0bdec-293">Nome: **SRS v2 - Set-SRSComputerName pacote**</span><span class="sxs-lookup"><span data-stu-id="0bdec-293">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="0bdec-294">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="0bdec-294">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="0bdec-295">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="0bdec-295">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="0bdec-296">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - Set-SRSComputerName pacote** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-296">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="0bdec-297">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-297">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="0bdec-298">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-298">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="0bdec-299">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-299">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="0bdec-300">Crie o pacote de Sysprep</span><span class="sxs-lookup"><span data-stu-id="0bdec-300">Create the Sysprep package</span></span>

1. <span data-ttu-id="0bdec-301">Na pasta **SRS v2 – pacote Sysprep** , crie um novo arquivo XML denominado **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-301">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="0bdec-302">Copie o seguinte texto para o arquivo de **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-302">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="0bdec-303">Como alternativa, você pode baixar o arquivo Unattend [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="0bdec-303">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="0bdec-304">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-304">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="0bdec-305">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="0bdec-305">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="0bdec-306">Nome: **SRS v2 - pacote Sysprep**</span><span class="sxs-lookup"><span data-stu-id="0bdec-306">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="0bdec-307">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="0bdec-307">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="0bdec-308">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="0bdec-308">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="0bdec-309">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – pacote Sysprep** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-309">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="0bdec-310">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-310">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="0bdec-311">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-311">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="0bdec-312">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-312">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="0bdec-313">Criar um pacote do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0bdec-313">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="0bdec-314">Obtenha uma mídia Windows 10 Enterprise x64 e copie o arquivo **WIM** para a **sistemas operacionais\\Windows 10 Enterprise** pasta.</span><span class="sxs-lookup"><span data-stu-id="0bdec-314">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="0bdec-315">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Imagens de sistema operacional**e selecione **Adicionar a imagem do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-315">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="0bdec-316">Especifique o caminho para o arquivo **WIM** que você acabou de copiar e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-316">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="0bdec-317">Atualize o campo de **versão** para coincidir com o número de compilação da imagem do Windows 10 Enterprise e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-317">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="0bdec-318">Revise a página de **detalhes** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-318">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="0bdec-319">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-319">Select **Close**.</span></span>

<span data-ttu-id="0bdec-320">Para obter mais informações, consulte [Gerenciar imagens do sistema operacional com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="0bdec-320">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="0bdec-321">Crie pacotes de driver de dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="0bdec-321">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="0bdec-322">Sistemas de sala Skype v2 é suportado para Surface Pro e 4 do Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="0bdec-322">Skype Room Systems v2 is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="0bdec-323">Você precisará criar um pacote de driver para cada modelo Surface Pro, que você tem em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0bdec-323">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bdec-324">Os drivers devem ser compatíveis com a compilação do Windows 10 Enterprise e a versão do Skype sala sistemas v2 deployment kit.</span><span class="sxs-lookup"><span data-stu-id="0bdec-324">The drivers must be compatible with the Windows 10 Enterprise build and the Skype Room Systems v2 deployment kit version.</span></span> <span data-ttu-id="0bdec-325">Para obter mais informações, consulte [Baixe o firmware mais recente e a drivers para dispositivos de superfície](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) e [Configure um console](console.md).</span><span class="sxs-lookup"><span data-stu-id="0bdec-325">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="0bdec-326">Baixe os drivers e o firmware mais recente.</span><span class="sxs-lookup"><span data-stu-id="0bdec-326">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="0bdec-327">Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="0bdec-327">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="0bdec-328">Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="0bdec-328">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="0bdec-329">Extraia o driver baixado e firmware.</span><span class="sxs-lookup"><span data-stu-id="0bdec-329">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="0bdec-330">Abra uma janela de Prompt de comando e no prompt de comando, insira um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="0bdec-330">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="0bdec-331">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Drivers**e, em seguida, selecione **O Driver de importação**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-331">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="0bdec-332">Selecione **importar todos os drivers no seguinte caminho de rede (UNC)**, selecione a pasta de origem (por exemplo, c\\_Sources\\Drivers\\Surface Pro) e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-332">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="0bdec-333">Na página **especificar os detalhes para os drivers importados** , selecione todos os drivers listados e selecione **Habilitar esses drivers e permitir que os computadores instalá-los**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-333">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="0bdec-334">Selecione **categorias**, criar uma nova categoria que coincide com o modelo de superfície, selecione **Okey**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-334">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="0bdec-335">Selecione o **novo pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-335">Select **New Package**.</span></span>

8.  <span data-ttu-id="0bdec-336">Especifique o nome do pacote que coincide com o modelo Surface Pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver em, selecione **Okey**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-336">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="0bdec-337">Na página de **imagens de inicialização** , certifique-se de que nenhum imagens de inicialização são selecionadas e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-337">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="0bdec-338">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-338">Select **Close**.</span></span>

11. <span data-ttu-id="0bdec-339">Vá para a **Biblioteca de Software** \> **sistemas operacionais** \> **Drivers**, selecione **pasta \> criar pasta**e insira um nome de pasta que coincide com o modelo Surface Pro que você acabou de importar os drivers para.</span><span class="sxs-lookup"><span data-stu-id="0bdec-339">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="0bdec-340">Mova todos os drivers importados para a pasta recém-criada para fácil navegação e a operação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-340">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="0bdec-341">Repita as mesmas etapas para outros modelos Surface Pro, que talvez seja necessário.</span><span class="sxs-lookup"><span data-stu-id="0bdec-341">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="0bdec-342">Para obter mais informações, consulte [Gerenciar drivers no System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="0bdec-342">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

### <a name="create-skype-room-system-configuration-package"></a><span data-ttu-id="0bdec-343">Criar um pacote de configuração do sistema de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="0bdec-343">Create Skype Room System Configuration Package</span></span>

1.  <span data-ttu-id="0bdec-344">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-344">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="0bdec-345">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="0bdec-345">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="0bdec-346">Nome: **SRS v2 - configurar o pacote de instalação do SRS**</span><span class="sxs-lookup"><span data-stu-id="0bdec-346">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="0bdec-347">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="0bdec-347">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="0bdec-348">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="0bdec-348">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="0bdec-349">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - configurar SRS instalação** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-349">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="0bdec-350">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-350">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="0bdec-351">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-351">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="0bdec-352">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-352">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="0bdec-353">Distribuir pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bdec-353">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="0bdec-354">Todos os pacotes devem ser distribuídos para os servidores que tiverem sido atribuídos a função de ponto de distribuição na hierarquia do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0bdec-354">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="0bdec-355">Siga as instruções abaixo para iniciar a distribuição de pacote.</span><span class="sxs-lookup"><span data-stu-id="0bdec-355">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="0bdec-356">Distribua os pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="0bdec-356">Distribute software packages.</span></span>

    1.  <span data-ttu-id="0bdec-357">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-357">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="0bdec-358">Selecione todos os pacotes de software que você deseja distribuir e selecione **Distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-358">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="0bdec-359">Revise a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-359">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="0bdec-360">Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-360">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="0bdec-361">Selecione **Avançar**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-361">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="0bdec-362">Distribua os pacotes de driver.</span><span class="sxs-lookup"><span data-stu-id="0bdec-362">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="0bdec-363">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Pacotes de Driver**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-363">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="0bdec-364">Selecione todos os pacotes de driver que você deseja distribuir e selecione **Distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-364">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="0bdec-365">Revise a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-365">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="0bdec-366">Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-366">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="0bdec-367">Selecione **Avançar**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-367">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="0bdec-368">Distribua os pacotes do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0bdec-368">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="0bdec-369">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Imagens do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="0bdec-370">Selecione todas as imagens de sistema operacional que você deseja distribuir e selecione **Distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-370">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="0bdec-371">Revise a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-371">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="0bdec-372">Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-372">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="0bdec-373">Selecione **Avançar**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-373">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="0bdec-374">Distribuição de pacote pode levar algum tempo, dependendo do tamanho do pacote, hierarquia do Configuration Manager, número de servidores de ponto de distribuição e a largura de banda disponível em sua rede.</span><span class="sxs-lookup"><span data-stu-id="0bdec-374">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="0bdec-375">Todos os pacotes devem ser distribuídos antes de começar a implantação de uma unidade de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="0bdec-375">All the packages must be distributed before you can start deploying a Skype Room Systems v2 unit.</span></span>
> 
> <span data-ttu-id="0bdec-376">Você pode examinar o status da sua distribuição de pacote no console do Configuration Manager indo para **monitoramento** \> **Status de distribuição** \> **Status do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-376">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="0bdec-377">Sequências de tarefas do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bdec-377">Configuration Manager task sequences</span></span>

<span data-ttu-id="0bdec-378">Use sequências de tarefas com o System Center Configuration Manager para automatizar as etapas de implantação de uma imagem do sistema operacional em um computador de destino.</span><span class="sxs-lookup"><span data-stu-id="0bdec-378">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="0bdec-379">Para implantar uma unidade de v2 Skype sala sistemas de forma automática, você cria uma sequência de tarefa que faz referência a imagem de inicialização usada para iniciar o computador de destino de sistemas de sala Skype v2, a imagem do sistema operacional Windows 10 Enterprise que você deseja instalar e qualquer outro conteúdo adicional, como outros aplicativos ou atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="0bdec-379">To deploy a Skype Room Systems v2 unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Skype Room Systems v2 computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="0bdec-380">Importar a sequência de tarefas de amostra</span><span class="sxs-lookup"><span data-stu-id="0bdec-380">Import the sample task sequence</span></span>

<span data-ttu-id="0bdec-381">Você pode baixar e facilmente importar uma sequência de tarefas de amostra e personalizá-lo para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="0bdec-381">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="0bdec-382">[**Baixe**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) a sequência de tarefas de amostra e copiar o arquivo zip baixado em um local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-382">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="0bdec-383">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Sequências de tarefas**e, em seguida, selecione **Importar sequência de tarefa**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-383">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="0bdec-384">Selecione **navegar**, vá para o local de pasta compartilhada que você usou na etapa 1, selecione o arquivo **. zip do Skype sala sistemas v2 implantação (EN-US)** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-384">Select **Browse**, go to the shared folder location you used in step 1, select the **Skype Room Systems v2 Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="0bdec-385">Definir a **ação** para **Criar novo**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-385">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="0bdec-386">Confirme as configurações e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-386">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="0bdec-387">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-387">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="0bdec-388">Valide que os pacotes de referência corretamente vinculados a cada etapa de sequência de tarefa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-388">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="0bdec-389">Selecione a sequência de tarefa importada e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-389">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="0bdec-390">O Editor de sequência de tarefas abre e exibe cada etapa sequencial que você precisa para implantar e configurar uma unidade de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="0bdec-390">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Skype Room Systems v2 unit.</span></span>

2. <span data-ttu-id="0bdec-391">Percorrer cada etapa e preencha as atualizações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="0bdec-391">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="0bdec-392">**Reinicie o Windows PE**: esta etapa é reiniciado e carrega o computador Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="0bdec-392">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="0bdec-393">Nenhuma alteração é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-393">No changes are required for this step.</span></span>

   2. <span data-ttu-id="0bdec-394">**Partição de disco 0 – UEFI**: esta etapa apaga a configuração do disco e cria partições com base em configurações definidas.</span><span class="sxs-lookup"><span data-stu-id="0bdec-394">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="0bdec-395">Recomendamos que você não faça alterações para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-395">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="0bdec-396">**Definir nome do computador SRS**: esta etapa inclui um aplicativo de HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade de v2 Skype sala sistemas durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-396">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Skype Room Systems v2 unit during the deployment.</span></span>
      -  <span data-ttu-id="0bdec-397">Esta é uma etapa opcional, mas ele pode ser desabilitado apenas se você quiser gerenciar por meio de um processo alternativo de nomeação do computador.</span><span class="sxs-lookup"><span data-stu-id="0bdec-397">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="0bdec-398">Verifique se o pacote **SRS v2 - Set-SRSComputerName** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-398">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="0bdec-399">Se não for, navegue até o pacote e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="0bdec-399">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="0bdec-400">**Aplicar o sistema de operacional**: esta etapa Especifica a imagem do sistema operacional a serem implantados e o arquivo de resposta Sysprep autônoma usar.</span><span class="sxs-lookup"><span data-stu-id="0bdec-400">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="0bdec-401">Verifique se o arquivo de imagem de sistema operacional Windows 10 Enterprise correto está selecionado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-401">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="0bdec-402">Verifique se **usar uma autônoma ou Sysprep o arquivo de resposta para uma instalação personalizada** está habilitado, e o **SRS v2 - pacote Sysprep** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="0bdec-402">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="0bdec-403">Além disso, certifique-se de que o **Nome de arquivo** está definido como **Unattend. XML**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-403">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="0bdec-404">**Aplicar configurações do Windows**: esta etapa reúne informações sobre a instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="0bdec-404">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="0bdec-405">Fornecer informações de registro e de licenciamento, incluindo a chave do produto, senha da conta de administrador local e fuso horário (dependendo das suas necessidades).</span><span class="sxs-lookup"><span data-stu-id="0bdec-405">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="0bdec-406">**Aplicar configurações de rede**: esta etapa permite especificar um grupo de trabalho ou o nome de domínio do Active Directory e a unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="0bdec-406">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="0bdec-407">Consulte [Considerações de ingresso de domínio do sistema de sala do Skype](domain-joining-considerations.md) para ações recomendadas que você precisa para implantar unidades v2 de sistemas de sala Skype como membros de um domínio Actve Directory.</span><span class="sxs-lookup"><span data-stu-id="0bdec-407">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Skype Room Systems v2 units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="0bdec-408">**Aplicar Drivers:** Esta etapa e seus subetapas são usadas para implantar baseada no modelo do Surface Pro, que você tem de firmware e drivers de dispositivo aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="0bdec-408">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="0bdec-409">Atualize cada etapa para especificar o pacote de driver relevantes associado com essa implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-409">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="0bdec-410">Cada pacote de driver é configurado para aproveitar os filtros Windows Management Instrumentation (WMI) para implantar drivers relevantes e firmware com base em o Surface Pro marca e modelo.</span><span class="sxs-lookup"><span data-stu-id="0bdec-410">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="0bdec-411">É altamente recomendável que você não alterar a configuração desses drivers, caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="0bdec-411">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="0bdec-412">**Configurar o Windows e o Configuration Manager**: esta etapa implanta e configura o cliente do Gerenciador de configuração.</span><span class="sxs-lookup"><span data-stu-id="0bdec-412">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="0bdec-413">Atualize esta etapa para especificar o pacote de cliente interno do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0bdec-413">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="0bdec-414">**Instalar o certificado de raiz**: esta etapa distribui o certificado raiz para dispositivos não – associados a um domínio e, portanto, é opcional, mas desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0bdec-414">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="0bdec-415">Habilite esta etapa se você precisa para implantar um certificado raiz para as unidades de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="0bdec-415">Enable this step if you need to deploy a root certificate to the Skype Room Systems v2 units.</span></span>
      -   <span data-ttu-id="0bdec-416">Se você precisar realizar esta etapa, verifique o **SRS v2 – pacote do certificado raiz** e o **redirecionamento de sistema de arquivo desabilitar 64 bits** são selecionados.</span><span class="sxs-lookup"><span data-stu-id="0bdec-416">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="0bdec-417">**Instalar e configurar o agente de OMS**: essa etapa instala a versão de 64 bits do agente do pacote de gerenciamento de operações do Microsoft e configura o agente para se conectar ao seu espaço de trabalho de análise de Log.</span><span class="sxs-lookup"><span data-stu-id="0bdec-417">**Install and Configure OMS Agent**: This step installs the 64-bit version of the Microsoft Operations Management Suite agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="0bdec-418">Esta etapa é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="0bdec-418">This step is disabled by default.</span></span> <span data-ttu-id="0bdec-419">Habilite esta etapa somente se você vai usar OMS para monitorar a integridade de unidades de v2 seus sistemas de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="0bdec-419">Enable this step only if you’re going to use OMS to monitor the health of your Skype Room Systems v2 units.</span></span>
       -   <span data-ttu-id="0bdec-420">Editar esta etapa e atualizar os parâmetros de linha de comando para especificar sua **ID de espaço de trabalho** e a **Chave do espaço de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-420">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="0bdec-421">Consulte [computadores com Windows se conectar ao serviço de Log de análise no Windows Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) para obter mais informações sobre como obter a ID de espaço de trabalho de pacote de gerenciamento de operações e a chave primária.</span><span class="sxs-lookup"><span data-stu-id="0bdec-421">See [Connect Windows computers to the Log Analytics service in Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="0bdec-422">Verifique se que o **redirecionamento de sistema de arquivo desabilitar 64 bits** e **SRS v2 – pacote do agente do Microsoft OMS** estão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="0bdec-422">Verify that the **SRS v2 – Microsoft OMS Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="0bdec-423">Para obter mais informações sobre como monitorar a integridade da sua implantação do Skype sala sistemas v2, consulte [gerenciamento de v2 de sistemas de sala Skype planejar com OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) e [gerenciamento de v2 implantar sistemas do Skype sala com OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span><span class="sxs-lookup"><span data-stu-id="0bdec-423">For more information about monitoring the health of your Skype Room Systems v2 deployment, see [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) and [Deploy Skype Room Systems v2 management with OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span></span>

   11. <span data-ttu-id="0bdec-424">**Arquivos de configuração de v2 SRS de cópia**: esta etapa copia os arquivos de instalação e configuração necessários do kit de implantação do Skype sala sistemas v2 para o disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="0bdec-424">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Skype Room Systems v2 deployment kit to the local hard drive.</span></span> <span data-ttu-id="0bdec-425">Sem personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-425">No customization is required for this step.</span></span>
       -   <span data-ttu-id="0bdec-426">Verifique se o **SRS v2 – SRS pacote de aplicativo** e o **redirecionamento de sistema de arquivo desabilitar 64 bits** são selecionado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-426">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="0bdec-427">**Install-SRSv2-atualizações de sistema operacional**: essa etapa implanta quaisquer atualizações de obrigatório do sistema operacional necessárias com a implantação de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="0bdec-427">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Skype Room Systems v2 deployment.</span></span> <span data-ttu-id="0bdec-428">Do the following:</span><span class="sxs-lookup"><span data-stu-id="0bdec-428">Do the following:</span></span>
       -   <span data-ttu-id="0bdec-429">Verifique o [console de configurar um v2 de sistemas de sala Skype](console.md) para ver quais atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="0bdec-429">Check [Configure a Skype Room Systems v2 console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="0bdec-430">Verifique se seu **SRS v2 – pacote de atualizações do sistema operacional** inclui todas as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="0bdec-430">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="0bdec-431">Verifique se o **SRS v2 – pacote de atualizações do sistema operacional** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-431">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="0bdec-432">Verifique se a diretiva de execução do PowerShell é definida para **desvio**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-432">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="0bdec-433">**Reiniciar o computador**: esta etapa reinicializa o computador depois que as atualizações obrigatórias de sistema operacional estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="0bdec-433">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="0bdec-434">Sem personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-434">No customization is required for this step.</span></span>

   14. <span data-ttu-id="0bdec-435">**Configurar componentes do Windows**: esta etapa configura os recursos necessários do Windows.</span><span class="sxs-lookup"><span data-stu-id="0bdec-435">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="0bdec-436">Sem personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-436">No customization is required for this step.</span></span>

   15. <span data-ttu-id="0bdec-437">**Reiniciar o computador**: esta etapa reinicializa o computador depois que os recursos do Windows são configurados.</span><span class="sxs-lookup"><span data-stu-id="0bdec-437">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="0bdec-438">Sem personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-438">No customization is required for this step.</span></span>

   16. <span data-ttu-id="0bdec-439">**Adicionar usuário Local do Skype**: essa etapa cria a conta do Skype local usada para entrar no Windows e inicie o aplicativo do Skype sala sistemas v2 automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0bdec-439">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Skype Room Systems v2 application.</span></span> <span data-ttu-id="0bdec-440">Esta etapa não tem nenhum pacote de software associado a ela, e sem personalização é necessária para ele.</span><span class="sxs-lookup"><span data-stu-id="0bdec-440">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="0bdec-441">**Definido para cima e para configurar o aplicativo de SRS**: esta etapa configura a instalação do aplicativo Skype sala sistemas v2 para a próxima inicialização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0bdec-441">**Set up and configure SRS application**: This step configures the Skype Room Systems v2 application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="0bdec-442">Verifique se que o **redirecionamento de sistema de arquivo desabilitar 64 bits** e **SRS v2 – configurar pacote de instalação do SRS** estão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="0bdec-442">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bdec-443">É muito importante que as etapas de sequência de tarefa devem ser na ordem fornecida.</span><span class="sxs-lookup"><span data-stu-id="0bdec-443">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="0bdec-444">Modificar a ordem das etapas ou etapas adicionais de configuração pode interromper a implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-444">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="0bdec-445">**Definido para cima e para configurar o aplicativo de SRS** etapa deve ser a última etapa na sequência de tarefas, caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="0bdec-445">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="0bdec-446">Criar a implantação da sequência de tarefas</span><span class="sxs-lookup"><span data-stu-id="0bdec-446">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="0bdec-447">Selecione a sequência de tarefas e selecione **implantar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-447">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="0bdec-448">Selecione **Procurar** para selecionar o conjunto de destino para implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-448">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="0bdec-449">Selecione **Todos os computadores desconhecido** e selecione **Okey**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-449">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="0bdec-450">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-450">Select **Next**.</span></span>

5. <span data-ttu-id="0bdec-451">Selecione **disponível** na lista suspensa **finalidade** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-451">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="0bdec-452">Selecione **apenas a mídia e PXE** na lista **disponibilizar o seguinte** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-452">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="0bdec-453">É muito importante que o **objetivo** é definido como **disponível**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-453">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="0bdec-454">Certifique-se de que o **objetivo** é **não** definido como **obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-454">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="0bdec-455">Também Certifique-se de que você selecione **apenas a mídia e PXE** nos **tornar disponível para o seguinte**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-455">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="0bdec-456">Configurar esses valores para algo diferente pode fazer com que todos os computadores obter a imagem de implantação de sistemas de sala Skype quando inicializado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-456">Setting these values to something else might cause all computers to get the Skype Room Systems deployment image when booted.</span></span>
7. <span data-ttu-id="0bdec-457">Não especifique qualquer agenda e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-457">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="0bdec-458">Não altere qualquer coisa dentro da seção **Experiência do usuário** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-458">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="0bdec-459">Não altere qualquer coisa dentro da seção de **alertas** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-459">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="0bdec-460">Não altere qualquer coisa dentro da seção de **Pontos de distribuição** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-460">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="0bdec-461">Confirme as configurações e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-461">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="0bdec-462">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-462">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="0bdec-463">Validar e solucionar problemas da solução</span><span class="sxs-lookup"><span data-stu-id="0bdec-463">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="0bdec-464">Depois de concluir as sequências de tarefas do System Center Configuration Manager, você precisará executar um teste para validar que a sequência de tarefa pode implantar e configurar unidades de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="0bdec-464">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Skype Room Systems v2 units.</span></span>

1.  <span data-ttu-id="0bdec-465">Conecte o dispositivo de teste à rede com fio, usando um dos adaptadores Ethernet suportados ou usando a superfície encaixe.</span><span class="sxs-lookup"><span data-stu-id="0bdec-465">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="0bdec-466">Se a funcionalidade de inicialização PXE não tiver sido configurada para o seu ambiente, você pode usar a imagem de inicialização no USB unidade flash [que você criou anteriormente](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) para inicializar a partir do USB e conecte-se ao Gerenciador de configuração.</span><span class="sxs-lookup"><span data-stu-id="0bdec-466">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="0bdec-467">Acessar o firmware e iniciar os inicialização PXE:</span><span class="sxs-lookup"><span data-stu-id="0bdec-467">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="0bdec-468">Certifique-se de que o dispositivo de superfície é desligado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-468">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="0bdec-469">Pressione e mantenha pressionado o botão de **Volume para cima** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-469">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="0bdec-470">Pressione e solte o botão de **energia** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-470">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="0bdec-471">Após o dispositivo começa a inicialização, solte o botão de **Volume para cima** .</span><span class="sxs-lookup"><span data-stu-id="0bdec-471">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="0bdec-472">Selecione a **configuração de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-472">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="0bdec-473">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="0bdec-473">Do one of the following:</span></span>

        -   <span data-ttu-id="0bdec-474">Selecione **inicialização PXE**e arraste-o para o topo da lista.</span><span class="sxs-lookup"><span data-stu-id="0bdec-474">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="0bdec-475">Como alternativa, você poderá passar esquerda no adaptador de rede para inicializar o dispositivo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0bdec-475">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="0bdec-476">Isso não afetará a ordem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="0bdec-476">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="0bdec-477">Selecione a unidade flash USB que contém a mídia de inicialização.</span><span class="sxs-lookup"><span data-stu-id="0bdec-477">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="0bdec-478">Selecione **Sair**e, em seguida, selecione **Reiniciar agora**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-478">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="0bdec-479">Quando solicitado, selecione **Enter** para serviço de inicialização de rede.</span><span class="sxs-lookup"><span data-stu-id="0bdec-479">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="0bdec-480">Windows PE carregará na memória e iniciará o Assistente de sequência de tarefa.</span><span class="sxs-lookup"><span data-stu-id="0bdec-480">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="0bdec-481">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="0bdec-481">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="0bdec-482">Selecione a sequência de tarefas que você importou anteriormente e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0bdec-482">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="0bdec-483">Depois que a configuração de disco for aplicada, você será solicitado que especifique um nome de computador para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bdec-483">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="0bdec-484">A interface do usuário exibirá o nome de um computador recomendada com base no número de série do dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="0bdec-484">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="0bdec-485">Você pode aceitar o nome proposto ou especifique um novo.</span><span class="sxs-lookup"><span data-stu-id="0bdec-485">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="0bdec-486">Siga as instruções na tela de atribuição de nome do computador.</span><span class="sxs-lookup"><span data-stu-id="0bdec-486">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="0bdec-487">Quando você selecionar **Aceitar**, começa a implantação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-487">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="0bdec-488">O restante do processo de implantação é automático e não pede qualquer entrada do usuário mais.</span><span class="sxs-lookup"><span data-stu-id="0bdec-488">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="0bdec-489">Depois que a sequência de tarefas de implantação estiver concluída, configurando o dispositivo, você verá a tela configuração a seguir que solicita a definir as configurações de aplicativo do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="0bdec-489">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Skype Room Systems v2 application settings.</span></span>

    ![Tela de instalação inicial para o aplicativo de v2 de sistemas de sala do Skype](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="0bdec-491">Conecte o Surface Pro no console do v2 Skype sistemas de sala e definir as configurações de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0bdec-491">Plug the Surface Pro into the Skype Room Systems v2 console, and configure the application settings.</span></span>

11.  <span data-ttu-id="0bdec-492">Valide se os recursos listados na [Ajuda do Skype sala sistemas v2](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estão funcionando no dispositivo implantado.</span><span class="sxs-lookup"><span data-stu-id="0bdec-492">Validate that the capabilities listed in [Skype Room Systems v2 help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="0bdec-493">Para solucionar problemas de uma falha na instalação, verifique o arquivo **SMSTS** , que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0bdec-493">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="0bdec-494">O arquivo SMSTS é armazenado em um dos vários caminhos, dependendo do estágio do processo de compilação.</span><span class="sxs-lookup"><span data-stu-id="0bdec-494">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="0bdec-495">Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS.</span><span class="sxs-lookup"><span data-stu-id="0bdec-495">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="0bdec-496">**Fase de implantação**</span><span class="sxs-lookup"><span data-stu-id="0bdec-496">**Deployment phase**</span></span>                                                            | <span data-ttu-id="0bdec-497">**Caminho de log de sequência de tarefa**</span><span class="sxs-lookup"><span data-stu-id="0bdec-497">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="0bdec-498">WinPE, antes de formato HDD</span><span class="sxs-lookup"><span data-stu-id="0bdec-498">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="0bdec-499">X:\\Windows\\Temp\\smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="0bdec-499">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="0bdec-500">WinPE, após o formato HDD</span><span class="sxs-lookup"><span data-stu-id="0bdec-500">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="0bdec-501">C:\\_SMSTaskSequence\\Logs\\Smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="0bdec-501">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="0bdec-502">Sistema operacional implantado, antes que o agente do Configuration Manager foi instalado</span><span class="sxs-lookup"><span data-stu-id="0bdec-502">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="0bdec-503">c:\\_SMSTaskSequence\\Logs\\Smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="0bdec-503">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="0bdec-504">Sistema operacional e o agente do Configuration Manager implantado</span><span class="sxs-lookup"><span data-stu-id="0bdec-504">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="0bdec-505">% windir %\\System32\\ccm\\logs\\Smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="0bdec-505">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="0bdec-506">Execução de sequência de tarefa concluída</span><span class="sxs-lookup"><span data-stu-id="0bdec-506">Task sequence execution complete</span></span>                                                | <span data-ttu-id="0bdec-507">% windir %\\System32\\ccm\\logs\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="0bdec-507">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="0bdec-508">Você pode selecionar **F8** a qualquer momento durante a sequência de tarefas para abrir um console de comando e, em seguida, obter acesso ao arquivo SMSTS.</span><span class="sxs-lookup"><span data-stu-id="0bdec-508">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="0bdec-509">Para solucionar problemas de inicialização PXE, verifique os dois arquivos de log no servidor do Gerenciador de configuração que são específicos para ações de PXE:</span><span class="sxs-lookup"><span data-stu-id="0bdec-509">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="0bdec-510">**Pxecontrol.log**, localizado no diretório de logs de instalação do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bdec-510">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="0bdec-511">**Smspxe.log**, localizado no diretório de logs do ponto de gerenciamento do Gerenciador de configuração (MP)</span><span class="sxs-lookup"><span data-stu-id="0bdec-511">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="0bdec-512">Para obter uma lista completa dos arquivos de log que você pode usar para solucionar ainda mais a sua instalação do Configuration Manager, consulte [arquivos de Log no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="0bdec-512">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
