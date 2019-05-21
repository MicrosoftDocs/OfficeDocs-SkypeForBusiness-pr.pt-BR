---
title: Instalar o Microsoft Teams usando MSI via SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Os administradores podem usar o Teams MSI para implantar em massa o Microsoft Teams para usuários ou computadores selecionados.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c009433696ac554114a2a06955b4f33beb6543f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281613"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="480c0-103">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="480c0-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="480c0-104">Assista à sessão a seguir para saber mais sobre os benefícios do cliente da área de trabalho do Windows, como planejar e como implantá-lo: [cliente de área de trabalho do Microsoft Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="480c0-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="480c0-105">Para usar o System Center Configuration Manager ou a política de grupo ou qualquer mecanismo de distribuição de terceiros para implantação ampla, a Microsoft forneceu arquivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) e [64](https://aka.ms/teams64bitmsi)bits) que os administradores podem usar para a implantação em massa de Teams para selecionar usuários ou computadores.</span><span class="sxs-lookup"><span data-stu-id="480c0-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="480c0-106">Os administradores podem usar esses arquivos para implantar equipes remotamente para que os usuários não precisem baixar manualmente o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="480c0-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="480c0-107">Quando implantada, o Microsoft Teams será iniciado automaticamente para todos os usuários que entrarem nesse computador.</span><span class="sxs-lookup"><span data-stu-id="480c0-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="480c0-108">(Você pode desabilitar o início automático após a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="480c0-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="480c0-109">[Veja abaixo](#disable-auto-launch-for-the-msi-installer).) Recomendamos que você implante o pacote no computador para que todos os novos usuários do computador também se beneficiem dessa implantação.</span><span class="sxs-lookup"><span data-stu-id="480c0-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="480c0-110">Para saber mais sobre o SCCM, confira [introdução ao System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="480c0-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="480c0-111">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="480c0-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="480c0-112">Recupere o pacote mais recente.</span><span class="sxs-lookup"><span data-stu-id="480c0-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="480c0-113">Use os padrões previamente preenchidos pelo MSI.</span><span class="sxs-lookup"><span data-stu-id="480c0-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="480c0-114">Implantar para computadores quando possível.</span><span class="sxs-lookup"><span data-stu-id="480c0-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="480c0-115">Como funciona o pacote MSI do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="480c0-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="480c0-116">Instalação do PC</span><span class="sxs-lookup"><span data-stu-id="480c0-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="480c0-117">Confira a [instalação do VDI](#vdi-installation) para obter orientação sobre como implantar o Microsoft Teams em um ambiente virtual DESKTOPINFRASTRUCTURE (VDI).</span><span class="sxs-lookup"><span data-stu-id="480c0-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="480c0-118">O MSI do teams colocará um instalador em arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="480c0-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="480c0-119">Sempre que um usuário entrar em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo Teams será instalada na pasta AppData daquele usuário.</span><span class="sxs-lookup"><span data-stu-id="480c0-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="480c0-120">Se um usuário já tiver o aplicativo Teams instalado na pasta AppData, o instalador do MSI ignorará o processo desse usuário.</span><span class="sxs-lookup"><span data-stu-id="480c0-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="480c0-121">Não use o MSI para implantar atualizações, porque o cliente será atualizado automaticamente quando detectar que uma nova versão está disponível no serviço.</span><span class="sxs-lookup"><span data-stu-id="480c0-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="480c0-122">Para implantar novamente o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="480c0-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="480c0-123">Se você implantar uma versão mais antiga do pacote MSI, o cliente será atualizado automaticamente quando possível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="480c0-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="480c0-124">Se uma versão muito antiga for implantada, o MSI disparará uma atualização de aplicativo antes que o usuário possa usar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="480c0-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="480c0-125">Não recomendamos que você altere os locais de instalação padrão, pois isso pode interromper o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="480c0-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="480c0-126">Com uma versão muito antiga, você poderá impedir que os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="480c0-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="480c0-127">Requisitos do computador de destino</span><span class="sxs-lookup"><span data-stu-id="480c0-127">Target computer requirements</span></span>

- <span data-ttu-id="480c0-128">.NET Framework 4,5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="480c0-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="480c0-129">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="480c0-129">Windows 7 or later</span></span>
- <span data-ttu-id="480c0-130">3 GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="480c0-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="480c0-131">Instalação do VDI</span><span class="sxs-lookup"><span data-stu-id="480c0-131">VDI installation</span></span>

<span data-ttu-id="480c0-132">Aqui está o processo para implantar o aplicativo da área de trabalho Teams.</span><span class="sxs-lookup"><span data-stu-id="480c0-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="480c0-133">Para obter uma orientação completa, consulte [Teams for Virtual Desktop Infrastructure](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="480c0-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="480c0-134">Baixe o pacote MSI do teams usando um dos links a seguir, dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="480c0-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="480c0-135">Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="480c0-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="480c0-136">versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="480c0-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="480c0-137">versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="480c0-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="480c0-138">Execute o seguinte comando para instalar o MSI na VM VDI (ou conclua a atualização).</span><span class="sxs-lookup"><span data-stu-id="480c0-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    <span data-ttu-id="480c0-139">Isso instala o Microsoft Teams para arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="480c0-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="480c0-140">Neste ponto, a configuração da imagem dourada está completa.</span><span class="sxs-lookup"><span data-stu-id="480c0-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="480c0-141">A próxima sessão de logon interativo inicia o Teams e solicita credenciais.</span><span class="sxs-lookup"><span data-stu-id="480c0-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="480c0-142">Observe que não é possível desabilitar a inicialização automática de equipes ao instalar o Microsoft Teams no VDI usando a propriedade ALLUSERS.</span><span class="sxs-lookup"><span data-stu-id="480c0-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSERS property.</span></span>

3. <span data-ttu-id="480c0-143">Execute o comando a seguir para desinstalar o MSI da VM VDI (ou preparar-se para atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="480c0-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="480c0-144">Isso desinstala equipes de arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="480c0-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="480c0-145">Procedimento de limpeza e reimplantação</span><span class="sxs-lookup"><span data-stu-id="480c0-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="480c0-146">Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI acompanhará que o usuário desinstalou o aplicativo Teams e não instalará mais equipes para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="480c0-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="480c0-147">Para reimplantar equipes para este usuário em um determinado computador onde ela foi desinstalada, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="480c0-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="480c0-148">Desinstalar o aplicativo Teams instalado para cada perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="480c0-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="480c0-149">Após a desinstalação, excluir o diretório recursivamente em%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="480c0-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="480c0-150">Reimplante o pacote MSI nesse computador específico.</span><span class="sxs-lookup"><span data-stu-id="480c0-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="480c0-151">Você pode usar o script de [limpeza de implantação do Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para executar as etapas 1 e 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="480c0-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="480c0-152">Desabilitar o início automático para o instalador MSI</span><span class="sxs-lookup"><span data-stu-id="480c0-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="480c0-153">O comportamento padrão do MSI é instalar o cliente do teams assim que um usuário entrar e iniciar automaticamente o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="480c0-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="480c0-154">Você pode modificar esse comportamento com os parâmetros abaixo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="480c0-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="480c0-155">Quando um usuário faz logon no Windows, o Microsoft Teams será instalado com o MSI</span><span class="sxs-lookup"><span data-stu-id="480c0-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="480c0-156">No entanto, o cliente do Teams não iniciará até que o usuário inicie manualmente as equipes</span><span class="sxs-lookup"><span data-stu-id="480c0-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="480c0-157">Um atalho para iniciar equipes será adicionado à área de trabalho do usuário</span><span class="sxs-lookup"><span data-stu-id="480c0-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="480c0-158">Uma vez iniciado manualmente, o Teams será iniciado automaticamente sempre que o usuário fizer logon</span><span class="sxs-lookup"><span data-stu-id="480c0-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="480c0-159">Para a versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="480c0-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="480c0-160">Para a versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="480c0-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="480c0-161">Se você executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="480c0-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="480c0-162">Mesmo que você o execute como administrador, sem executá-lo com permissões elevadas, o instalador não poderá configurar a opção de desabilitar o início automático.</span><span class="sxs-lookup"><span data-stu-id="480c0-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
