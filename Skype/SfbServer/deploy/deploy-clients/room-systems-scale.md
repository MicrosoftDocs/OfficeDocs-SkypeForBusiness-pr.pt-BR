---
title: Implantar sistemas de sala Skype usando o System Center Configuration Manager
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este tópico para saber mais sobre como implantar sistemas de sala Skype v2 em implantações de grande escala.
ms.openlocfilehash: 33ac42e42695a7881d6348aee32046223f97b418
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2018
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a><span data-ttu-id="b98f3-103">Implantar sistemas de sala Skype v2 usando o System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b98f3-103">Deploy Skype Room Systems v2 by using System Center Configuration Manager</span></span>

<span data-ttu-id="b98f3-104">Este artigo fornece todas as informações necessárias para criar suas implantações do Skype sala sistemas v2 usando o System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b98f3-104">This article gives you all the necessary information to create your Skype Room Systems v2 deployments by using System Center Configuration Manager.</span></span>

<span data-ttu-id="b98f3-105">Com os métodos de fácil utilização fornecidos pelo System Center Configuration Manager, você pode implantar o sistema operacional e outros aplicativos em vários dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="b98f3-105">With the easy-to-use methods provided by System Center Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="b98f3-106">Usar a abordagem ilustrada abaixo para orientá-lo a configuração do Configuration Manager e personalize os pacotes de amostra e os scripts fornecidos no decorrer deste guia, conforme necessário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b98f3-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Processo de implantação do Skype sala sistemas v2 usando o Configuration Manager](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="b98f3-108">Essa solução foi testada apenas com implantações baseadas em Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="b98f3-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="b98f3-109">Siga as diretrizes do fabricante para configurações que não são baseadas em Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="b98f3-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="b98f3-110">Valide os pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b98f3-110">Validate prerequisites</span></span>

<span data-ttu-id="b98f3-111">Para implantar sistemas de sala Skype v2 com o Configuration Manager, certifique-se de que você atende os seguintes pré-requisitos e requisitos.</span><span class="sxs-lookup"><span data-stu-id="b98f3-111">To deploy Skype Room Systems v2 with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="system-center-configuration-manager-requirements"></a><span data-ttu-id="b98f3-112">Requisitos do System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b98f3-112">System Center Configuration Manager requirements</span></span>

-   <span data-ttu-id="b98f3-113">Versão do System Center Configuration Manager deve ser de pelo menos 1706 ou acima.</span><span class="sxs-lookup"><span data-stu-id="b98f3-113">System Center Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="b98f3-114">É recomendável usar 1710 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b98f3-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="b98f3-115">Confira o [suporte para o Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) para saber mais sobre as versões do Windows 10 Configuration Manager oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="b98f3-115">Check out [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="b98f3-116">Uma versão compatível do Windows Assessment e Kit de implantação (ADK) para Windows 10 deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="b98f3-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="b98f3-117">Consulte as versões do [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que você pode usar com diferentes versões do Configuration Manager e certifique-se de que sua implantação incluir a versão correta.</span><span class="sxs-lookup"><span data-stu-id="b98f3-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="b98f3-118">Os servidores de sistema do site devem ser atribuídos a função de ponto de distribuição e as imagens de inicialização devem ser habilitadas para [preboot suporte do ambiente (PXE) de execução](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) habilitar implantações iniciadas de rede.</span><span class="sxs-lookup"><span data-stu-id="b98f3-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="b98f3-119">Se o suporte a PXE não estiver habilitado, você pode usar a [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações.</span><span class="sxs-lookup"><span data-stu-id="b98f3-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="b98f3-120">Uma conta de acesso de rede deve ser configurada para oferecer suporte a novos cenários de implantação de computador (bare metal).</span><span class="sxs-lookup"><span data-stu-id="b98f3-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="b98f3-121">Para saber mais sobre a configuração de uma conta de acesso de rede, consulte [Gerenciar contas para acessar o conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="b98f3-121">To learn more about the configuration of a network access account, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="b98f3-122">Recomendamos que você habilite o [suporte ao multicast](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), se você provavelmente precisará implantar a imagem de v2 Skype sala sistemas mesma várias unidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b98f3-122">We recommend that you enable [multicast support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Skype Room Systems v2 image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="b98f3-123">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="b98f3-123">Networking requirements</span></span>

-   <span data-ttu-id="b98f3-124">Sua rede deve ter um servidor Dynamic Host Configuration Protocol (DHCP), configurado para distribuição automática de endereço IP para as sub-redes onde unidades do Skype sala sistemas v2 serão implantadas.</span><span class="sxs-lookup"><span data-stu-id="b98f3-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Skype Room Systems v2 units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b98f3-125">Duração de concessão DHCP deve ser definida como um valor maior que a duração de implantação de imagem.</span><span class="sxs-lookup"><span data-stu-id="b98f3-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="b98f3-126">Caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="b98f3-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="b98f3-127">Sua rede, incluindo comutadores e LANs virtuais (VLANs), deve ser configurado para oferecer suporte a PXE.</span><span class="sxs-lookup"><span data-stu-id="b98f3-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="b98f3-128">Consulte seu fornecedor de rede para obter mais informações sobre a configuração IP Helper e PXE.</span><span class="sxs-lookup"><span data-stu-id="b98f3-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="b98f3-129">Como alternativa, você pode usar [mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) para suas implantações, se o suporte PXE não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b98f3-130">Para Surface Pro dispositivos, inicialização a partir da rede (inicialização PXE) só são suportados quando você usa um adaptador de Ethernet ou estação de encaixe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b98f3-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="b98f3-131">Adaptadores de Ethernet de terceiros não oferecem suporte a inicialização PXE com Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="b98f3-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="b98f3-132">Para obter mais informações, consulte [implantação de superfície e adaptadores Ethernet](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .</span><span class="sxs-lookup"><span data-stu-id="b98f3-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="b98f3-133">Configurar o System Center Configuration Manager para implantação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="b98f3-133">Configure System Center Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="b98f3-134">Este artigo pressupõe que você já possui uma implantação do System Center Configuration Manager íntegro e não detalhes de todas as etapas necessárias para implantar e configurar o Gerenciador de configuração do zero.</span><span class="sxs-lookup"><span data-stu-id="b98f3-134">This article assumes you already have a healthy System Center Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="b98f3-135">A [documentação e as diretrizes de configuração](https://docs.microsoft.com/sccm/) no System Center Configuration Manager é um ótimo recurso; Recomendamos que você comece com esses recursos, se você ainda não tenha implantado o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b98f3-135">The [documentation and the configuration guidance](https://docs.microsoft.com/sccm/) on the System Center Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="b98f3-136">Use as instruções a seguir para verificar se os recursos de implantação (OSD) do sistema operacional estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="b98f3-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="b98f3-137">Validar e atualizar o Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b98f3-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="b98f3-138">No console do Configuration Manager, vá para **Administração** \> **atualizações e manutenção**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="b98f3-139">Verifique a compilação instalada e atualizações aplicáveis que ainda não tenham sido instaladas.</span><span class="sxs-lookup"><span data-stu-id="b98f3-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="b98f3-140">Revise o [suporte para Windows 10 no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Se você precisar atualizar a implantação, selecione a atualização que você deseja instalar e, em seguida, selecione **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-140">Review [Support for Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="b98f3-141">Quando o download for concluído, selecione a atualização e, em seguida, selecione **Instalar o pacote de atualização**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="b98f3-142">Configurar os pontos de distribuição para oferecer suporte a PXE e multicast</span><span class="sxs-lookup"><span data-stu-id="b98f3-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="b98f3-143">No console do Configuration Manager, vá para **Administração** \> **Pontos de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="b98f3-144">Selecione o servidor de ponto de distribuição que atender a implantação do Skype sala sistemas v2 e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-144">Select the distribution point server that will serve the Skype Room Systems v2 deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="b98f3-145">Selecione a guia **PXE** e certifique-se de que as configurações a seguir estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="b98f3-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span> 
    -   <span data-ttu-id="b98f3-146">Habilitar o suporte a PXE para clientes</span><span class="sxs-lookup"><span data-stu-id="b98f3-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="b98f3-147">Permitir que esse ponto de distribuição responder às solicitações de entrada PXE</span><span class="sxs-lookup"><span data-stu-id="b98f3-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="b98f3-148">Habilitar o suporte de computador desconhecido</span><span class="sxs-lookup"><span data-stu-id="b98f3-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="b98f3-149">*Opcional:* Para habilitar o suporte ao multicast, selecione a guia **Multicast** e certifique-se de que as configurações a seguir estão habilitadas:</span><span class="sxs-lookup"><span data-stu-id="b98f3-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="b98f3-150">Habilitar multicast simultaneamente enviar dados para vários clientes</span><span class="sxs-lookup"><span data-stu-id="b98f3-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="b98f3-151">Configurar o intervalo de portas UDP conforme recomendação da sua equipe de rede</span><span class="sxs-lookup"><span data-stu-id="b98f3-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="b98f3-152">Configurar a conta de acesso de rede</span><span class="sxs-lookup"><span data-stu-id="b98f3-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="b98f3-153">No console do Configuration Manager, vá para **Administração** \> **Configuração de Site** \> **Sites**e selecione o site.</span><span class="sxs-lookup"><span data-stu-id="b98f3-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="b98f3-154">No grupo **configurações** , selecione **Configurar componentes de Site** \> **A distribuição de Software**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="b98f3-155">Selecione a guia de **Conta de acesso de rede** Set up uma ou mais contas e selecione **Okey**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="b98f3-156">As contas não precisam quaisquer direitos especiais, exceto para o **acesso a este computador a partir da rede** diretamente no servidor de ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="b98f3-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="b98f3-157">Uma conta de usuário de domínio genérico será apropriada.</span><span class="sxs-lookup"><span data-stu-id="b98f3-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="b98f3-158">Para obter mais informações, consulte [Gerenciar contas para acessar o conteúdo no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span><span class="sxs-lookup"><span data-stu-id="b98f3-158">For more information, see [Manage accounts to access content in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="b98f3-159">Configurar uma imagem de inicialização</span><span class="sxs-lookup"><span data-stu-id="b98f3-159">Configure a boot image</span></span>

1.  <span data-ttu-id="b98f3-160">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistema operacional** \> **Imagens de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="b98f3-161">Selecione a **imagem de inicialização (x64)** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="b98f3-162">Selecione a guia **Fonte de dados** e habilite **implantar essa imagem de inicialização do ponto de distribuição habilitado para PXE**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="b98f3-163">Selecione a guia **Componentes opcionais** para instalar os componentes necessários:</span><span class="sxs-lookup"><span data-stu-id="b98f3-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="b98f3-164">Selecione o ícone de estrela e procurar **HTML (HTA WinPE)**</span><span class="sxs-lookup"><span data-stu-id="b98f3-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="b98f3-165">Selecione **Okey** para adicionar suporte a aplicativos em HTML para a imagem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="b98f3-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="b98f3-166">*Opcional:* Para personalizar a experiência de implantação, selecione a guia de **personalização** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="b98f3-167">Habilite o **comando suporte (somente para teste)** se você deseja que tenham acesso a um prompt de comando durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="b98f3-168">Quando esta opção estiver ativada, você pode iniciar um prompt de comando, selecionando F8 a qualquer momento durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-168">When this is enabled, you can         start a command prompt by selecting F8 at any time during the deployment.</span></span>
    -   <span data-ttu-id="b98f3-169">Você também pode especificar uma imagem de plano de fundo personalizado a ser exibida durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="b98f3-170">Para definir uma imagem, habilitar **especificar o arquivo de imagem de plano de fundo personalizado (caminho UNC** e selecione seu plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="b98f3-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="b98f3-171">Quando solicitado, selecione **Sim** e distribuir a imagem de inicialização atualizada para seus pontos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="b98f3-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="b98f3-172">Para obter mais informações, consulte [imagens de inicialização de gerenciar com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span><span class="sxs-lookup"><span data-stu-id="b98f3-172">For more information, see [Manage boot images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="b98f3-173">Você pode criar uma mídia USB inicializável para lançar implantações de baseadas em sequência de tarefa Configuration Manager para ambientes que não oferece suporte a PXE.</span><span class="sxs-lookup"><span data-stu-id="b98f3-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="b98f3-174">A mídia inicializável contém apenas a imagem de inicialização, comandos prestart opcionais e seus arquivos necessários e binários do Configuration Manager para oferecer suporte à inicialização no Windows PE e conectando-se ao Gerenciador de configuração para o restante do processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="b98f3-175">Para obter mais informações, consulte [como criar uma mídia inicializável](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span><span class="sxs-lookup"><span data-stu-id="b98f3-175">For more information, see [How to Create Bootable Media](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="b98f3-176">Crie pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b98f3-176">Create Configuration Manager packages</span></span>

<span data-ttu-id="b98f3-177">Gerenciador de configuração requer um número de pacotes para implantar e configurar as unidades do sistema de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="b98f3-177">Configuration Manager requires a number of packages to deploy and configure the Skype Room System v2 units.</span></span>

<span data-ttu-id="b98f3-178">Você precisa criar e configurar os pacotes a seguir e, em seguida, distribuí-las para os sistemas de site do Configuration Manager que tiverem sido atribuídos a função de servidor do ponto de distribuição.</span><span class="sxs-lookup"><span data-stu-id="b98f3-178">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="b98f3-179">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="b98f3-179">**Package name**</span></span>                     | <span data-ttu-id="b98f3-180">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b98f3-180">**Type**</span></span>               | <span data-ttu-id="b98f3-181">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b98f3-181">**Description**</span></span>                                                                        |
|--------------------------------------|------------------------|----------------------------------------------------------------------------------------|
| <span data-ttu-id="b98f3-182">SRS v2 - SRS pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b98f3-182">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="b98f3-183">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="b98f3-183">Software package</span></span>       | <span data-ttu-id="b98f3-184">Pacote para o kit de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="b98f3-184">Package for the Skype Room Systems v2 deployment kit</span></span>                                   |
| <span data-ttu-id="b98f3-185">SRS v2 - pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="b98f3-185">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="b98f3-186">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="b98f3-186">Software package</span></span>       | <span data-ttu-id="b98f3-187">Pacote para o Unattended.xml personalizado configurar unidades de v2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="b98f3-187">Package for the custom Unattended.xml to configure Skype Room Systems v2 units</span></span>         |
| <span data-ttu-id="b98f3-188">SRS v2 - Set-SRSComputerName pacote</span><span class="sxs-lookup"><span data-stu-id="b98f3-188">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="b98f3-189">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="b98f3-189">Software package</span></span>       | <span data-ttu-id="b98f3-190">Pacote para o aplicativo HTML (HTA) atribuir um nome de computador durante a implantação</span><span class="sxs-lookup"><span data-stu-id="b98f3-190">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span> |
| <span data-ttu-id="b98f3-191">SRS v2 - pacote de atualizações de sistema operacional</span><span class="sxs-lookup"><span data-stu-id="b98f3-191">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="b98f3-192">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="b98f3-192">Software package</span></span>       | <span data-ttu-id="b98f3-193">Pacote para implantar as atualizações obrigatórias do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="b98f3-193">Package to deploy mandatory operating system updates</span></span>                                   |
| <span data-ttu-id="b98f3-194">SRS v2 - pacote do certificado raiz</span><span class="sxs-lookup"><span data-stu-id="b98f3-194">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="b98f3-195">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="b98f3-195">Software package</span></span>       | <span data-ttu-id="b98f3-196">Pacote para implantar o certificado raiz (não é necessário para unidades de domínio)</span><span class="sxs-lookup"><span data-stu-id="b98f3-196">Package to deploy the root certificate (not required for domain-joined units)</span></span>          |
| <span data-ttu-id="b98f3-197">SRS v2 - pacote do Microsoft OMS agente</span><span class="sxs-lookup"><span data-stu-id="b98f3-197">SRS v2 - Microsoft OMS Agent Package</span></span> | <span data-ttu-id="b98f3-198">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="b98f3-198">Software package</span></span>       | <span data-ttu-id="b98f3-199">Pacote para implantar e configurar o agente do pacote de gerenciamento de operações do Microsoft</span><span class="sxs-lookup"><span data-stu-id="b98f3-199">Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>        |
| <span data-ttu-id="b98f3-200">SRS v2 - pacote de plano de fundo do WinPE</span><span class="sxs-lookup"><span data-stu-id="b98f3-200">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="b98f3-201">Pacote de software</span><span class="sxs-lookup"><span data-stu-id="b98f3-201">Software package</span></span>       | <span data-ttu-id="b98f3-202">Pacote para a imagem de plano de fundo personalizado a ser usada com imagens de inicialização</span><span class="sxs-lookup"><span data-stu-id="b98f3-202">Package for the custom background image to use with boot images</span></span>                        |
| <span data-ttu-id="b98f3-203">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b98f3-203">Windows 10 Enterprise</span></span>                | <span data-ttu-id="b98f3-204">Imagem do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="b98f3-204">Operating system image</span></span> | <span data-ttu-id="b98f3-205">Pacote para o arquivo de instalação do sistema operacional (WIM)</span><span class="sxs-lookup"><span data-stu-id="b98f3-205">Package for the operating system installation file (install.wim)</span></span>                       |
| <span data-ttu-id="b98f3-206">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="b98f3-206">Surface Pro</span></span>                          | <span data-ttu-id="b98f3-207">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="b98f3-207">Driver package</span></span>         | <span data-ttu-id="b98f3-208">Pacote para drivers de dispositivo e firmware Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="b98f3-208">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                  |
| <span data-ttu-id="b98f3-209">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="b98f3-209">Surface Pro 4</span></span>                        | <span data-ttu-id="b98f3-210">Pacote de driver</span><span class="sxs-lookup"><span data-stu-id="b98f3-210">Driver package</span></span>         | <span data-ttu-id="b98f3-211">Pacote para drivers de dispositivo e firmware para 4 do Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="b98f3-211">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                |

<span data-ttu-id="b98f3-212">Para obter mais informações, consulte [pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="b98f3-212">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="b98f3-213">Criar arquivos de origem de pastas para o pacote</span><span class="sxs-lookup"><span data-stu-id="b98f3-213">Create folders for the package source files</span></span>

<span data-ttu-id="b98f3-214">Gerenciador de configuração requer os arquivos de origem de pacote para ser organizados em uma estrutura de pasta específica, eles são criados pela primeira vez e quando os campos são atualizados.</span><span class="sxs-lookup"><span data-stu-id="b98f3-214">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="b98f3-215">Crie a seguinte estrutura de pasta no site de administração central do System Center Configuration Manager ou sites primário ou em um compartilhamento de servidor que você está usando para arquivos de origem do pacote de host:</span><span class="sxs-lookup"><span data-stu-id="b98f3-215">Create the following folder structure on the System Center Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="b98f3-216">SRS v2 - pacote do Microsoft OMS agente</span><span class="sxs-lookup"><span data-stu-id="b98f3-216">SRS v2 - Microsoft OMS Agent Package</span></span>
-   <span data-ttu-id="b98f3-217">SRS v2 - pacote de atualizações de sistema operacional</span><span class="sxs-lookup"><span data-stu-id="b98f3-217">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="b98f3-218">SRS v2 - pacote do certificado raiz</span><span class="sxs-lookup"><span data-stu-id="b98f3-218">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="b98f3-219">SRS v2 - Set-SRSComputerName pacote</span><span class="sxs-lookup"><span data-stu-id="b98f3-219">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="b98f3-220">SRS v2 - SRS pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b98f3-220">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="b98f3-221">SRS v2 - pacote Sysprep</span><span class="sxs-lookup"><span data-stu-id="b98f3-221">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="b98f3-222">Drivers</span><span class="sxs-lookup"><span data-stu-id="b98f3-222">Drivers</span></span>
    -   <span data-ttu-id="b98f3-223">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="b98f3-223">Surface Pro</span></span>
    -   <span data-ttu-id="b98f3-224">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="b98f3-224">Surface Pro 4</span></span>
-   <span data-ttu-id="b98f3-225">Sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="b98f3-225">Operating Systems</span></span>
    -   <span data-ttu-id="b98f3-226">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b98f3-226">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="b98f3-227">Você também pode [Baixar](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) e usar o arquivo zip que inclui a estrutura de pasta para os pacotes e os scripts que você precisará usar o modelo de sequência de tarefa, que você precisa importar.</span><span class="sxs-lookup"><span data-stu-id="b98f3-227">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a><span data-ttu-id="b98f3-228">Crie o pacote do pacote de gerenciamento de operações do Microsoft agent</span><span class="sxs-lookup"><span data-stu-id="b98f3-228">Create the Microsoft Operations Management Suite agent package</span></span>

1.  <span data-ttu-id="b98f3-229">Baixe o agente do pacote de gerenciamento de operações X-64 contra <https://go.microsoft.com/fwlink/?LinkId=828603>.</span><span class="sxs-lookup"><span data-stu-id="b98f3-229">Download the Operations Management Suite X-64 agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2.  <span data-ttu-id="b98f3-230">Extraia o pacote para a pasta **SRS v2 - pacote do Microsoft OMS agente** abrindo uma janela de Prompt de comando e inserindo **/c de MMASetup-AMD64.exe:** no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="b98f3-230">Extract the package into the **SRS v2 - Microsoft OMS Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3.  <span data-ttu-id="b98f3-231">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-231">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="b98f3-232">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="b98f3-232">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="b98f3-233">Nome **: SRS v2 - pacote do Microsoft OMS agente**</span><span class="sxs-lookup"><span data-stu-id="b98f3-233">Name **: SRS v2 - Microsoft OMS Agent Package**</span></span>

    -   <span data-ttu-id="b98f3-234">Fabricante **: Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="b98f3-234">Manufacturer **: Microsoft Corporation**</span></span>

    -   <span data-ttu-id="b98f3-235">Versão **: 8.1.11081.0** (Insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="b98f3-235">Version **: 8.1.11081.0** (enter the version of the downloaded installation file)</span></span>

    -   <span data-ttu-id="b98f3-236">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - pacote do Microsoft OMS agente** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-236">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft OMS Agent Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="b98f3-237">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-237">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-238">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-238">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="b98f3-239">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-239">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="b98f3-240">Crie o pacote de atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="b98f3-240">Create the operating system updates package</span></span>

1.  <span data-ttu-id="b98f3-241">Na pasta **SRS v2 - pacote de atualizações do sistema operacional** , crie um novo script do PowerShell chamado **Install-SRSv2 SO Updates.ps1**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-241">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2.  <span data-ttu-id="b98f3-242">Copie o script abaixo para o script **Install-SRSv2 SO Updates.ps1** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-242">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="b98f3-243">Como alternativa, você pode baixar o script Install-SRSv2 SO Updates.ps1 [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="b98f3-243">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="b98f3-244">Baixe os pacotes do Windows Update obrigatórios para a mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="b98f3-244">Download the mandatory Windows Update packages into the same folder.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="b98f3-245">No momento em que este artigo foi publicado, [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) era necessária.</span><span class="sxs-lookup"><span data-stu-id="b98f3-245">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="b98f3-246">Verifique se [Configure um console do Skype sala sistemas v2](console.md), para ver se quaisquer outras atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="b98f3-246">Check [Configure a Skype Room Systems v2 console](console.md), to see whether any other updates are required.</span></span>

4.  <span data-ttu-id="b98f3-247">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-247">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5.  <span data-ttu-id="b98f3-248">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="b98f3-248">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="b98f3-249">Nome: **SRS v2 – SO atualiza o pacote**</span><span class="sxs-lookup"><span data-stu-id="b98f3-249">Name: **SRS v2 – OS Updates Package**</span></span>
    -   <span data-ttu-id="b98f3-250">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="b98f3-250">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="b98f3-251">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="b98f3-251">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="b98f3-252">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - pacote de atualizações do sistema operacional** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-252">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-253">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-253">Select **Do not create a program**, and then select **Next**.</span></span>

7.  <span data-ttu-id="b98f3-254">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-254">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8.  <span data-ttu-id="b98f3-255">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-255">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="b98f3-256">Criar o pacote do certificado raiz (opcional)</span><span class="sxs-lookup"><span data-stu-id="b98f3-256">Create the root certificate package (optional)</span></span>

<span data-ttu-id="b98f3-257">Você criar este pacote para distribuir o certificado raiz para dispositivos que não estar associado a um domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b98f3-257">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="b98f3-258">Crie este pacote somente se as seguintes condições se aplicam:</span><span class="sxs-lookup"><span data-stu-id="b98f3-258">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="b98f3-259">Sua implantação incluir local Lync ou Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b98f3-259">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="b98f3-260">Unidades de v2 Skype sala sistemas são configuradas para trabalhar em um grupo de trabalho em vez de um membro do domínio.</span><span class="sxs-lookup"><span data-stu-id="b98f3-260">Skype Room Systems v2 units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="b98f3-261">Copie o certificado raiz para a pasta **SRS v2 – pacote do certificado raiz** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-261">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="b98f3-262">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-262">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="b98f3-263">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="b98f3-263">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="b98f3-264">Nome: **SRS v2 – pacote do certificado raiz**</span><span class="sxs-lookup"><span data-stu-id="b98f3-264">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="b98f3-265">Fabricante: *nome da sua organização*</span><span class="sxs-lookup"><span data-stu-id="b98f3-265">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="b98f3-266">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="b98f3-266">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="b98f3-267">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – pacote do certificado raiz** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-267">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="b98f3-268">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-268">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="b98f3-269">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-269">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-270">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-270">Select **Close**.</span></span>

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a><span data-ttu-id="b98f3-271">Criar um pacote do kit de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="b98f3-271">Create the Skype Room Systems v2 deployment kit package</span></span>

1.  <span data-ttu-id="b98f3-272">Baixe a versão mais recente do **kit de implantação do Skype sala sistemas v2** de <https://go.microsoft.com/fwlink/?linkid=851168>e instalá-lo a uma estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b98f3-272">Download the latest version of the **Skype Room Systems v2 deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="b98f3-273">Copiar o conteúdo de **c:\\arquivos de programa (x86)\\Kit de implantação do sistema do Skype sala** para a pasta **SRS v2 - SRS pacote de aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-273">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="b98f3-274">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-274">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="b98f3-275">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="b98f3-275">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="b98f3-276">Nome: **SRS v2 – SRS pacote de aplicativos**</span><span class="sxs-lookup"><span data-stu-id="b98f3-276">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="b98f3-277">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="b98f3-277">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="b98f3-278">Versão: **3.1.104.0** (Insira a versão do arquivo de instalação baixado)</span><span class="sxs-lookup"><span data-stu-id="b98f3-278">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="b98f3-279">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – SRS pacote de aplicativos** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-279">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="b98f3-280">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-280">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-281">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-281">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="b98f3-282">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-282">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="b98f3-283">Crie o pacote de atribuição de nome de computador</span><span class="sxs-lookup"><span data-stu-id="b98f3-283">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="b98f3-284">Na pasta **SRS v2 - Set-SRSComputerName pacote** , crie um novo aplicativo de HTML chamado **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-284">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="b98f3-285">Copie o script a seguir para o arquivo de **Set-SRSComputerName.hta** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-285">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="b98f3-286">Como alternativa, você pode baixar o arquivo Set-SRSComputerName.hta [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="b98f3-286">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="b98f3-287">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-287">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="b98f3-288">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="b98f3-288">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="b98f3-289">Nome: **SRS v2 - Set-SRSComputerName pacote**</span><span class="sxs-lookup"><span data-stu-id="b98f3-289">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="b98f3-290">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="b98f3-290">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="b98f3-291">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="b98f3-291">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="b98f3-292">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 - Set-SRSComputerName pacote** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-292">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="b98f3-293">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-293">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-294">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-294">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="b98f3-295">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-295">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="b98f3-296">Crie o pacote de Sysprep</span><span class="sxs-lookup"><span data-stu-id="b98f3-296">Create the Sysprep package</span></span>

1.  <span data-ttu-id="b98f3-297">Na pasta **SRS v2 – pacote Sysprep** , crie um novo arquivo XML denominado **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-297">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2.  <span data-ttu-id="b98f3-298">Copie o seguinte texto para o arquivo de **Unattend. XML** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-298">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="b98f3-299">Como alternativa, você pode baixar o arquivo Unattend [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="b98f3-299">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
```
<?xml version="1.0" encoding="utf-8"?>
<unattend xmlns="urn:schemas-microsoft-com:unattend">
    <servicing>
        <package action="configure">
            <assemblyIdentity name="Microsoft-Windows-Foundation-Package" version="10.0.15063.0" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="" />
            <selection name="Client-DeviceLockdown" state="true" />
            <selection name="Client-EmbeddedLogon" state="true" />
            <selection name="Client-EmbeddedBootExp" state="true" />
            <selection name="Client-EmbeddedShellLauncher" state="true" />
            <selection name="Client-KeyboardFilter" state="true" />
            <selection name="Internet-Explorer-Optional-amd64" state="false" />
            <selection name="MediaPlayback" state="false" />
            <selection name="WindowsMediaPlayer" state="false" />
            <selection name="Xps-Foundation-Xps-Viewer" state="false" />
            <selection name="WorkFolders-Client" state="false" />
            <selection name="SMB1Protocol" state="false" />
            <selection name="SearchEngine-Client-Package" state="false" />
            <selection name="Printing-Foundation-Features" state="false" />
            <selection name="FaxServicesClientPackage" state="false" />
            <selection name="Printing-Foundation-InternetPrinting-Client" state="false" />
            <selection name="Printing-XPSServices-Features" state="false" />
            <selection name="Printing-PrintToPDFServices-Features" state="false" />
            <selection name="Microsoft-Hyper-V-Hypervisor" state="true" />
            <selection name="Microsoft-Hyper-V-All" state="true" />
            <selection name="Microsoft-Hyper-V" state="true" />
        </package>
    </servicing>
    <settings pass="auditSystem">
        <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
            <AutoLogon>
                <Enabled>true</Enabled>
                <Username>Admin</Username>
                <Password>
                    <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
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
    <settings pass="oobeSystem">
        <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        </component>
    </settings>
    <cpi:offlineImage cpi:source="wim://com-sccm01/_sources/capture/srscaptured.wim#SRSImage" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
</unattend>
```
3.  <span data-ttu-id="b98f3-300">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**e, em seguida, selecione **Criar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-300">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="b98f3-301">Insira as informações a seguir para criar o pacote:</span><span class="sxs-lookup"><span data-stu-id="b98f3-301">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="b98f3-302">Nome: **SRS v2 - pacote Sysprep**</span><span class="sxs-lookup"><span data-stu-id="b98f3-302">Name: **SRS v2 - Sysprep Package**</span></span>
    -   <span data-ttu-id="b98f3-303">Fabricante: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="b98f3-303">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="b98f3-304">Versão: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="b98f3-304">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="b98f3-305">Marque a caixa de seleção **Este pacote contém arquivos de origem** , insira o caminho da pasta **SRS v2 – pacote Sysprep** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-305">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="b98f3-306">Selecione **não criar um programa**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-306">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-307">Revise a página **Confirme as configurações** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-307">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="b98f3-308">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-308">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="b98f3-309">Criar um pacote do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b98f3-309">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="b98f3-310">Obtenha uma mídia Windows 10 Enterprise x64 e copie o arquivo **WIM** para a **sistemas operacionais\\Windows 10 Enterprise** pasta.</span><span class="sxs-lookup"><span data-stu-id="b98f3-310">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="b98f3-311">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Imagens de sistema operacional**e selecione **Adicionar a imagem do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-311">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="b98f3-312">Especifique o caminho para o arquivo **WIM** que você acabou de copiar e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-312">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="b98f3-313">Atualize o campo de **versão** para coincidir com o número de compilação da imagem do Windows 10 Enterprise e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-313">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="b98f3-314">Revise a página de **detalhes** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-314">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-315">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-315">Select **Close**.</span></span>

<span data-ttu-id="b98f3-316">Para obter mais informações, consulte [Gerenciar imagens do sistema operacional com o System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span><span class="sxs-lookup"><span data-stu-id="b98f3-316">For more information, see [Manage operating system images with System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="b98f3-317">Crie pacotes de driver de dispositivo Surface Pro</span><span class="sxs-lookup"><span data-stu-id="b98f3-317">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="b98f3-318">Sistemas de sala Skype v2 é suportado para Surface Pro e 4 do Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="b98f3-318">Skype Room Systems v2 is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="b98f3-319">Você precisará criar um pacote de driver para cada modelo Surface Pro, que você tem em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b98f3-319">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

1.  <span data-ttu-id="b98f3-320">Baixe os drivers e o firmware mais recente.</span><span class="sxs-lookup"><span data-stu-id="b98f3-320">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="b98f3-321">Para Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="b98f3-321">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="b98f3-322">Para Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="b98f3-322">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>
> [!IMPORTANT]
> <span data-ttu-id="b98f3-323">Os drivers devem ser compatíveis com a compilação do Windows 10 Enterprise e a versão do Skype sala sistemas v2 deployment kit.</span><span class="sxs-lookup"><span data-stu-id="b98f3-323">The drivers must be compatible with the Windows 10 Enterprise build and the Skype Room Systems v2 deployment kit version.</span></span> <span data-ttu-id="b98f3-324">Para obter mais informações, consulte [o firmware mais recente e a drivers para dispositivos de superfície de Download](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="b98f3-324">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span>
2.  <span data-ttu-id="b98f3-325">Extraia o driver baixado e firmware.</span><span class="sxs-lookup"><span data-stu-id="b98f3-325">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="b98f3-326">Abra uma janela de Prompt de comando e no prompt de comando, insira um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="b98f3-326">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="b98f3-327">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Drivers**e, em seguida, selecione **O Driver de importação**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-327">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="b98f3-328">Selecione **importar todos os drivers no seguinte caminho de rede (UNC)**, selecione a pasta de origem (por exemplo, c\\_Sources\\Drivers\\Surface Pro) e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-328">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="b98f3-329">Na página **especificar os detalhes para os drivers importados** , selecione todos os drivers listados e selecione **Habilitar esses drivers e permitir que os computadores instalá-los**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-329">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="b98f3-330">Selecione **categorias**, criar uma nova categoria que coincide com o modelo de superfície, selecione **Okey**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-330">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="b98f3-331">Selecione o **novo pacote**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-331">Select **New Package**.</span></span>

8.  <span data-ttu-id="b98f3-332">Especifique o nome do pacote que coincide com o modelo Surface Pro, insira um caminho de pasta para armazenar os arquivos do pacote de driver em, selecione **Okey**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-332">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="b98f3-333">Na página de **imagens de inicialização** , certifique-se de que nenhum imagens de inicialização são selecionadas e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-333">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="b98f3-334">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-334">Select **Close**.</span></span>

11. <span data-ttu-id="b98f3-335">Vá para a **Biblioteca de Software** \> **sistemas operacionais** \> **Drivers**, selecione **pasta \> criar pasta**e insira um nome de pasta que coincide com o modelo Surface Pro que você acabou de importar os drivers para.</span><span class="sxs-lookup"><span data-stu-id="b98f3-335">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="b98f3-336">Mova todos os drivers importados para a pasta recém-criada para fácil navegação e a operação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-336">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="b98f3-337">Repita as mesmas etapas para outros modelos Surface Pro, que talvez seja necessário.</span><span class="sxs-lookup"><span data-stu-id="b98f3-337">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="b98f3-338">Para obter mais informações, consulte [Gerenciar drivers no System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span><span class="sxs-lookup"><span data-stu-id="b98f3-338">For more information, see [Manage drivers in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).</span></span>

## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="b98f3-339">Distribuir pacotes do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b98f3-339">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="b98f3-340">Todos os pacotes devem ser distribuídos para os servidores que tiverem sido atribuídos a função de ponto de distribuição na hierarquia do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b98f3-340">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="b98f3-341">Siga as instruções abaixo para iniciar a distribuição de pacote.</span><span class="sxs-lookup"><span data-stu-id="b98f3-341">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="b98f3-342">Distribua os pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="b98f3-342">Distribute software packages.</span></span>

    1.  <span data-ttu-id="b98f3-343">No console do Configuration Manager, vá para **A biblioteca de Software** \> **Gerenciamento de aplicativos** \> **pacotes**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-343">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="b98f3-344">Selecione todos os pacotes de software que você deseja distribuir e selecione **Distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-344">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="b98f3-345">Revise a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-345">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="b98f3-346">Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-346">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="b98f3-347">Selecione **Avançar**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-347">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="b98f3-348">Distribua os pacotes de driver.</span><span class="sxs-lookup"><span data-stu-id="b98f3-348">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="b98f3-349">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Pacotes de Driver**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-349">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="b98f3-350">Selecione todos os pacotes de driver que você deseja distribuir e selecione **Distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-350">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="b98f3-351">Revise a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-351">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="b98f3-352">Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-352">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="b98f3-353">Selecione **Avançar**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-353">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="b98f3-354">Distribua os pacotes do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b98f3-354">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="b98f3-355">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Imagens do sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-355">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="b98f3-356">Selecione todas as imagens de sistema operacional que você deseja distribuir e selecione **Distribuir conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-356">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="b98f3-357">Revise a lista de pacotes e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-357">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="b98f3-358">Adicione todos os servidores de ponto de distribuição (ou grupos de ponto de distribuição, dependendo de sua hierarquia do Configuration Manager) à lista e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-358">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="b98f3-359">Selecione **Avançar**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-359">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="b98f3-360">Distribuição de pacote pode levar algum tempo, dependendo do tamanho do pacote, hierarquia do Configuration Manager, número de servidores de ponto de distribuição e a largura de banda disponível em sua rede.</span><span class="sxs-lookup"><span data-stu-id="b98f3-360">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>

> <span data-ttu-id="b98f3-361">Todos os pacotes devem ser distribuídos antes de começar a implantação de uma unidade de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="b98f3-361">All the packages must be distributed before you can start deploying a Skype Room Systems v2 unit.</span></span>

> <span data-ttu-id="b98f3-362">Você pode examinar o status da sua distribuição de pacote no console do Configuration Manager indo para **monitoramento** \> **Status de distribuição** \> **Status do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-362">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="b98f3-363">Sequências de tarefas do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b98f3-363">Configuration Manager task sequences</span></span>

<span data-ttu-id="b98f3-364">Use sequências de tarefas com o System Center Configuration Manager para automatizar as etapas de implantação de uma imagem do sistema operacional em um computador de destino.</span><span class="sxs-lookup"><span data-stu-id="b98f3-364">You use task sequences with System Center Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="b98f3-365">Para implantar uma unidade de v2 Skype sala sistemas de forma automática, você cria uma sequência de tarefa que faz referência a imagem de inicialização usada para iniciar o computador de destino de sistemas de sala Skype v2, a imagem do sistema operacional Windows 10 Enterprise que você deseja instalar e qualquer outro conteúdo adicional, como outros aplicativos ou atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="b98f3-365">To deploy a Skype Room Systems v2 unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Skype Room Systems v2 computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="b98f3-366">Importar a sequência de tarefas de amostra</span><span class="sxs-lookup"><span data-stu-id="b98f3-366">Import the sample task sequence</span></span>

<span data-ttu-id="b98f3-367">Você pode baixar e facilmente importar uma sequência de tarefas de amostra e personalizá-lo para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="b98f3-367">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="b98f3-368">[**Baixe**]() a sequência de tarefas de amostra e copiar o arquivo zip baixado em um local compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-368">[**Download**]() the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="b98f3-369">No console do Configuration Manager, vá para **A biblioteca de Software** \> **sistemas operacionais** \> **Sequências de tarefas**e, em seguida, selecione **Importar sequência de tarefa**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-369">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="b98f3-370">Selecione **navegar**, vá para o local de pasta compartilhada que você usou na etapa 1, selecione o arquivo **. zip do Skype sala sistemas v2 implantação (EN-US)** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-370">Select **Browse**, go to the shared folder location you used in step 1, select the **Skype Room Systems v2 Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="b98f3-371">Definir a **ação** para **Criar novo**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-371">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="b98f3-372">Confirme as configurações e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-372">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="b98f3-373">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-373">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="b98f3-374">Valide que os pacotes de referência corretamente vinculados a cada etapa de sequência de tarefa.</span><span class="sxs-lookup"><span data-stu-id="b98f3-374">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1.  <span data-ttu-id="b98f3-375">Selecione a sequência de tarefa importada e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-375">Select the imported task sequence, and then select **Edit**.</span></span>

     <span data-ttu-id="b98f3-376">O Editor de sequência de tarefas abre e exibe cada etapa sequencial que você precisa para implantar e configurar uma unidade de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="b98f3-376">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Skype Room Systems v2 unit.</span></span>

1.  <span data-ttu-id="b98f3-377">Percorrer cada etapa e preencha as atualizações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="b98f3-377">Walk through each step and complete the recommended updates:</span></span>

    1.  <span data-ttu-id="b98f3-378">**Reinicie o Windows PE**: esta etapa é reiniciado e carrega o computador Windows PXE.</span><span class="sxs-lookup"><span data-stu-id="b98f3-378">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="b98f3-379">Nenhuma alteração é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b98f3-379">No changes are required for this step.</span></span>

    2.  <span data-ttu-id="b98f3-380">**Partição de disco 0 – UEFI**: esta etapa apaga a configuração do disco e cria partições com base em configurações definidas.</span><span class="sxs-lookup"><span data-stu-id="b98f3-380">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="b98f3-381">Recomendamos que você não faça alterações para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b98f3-381">We recommend that you not make any changes to this step.</span></span>

    3.  <span data-ttu-id="b98f3-382">**Definir nome do computador SRS**: esta etapa inclui um aplicativo de HTML para fornecer uma interface do usuário para definir um nome de computador para a unidade de v2 Skype sala sistemas durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-382">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Skype Room Systems v2 unit during the deployment.</span></span>
        -  <span data-ttu-id="b98f3-383">Esta é uma etapa opcional, mas ele pode ser desabilitado apenas se você quiser gerenciar por meio de um processo alternativo de nomeação do computador.</span><span class="sxs-lookup"><span data-stu-id="b98f3-383">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
        -  <span data-ttu-id="b98f3-384">Verifique se o pacote **SRS v2 - Set-SRSComputerName** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-384">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="b98f3-385">Se não for, navegue até o pacote e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="b98f3-385">If it isn’t, browse to the package and select it.</span></span>

    4.  <span data-ttu-id="b98f3-386">**Aplicar o sistema de operacional**: esta etapa Especifica a imagem do sistema operacional a serem implantados e o arquivo de resposta Sysprep autônoma usar.</span><span class="sxs-lookup"><span data-stu-id="b98f3-386">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
        -  <span data-ttu-id="b98f3-387">Verifique se o arquivo de imagem de sistema operacional Windows 10 Enterprise correto está selecionado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-387">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
        -  <span data-ttu-id="b98f3-388">Verifique se **usar uma autônoma ou Sysprep o arquivo de resposta para uma instalação personalizada** está habilitado, e o **SRS v2 - pacote Sysprep** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="b98f3-388">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="b98f3-389">Além disso, certifique-se de que o **Nome de arquivo** está definido como **Unattend. XML**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-389">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

    5.  <span data-ttu-id="b98f3-390">**Aplicar configurações do Windows**: esta etapa reúne informações sobre a instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b98f3-390">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
        -  <span data-ttu-id="b98f3-391">Fornecer informações de registro e de licenciamento, incluindo a chave do produto, senha da conta de administrador local e fuso horário (dependendo das suas necessidades).</span><span class="sxs-lookup"><span data-stu-id="b98f3-391">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

    6.  <span data-ttu-id="b98f3-392">**Aplicar configurações de rede**: esta etapa permite especificar um grupo de trabalho ou o nome de domínio do Active Directory e a unidade organizacional.</span><span class="sxs-lookup"><span data-stu-id="b98f3-392">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>

    7.  <span data-ttu-id="b98f3-393">**Aplicar Drivers:** Esta etapa e seus subetapas são usadas para implantar baseada no modelo do Surface Pro, que você tem de firmware e drivers de dispositivo aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="b98f3-393">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="b98f3-394">Atualize cada etapa para especificar o pacote de driver relevantes associado com essa implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-394">Update each step to specify the relevant driver package associated with this deployment.</span></span>
        -   <span data-ttu-id="b98f3-395">Cada pacote de driver é configurado para aproveitar os filtros Windows Management Instrumentation (WMI) para implantar drivers relevantes e firmware com base em o Surface Pro marca e modelo.</span><span class="sxs-lookup"><span data-stu-id="b98f3-395">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
        -   <span data-ttu-id="b98f3-396">É altamente recomendável que você não alterar a configuração desses drivers, caso contrário, a implantação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="b98f3-396">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

    8.  <span data-ttu-id="b98f3-397">**Configurar o Windows e o Configuration Manager**: esta etapa implanta e configura o cliente do Gerenciador de configuração.</span><span class="sxs-lookup"><span data-stu-id="b98f3-397">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="b98f3-398">Atualize esta etapa para especificar o pacote de cliente interno do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b98f3-398">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

    9.  <span data-ttu-id="b98f3-399">**Instalar o certificado de raiz**: esta etapa distribui o certificado raiz para dispositivos não – associados a um domínio e, portanto, é opcional.</span><span class="sxs-lookup"><span data-stu-id="b98f3-399">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional.</span></span>
        -   <span data-ttu-id="b98f3-400">Remover ou desabilitar esta etapa se você não precisará implantar um certificado raiz para as unidades de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="b98f3-400">Remove or disable this step if you don’t need to deploy a root certificate to the Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="b98f3-401">Se você precisar executar esta etapa, verifique se o **SRS v2 – pacote do certificado raiz** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-401">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** is selected.</span></span>

    10. <span data-ttu-id="b98f3-402">**Instalar e configurar o agente de OMS**: essa etapa instala a versão de 64 bits do agente do pacote de gerenciamento de operações do Microsoft e configura o agente para se conectar ao seu espaço de trabalho de análise de Log.</span><span class="sxs-lookup"><span data-stu-id="b98f3-402">**Install and Configure OMS Agent**: This step installs the 64-bit version of the Microsoft Operations Management Suite agent and configures the agent to connect to your Log Analytics workspace.</span></span>
        -   <span data-ttu-id="b98f3-403">Desabilite esta etapa somente se você vai usar algumas outras plataformas para monitorar a integridade de unidades de v2 seus sistemas de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="b98f3-403">Disable this step only if you’re going to use some other platforms to monitor the health of your Skype Room Systems v2 units.</span></span>
        -   <span data-ttu-id="b98f3-404">Editar esta etapa e atualizar os parâmetros de linha de comando para especificar sua **ID de espaço de trabalho** e a **Chave do espaço de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-404">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
        -   <span data-ttu-id="b98f3-405">Consulte [computadores com Windows se conectar ao serviço de Log de análise no Windows Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) para obter mais informações sobre como obter a ID de espaço de trabalho de pacote de gerenciamento de operações e a chave primária.</span><span class="sxs-lookup"><span data-stu-id="b98f3-405">See [Connect Windows computers to the Log Analytics service in Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
        -   <span data-ttu-id="b98f3-406">Verifique se o **SRS v2 – pacote do Microsoft OMS agente** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-406">Verify that the **SRS v2 – Microsoft OMS Agent Package** is selected.</span></span>
        -   <span data-ttu-id="b98f3-407">Para obter mais informações sobre como monitorar a integridade da sua implantação do Skype sala sistemas v2, consulte [gerenciamento de v2 de sistemas de sala Skype planejar com OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) e [gerenciamento de v2 implantar sistemas do Skype sala com OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span><span class="sxs-lookup"><span data-stu-id="b98f3-407">For more information about monitoring the health of your Skype Room Systems v2 deployment, see [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) and [Deploy Skype Room Systems v2 management with OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).</span></span>

    11. <span data-ttu-id="b98f3-408">**Arquivos de configuração de v2 SRS de cópia**: esta etapa copia os arquivos de instalação e configuração necessários do kit de implantação do Skype sala sistemas v2 para o disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="b98f3-408">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Skype Room Systems v2 deployment kit to the local hard drive.</span></span> <span data-ttu-id="b98f3-409">Sem personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b98f3-409">No customization is required for this step.</span></span>

    12. <span data-ttu-id="b98f3-410">**Install-SRSv2-atualizações de sistema operacional**: essa etapa implanta quaisquer atualizações de obrigatório do sistema operacional necessárias com a implantação de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="b98f3-410">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Skype Room Systems v2 deployment.</span></span> <span data-ttu-id="b98f3-411">Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b98f3-411">Do the following:</span></span>
        -   <span data-ttu-id="b98f3-412">Verifique o [console de configurar um v2 de sistemas de sala Skype](console.md) para ver quais atualizações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="b98f3-412">Check [Configure a Skype Room Systems v2 console](console.md) to see which updates are required.</span></span>
        -   <span data-ttu-id="b98f3-413">Verifique se seu **SRS v2 – pacote de atualizações do sistema operacional** inclui todas as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="b98f3-413">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
        -   <span data-ttu-id="b98f3-414">Verifique se o **SRS v2 – pacote de atualizações do sistema operacional** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-414">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
        -   <span data-ttu-id="b98f3-415">Verifique se a diretiva de execução do PowerShell é definida para **desvio**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-415">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

    13. <span data-ttu-id="b98f3-416">**Reiniciar o computador**: esta etapa reinicializa o computador depois que as atualizações obrigatórias de sistema operacional estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="b98f3-416">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="b98f3-417">Sem personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b98f3-417">No customization is required for this step.</span></span>

    14. <span data-ttu-id="b98f3-418">**Adicionar usuário Local do Skype**: essa etapa cria a conta do Skype local usada para entrar no Windows e inicie o aplicativo do Skype sala sistemas v2 automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b98f3-418">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Skype Room Systems v2 application.</span></span> <span data-ttu-id="b98f3-419">Esta etapa não tem nenhum pacote de software associado a ela, e sem personalização é necessária para ele.</span><span class="sxs-lookup"><span data-stu-id="b98f3-419">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

    15. <span data-ttu-id="b98f3-420">**Definido para cima e para configurar o aplicativo de SRS**: essa etapa instala e configura o aplicativo de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="b98f3-420">**Set up and configure SRS application**: This step installs and configures the Skype Room Systems v2 application.</span></span> <span data-ttu-id="b98f3-421">Esta etapa usa os bits copiados localmente para instalar o aplicativo e, portanto, não têm qualquer pacotes de software associado a ela.</span><span class="sxs-lookup"><span data-stu-id="b98f3-421">This step uses the locally copied bits to install the application and therefore doesn’t have any software packages associated with it.</span></span> <span data-ttu-id="b98f3-422">Sem personalização é necessária para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b98f3-422">No customization is required for this step.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="b98f3-423">Criar a implantação da sequência de tarefas</span><span class="sxs-lookup"><span data-stu-id="b98f3-423">Create deployment for the task sequence</span></span>

1.  <span data-ttu-id="b98f3-424">Selecione a sequência de tarefas e selecione **implantar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-424">Select the task sequence, and then select **Deploy**.</span></span>

2.  <span data-ttu-id="b98f3-425">Selecione **Procurar** para selecionar o conjunto de destino para implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-425">Select **Browse** to select target collection for deployment.</span></span>

3.  <span data-ttu-id="b98f3-426">Selecione **Todos os computadores desconhecido** e selecione **Okey**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-426">Select **All Unknown Computers** and then select **OK**.</span></span>

4.  <span data-ttu-id="b98f3-427">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-427">Select **Next**.</span></span>

5.  <span data-ttu-id="b98f3-428">Selecione **disponível** na lista suspensa **finalidade** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-428">Select **Available** on the **Purpose** drop down list.</span></span>

6.  <span data-ttu-id="b98f3-429">Selecione **apenas a mídia e PXE** na lista **disponibilizar o seguinte** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-429">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
> [!WARNING]
> <span data-ttu-id="b98f3-430">É muito importante que o **objetivo** é definido como **disponível**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-430">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="b98f3-431">Certifique-se de que o **objetivo** é **não** definido como **obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-431">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="b98f3-432">Também Certifique-se de que você selecione **apenas a mídia e PXE** nos **tornar disponível para o seguinte**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-432">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span> <span data-ttu-id="b98f3-433">Configurar esses valores para algo diferente pode fazer com que todos os computadores obter a imagem de implantação de sistemas de sala Skype quando inicializado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-433">Setting these values to something else might cause all computers to get the Skype Room Systems deployment image when booted.</span></span>
7.  <span data-ttu-id="b98f3-434">Não especifique qualquer agenda e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-434">Do not specify any schedule and select **Next**.</span></span>

8.  <span data-ttu-id="b98f3-435">Não altere qualquer coisa dentro da seção **Experiência do usuário** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-435">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9.  <span data-ttu-id="b98f3-436">Não altere qualquer coisa dentro da seção de **alertas** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-436">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10.  <span data-ttu-id="b98f3-437">Não altere qualquer coisa dentro da seção de **Pontos de distribuição** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-437">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11.  <span data-ttu-id="b98f3-438">Confirme as configurações e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-438">Confirm the settings and then select **Next**.</span></span>

12.  <span data-ttu-id="b98f3-439">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-439">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="b98f3-440">Validar e solucionar problemas da solução</span><span class="sxs-lookup"><span data-stu-id="b98f3-440">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="b98f3-441">Depois de concluir as sequências de tarefas do System Center Configuration Manager, você precisará executar um teste para validar que a sequência de tarefa pode implantar e configurar unidades de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="b98f3-441">After you’ve completed the System Center Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Skype Room Systems v2 units.</span></span>

1.  <span data-ttu-id="b98f3-442">Conecte o dispositivo de teste à rede com fio, usando um dos adaptadores Ethernet suportados ou usando a superfície encaixe.</span><span class="sxs-lookup"><span data-stu-id="b98f3-442">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="b98f3-443">Se a funcionalidade de inicialização PXE não tiver sido configurada para o seu ambiente, você pode usar a imagem de inicialização no USB unidade flash [que você criou anteriormente](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) para inicializar a partir do USB e conecte-se ao Gerenciador de configuração.</span><span class="sxs-lookup"><span data-stu-id="b98f3-443">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="b98f3-444">Acessar o firmware e iniciar os inicialização PXE:</span><span class="sxs-lookup"><span data-stu-id="b98f3-444">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="b98f3-445">Certifique-se de que o dispositivo de superfície é desligado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-445">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="b98f3-446">Pressione e mantenha pressionado o botão de **Volume para cima** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-446">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="b98f3-447">Pressione e solte o botão de **energia** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-447">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="b98f3-448">Após o dispositivo começa a inicialização, solte o botão de **Volume para cima** .</span><span class="sxs-lookup"><span data-stu-id="b98f3-448">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="b98f3-449">Selecione a **configuração de inicialização**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-449">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="b98f3-450">Use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b98f3-450">Do one of the following:</span></span>

        -   <span data-ttu-id="b98f3-451">Selecione **inicialização PXE**e arraste-o para o topo da lista.</span><span class="sxs-lookup"><span data-stu-id="b98f3-451">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="b98f3-452">Como alternativa, você poderá passar esquerda no adaptador de rede para inicializar o dispositivo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b98f3-452">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="b98f3-453">Isso não afetará a ordem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="b98f3-453">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="b98f3-454">Selecione a unidade flash USB que contém a mídia de inicialização.</span><span class="sxs-lookup"><span data-stu-id="b98f3-454">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="b98f3-455">Selecione **Sair**e, em seguida, selecione **Reiniciar agora**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-455">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="b98f3-456">Quando solicitado, selecione **Enter** para serviço de inicialização de rede.</span><span class="sxs-lookup"><span data-stu-id="b98f3-456">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="b98f3-457">Windows PE carregará na memória e iniciará o Assistente de sequência de tarefa.</span><span class="sxs-lookup"><span data-stu-id="b98f3-457">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="b98f3-458">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="b98f3-458">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="b98f3-459">Selecione a sequência de tarefas que você importou anteriormente e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98f3-459">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="b98f3-460">Depois que a configuração de disco for aplicada, você será solicitado que especifique um nome de computador para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b98f3-460">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="b98f3-461">A interface do usuário exibirá o nome de um computador recomendada com base no número de série do dispositivo Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="b98f3-461">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="b98f3-462">Você pode aceitar o nome proposto ou especifique um novo.</span><span class="sxs-lookup"><span data-stu-id="b98f3-462">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="b98f3-463">Siga as instruções na tela de atribuição de nome do computador.</span><span class="sxs-lookup"><span data-stu-id="b98f3-463">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="b98f3-464">Quando você selecionar **Aceitar**, começa a implantação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-464">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="b98f3-465">O restante do processo de implantação é automático e não pede qualquer entrada do usuário mais.</span><span class="sxs-lookup"><span data-stu-id="b98f3-465">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="b98f3-466">Depois que a sequência de tarefas de implantação estiver concluída, configurando o dispositivo, você verá a tela configuração a seguir que solicita a definir as configurações de aplicativo do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="b98f3-466">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Skype Room Systems v2 application settings.</span></span>

    ![Tela de instalação inicial para o aplicativo de v2 de sistemas de sala do Skype](../../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="b98f3-468">Conecte o Surface Pro no console do v2 Skype sistemas de sala e definir as configurações de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b98f3-468">Plug the Surface Pro into the Skype Room Systems v2 console, and configure the application settings.</span></span>

11.  <span data-ttu-id="b98f3-469">Valide se os recursos listados na [Ajuda do Skype sala sistemas v2](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estão funcionando no dispositivo implantado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-469">Validate that the capabilities listed in [Skype Room Systems v2 help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="b98f3-470">Para solucionar problemas de uma falha na instalação, verifique o arquivo **SMSTS** , que registra todas as etapas executadas em uma sequência de tarefas do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b98f3-470">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="b98f3-471">O arquivo SMSTS é armazenado em um dos vários caminhos, dependendo do estágio do processo de compilação.</span><span class="sxs-lookup"><span data-stu-id="b98f3-471">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="b98f3-472">Verifique a tabela a seguir para identificar o caminho para o arquivo SMSTS.</span><span class="sxs-lookup"><span data-stu-id="b98f3-472">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="b98f3-473">**Fase de implantação**</span><span class="sxs-lookup"><span data-stu-id="b98f3-473">**Deployment phase**</span></span>                                                            | <span data-ttu-id="b98f3-474">**Caminho de log de sequência de tarefa**</span><span class="sxs-lookup"><span data-stu-id="b98f3-474">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="b98f3-475">WinPE, antes de formato HDD</span><span class="sxs-lookup"><span data-stu-id="b98f3-475">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="b98f3-476">X:\\Windows\\Temp\\smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="b98f3-476">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="b98f3-477">WinPE, após o formato HDD</span><span class="sxs-lookup"><span data-stu-id="b98f3-477">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="b98f3-478">C:\\_SMSTaskSequence\\Logs\\Smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="b98f3-478">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="b98f3-479">Sistema operacional implantado, antes que o agente do Configuration Manager foi instalado</span><span class="sxs-lookup"><span data-stu-id="b98f3-479">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="b98f3-480">c:\\_SMSTaskSequence\\Logs\\Smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="b98f3-480">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="b98f3-481">Sistema operacional e o agente do Configuration Manager implantado</span><span class="sxs-lookup"><span data-stu-id="b98f3-481">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="b98f3-482">% windir %\\System32\\ccm\\logs\\Smstslog\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="b98f3-482">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="b98f3-483">Execução de sequência de tarefa concluída</span><span class="sxs-lookup"><span data-stu-id="b98f3-483">Task sequence execution complete</span></span>                                                | <span data-ttu-id="b98f3-484">% windir %\\System32\\ccm\\logs\\SMSTS</span><span class="sxs-lookup"><span data-stu-id="b98f3-484">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="b98f3-485">Você pode selecionar F8 a qualquer momento durante a sequência de tarefas para abrir um console de comando e obter acesso ao arquivo SMSTS.</span><span class="sxs-lookup"><span data-stu-id="b98f3-485">You can select F8 at any time during the task sequence to open a command console and get access to the SMSTS.log file.</span></span>

<span data-ttu-id="b98f3-486">Para resolver problemas de inicialização do PXE, verifique os dois arquivos de log no servidor do Gerenciador de configuração que são específicos para ações de PXE:</span><span class="sxs-lookup"><span data-stu-id="b98f3-486">To resolve PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="b98f3-487">**Pxecontrol.log**, localizado no diretório de logs de instalação do Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b98f3-487">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="b98f3-488">**Smspxe.log**, localizado no diretório de logs do ponto de gerenciamento do Gerenciador de configuração (MP)</span><span class="sxs-lookup"><span data-stu-id="b98f3-488">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="b98f3-489">Para obter uma lista completa dos arquivos de log que você pode usar para solucionar ainda mais a sua instalação do Configuration Manager, consulte [arquivos de Log no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="b98f3-489">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>
