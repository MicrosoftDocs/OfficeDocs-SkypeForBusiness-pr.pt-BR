---
title: Instalar o Microsoft Teams usando MSI via SCCM
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Os administradores podem usar o Teams MSI para implantar em massa o Microsoft Teams para usuários ou computadores selecionados.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8412b6998e824c05ac4d7f394d2283c265f78b04
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "31749681"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="67ac2-103">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="67ac2-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="67ac2-104">Assista a sessão a seguir para saber mais sobre os benefícios do cliente de Desktop do Windows, como planejar para ele e como implantá-lo: [Equipes Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="67ac2-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="67ac2-105">Para usar o System Center Configuration Manager ou política de grupo ou qualquer mecanismos de distribuição de terceiros para implantação em larga escala, a Microsoft forneceu arquivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) e [64 bits](https://aka.ms/teams64bitmsi)) que os administradores podem usar para a implantação em massa de equipes para selecionar os usuários ou computadores.</span><span class="sxs-lookup"><span data-stu-id="67ac2-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="67ac2-106">Os administradores podem usar esses arquivos para implantar remotamente equipes para que os usuários não precisam baixar manualmente o aplicativo de equipes.</span><span class="sxs-lookup"><span data-stu-id="67ac2-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="67ac2-107">Quando implantado, equipes gerará automaticamente lançamento para todos os usuários que entram nesta máquina.</span><span class="sxs-lookup"><span data-stu-id="67ac2-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="67ac2-108">(É possível desabilitar depois de instalar o aplicativo de início automático.</span><span class="sxs-lookup"><span data-stu-id="67ac2-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="67ac2-109">[Veja abaixo](#disable-auto-launch-for-the-msi-installer).) Recomendamos que você implante o pacote para o computador, para que todos os novos usuários do computador também serão beneficiados com essa implantação.</span><span class="sxs-lookup"><span data-stu-id="67ac2-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="67ac2-110">Para saber mais sobre SCCM, consulte [Introdução para o System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="67ac2-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="67ac2-111">Procedimento de implantação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="67ac2-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="67ac2-112">Recupere o pacote mais recente.</span><span class="sxs-lookup"><span data-stu-id="67ac2-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="67ac2-113">Use os padrões pré-preenchido pelo MSI.</span><span class="sxs-lookup"><span data-stu-id="67ac2-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="67ac2-114">Implante em computadores quando possível.</span><span class="sxs-lookup"><span data-stu-id="67ac2-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="67ac2-115">Como funciona ao pacote MSI de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="67ac2-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="67ac2-116">Instalação de PC</span><span class="sxs-lookup"><span data-stu-id="67ac2-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="67ac2-117">Consulte [a instalação de VDI](#vdi-installation) para obter orientação sobre como implantar as equipes em um ambiente Virtual DesktopInfrastructure (VDI).</span><span class="sxs-lookup"><span data-stu-id="67ac2-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="67ac2-118">O MSI equipes colocará um instalador em arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="67ac2-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="67ac2-119">Sempre que um usuário se conecta em um novo perfil de usuário do Windows, o instalador será iniciado e uma cópia do aplicativo equipes será instalada na pasta de appdata desse usuário.</span><span class="sxs-lookup"><span data-stu-id="67ac2-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="67ac2-120">Se um usuário já tiver o aplicativo de equipes instalado na pasta appdata, o instalador MSI irá ignorar o processo para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="67ac2-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="67ac2-121">Não use o MSI para implantar atualizações, pois o cliente irá atualizar automaticamente quando detecta que uma nova versão é disponibilizada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="67ac2-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="67ac2-122">Para reimplantar o instalador mais recente use o processo de reimplantando MSI descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="67ac2-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="67ac2-123">Se você implantar uma versão mais antiga do pacote do MSI, o cliente será atualizado automaticamente sempre que possível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="67ac2-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="67ac2-124">Se uma versão antiga muito obtém implantada, o MSI irá disparar uma atualização do aplicativo antes que o usuário seja capaz de usar equipes.</span><span class="sxs-lookup"><span data-stu-id="67ac2-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="67ac2-125">Não recomendamos que você altere os locais de instalação padrão, como isso poderia quebrará o fluxo de atualização.</span><span class="sxs-lookup"><span data-stu-id="67ac2-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="67ac2-126">Ter uma versão antiga muito eventualmente bloqueará os usuários acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="67ac2-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="67ac2-127">Requisitos do computador de destino</span><span class="sxs-lookup"><span data-stu-id="67ac2-127">Target computer requirements</span></span>

- <span data-ttu-id="67ac2-128">.NET framework 4.5 ou posterior</span><span class="sxs-lookup"><span data-stu-id="67ac2-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="67ac2-129">Windows 7 ou posterior</span><span class="sxs-lookup"><span data-stu-id="67ac2-129">Windows 7 or later</span></span>
- <span data-ttu-id="67ac2-130">3 GB de espaço em disco para cada perfil de usuário (recomendado)</span><span class="sxs-lookup"><span data-stu-id="67ac2-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="67ac2-131">Instalação de VDI</span><span class="sxs-lookup"><span data-stu-id="67ac2-131">VDI installation</span></span>

<span data-ttu-id="67ac2-132">Aqui é o processo para implantar o aplicativo de área de trabalho de equipes.</span><span class="sxs-lookup"><span data-stu-id="67ac2-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="67ac2-133">Para obter orientação completa, consulte [as equipes de infraestrutura de área de trabalho virtualizados](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="67ac2-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="67ac2-134">Baixe o pacote MSI equipes usando um dos links a seguir, dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="67ac2-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="67ac2-135">Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="67ac2-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="67ac2-136">versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="67ac2-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="67ac2-137">versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="67ac2-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="67ac2-138">Execute o seguinte comando para instalar o MSI do VM VDI (ou concluir atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="67ac2-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="67ac2-139">Essa etapa instala equipes para arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="67ac2-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="67ac2-140">Neste ponto, a configuração de imagem de ouro estará concluída.</span><span class="sxs-lookup"><span data-stu-id="67ac2-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="67ac2-141">A próxima sessão de logon interativo inicia equipes e solicita credenciais.</span><span class="sxs-lookup"><span data-stu-id="67ac2-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="67ac2-142">Observe que não é possível desabilitar a inicialização automática das equipes ao instalar equipes em VDI usando a propriedade ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="67ac2-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="67ac2-143">Execute o seguinte comando para desinstalar o MSI de VDI VM (ou se preparar para atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="67ac2-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="67ac2-144">Isso desinstala equipes de arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="67ac2-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="67ac2-145">Limpeza e o procedimento de reimplantação</span><span class="sxs-lookup"><span data-stu-id="67ac2-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="67ac2-146">Se um usuário desinstala equipes de seu perfil de usuário, o instalador MSI irá controlar que o usuário tiver desinstalado o aplicativo de equipes e não são mais instalar equipes para esse perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="67ac2-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="67ac2-147">Para reimplantar equipes para esse usuário em um computador particular, onde ele foi desinstalado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="67ac2-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="67ac2-148">Desinstale o aplicativo de equipes instalado para cada perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="67ac2-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="67ac2-149">Após a desinstalação, exclua o diretório recursivamente em % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="67ac2-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="67ac2-150">Reimplante o pacote MSI nesse computador específico.</span><span class="sxs-lookup"><span data-stu-id="67ac2-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="67ac2-151">Você pode usar o nosso script de [implantação de equipes da Microsoft limpar](scripts/Powershell-script-teams-deployment-clean-up.md) para realizar as etapas 1 e 2 por meio do SCCM.</span><span class="sxs-lookup"><span data-stu-id="67ac2-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="67ac2-152">Desabilitar o recurso de início automático para o instalador MSI</span><span class="sxs-lookup"><span data-stu-id="67ac2-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="67ac2-153">Comportamento padrão do MSI é instalar o cliente de equipes, assim que um usuário entrar e iniciar automaticamente o equipes.</span><span class="sxs-lookup"><span data-stu-id="67ac2-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="67ac2-154">Você pode modificar esse comportamento com os parâmetros abaixo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="67ac2-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="67ac2-155">Quando um usuário fizer logon no Windows, equipes serão instaladas com o MSI</span><span class="sxs-lookup"><span data-stu-id="67ac2-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="67ac2-156">No entanto, o cliente de equipes não será iniciado até que o usuário tiver iniciado equipes manualmente</span><span class="sxs-lookup"><span data-stu-id="67ac2-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="67ac2-157">Um atalho para iniciar as equipes será adicionado na área de trabalho do usuário</span><span class="sxs-lookup"><span data-stu-id="67ac2-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="67ac2-158">Uma vez iniciado manualmente, equipes serão inicialização automática sempre que o usuário fizer logon</span><span class="sxs-lookup"><span data-stu-id="67ac2-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="67ac2-159">Para obter a versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="67ac2-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="67ac2-160">Para obter a versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="67ac2-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="67ac2-161">Se você executar o MSI manualmente, certifique-se de executá-lo com permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="67ac2-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="67ac2-162">Mesmo se você executá-lo como um administrador, sem executá-lo com permissões elevadas, o instalador não poderão configurar a opção para desabilitar AutoIniciar.</span><span class="sxs-lookup"><span data-stu-id="67ac2-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
