---
title: Instalar o Microsoft Teams usando MSI por meio do Gerenciador de configuração do Microsoft Endpoint
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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c048e321241f4403fbb69f71e56b3fc179346951
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327823"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="940d9-103">Instalar o Microsoft Teams usando o Gerenciador de configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="940d9-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="940d9-104">Assista à sessão a seguir para conhecer os benefícios do Windows Desktop Client e como planejar e executar sua implantação: [Cliente de Desktop do Microsoft Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="940d9-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="940d9-105">Para usar o Gerenciador de configuração do Microsoft Endpoint ou a política de grupo ou qualquer mecanismo de distribuição de terceiros para implantação ampla, a Microsoft forneceu arquivos MSI (32 bits e 64 bits) que os administradores podem usar para a implantação em massa do teams para selecionar usuários ou computadores.</span><span class="sxs-lookup"><span data-stu-id="940d9-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="940d9-106">Os administradores podem usar esses arquivos para implantar o Teams remotamente, de modo que os usuários não precisem baixar manualmente o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="940d9-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="940d9-107">Quando implantado, o Teams iniciará automaticamente para todos os usuários que fizerem logon naquele computador.</span><span class="sxs-lookup"><span data-stu-id="940d9-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="940d9-108">(Você pode desabilitar o início automático depois de instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="940d9-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="940d9-109">[Confira abaixo](#disable-auto-launch-for-the-msi-installer).) É recomendável implantar o pacote no computador para que todos os novos usuários dele também se beneficiem com a implantação.</span><span class="sxs-lookup"><span data-stu-id="940d9-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="940d9-110">Estes são os links para os arquivos MSI:</span><span class="sxs-lookup"><span data-stu-id="940d9-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="940d9-111">Entity</span><span class="sxs-lookup"><span data-stu-id="940d9-111">Entity</span></span>  |<span data-ttu-id="940d9-112">32 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-112">32 bit</span></span>      |<span data-ttu-id="940d9-113">64 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="940d9-114">Empresas</span><span class="sxs-lookup"><span data-stu-id="940d9-114">Commercial</span></span>     | [<span data-ttu-id="940d9-115">32 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="940d9-116">64 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="940d9-117">Governo Federal-GCC</span><span class="sxs-lookup"><span data-stu-id="940d9-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="940d9-118">32 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="940d9-119">64 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="940d9-120">Governo Federal-GCC alto</span><span class="sxs-lookup"><span data-stu-id="940d9-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="940d9-121">32 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="940d9-122">64 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="940d9-123">Governo Federal-DoD</span><span class="sxs-lookup"><span data-stu-id="940d9-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="940d9-124">32 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="940d9-125">64 bit</span><span class="sxs-lookup"><span data-stu-id="940d9-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="940d9-126">O Teams também pode ser incluído em uma implantação do Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="940d9-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="940d9-127">Para obter mais informações, confira [Implantar o Microsoft Teams com Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="940d9-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="940d9-128">Para saber mais sobre o Gerenciador de configuração do Microsoft EndPoint, consulte [o que é o Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="940d9-128">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="940d9-129">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="940d9-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="940d9-130">Recupere o pacote mais recente.</span><span class="sxs-lookup"><span data-stu-id="940d9-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="940d9-131">Use os padrões pré-preenchidos pelo MSI.</span><span class="sxs-lookup"><span data-stu-id="940d9-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="940d9-132">Implante nos computadores quando possível.</span><span class="sxs-lookup"><span data-stu-id="940d9-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="940d9-133">Como o pacote Microsoft Teams MSI funciona</span><span class="sxs-lookup"><span data-stu-id="940d9-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="940d9-134">Instalação no PC</span><span class="sxs-lookup"><span data-stu-id="940d9-134">PC installation</span></span>

<span data-ttu-id="940d9-135">O Teams MSI colocará um instalador em Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="940d9-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="940d9-136">Sempre que um usuário entrar em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo Teams será instalada na `AppData` pasta desse usuário.</span><span class="sxs-lookup"><span data-stu-id="940d9-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="940d9-137">Se um usuário já tiver o aplicativo Teams instalado na `AppData` pasta, o instalador do MSI ignorará o processo desse usuário.</span><span class="sxs-lookup"><span data-stu-id="940d9-137">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="940d9-138">Não use o MSI para implantar atualizações, pois o cliente atualizará automaticamente quando detectar que há uma nova versão disponível no serviço.</span><span class="sxs-lookup"><span data-stu-id="940d9-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="940d9-139">Para reimplantar o instalador mais recente, use o processo de reimplantação do MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="940d9-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="940d9-140">Se você implantar uma versão mais antiga do pacote MSI, o cliente atualizará automaticamente (exceto em ambientes da VDI) para o usuário quando possível.</span><span class="sxs-lookup"><span data-stu-id="940d9-140">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="940d9-141">Se uma versão muito antiga for implantada, o MSI acionará uma atualização do aplicativo antes que o usuário possa usar o Teams.</span><span class="sxs-lookup"><span data-stu-id="940d9-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="940d9-142">Não recomendamos mudar os locais de instalação padrão, pois isso pode interromper o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="940d9-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="940d9-143">Uma versão muito antiga pode impedir que os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="940d9-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="940d9-144">Requisitos do computador de destino</span><span class="sxs-lookup"><span data-stu-id="940d9-144">Target computer requirements</span></span>

- <span data-ttu-id="940d9-145">.NET framework 4.5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="940d9-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="940d9-146">Windows 8,1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="940d9-146">Windows 8.1 or later</span></span>
- <span data-ttu-id="940d9-147">Windows Server 2012 R2 ou posterior</span><span class="sxs-lookup"><span data-stu-id="940d9-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="940d9-148">3 GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="940d9-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="940d9-149">Instalação da VDI</span><span class="sxs-lookup"><span data-stu-id="940d9-149">VDI installation</span></span>

<span data-ttu-id="940d9-150">Para obter uma orientação completa sobre como implantar o aplicativo da área de trabalho Teams no VDI, consulte [Teams para infraestrutura de área de trabalho virtualizada](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="940d9-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="940d9-151">Procedimento de limpeza e reimplantação</span><span class="sxs-lookup"><span data-stu-id="940d9-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="940d9-152">Se um usuário desinstalar o Teams do seu perfil de usuário, o instalador do MSI rastreará que o usuário desinstalou o aplicativo Teams e não instalará mais o Teams para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="940d9-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="940d9-153">Para reimplantar o Teams para esse usuário em um determinado computador em que foi desinstalado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="940d9-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="940d9-154">Desinstale o aplicativo Teams instalado para todos os perfis de usuário.</span><span class="sxs-lookup"><span data-stu-id="940d9-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="940d9-155">Após a desinstalação, exclua o diretório `%localappdata%\Microsoft\Teams\`recursivamente em.</span><span class="sxs-lookup"><span data-stu-id="940d9-155">After uninstall, delete directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="940d9-156">Reimplante o pacote MSI no computador específico.</span><span class="sxs-lookup"><span data-stu-id="940d9-156">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="940d9-157">Impedir que o Microsoft Teams inicie automaticamente após a instalação</span><span class="sxs-lookup"><span data-stu-id="940d9-157">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="940d9-158">O comportamento padrão do MSI é instalar o aplicativo Teams assim que um usuário entrar e iniciar automaticamente o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="940d9-158">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="940d9-159">Se não quiser que as equipes iniciem automaticamente para os usuários após a instalação, você pode usar a política de grupo para definir uma configuração de política ou desabilitar o início automático para o instalador MSI.</span><span class="sxs-lookup"><span data-stu-id="940d9-159">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="940d9-160">Usar política de grupo (recomendado)</span><span class="sxs-lookup"><span data-stu-id="940d9-160">Use Group Policy (recommended)</span></span>

<span data-ttu-id="940d9-161">Habilite a configuração **impedir que o Microsoft Teams seja iniciado automaticamente após a instalação** da política de grupo.</span><span class="sxs-lookup"><span data-stu-id="940d9-161">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="940d9-162">Você pode encontrar essa configuração de política nas equipes do usuário Templates\Microsoft de configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="940d9-162">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="940d9-163">Esse é o método recomendado porque você pode desativar ou ativar a configuração de política de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="940d9-163">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="940d9-164">Quando você habilitar essa configuração de política antes de instalar o Microsoft Teams, o Teams não iniciará automaticamente quando os usuários fizerem logon no Windows.</span><span class="sxs-lookup"><span data-stu-id="940d9-164">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="940d9-165">Após o usuário entrar no Microsoft Teams pela primeira vez, o Teams é iniciado automaticamente na próxima vez que o usuário faz logon.</span><span class="sxs-lookup"><span data-stu-id="940d9-165">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="940d9-166">Para saber mais, consulte [usar a política de grupo para impedir que o Microsoft Teams inicie automaticamente após a instalação](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span><span class="sxs-lookup"><span data-stu-id="940d9-166">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="940d9-167">Se você já implantou o Microsoft Teams e quer definir essa política para desabilitar o AutoStart do Teams, primeiro defina a configuração da política de grupo com o valor desejado e execute o script do Microsoft [AutoStart Reset](scripts/powershell-script-teams-reset-autostart.md) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="940d9-167">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="940d9-168">Desabilitar o início automático do instalador MSI</span><span class="sxs-lookup"><span data-stu-id="940d9-168">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="940d9-169">Você pode desabilitar o início automático para o instalador MSI usando o parâmetro **Options = "noAutoStart = true"** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="940d9-169">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="940d9-170">Para a versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="940d9-170">For the 32-bit version</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="940d9-171">Para a versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="940d9-171">For the 64-bit version</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="940d9-172">Quando um usuário faz logon no Windows, o Microsoft Teams é instalado com o MSI e um atalho para iniciar o Teams é adicionado à área de trabalho do usuário.</span><span class="sxs-lookup"><span data-stu-id="940d9-172">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="940d9-173">O Microsoft Teams não começará até que o usuário inicie manualmente o Teams.</span><span class="sxs-lookup"><span data-stu-id="940d9-173">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="940d9-174">Após o usuário iniciar manualmente o Teams, o Teams é iniciado automaticamente sempre que o usuário faz logon.</span><span class="sxs-lookup"><span data-stu-id="940d9-174">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="940d9-175">Se executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="940d9-175">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="940d9-176">Mesmo que você o execute como administrador, sem executá-lo com permissões elevadas, o instalador não poderá configurar a opção de desabilitar o início automático.</span><span class="sxs-lookup"><span data-stu-id="940d9-176">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
