---
title: Instalar o Microsoft Teams usando MSI via SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Os administradores podem usar o Teams MSI para implantar em massa o Microsoft Teams para usuários ou computadores selecionados.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "37567956"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="5beda-103">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="5beda-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="5beda-104">Assista à sessão a seguir para conhecer os benefícios do Windows Desktop Client e como planejar e executar sua implantação: [Cliente de Desktop do Microsoft Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="5beda-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="5beda-105">Para usar o System Center Configuration Manager, a Política de Grupo ou qualquer mecanismo de distribuição de terceiros para ampla implantação, a Microsoft oferece arquivos MSI (de [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa do Teams para usuários ou computadores selecionados.</span><span class="sxs-lookup"><span data-stu-id="5beda-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="5beda-106">Os administradores podem usar esses arquivos para implantar o Teams remotamente, de modo que os usuários não precisem baixar manualmente o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="5beda-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="5beda-107">Quando implantado, o Teams iniciará automaticamente para todos os usuários que fizerem login naquele computador.</span><span class="sxs-lookup"><span data-stu-id="5beda-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="5beda-108">(Você pode desabilitar o início automático depois de instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5beda-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="5beda-109">[Confira abaixo](#disable-auto-launch-for-the-msi-installer).) É recomendável implantar o pacote no computador para que todos os novos usuários dele também se beneficiem com a implantação.</span><span class="sxs-lookup"><span data-stu-id="5beda-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="5beda-110">O Teams também pode ser incluído em uma implantação do Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="5beda-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="5beda-111">Para obter mais informações, confira [Implantar o Microsoft Teams com Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="5beda-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="5beda-112">Para saber mais sobre o SCCM, confira [Introdução ao System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="5beda-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="5beda-113">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="5beda-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="5beda-114">Recupere o pacote mais recente.</span><span class="sxs-lookup"><span data-stu-id="5beda-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="5beda-115">Use os padrões pré-preenchidos pelo MSI.</span><span class="sxs-lookup"><span data-stu-id="5beda-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="5beda-116">Implante nos computadores quando possível.</span><span class="sxs-lookup"><span data-stu-id="5beda-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="5beda-117">Como o pacote Microsoft Teams MSI funciona</span><span class="sxs-lookup"><span data-stu-id="5beda-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="5beda-118">Instalação no PC</span><span class="sxs-lookup"><span data-stu-id="5beda-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="5beda-119">Confira [Instalação da VDI](#vdi-installation) para obter instruções sobre como implantar o Teams em um ambiente de Virtual Desktop Infrastructure (VDI).</span><span class="sxs-lookup"><span data-stu-id="5beda-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="5beda-120">O Teams MSI colocará um instalador em Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="5beda-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="5beda-121">Sempre que um usuário fizer login em um novo perfil de usuário do Windows, o instalador será iniciado, e uma cópia do aplicativo Teams será instalada na pasta appdata desse usuário.</span><span class="sxs-lookup"><span data-stu-id="5beda-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="5beda-122">Se o usuário já tiver o aplicativo Teams instalado na pasta appdata, o instalador do MSI ignorará o processo para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="5beda-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="5beda-123">Não use o MSI para implantar atualizações, pois o cliente atualizará automaticamente quando detectar que há uma nova versão disponível no serviço.</span><span class="sxs-lookup"><span data-stu-id="5beda-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="5beda-124">Para reimplantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="5beda-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="5beda-125">Se você implantar uma versão mais antiga do pacote MSI, o cliente atualizará automaticamente (exceto em ambientes da VDI) para o usuário quando possível.</span><span class="sxs-lookup"><span data-stu-id="5beda-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="5beda-126">Se uma versão muito antiga for implantada, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams.</span><span class="sxs-lookup"><span data-stu-id="5beda-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="5beda-127">Não recomendamos mudar os locais de instalação padrão, pois isso pode interromper o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="5beda-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="5beda-128">Uma versão muito antiga pode impedir que os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="5beda-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="5beda-129">Requisitos do computador de destino</span><span class="sxs-lookup"><span data-stu-id="5beda-129">Target computer requirements</span></span>

- <span data-ttu-id="5beda-130">.NET framework 4.5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="5beda-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="5beda-131">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="5beda-131">Windows 7 or later</span></span>
- <span data-ttu-id="5beda-132">3 GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="5beda-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="5beda-133">Instalação da VDI</span><span class="sxs-lookup"><span data-stu-id="5beda-133">VDI installation</span></span>

<span data-ttu-id="5beda-134">Este é o processo de implantação do aplicativo de área de trabalho do Teams.</span><span class="sxs-lookup"><span data-stu-id="5beda-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="5beda-135">Para obter instruções completas, confira [Teams para Virtual Desktop Infrastructure](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="5beda-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="5beda-136">Baixe o pacote MSI do Teams usando um dos seguintes links, dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="5beda-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="5beda-137">Recomendamos a versão de 64 bits de uma máquina virtual (VM) da VDI com um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5beda-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="5beda-138">Versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="5beda-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="5beda-139">Versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="5beda-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="5beda-140">Execute o seguinte comando para instalar o MSI na VM da VDI (ou conclua a atualização).</span><span class="sxs-lookup"><span data-stu-id="5beda-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="5beda-141">Isso instala o Teams em Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="5beda-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="5beda-142">Nesse ponto, a configuração da imagem dourada está concluída.</span><span class="sxs-lookup"><span data-stu-id="5beda-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="5beda-143">A próxima sessão de logon interativo inicia o Teams e pede credenciais.</span><span class="sxs-lookup"><span data-stu-id="5beda-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="5beda-144">Lembre-se de que não é possível desativar o início automático do Teams ao instalá-lo na VDI usando a propriedade ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="5beda-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="5beda-145">Execute o comando a seguir para desinstalar o MSI na VM da VDI (ou preparar para atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="5beda-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="5beda-146">Isso desinstala o Teams do Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="5beda-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="5beda-147">Procedimento de limpeza e reimplantação</span><span class="sxs-lookup"><span data-stu-id="5beda-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="5beda-148">Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI rastreará que o usuário desinstalou o aplicativo Teams e não instalará mais o Teams para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="5beda-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="5beda-149">Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5beda-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="5beda-150">Desinstale o aplicativo Teams instalado para todos os perfis de usuário.</span><span class="sxs-lookup"><span data-stu-id="5beda-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="5beda-151">Após a desinstalação, exclua o diretório recursivamente em %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="5beda-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="5beda-152">Reimplante o pacote MSI no computador específico.</span><span class="sxs-lookup"><span data-stu-id="5beda-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="5beda-153">Você pode usar nosso script de [Limpeza de implantação do Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para concluir as etapas 1 e 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="5beda-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="5beda-154">Desabilitar o início automático do instalador MSI</span><span class="sxs-lookup"><span data-stu-id="5beda-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="5beda-155">O comportamento padrão do MSI é instalar o cliente do Teams assim que um usuário entrar e iniciá-lo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5beda-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="5beda-156">Você pode modificar esse comportamento com os parâmetros abaixo desta maneira:</span><span class="sxs-lookup"><span data-stu-id="5beda-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="5beda-157">Quando um usuário fizer logon no Windows, as equipes serão instaladas com o MSI</span><span class="sxs-lookup"><span data-stu-id="5beda-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="5beda-158">No entanto, o cliente do Teams não será iniciado até que o usuário o tenha iniciado manualmente</span><span class="sxs-lookup"><span data-stu-id="5beda-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="5beda-159">Um atalho para iniciar o Teams será adicionado à área de trabalho do usuário</span><span class="sxs-lookup"><span data-stu-id="5beda-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="5beda-160">Uma vez iniciado manualmente, o Teams será iniciado automaticamente sempre que o usuário fizer logon</span><span class="sxs-lookup"><span data-stu-id="5beda-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="5beda-161">Para a versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="5beda-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="5beda-162">Para a versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="5beda-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="5beda-163">Se executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="5beda-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="5beda-164">Mesmo que você o execute como administrador, se isso não for feito com permissões elevadas, o instalador não poderá configurar a opção para desabilitar o início automático.</span><span class="sxs-lookup"><span data-stu-id="5beda-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
