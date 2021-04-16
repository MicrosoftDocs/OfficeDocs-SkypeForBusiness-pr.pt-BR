---
title: Obter clientes do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
localization_priority: Priority
search.appverid: MET150
description: Aprenda a usar os vários clientes disponíveis para o Microsoft Teams, que incluem web, área de trabalho (Windows e Mac) e dispositivos móveis (Android e iOS).
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8385e6721a24c3ad1bd320dd2f6e5e14091181b0
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768220"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="24c34-103">Obter clientes do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24c34-103">Get clients for Microsoft Teams</span></span>

<span data-ttu-id="24c34-104">O Microsoft Teams tem clientes disponíveis para desktop (Windows, Mac e Linux), web e dispositivos móveis (Android e iOS).</span><span class="sxs-lookup"><span data-stu-id="24c34-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="24c34-105">Todos esses clientes precisam de uma conexão à internet ativa e não são suportados em modo offline.</span><span class="sxs-lookup"><span data-stu-id="24c34-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="24c34-106">Para obter detalhes sobre os recursos de cada cliente em diferentes plataformas, confira [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="24c34-106">For details about each clients' capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>
>
> <span data-ttu-id="24c34-107">A partir de 29 de novembro de 2018, você não poderá mais usar o aplicativo Microsoft Teams para Windows 10 S (Visualização), disponível na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="24c34-107">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="24c34-108">Em vez disso, agora você pode baixar e instalar o cliente de área de trabalho do Teams em dispositivos executando o modo Windows 10 S.</span><span class="sxs-lookup"><span data-stu-id="24c34-108">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="24c34-109">Para baixar o cliente de área de trabalho, vá para [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/p/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="24c34-109">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/p/?linkid=855754).</span></span> <span data-ttu-id="24c34-110">As compilações MSI do cliente de área de trabalho do Teams ainda não estão disponíveis para dispositivos executando o modo Windows 10 S.</span><span class="sxs-lookup"><span data-stu-id="24c34-110">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="24c34-111">Para obter mais informações sobre o modo Windows 10 S, consulte [Introdução ao Windows 10 no modo S](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="24c34-111">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span>

## <a name="desktop-client"></a><span data-ttu-id="24c34-112">Cliente de desktop</span><span class="sxs-lookup"><span data-stu-id="24c34-112">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="24c34-113">Assista à sessão a seguir para conhecer os benefícios do Windows Desktop Client e como planejar e executar sua implantação: [Cliente de Desktop do Microsoft Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="24c34-113">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="24c34-114">O cliente de área de trabalho do Microsoft Teams é um aplicativo autônomo e também está [disponível no Microsoft 365 Apps para Grandes Empresas](/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="24c34-114">The Microsoft Teams desktop client is a standalone application and is also [available in Microsoft 365 Apps for enterprise](/deployoffice/teams-install).</span></span> <span data-ttu-id="24c34-115">O Teams está disponível para versões de 32 e 64 bits do Windows (8.1 ou posterior), ARM64 para Windows 10 no ARM e Windows Server (2012 R2 ou posterior), bem como para macOS e Linux (em formatos `.deb` e `.rpm`).</span><span class="sxs-lookup"><span data-stu-id="24c34-115">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later), ARM64 for Windows 10 on ARM, and Windows Server (2012 R2 or later), as well as for macOS and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="24c34-116">No Windows, o Teams exige o .NET Framework 4.5 ou posterior; o instalador do Teams oferecerá instalá-lo para você se você não o tiver.</span><span class="sxs-lookup"><span data-stu-id="24c34-116">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="24c34-117">No Linux, os gerenciadores de pacote, como `apt` e `yum`, tentarão instalar quaisquer requisitos para você.</span><span class="sxs-lookup"><span data-stu-id="24c34-117">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="24c34-118">No entanto, se eles não instalarem, você precisará instalar todos os requisitos relatados antes de instalar o Teams no Linux.</span><span class="sxs-lookup"><span data-stu-id="24c34-118">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="24c34-119">Os clientes de área de trabalho fornecem suporte de comunicação em tempo real (áudio, vídeo e compartilhamento de conteúdo) para reuniões de equipe, chamadas em grupo e chamadas individuais privadas.</span><span class="sxs-lookup"><span data-stu-id="24c34-119">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="24c34-120">Os clientes de desktop podem ser baixados e instalados diretamente pelos usuários finais[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) se tiverem as permissões locais apropriadas (direitos de administrador não são necessários para instalar o cliente Teams em um PC, mas são necessários em um Mac).</span><span class="sxs-lookup"><span data-stu-id="24c34-120">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="24c34-121">Para obter mais detalhes sobre a instalação do Teams em um Chromebook, confira [Como instalar e executar o Microsoft Office em um Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span><span class="sxs-lookup"><span data-stu-id="24c34-121">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="24c34-122">Os administradores de TI podem escolher seu método preferido para distribuir os arquivos de instalação aos computadores de sua organização.</span><span class="sxs-lookup"><span data-stu-id="24c34-122">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="24c34-123">Entre os exemplos estão o Microsoft Endpoint Configuration Manager (Windows) ou Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="24c34-123">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="24c34-124">Para obter o pacote MSI para distribuições do Windows, consulte [Instalar o Microsoft Teams usando MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="24c34-124">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="24c34-125">A distribuição do cliente por esses mecanismos é apenas para a instalação inicial dos clientes Microsoft Teams, e não para atualizações futuras.</span><span class="sxs-lookup"><span data-stu-id="24c34-125">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="24c34-126">Windows</span><span class="sxs-lookup"><span data-stu-id="24c34-126">Windows</span></span>

<span data-ttu-id="24c34-127">A instalação do Microsoft Teams para Windows oferece instaladores para download nas arquiteturas de 32 bits e 64 bits.</span><span class="sxs-lookup"><span data-stu-id="24c34-127">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="24c34-128">A arquitetura (32 bits vs. 64 bits) do Microsoft Teams é independente da arquitetura do Windows e do Office instalados.</span><span class="sxs-lookup"><span data-stu-id="24c34-128">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="24c34-129">O cliente Windows é implantado na pasta AppData localizada no perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="24c34-129">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="24c34-130">A implantação no perfil local do usuário permite que o cliente seja instalado sem exigir direitos elevados.</span><span class="sxs-lookup"><span data-stu-id="24c34-130">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="24c34-131">O cliente Windows aproveita os seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="24c34-131">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="24c34-132">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="24c34-132">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="24c34-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="24c34-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="24c34-134">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="24c34-134">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="24c34-135">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="24c34-135">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="24c34-136">Quando os usuários iniciam uma chamada usando o cliente Microsoft Teams pela primeira vez, eles podem notar um aviso com as configurações de firewall do Windows, que solicita que os usuários permitam a comunicação.</span><span class="sxs-lookup"><span data-stu-id="24c34-136">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="24c34-137">Os usuários podem ser instruídos a ignorar esta mensagem porque a chamada funcionará mesmo quando o aviso for recusado.</span><span class="sxs-lookup"><span data-stu-id="24c34-137">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Captura de tela de um diálogo do Alerta de Segurança do Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="24c34-139">A configuração do Firewall do Windows será alterada mesmo quando o aviso for descartado ao selecionar “Cancelar”.</span><span class="sxs-lookup"><span data-stu-id="24c34-139">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="24c34-140">Duas regras de entrada para o teams.exe serão criadas com a ação Permitir para os protocolos TCP e UDP.</span><span class="sxs-lookup"><span data-stu-id="24c34-140">Two inbound rules for teams.exe will be created with Allow action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="24c34-141">Se você deseja impedir que o Teams solicite que os usuários criem regras de firewall quando eles fizerem sua primeira chamada do Teams, use o [Script do PowerShell de exemplo - regra de firewall de entrada](#sample-powershell-script---inbound-firewall-rule) a seguir.</span><span class="sxs-lookup"><span data-stu-id="24c34-141">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span>

### <a name="mac"></a><span data-ttu-id="24c34-142">Mac</span><span class="sxs-lookup"><span data-stu-id="24c34-142">Mac</span></span>

<span data-ttu-id="24c34-143">Usuários de Mac podem instalar o Teams usando um arquivo de instalação PKG para computadores macOS.</span><span class="sxs-lookup"><span data-stu-id="24c34-143">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="24c34-144">É necessário acesso administrativo para instalar o cliente Mac.</span><span class="sxs-lookup"><span data-stu-id="24c34-144">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="24c34-145">O cliente macOS é instalado na pasta /Applications.</span><span class="sxs-lookup"><span data-stu-id="24c34-145">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="24c34-146">Instalar o Teams usando o arquivo PKG</span><span class="sxs-lookup"><span data-stu-id="24c34-146">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="24c34-147">Na [página de download do Teams](https://teams.microsoft.com/downloads), em **Mac**, clique em **Download**.</span><span class="sxs-lookup"><span data-stu-id="24c34-147">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="24c34-148">Clique duas vezes no arquivo PKG.</span><span class="sxs-lookup"><span data-stu-id="24c34-148">Double click the PKG file.</span></span>
3. <span data-ttu-id="24c34-149">Siga o assistente de instalação para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="24c34-149">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="24c34-150">O Teams será instalado na pasta /Applications.</span><span class="sxs-lookup"><span data-stu-id="24c34-150">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="24c34-151">É uma instalação em toda a máquina.</span><span class="sxs-lookup"><span data-stu-id="24c34-151">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="24c34-152">Durante a instalação, o PKG solicitará credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="24c34-152">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="24c34-153">O usuário precisa inserir as credenciais de administrador, independentemente de o usuário ser ou não um administrador.</span><span class="sxs-lookup"><span data-stu-id="24c34-153">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="24c34-154">Se um usuário tiver atualmente uma instalação DMG do Teams e quiser substituí-lo pela instalação PKG, o usuário deverá:</span><span class="sxs-lookup"><span data-stu-id="24c34-154">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="24c34-155">Sair do aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="24c34-155">Exit the Teams app.</span></span>
2. <span data-ttu-id="24c34-156">Desinstalar o aplicativo do Teams.</span><span class="sxs-lookup"><span data-stu-id="24c34-156">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="24c34-157">Instalar o arquivo PKG.</span><span class="sxs-lookup"><span data-stu-id="24c34-157">Install the PKG file.</span></span>

<span data-ttu-id="24c34-158">Os administradores de TI podem usar a implantação gerenciada do Teams para distribuir os arquivos de instalação para todos os Macs de sua organização, como o Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="24c34-158">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="24c34-159">Se você tiver problemas ao instalar o PKG, avise-nos.</span><span class="sxs-lookup"><span data-stu-id="24c34-159">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="24c34-160">Na seção **Comentários**, no final deste artigo, clique em **Comentários sobre o produto**.</span><span class="sxs-lookup"><span data-stu-id="24c34-160">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="24c34-161">Linux</span><span class="sxs-lookup"><span data-stu-id="24c34-161">Linux</span></span>

<span data-ttu-id="24c34-162">Os usuários poderão instalar pacotes nativos do Linux nos formatos `.deb` e `.rpm`.</span><span class="sxs-lookup"><span data-stu-id="24c34-162">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span> <span data-ttu-id="24c34-163">A instalação do pacote DEB ou RPM instalará automaticamente o repositório de pacotes.</span><span class="sxs-lookup"><span data-stu-id="24c34-163">Installing the DEB or RPM package will automatically install the package repository.</span></span>

- <span data-ttu-id="24c34-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="24c34-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="24c34-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="24c34-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span>

<span data-ttu-id="24c34-166">A chave de assinatura para habilitar a atualização automática usando o gerenciador de pacotes do sistema é instalado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="24c34-166">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="24c34-167">No entanto, ele também pode ser encontrado em: <https://packages.microsoft.com/keys/microsoft.asc>.</span><span class="sxs-lookup"><span data-stu-id="24c34-167">However, it can also be found at: <https://packages.microsoft.com/keys/microsoft.asc>.</span></span> <span data-ttu-id="24c34-168">o Microsoft Teams é lançado mensalmente, e se o repositório for instalado corretamente, o gerenciador de pacotes do sistema deverá lidar com a atualização automática da mesma forma que outros pacotes no sistema.</span><span class="sxs-lookup"><span data-stu-id="24c34-168">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="24c34-169">Se você encontrar um bug, envie-o usando o `Report a Problem` no cliente.</span><span class="sxs-lookup"><span data-stu-id="24c34-169">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="24c34-170">Para problemas conhecidos, confira [Suporte do Teams na sua organização](/MicrosoftTeams/troubleshoot/teams-welcome).</span><span class="sxs-lookup"><span data-stu-id="24c34-170">For known issues, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
> <span data-ttu-id="24c34-171">Para o suporte do Teams para Linux, você pode usar o [canal de suporte do fórum do Linux nas perguntas e respostas Microsoft](/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="24c34-171">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](/answers/topics/teams.html).</span></span> <span data-ttu-id="24c34-172">Lembre-se de usar a marca `teams-linux` ao postar as perguntas.</span><span class="sxs-lookup"><span data-stu-id="24c34-172">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="24c34-173">Instalar o Teams usando o pacote DEB</span><span class="sxs-lookup"><span data-stu-id="24c34-173">Install Teams using DEB package</span></span>

1. <span data-ttu-id="24c34-174">Baixe o pacote de <https://aka.ms/getteams>.</span><span class="sxs-lookup"><span data-stu-id="24c34-174">Download the package from <https://aka.ms/getteams>.</span></span>
2. <span data-ttu-id="24c34-175">Instale usando uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="24c34-175">Install using one of the following:</span></span>
    - <span data-ttu-id="24c34-176">Abra a ferramenta de gerenciamento de pacotes relevante e siga o processo autodirigido de instalação de aplicativos do Linux.</span><span class="sxs-lookup"><span data-stu-id="24c34-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="24c34-177">Ou se você adora o Terminal, digite: `sudo dpkg -i **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="24c34-177">Or if you love Terminal, type: `sudo dpkg -i **teams download file**`</span></span>

<span data-ttu-id="24c34-178">Você pode lançar o Teams por meio de Atividades ou por meio do Terminal digitando `teams`.</span><span class="sxs-lookup"><span data-stu-id="24c34-178">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="24c34-179">Instalar o Teams usando o pacote RPM</span><span class="sxs-lookup"><span data-stu-id="24c34-179">Install Teams using RPM package</span></span>

1. <span data-ttu-id="24c34-180">Baixe o pacote de <https://aka.ms/getteams>.</span><span class="sxs-lookup"><span data-stu-id="24c34-180">Download the package from <https://aka.ms/getteams>.</span></span>
2. <span data-ttu-id="24c34-181">Instale usando uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="24c34-181">Install using one of the following:</span></span>
    - <span data-ttu-id="24c34-182">Abra a ferramenta de gerenciamento de pacotes relevante e siga o processo autodirigido de instalação de aplicativos do Linux.</span><span class="sxs-lookup"><span data-stu-id="24c34-182">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="24c34-183">Ou se você adora o Terminal, digite: `sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="24c34-183">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="24c34-184">Você pode lançar o Teams por meio de Atividades ou por meio do Terminal digitando `teams`.</span><span class="sxs-lookup"><span data-stu-id="24c34-184">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="24c34-185">Instalar manualmente da linha de comando</span><span class="sxs-lookup"><span data-stu-id="24c34-185">Install manually from the command line</span></span>

<span data-ttu-id="24c34-186">Instale manualmente nas distribuições do Debian e do Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="24c34-186">Install manually on Debian and Ubuntu distributions:</span></span>

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

<span data-ttu-id="24c34-187">Instale manualmente em distribuições baseadas em RHEL, Fedora e CentOS:</span><span class="sxs-lookup"><span data-stu-id="24c34-187">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="24c34-188">Como alternativa, para usar yum em vez de dnf:</span><span class="sxs-lookup"><span data-stu-id="24c34-188">Alternatively, to use yum instead of dnf:</span></span>

```bash
yum check-update
sudo yum install teams
```

<span data-ttu-id="24c34-189">Instale manualmente em distribuições baseadas em openSUSE:</span><span class="sxs-lookup"><span data-stu-id="24c34-189">Install manually on openSUSE based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="24c34-190">Clientes Web</span><span class="sxs-lookup"><span data-stu-id="24c34-190">Web client</span></span>

<span data-ttu-id="24c34-191">O cliente Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) é um cliente completo e funcional que pode ser usado em vários navegadores.</span><span class="sxs-lookup"><span data-stu-id="24c34-191">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="24c34-192">O cliente Web suporta Chamadas e Reuniões usando o webRTC, portanto, não há necessidade de usar um plugin ou download para executar o Teams em um navegador da web.</span><span class="sxs-lookup"><span data-stu-id="24c34-192">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="24c34-193">O navegador deve ser configurado para permitir cookies de terceiros.</span><span class="sxs-lookup"><span data-stu-id="24c34-193">The browser must be configured to allow third-party cookies.</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="24c34-194">O cliente Web executa a detecção da versão do navegador ao se conectar[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="24c34-194">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="24c34-195">Se uma versão do navegador não suportada for detectada, ela bloqueará o acesso à interface da Web e recomendará que o usuário faça o download do cliente de desktop ou do aplicativo para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="24c34-195">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="24c34-196">Clientes móveis</span><span class="sxs-lookup"><span data-stu-id="24c34-196">Mobile clients</span></span>

<span data-ttu-id="24c34-197">Os aplicativos móveis da Microsoft Teams estão disponíveis para Android e iOS e são voltados para usuários em trânsito que participam de conversas baseadas em bate-papo e permitem chamadas de áudio ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="24c34-197">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="24c34-198">Para aplicativos para dispositivos móveis, acesse as lojas relevantes, Google Play e a Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="24c34-198">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="24c34-199">O aplicativo Windows Phone foi retirado em 20 de julho de 2018 e pode não funcionar mais.</span><span class="sxs-lookup"><span data-stu-id="24c34-199">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span>

<span data-ttu-id="24c34-200">Na China, veja como [obter o Teams para Android](get-teams-android-in-china.md).</span><span class="sxs-lookup"><span data-stu-id="24c34-200">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span>

<span data-ttu-id="24c34-201">As plataformas móveis suportadas para os aplicativos móveis da Microsoft Teams são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="24c34-201">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

- <span data-ttu-id="24c34-202">**Android**: o suporte é limitado às últimas quatro versões principais do Android.</span><span class="sxs-lookup"><span data-stu-id="24c34-202">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="24c34-203">Quando uma nova versão principal do Android é lançada, a nova versão e as três versões anteriores são oficialmente suportadas.</span><span class="sxs-lookup"><span data-stu-id="24c34-203">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

- <span data-ttu-id="24c34-204">**iOS**: o suporte é limitado às duas versões principais mais recentes do iOS.</span><span class="sxs-lookup"><span data-stu-id="24c34-204">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="24c34-205">Quando uma nova versão principal do iOS é lançada, a nova versão do iOS e a versão anterior são oficialmente suportadas.</span><span class="sxs-lookup"><span data-stu-id="24c34-205">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="24c34-206">A versão móvel deve estar disponível ao público para que o Teams funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="24c34-206">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="24c34-207">Os aplicativos móveis são distribuídos e atualizados somente por meio da loja de aplicativos da respectiva plataforma móvel.</span><span class="sxs-lookup"><span data-stu-id="24c34-207">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="24c34-208">A distribuição dos aplicativos móveis via MDM ou carregamento lateral não são suportados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="24c34-208">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="24c34-209">Depois que o aplicativo móvel for instalado em uma plataforma móvel compatível, o próprio aplicativo móvel do Teams será suportado, desde que a versão esteja dentro de três meses a partir da versão atual.</span><span class="sxs-lookup"><span data-stu-id="24c34-209">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>

| | | |
|---|---|---|
|![Um ícone representando um ponto de decisão](media/Get_clients_for_Microsoft_Teams_image4.png)|<span data-ttu-id="24c34-211">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="24c34-211">Decision Point</span></span>|<span data-ttu-id="24c34-212">Existe alguma restrição que esteja impedindo os usuários de instalar o cliente Microsoft Teams adequado em seus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="24c34-212">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>|
|![Um ícone representando os próximos passos](media/Get_clients_for_Microsoft_Teams_image5.png)|<span data-ttu-id="24c34-214">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="24c34-214">Next Steps</span></span>|<span data-ttu-id="24c34-215">Se sua organização restringe a instalação de software, verifique se esse processo é compatível com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="24c34-215">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="24c34-216">Nota: Os direitos de administrador não são obrigatórios para a instalação do cliente PC, mas são obrigatórios para a instalação em Mac.</span><span class="sxs-lookup"><span data-stu-id="24c34-216">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>|
|

## <a name="client-update-management"></a><span data-ttu-id="24c34-217">Gerenciamento de atualização do cliente</span><span class="sxs-lookup"><span data-stu-id="24c34-217">Client update management</span></span>

<span data-ttu-id="24c34-218">No momento, os clientes são atualizados automaticamente pelo serviço do Microsoft Teams, sem a necessidade de intervenção de um administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="24c34-218">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="24c34-219">Se uma atualização estiver disponível, o cliente fará o download automaticamente e, quando o aplicativo ficar inativo por um período de tempo, o processo de atualização será iniciado.</span><span class="sxs-lookup"><span data-stu-id="24c34-219">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="24c34-220">Configurações do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="24c34-220">Client-side configurations</span></span>

<span data-ttu-id="24c34-221">No momento, não estão disponibilizadas opções para configurar o cliente através do administrador do locatário, do PowerShell, do Group Policy Objects, nem do registro.</span><span class="sxs-lookup"><span data-stu-id="24c34-221">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="24c34-222">Configurações de notificação</span><span class="sxs-lookup"><span data-stu-id="24c34-222">Notification settings</span></span>

<span data-ttu-id="24c34-223">No momento, não estão disponibilizadas opções para administradores de TI definirem as configurações de notificação do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="24c34-223">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="24c34-224">Todas as opções de notificação são definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="24c34-224">All notification options are set by the user.</span></span> <span data-ttu-id="24c34-225">A figura abaixo descreve as configurações padrão do cliente.</span><span class="sxs-lookup"><span data-stu-id="24c34-225">The figure below outlines the default client settings.</span></span>

![Captura de tela das configurações de notificação.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="24c34-227">Script do PowerShell de exemplo - regra de firewall de entrada</span><span class="sxs-lookup"><span data-stu-id="24c34-227">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="24c34-228">Este script de exemplo, que precisa ser executado em computadores clientes no contexto de uma conta de administrador elevada, criará uma nova regra de firewall de entrada para cada pasta de usuário encontrada em c:\usuários.</span><span class="sxs-lookup"><span data-stu-id="24c34-228">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="24c34-229">Quando o Teams encontrar essa regra, impedirá que o aplicativo do Teams solicite que os usuários criem regras de firewall quando os usuários fizerem a primeira chamada no Teams.</span><span class="sxs-lookup"><span data-stu-id="24c34-229">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span>

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions.
   The script will create a new inbound firewall rule for each user folder found in c:\users.
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
