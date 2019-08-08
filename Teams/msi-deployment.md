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
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e2354c28916af3c1c0be47848ee7bd2a72bf278
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238662"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="3be5e-103">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="3be5e-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="3be5e-104">Assista à sessão a seguir para saber mais sobre os benefícios do cliente da área de trabalho do Windows, como planejar e como implantá-lo: [cliente de área de trabalho do Microsoft Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="3be5e-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="3be5e-105">Para usar o System Center Configuration Manager ou a política de grupo ou qualquer mecanismo de distribuição de terceiros para implantação ampla, a Microsoft forneceu arquivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) e [64](https://aka.ms/teams64bitmsi)bits) que os administradores podem usar para a implantação em massa de Teams para selecionar usuários ou computadores.</span><span class="sxs-lookup"><span data-stu-id="3be5e-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="3be5e-106">Os administradores podem usar esses arquivos para implantar equipes remotamente para que os usuários não precisem baixar manualmente o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="3be5e-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="3be5e-107">Quando implantada, o Microsoft Teams será iniciado automaticamente para todos os usuários que entrarem nesse computador.</span><span class="sxs-lookup"><span data-stu-id="3be5e-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="3be5e-108">(Você pode desabilitar o início automático após a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3be5e-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="3be5e-109">[Veja abaixo](#disable-auto-launch-for-the-msi-installer).) Recomendamos que você implante o pacote no computador para que todos os novos usuários do computador também se beneficiem dessa implantação.</span><span class="sxs-lookup"><span data-stu-id="3be5e-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="3be5e-110">As equipes também podem ser incluídas com uma implantação do Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="3be5e-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="3be5e-111">Para obter mais informações, consulte [implantar o Microsoft Teams com o Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="3be5e-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="3be5e-112">Para saber mais sobre o SCCM, confira [introdução ao System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="3be5e-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="3be5e-113">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="3be5e-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="3be5e-114">Recupere o pacote mais recente.</span><span class="sxs-lookup"><span data-stu-id="3be5e-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="3be5e-115">Use os padrões previamente preenchidos pelo MSI.</span><span class="sxs-lookup"><span data-stu-id="3be5e-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="3be5e-116">Implantar para computadores quando possível.</span><span class="sxs-lookup"><span data-stu-id="3be5e-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="3be5e-117">Como funciona o pacote MSI do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3be5e-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="3be5e-118">Instalação do PC</span><span class="sxs-lookup"><span data-stu-id="3be5e-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="3be5e-119">Confira a [instalação do VDI](#vdi-installation) para obter orientação sobre como implantar o Microsoft Teams em um ambiente virtual DESKTOPINFRASTRUCTURE (VDI).</span><span class="sxs-lookup"><span data-stu-id="3be5e-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="3be5e-120">O MSI do teams colocará um instalador em arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="3be5e-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="3be5e-121">Sempre que um usuário entrar em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo Teams será instalada na pasta AppData daquele usuário.</span><span class="sxs-lookup"><span data-stu-id="3be5e-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="3be5e-122">Se um usuário já tiver o aplicativo Teams instalado na pasta AppData, o instalador do MSI ignorará o processo desse usuário.</span><span class="sxs-lookup"><span data-stu-id="3be5e-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="3be5e-123">Não use o MSI para implantar atualizações, porque o cliente será atualizado automaticamente quando detectar que uma nova versão está disponível no serviço.</span><span class="sxs-lookup"><span data-stu-id="3be5e-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="3be5e-124">Para implantar novamente o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="3be5e-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="3be5e-125">Se você implantar uma versão mais antiga do pacote MSI, o cliente será atualizado automaticamente (exceto em ambientes VDI) quando possível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="3be5e-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="3be5e-126">Se uma versão muito antiga for implantada, o MSI disparará uma atualização de aplicativo antes que o usuário possa usar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3be5e-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="3be5e-127">Não recomendamos que você altere os locais de instalação padrão, pois isso pode interromper o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="3be5e-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="3be5e-128">Com uma versão muito antiga, você poderá impedir que os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="3be5e-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="3be5e-129">Requisitos do computador de destino</span><span class="sxs-lookup"><span data-stu-id="3be5e-129">Target computer requirements</span></span>

- <span data-ttu-id="3be5e-130">.NET Framework 4,5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="3be5e-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="3be5e-131">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="3be5e-131">Windows 7 or later</span></span>
- <span data-ttu-id="3be5e-132">3 GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="3be5e-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="3be5e-133">Instalação do VDI</span><span class="sxs-lookup"><span data-stu-id="3be5e-133">VDI installation</span></span>

<span data-ttu-id="3be5e-134">Aqui está o processo para implantar o aplicativo da área de trabalho Teams.</span><span class="sxs-lookup"><span data-stu-id="3be5e-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="3be5e-135">Para obter uma orientação completa, consulte [Teams for Virtual Desktop Infrastructure](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="3be5e-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="3be5e-136">Baixe o pacote MSI do teams usando um dos links a seguir, dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="3be5e-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="3be5e-137">Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3be5e-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="3be5e-138">versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="3be5e-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="3be5e-139">versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="3be5e-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="3be5e-140">Execute o seguinte comando para instalar o MSI na VM VDI (ou conclua a atualização).</span><span class="sxs-lookup"><span data-stu-id="3be5e-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="3be5e-141">Isso instala o Microsoft Teams para arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="3be5e-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="3be5e-142">Neste ponto, a configuração da imagem dourada está completa.</span><span class="sxs-lookup"><span data-stu-id="3be5e-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="3be5e-143">A próxima sessão de logon interativo inicia o Teams e solicita credenciais.</span><span class="sxs-lookup"><span data-stu-id="3be5e-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="3be5e-144">Observe que não é possível desabilitar a inicialização automática de equipes ao instalar o Microsoft Teams no VDI usando a propriedade MyUser.</span><span class="sxs-lookup"><span data-stu-id="3be5e-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="3be5e-145">Execute o comando a seguir para desinstalar o MSI da VM VDI (ou preparar-se para atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="3be5e-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="3be5e-146">Isso desinstala equipes de arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="3be5e-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="3be5e-147">Procedimento de limpeza e reimplantação</span><span class="sxs-lookup"><span data-stu-id="3be5e-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="3be5e-148">Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI acompanhará que o usuário desinstalou o aplicativo Teams e não instalará mais equipes para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="3be5e-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="3be5e-149">Para reimplantar equipes para este usuário em um determinado computador onde ela foi desinstalada, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3be5e-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="3be5e-150">Desinstalar o aplicativo Teams instalado para cada perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="3be5e-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="3be5e-151">Após a desinstalação, excluir o diretório recursivamente em%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="3be5e-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="3be5e-152">Reimplante o pacote MSI nesse computador específico.</span><span class="sxs-lookup"><span data-stu-id="3be5e-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="3be5e-153">Você pode usar o script de [limpeza de implantação do Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para executar as etapas 1 e 2 via SCCM.</span><span class="sxs-lookup"><span data-stu-id="3be5e-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="3be5e-154">Desabilitar o início automático para o instalador MSI</span><span class="sxs-lookup"><span data-stu-id="3be5e-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="3be5e-155">O comportamento padrão do MSI é instalar o cliente do teams assim que um usuário entrar e iniciar automaticamente o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3be5e-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="3be5e-156">Você pode modificar esse comportamento com os parâmetros abaixo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3be5e-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="3be5e-157">Quando um usuário faz logon no Windows, o Microsoft Teams será instalado com o MSI</span><span class="sxs-lookup"><span data-stu-id="3be5e-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="3be5e-158">No entanto, o cliente do Teams não iniciará até que o usuário inicie manualmente as equipes</span><span class="sxs-lookup"><span data-stu-id="3be5e-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="3be5e-159">Um atalho para iniciar equipes será adicionado à área de trabalho do usuário</span><span class="sxs-lookup"><span data-stu-id="3be5e-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="3be5e-160">Uma vez iniciado manualmente, o Teams será iniciado automaticamente sempre que o usuário fizer logon</span><span class="sxs-lookup"><span data-stu-id="3be5e-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="3be5e-161">Para a versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="3be5e-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="3be5e-162">Para a versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="3be5e-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="3be5e-163">Se você executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="3be5e-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="3be5e-164">Mesmo que você o execute como administrador, sem executá-lo com permissões elevadas, o instalador não poderá configurar a opção de desabilitar o início automático.</span><span class="sxs-lookup"><span data-stu-id="3be5e-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
