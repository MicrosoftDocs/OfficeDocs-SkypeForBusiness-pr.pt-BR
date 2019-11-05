---
title: Obter clientes do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar os vários clientes disponíveis para o Microsoft Teams, que incluem web, área de trabalho (Windows e Mac) e dispositivos móveis (Android e iOS).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fcc0ef8a4fd8dab857fcf4c75af61c2c258b364
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37971657"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="d301d-103">Obter clientes do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d301d-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="d301d-104">O Microsoft Teams tem clientes disponíveis para área de trabalho (Windows, Mac e Linux), Web e dispositivos móveis (Android e iOS).</span><span class="sxs-lookup"><span data-stu-id="d301d-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="d301d-105">Todos esses clientes precisam de uma conexão à internet ativa e não são suportados em modo offline.</span><span class="sxs-lookup"><span data-stu-id="d301d-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="d301d-106">A partir de 29 de novembro de 2018, você não poderá mais usar o aplicativo Microsoft Teams para Windows 10 S (Visualização), disponível na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d301d-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="d301d-107">Em vez disso, agora você pode baixar e instalar o cliente da área de trabalho do teams em dispositivos que executam o modo Windows 10 S.</span><span class="sxs-lookup"><span data-stu-id="d301d-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="d301d-108">Para baixar o cliente de desktop, vá [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)para.</span><span class="sxs-lookup"><span data-stu-id="d301d-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="d301d-109">Os builds MSI do cliente de desktop Teams ainda não estão disponíveis para dispositivos que executam o modo Windows 10 S.</span><span class="sxs-lookup"><span data-stu-id="d301d-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="d301d-110">Para obter mais informações sobre o modo Windows 10 S, consulte [apresentando o Windows 10 no modo s](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="d301d-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="d301d-111">Cliente de desktop</span><span class="sxs-lookup"><span data-stu-id="d301d-111">Desktop client</span></span>

> [!Tip]
> <span data-ttu-id="d301d-112">Assista à sessão a seguir para conhecer os benefícios do Windows Desktop Client e como planejar e executar sua implantação: [Cliente de Desktop do Microsoft Teams](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="d301d-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="d301d-113">O cliente de desktop do Microsoft Teams é um aplicativo autônomo e também está [disponível no Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="d301d-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="d301d-114">O Microsoft Teams está disponível para Windows (7 +), versões de 32 bits e 64 bits, macOS (10.10s +) e Linux (pacote `.deb`Debian, Gerenciador `.rpm`de pacotes Red Hat).</span><span class="sxs-lookup"><span data-stu-id="d301d-114">Teams is available for Windows (7+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (Debian package `.deb`, Red Hat Package Manager `.rpm`).</span></span> <span data-ttu-id="d301d-115">No Windows, o Teams exige o .NET Framework 4.5 ou posterior; o instalador do Teams oferecerá instalá-lo para você se você não o tiver.</span><span class="sxs-lookup"><span data-stu-id="d301d-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="d301d-116">No Linux, os gerentes de pacotes, como apt e yum, tentam instalar quaisquer requisitos para você.</span><span class="sxs-lookup"><span data-stu-id="d301d-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="d301d-117">No entanto, se não fizer isso, você precisará instalar todos os requisitos relatados antes de instalar o Microsoft Teams no Linux.</span><span class="sxs-lookup"><span data-stu-id="d301d-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="d301d-118">Os clientes de área de trabalho fornecem suporte de comunicação em tempo real (áudio, vídeo e compartilhamento de conteúdo) para reuniões de equipe, chamadas em grupo e chamadas individuais privadas.</span><span class="sxs-lookup"><span data-stu-id="d301d-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="d301d-119">Os clientes de desktop podem ser baixados e instalados diretamente pelos usuários finais[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) se tiverem as permissões locais apropriadas (direitos de administrador não são necessários para instalar o cliente Teams em um PC, mas são necessários em um Mac).</span><span class="sxs-lookup"><span data-stu-id="d301d-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="d301d-120">Os administradores de ti podem escolher o método preferencial para distribuir os arquivos de instalação para os computadores de sua organização.</span><span class="sxs-lookup"><span data-stu-id="d301d-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="d301d-121">Alguns exemplos incluem o System Center Configuration Manager (Windows) ou o JAMF pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="d301d-121">Some examples include System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="d301d-122">Para obter o pacote MSI para distribuições do Windows, consulte [Instalar o Microsoft Teams usando MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="d301d-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="d301d-123">A distribuição do cliente por esses mecanismos é apenas para a instalação inicial dos clientes Microsoft Teams, e não para atualizações futuras.</span><span class="sxs-lookup"><span data-stu-id="d301d-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="d301d-124">Windows</span><span class="sxs-lookup"><span data-stu-id="d301d-124">Windows</span></span>

<span data-ttu-id="d301d-125">A instalação do Microsoft Teams para Windows oferece instaladores para download nas arquiteturas de 32 bits e 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d301d-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="d301d-126">A arquitetura (32 bits vs. 64 bits) do Microsoft Teams é independente da arquitetura do Windows e do Office instalados.</span><span class="sxs-lookup"><span data-stu-id="d301d-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="d301d-127">O cliente Windows é implantado na pasta AppData localizada no perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="d301d-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="d301d-128">A implantação no perfil local do usuário permite que o cliente seja instalado sem exigir direitos elevados.</span><span class="sxs-lookup"><span data-stu-id="d301d-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="d301d-129">O cliente Windows aproveita os seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="d301d-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="d301d-130">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="d301d-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="d301d-131">% LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="d301d-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="d301d-132">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="d301d-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="d301d-133">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="d301d-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="d301d-134">Quando os usuários iniciam uma chamada usando o cliente Microsoft Teams pela primeira vez, eles podem notar um aviso com as configurações de firewall do Windows, que solicita que os usuários permitam a comunicação.</span><span class="sxs-lookup"><span data-stu-id="d301d-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="d301d-135">Os usuários podem ser instruídos a ignorar esta mensagem porque a chamada funcionará mesmo quando o aviso for recusado.</span><span class="sxs-lookup"><span data-stu-id="d301d-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Captura de tela de um diálogo do Alerta de Segurança do Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="d301d-137">A configuração do Firewall do Windows será alterada mesmo quando o aviso for descartado ao selecionar “Cancelar”.</span><span class="sxs-lookup"><span data-stu-id="d301d-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="d301d-138">Serão criadas duas regras de entrada para teams.exe com a ação Block para protocolos TCP e UDP.</span><span class="sxs-lookup"><span data-stu-id="d301d-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="d301d-139">Mac</span><span class="sxs-lookup"><span data-stu-id="d301d-139">Mac</span></span>

<span data-ttu-id="d301d-140">Usuários de Mac podem instalar o Teams usando um arquivo de instalação PKG para computadores macOS.</span><span class="sxs-lookup"><span data-stu-id="d301d-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="d301d-141">É necessário acesso administrativo para instalar o cliente Mac.</span><span class="sxs-lookup"><span data-stu-id="d301d-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="d301d-142">O cliente macOS é instalado na pasta /Applications.</span><span class="sxs-lookup"><span data-stu-id="d301d-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="d301d-143">Instalar o Teams usando o arquivo PKG</span><span class="sxs-lookup"><span data-stu-id="d301d-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="d301d-144">Na [página de download do Teams](https://teams.microsoft.com/downloads), em **Mac**, clique em **Download**.</span><span class="sxs-lookup"><span data-stu-id="d301d-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="d301d-145">Clique duas vezes no arquivo PKG.</span><span class="sxs-lookup"><span data-stu-id="d301d-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="d301d-146">Siga o assistente de instalação para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="d301d-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="d301d-147">O Teams será instalado na pasta /Applications.</span><span class="sxs-lookup"><span data-stu-id="d301d-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="d301d-148">É uma instalação em toda a máquina.</span><span class="sxs-lookup"><span data-stu-id="d301d-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="d301d-149">Durante a instalação, o PKG solicitará credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="d301d-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="d301d-150">O usuário precisa inserir as credenciais de administrador, independentemente de o usuário ser ou não um administrador.</span><span class="sxs-lookup"><span data-stu-id="d301d-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="d301d-151">Se um usuário tiver atualmente uma instalação DMG do Teams e quiser substituí-lo pela instalação PKG, o usuário deverá:</span><span class="sxs-lookup"><span data-stu-id="d301d-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="d301d-152">Sair do aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="d301d-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="d301d-153">Desinstalar o aplicativo do Teams.</span><span class="sxs-lookup"><span data-stu-id="d301d-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="d301d-154">Instalar o arquivo PKG.</span><span class="sxs-lookup"><span data-stu-id="d301d-154">Install the PKG file.</span></span>

<span data-ttu-id="d301d-155">Os administradores de TI podem usar a implantação gerenciada do Teams para distribuir os arquivos de instalação para todos os Macs de sua organização, como o Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="d301d-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="d301d-156">Se você tiver problemas ao instalar o PKG, avise-nos.</span><span class="sxs-lookup"><span data-stu-id="d301d-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="d301d-157">Na seção **Comentários**, no final deste artigo, clique em **Comentários sobre o produto**.</span><span class="sxs-lookup"><span data-stu-id="d301d-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="d301d-158">Linux</span><span class="sxs-lookup"><span data-stu-id="d301d-158">Linux</span></span>

<span data-ttu-id="d301d-159">Os usuários do Linux podem instalar o Microsoft `.deb` Teams usando um pacote Debian ou `.rpm`um pacote Red Hat.</span><span class="sxs-lookup"><span data-stu-id="d301d-159">Linux users can install Teams using a Debian `.deb` package or as a Red Hat package `.rpm`.</span></span> 

> [!NOTE] 
> <span data-ttu-id="d301d-160">O Microsoft Teams para cliente Linux está disponível para visualização limitada.</span><span class="sxs-lookup"><span data-stu-id="d301d-160">The Teams on Linux client is available in limited preview.</span></span> <span data-ttu-id="d301d-161">Enviar bugs usando `Report a Problem` de dentro do cliente.</span><span class="sxs-lookup"><span data-stu-id="d301d-161">Submit bugs using `Report a Problem` from within the client.</span></span> <span data-ttu-id="d301d-162">Para saber mais sobre problemas conhecidos, veja [problemas conhecidos](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d301d-162">For known issues, see [Known Issues](Known-issues.md).</span></span>

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="d301d-163">Instalar o Microsoft Teams usando o pacote DEB</span><span class="sxs-lookup"><span data-stu-id="d301d-163">Install Teams using DEB package</span></span>

1. <span data-ttu-id="d301d-164">Baixar o pacote de https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="d301d-164">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="d301d-165">(O cliente Linux está em visualização limitada e será iniciado em breve.</span><span class="sxs-lookup"><span data-stu-id="d301d-165">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="d301d-166">Se você não vir o cliente Linux na página de downloads, ele ainda não foi iniciado.)</span><span class="sxs-lookup"><span data-stu-id="d301d-166">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="d301d-167">Instale usando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d301d-167">Install using one of the following:</span></span>  
    - <span data-ttu-id="d301d-168">Abra o pacote usando a ferramenta de software Ubuntu e percorra o processo de instalação do aplicativo Linux autoorientado.</span><span class="sxs-lookup"><span data-stu-id="d301d-168">Open the package using Ubuntu Software Tool and go through self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="d301d-169">Ou, se você ama terminal, digite:`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="d301d-169">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="d301d-170">Você pode iniciar o Microsoft Teams por meio de atividades `Teams`ou via terminal digitando.</span><span class="sxs-lookup"><span data-stu-id="d301d-170">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="d301d-171">Instalar o Microsoft Teams usando o pacote RPM</span><span class="sxs-lookup"><span data-stu-id="d301d-171">Install Teams using RPM package</span></span>

1. <span data-ttu-id="d301d-172">Baixar o pacote de https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="d301d-172">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="d301d-173">(O cliente Linux está em visualização limitada e será iniciado em breve.</span><span class="sxs-lookup"><span data-stu-id="d301d-173">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="d301d-174">Se você não vir o cliente Linux na página de downloads, ele ainda não foi iniciado.)</span><span class="sxs-lookup"><span data-stu-id="d301d-174">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="d301d-175">Instale usando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d301d-175">Install using one of the following:</span></span>
    - <span data-ttu-id="d301d-176">Abra o pacote usando a ferramenta de gerenciamento de pacotes do Red Hat e percorra o processo de instalação do aplicativo Linux autoorientado.</span><span class="sxs-lookup"><span data-stu-id="d301d-176">Open the package using Red Hat Package Management Tool and go through self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="d301d-177">Ou, se você ama terminal, digite:`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="d301d-177">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="d301d-178">Você pode iniciar o Microsoft Teams por meio de atividades `Teams`ou via terminal digitando.</span><span class="sxs-lookup"><span data-stu-id="d301d-178">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

## <a name="web-client"></a><span data-ttu-id="d301d-179">Clientes Web</span><span class="sxs-lookup"><span data-stu-id="d301d-179">Web client</span></span> 

<span data-ttu-id="d301d-180">O cliente Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) é um cliente completo e funcional que pode ser usado em vários navegadores.</span><span class="sxs-lookup"><span data-stu-id="d301d-180">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="d301d-181">O cliente Web suporta Chamadas e Reuniões usando o webRTC, portanto, não há necessidade de usar um plugin ou download para executar o Teams em um navegador da web.</span><span class="sxs-lookup"><span data-stu-id="d301d-181">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="d301d-182">O navegador deve ser configurado para permitir cookies de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d301d-182">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="d301d-183">O cliente Web executa a detecção da versão do navegador ao se conectar[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="d301d-183">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="d301d-184">Se uma versão do navegador não suportada for detectada, ela bloqueará o acesso à interface da Web e recomendará que o usuário faça o download do cliente de desktop ou do aplicativo para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="d301d-184">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="d301d-185">Clientes móveis</span><span class="sxs-lookup"><span data-stu-id="d301d-185">Mobile clients</span></span>

<span data-ttu-id="d301d-186">Os aplicativos móveis da Microsoft Teams estão disponíveis para Android e iOS e são voltados para usuários em trânsito que participam de conversas baseadas em bate-papo e permitem chamadas de áudio ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d301d-186">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="d301d-187">Para aplicativos para dispositivos móveis, acesse as lojas relevantes, Google Play e a Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="d301d-187">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="d301d-188">O aplicativo Windows Phone foi retirado em 20 de julho de 2018 e pode não funcionar mais.</span><span class="sxs-lookup"><span data-stu-id="d301d-188">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="d301d-189">As plataformas móveis suportadas para os aplicativos móveis da Microsoft Teams são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="d301d-189">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="d301d-190">**Android**: 4.4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d301d-190">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="d301d-191">**iOS**: 10.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d301d-191">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="d301d-192">A versão móvel deve estar disponível ao público para que o Teams funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="d301d-192">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="d301d-193">Os aplicativos móveis são distribuídos e atualizados por meio da respectiva loja de aplicativos da plataforma móvel somente.</span><span class="sxs-lookup"><span data-stu-id="d301d-193">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="d301d-194">Não há suporte para a distribuição de aplicativos móveis via MDM ou carregamento no lado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d301d-194">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="d301d-195">Quando o aplicativo móvel tiver sido instalado em uma plataforma móvel compatível, o próprio aplicativo móvel do teams será compatível, contanto que a versão seja dentro de três meses do lançamento atual.</span><span class="sxs-lookup"><span data-stu-id="d301d-195">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Um ícone que representa um ponto de decisão](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="d301d-197">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="d301d-197">Decision Point</span></span>         |<span data-ttu-id="d301d-198">Existe alguma restrição que esteja impedindo os usuários de instalar o cliente Microsoft Teams adequado em seus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="d301d-198">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Um ícone representando os próximos passos](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="d301d-200">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="d301d-200">Next Steps</span></span>         |<span data-ttu-id="d301d-201">Se sua organização restringe a instalação de software, verifique se esse processo é compatível com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d301d-201">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="d301d-202">Nota: Os direitos de administrador não são obrigatórios para a instalação do cliente PC, mas são obrigatórios para a instalação em Mac.</span><span class="sxs-lookup"><span data-stu-id="d301d-202">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="d301d-203">Gerenciamento de atualização do cliente</span><span class="sxs-lookup"><span data-stu-id="d301d-203">Client update management</span></span>

<span data-ttu-id="d301d-204">No momento, os clientes são atualizados automaticamente pelo serviço do Microsoft Teams, sem a necessidade de intervenção de um administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="d301d-204">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="d301d-205">Se houver uma atualização disponível, o cliente baixará automaticamente a atualização e, quando o aplicativo ficar ocioso por um período de tempo, o processo de atualização será iniciado.</span><span class="sxs-lookup"><span data-stu-id="d301d-205">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="d301d-206">Configurações do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="d301d-206">Client-side configurations</span></span>

<span data-ttu-id="d301d-207">No momento, não estão disponibilizadas opções para configurar o cliente através do administrador do locatário, do PowerShell, do Group Policy Objects, nem do registro.</span><span class="sxs-lookup"><span data-stu-id="d301d-207">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="d301d-208">Configurações de notificação</span><span class="sxs-lookup"><span data-stu-id="d301d-208">Notification settings</span></span>

<span data-ttu-id="d301d-209">No momento, não estão disponibilizadas opções para administradores de TI definirem as configurações de notificação do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="d301d-209">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="d301d-210">Todas as opções de notificação são definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="d301d-210">All notification options are set by the user.</span></span> <span data-ttu-id="d301d-211">A figura abaixo descreve as configurações padrão do cliente.</span><span class="sxs-lookup"><span data-stu-id="d301d-211">The figure below outlines the default client settings.</span></span>

![Captura de tela das configurações de notificação.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="d301d-213">Exemplo de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d301d-213">Sample PowerShell Script</span></span>

<span data-ttu-id="d301d-214">Este script de exemplo, que precisa ser executado em computadores clientes no contexto de uma conta de administrador elevada, criará uma nova regra de firewall de entrada para cada pasta de usuário encontrada em c:\usuários.</span><span class="sxs-lookup"><span data-stu-id="d301d-214">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="d301d-215">Quando o Teams encontrar essa regra, impedirá que o aplicativo do Teams solicite que os usuários criem regras de firewall quando os usuários fizerem a primeira chamada no Teams.</span><span class="sxs-lookup"><span data-stu-id="d301d-215">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
