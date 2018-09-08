---
title: Obter clientes para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar as diversos clientes disponíveis para o Microsoft Teams, incluindo web, desktop (Windows e Mac) e móvel (Android, iOS e Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bbadb9324942cdb354570673a0fd923c9e04bdbd
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891325"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="7cadb-103">Obter clientes para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7cadb-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="7cadb-104">Microsoft Teams possui clientes móveis e disponíveis para a área de trabalho web (Windows e Mac), (Android, iOS e Windows Phone).</span><span class="sxs-lookup"><span data-stu-id="7cadb-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android,  iOS, and Windows Phone).</span></span> <span data-ttu-id="7cadb-105">Todos esses clientes precisam de uma conexão à internet ativa e não são suportados em modo offline.</span><span class="sxs-lookup"><span data-stu-id="7cadb-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="desktop-client"></a><span data-ttu-id="7cadb-106">Cliente de desktop</span><span class="sxs-lookup"><span data-stu-id="7cadb-106">Desktop client</span></span>
--------------

<span data-ttu-id="7cadb-107">O cliente de desktop do Microsoft Teams é um aplicativo autônomo e atualmente não faz parte do Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="7cadb-107">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="7cadb-108">As equipes está disponível para o Windows (7 +), versões de 32 bits e 64 bits e macOS (10.10 +).</span><span class="sxs-lookup"><span data-stu-id="7cadb-108">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="7cadb-109">No Windows, equipes requer o .NET framework 4.5 ou posterior; o instalador de equipes se oferecerá para instalá-lo se você não tiver a ele.</span><span class="sxs-lookup"><span data-stu-id="7cadb-109">On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="7cadb-110">Os clientes de área de trabalho oferecem suporte a comunicação em tempo real (áudio, vídeo e conteúdo compartilhamento) para reuniões de equipe, chamadas individuais chamando e particulares do grupo.</span><span class="sxs-lookup"><span data-stu-id="7cadb-110">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="7cadb-111">Clientes de área de trabalho podem ser baixados e instalados pelos usuários finais diretamente do [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) se eles têm as permissões apropriadas de locais (direitos de administrador não são necessários para instalar o cliente de equipes em um PC, mas são necessários em um Mac).</span><span class="sxs-lookup"><span data-stu-id="7cadb-111">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="7cadb-112">Administradores de TI podem escolher seu método preferencial para distribuir os arquivos de instalação para computadores em sua organização, como o System Center Configuration Manager (Windows) ou Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="7cadb-112">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="7cadb-113">Para obter o pacote MSI para distribuição do Windows, consulte [instalar equipes da Microsoft usando o MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="7cadb-113">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7cadb-114">A distribuição do cliente por esses mecanismos é apenas para a instalação inicial dos clientes Microsoft Teams, e não para atualizações futuras.</span><span class="sxs-lookup"><span data-stu-id="7cadb-114">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="7cadb-115">Windows</span><span class="sxs-lookup"><span data-stu-id="7cadb-115">Windows</span></span>

<span data-ttu-id="7cadb-116">A instalação do Microsoft Teams para Windows oferece instaladores para download nas arquiteturas de 32 bits e 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7cadb-116">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="7cadb-117">A arquitetura (32 bits versus 64 bits) do Microsoft Teams é independente da arquitetura do Windows e do Office que está instalado.</span><span class="sxs-lookup"><span data-stu-id="7cadb-117">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="7cadb-118">O cliente Windows é implantado na pasta AppData localizada no perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="7cadb-118">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="7cadb-119">A implantação no perfil local do usuário permite que o cliente seja instalado sem exigir direitos elevados.</span><span class="sxs-lookup"><span data-stu-id="7cadb-119">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="7cadb-120">O cliente Windows é instalado nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="7cadb-120">The Windows client is installed in the following locations:</span></span>

- <span data-ttu-id="7cadb-121">%appdata%\\local\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="7cadb-121">%appdata%\\local\\Microsoft\\Teams</span></span>

- <span data-ttu-id="7cadb-122">%appdata%\\roaming\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="7cadb-122">%appdata%\\roaming\\Microsoft\\Teams</span></span>

<span data-ttu-id="7cadb-123">Quando os usuários iniciam uma chamada usando o cliente Microsoft Teams pela primeira vez, eles podem notar um aviso com as configurações de firewall do Windows, que solicita que os usuários permitam a comunicação.</span><span class="sxs-lookup"><span data-stu-id="7cadb-123">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="7cadb-124">Os usuários podem ser instruídos para ignorar essa mensagem porque a chamada funcione, mesmo quando o aviso é descartado.</span><span class="sxs-lookup"><span data-stu-id="7cadb-124">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Captura de tela de um diálogo do Alerta de Segurança do Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="7cadb-126">A configuração do Firewall do Windows será alterada mesmo quando o aviso for descartado ao selecionar “Cancelar”.</span><span class="sxs-lookup"><span data-stu-id="7cadb-126">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="7cadb-127">Serão criadas duas regras de entrada para teams.exe com a ação Block para protocolos TCP e UDP.</span><span class="sxs-lookup"><span data-stu-id="7cadb-127">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="7cadb-128">Mac</span><span class="sxs-lookup"><span data-stu-id="7cadb-128">Mac</span></span>

<span data-ttu-id="7cadb-129">Usuários de Mac podem instalar equipes usando um arquivo de instalação do pacote para computadores macOS.</span><span class="sxs-lookup"><span data-stu-id="7cadb-129">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="7cadb-130">É obrigatório acesso administrativo para instalar o cliente Mac.</span><span class="sxs-lookup"><span data-stu-id="7cadb-130">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="7cadb-131">O cliente macOS é instalado na pasta/aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7cadb-131">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="7cadb-132">Instalar as equipes usando o arquivo de pacote</span><span class="sxs-lookup"><span data-stu-id="7cadb-132">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="7cadb-133">Na [página de download de equipes](https://teams.microsoft.com/downloads), **Mac**, clique em **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="7cadb-133">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="7cadb-134">Clique duas vezes o arquivo de pacote.</span><span class="sxs-lookup"><span data-stu-id="7cadb-134">Double click the PKG file.</span></span>
3. <span data-ttu-id="7cadb-135">Siga o Assistente de instalação para concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="7cadb-135">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="7cadb-136">Pasta/aplicativos equipes serão instaladas.</span><span class="sxs-lookup"><span data-stu-id="7cadb-136">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="7cadb-137">É uma instalação de toda a máquina.</span><span class="sxs-lookup"><span data-stu-id="7cadb-137">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="7cadb-138">Durante a instalação, o pacote vai solicitar credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="7cadb-138">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="7cadb-139">O usuário precisa digitar as credenciais de administrador, independentemente de estarem ou não o usuário é um administrador.</span><span class="sxs-lookup"><span data-stu-id="7cadb-139">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="7cadb-140">Se um usuário atualmente tem uma instalação DMG das equipes e quiser substituí-la com a instalação do pacote, o usuário deve:</span><span class="sxs-lookup"><span data-stu-id="7cadb-140">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="7cadb-141">Saia do aplicativo de equipes.</span><span class="sxs-lookup"><span data-stu-id="7cadb-141">Exit the Teams app.</span></span>
2. <span data-ttu-id="7cadb-142">Desinstale o aplicativo de equipes.</span><span class="sxs-lookup"><span data-stu-id="7cadb-142">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="7cadb-143">Instale o arquivo de pacote.</span><span class="sxs-lookup"><span data-stu-id="7cadb-143">Install the PKG file.</span></span>

<span data-ttu-id="7cadb-144">Administradores de TI podem usar implantação gerenciada de equipes para distribuir os arquivos de instalação para todos os Macs na sua organização, como Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="7cadb-144">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="7cadb-145">Se você perceber problemas ao instalar o pacote, fale conosco.</span><span class="sxs-lookup"><span data-stu-id="7cadb-145">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="7cadb-146">Na seção **comentários** no final deste artigo, clique em **comentários sobre o produto**.</span><span class="sxs-lookup"><span data-stu-id="7cadb-146">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="7cadb-147">Cliente web</span><span class="sxs-lookup"><span data-stu-id="7cadb-147">Web client</span></span> 
----------

<span data-ttu-id="7cadb-148">O cliente da web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) é um cliente de funcional completo que pode ser usado em uma variedade de navegadores.</span><span class="sxs-lookup"><span data-stu-id="7cadb-148">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="7cadb-149">O cliente web oferece suporte a reuniões e chamadas usando webRTC, portanto, há não plug-in ou download necessário para executar as equipes em um navegador da web.</span><span class="sxs-lookup"><span data-stu-id="7cadb-149">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="7cadb-150">O navegador deve ser configurado para permitir que os cookies de terceiros.</span><span class="sxs-lookup"><span data-stu-id="7cadb-150">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="7cadb-151">Cliente web executa a detecção de versão do navegador após a conexão com [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="7cadb-151">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="7cadb-152">Se for detectada uma versão sem suporte do navegador, ela será bloqueie o acesso à interface da web e recomendável que o usuário baixe o cliente de área de trabalho ou aplicativos móveis.</span><span class="sxs-lookup"><span data-stu-id="7cadb-152">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="7cadb-153">Clientes móveis</span><span class="sxs-lookup"><span data-stu-id="7cadb-153">Mobile clients</span></span>
--------------

<span data-ttu-id="7cadb-154">Os aplicativos móveis do Microsoft Teams estão disponíveis para Android, iOS e Windows Phone, estão voltados para usuários participando de conversas baseadas em bate-papo em qualquer lugar, e permitem chamadas de áudio ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="7cadb-154">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="7cadb-155">Para aplicativos móveis, acesse a respectiva loja de aplicativos Google Play, Apple App Store ou Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7cadb-155">For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span>

<span data-ttu-id="7cadb-156">As plataformas móveis suportadas para os aplicativos móveis da Microsoft Teams são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="7cadb-156">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="7cadb-157">**Android**: 4.4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="7cadb-157">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="7cadb-158">**iOS**: 10.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="7cadb-158">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="7cadb-159">A versão móvel deve estar disponível para o público na ordem para equipes trabalhem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="7cadb-159">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="7cadb-160">Os aplicativos móveis são distribuídos e atualizados apenas pela respectiva loja de aplicativos da plataforma móvel e não estão disponíveis para ser distribuídos por meio de soluções MDM (gerenciamento de dispositivos móveis) ou carregamento lateral.</span><span class="sxs-lookup"><span data-stu-id="7cadb-160">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="7cadb-162">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="7cadb-162">Decision Point</span></span>         |<span data-ttu-id="7cadb-163">Existe alguma restrição que esteja impedindo os usuários de instalar o cliente Microsoft Teams adequado em seus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="7cadb-163">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Ícone de próximos passos.](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="7cadb-165">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="7cadb-165">Next Steps</span></span>         |<span data-ttu-id="7cadb-166">Se sua organização restringe a instalação de software, verifique se esse processo é compatível com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7cadb-166">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="7cadb-167">Nota: Os direitos de administrador não são obrigatórios para a instalação do cliente PC, mas são obrigatórios para a instalação em Mac.</span><span class="sxs-lookup"><span data-stu-id="7cadb-167">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="7cadb-168"><span id="_Hlk477176062" class="anchor"></span>  Ponto de decisão  Existe alguma restrição que esteja impedindo os usuários de instalar o cliente Microsoft Teams adequado em seus dispositivos?</span><span class="sxs-lookup"><span data-stu-id="7cadb-168"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="7cadb-169">Gerenciamento de atualização do cliente</span><span class="sxs-lookup"><span data-stu-id="7cadb-169">Client update management</span></span>
------------------------

<span data-ttu-id="7cadb-170">No momento, os clientes são atualizados automaticamente pelo serviço do Microsoft Teams, sem a necessidade de intervenção de um administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="7cadb-170">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="7cadb-171">Se uma atualização estiver disponível, o cliente baixará automaticamente a atualização e, quando o aplicativo estiver ocioso por um período de tempo, o processo de atualização será iniciado.</span><span class="sxs-lookup"><span data-stu-id="7cadb-171">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="7cadb-172">Configurações do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="7cadb-172">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="7cadb-173">No momento, não estão disponibilizadas opções para configurar o cliente através do administrador do locatário, do PowerShell, do Group Policy Objects, nem do registro.</span><span class="sxs-lookup"><span data-stu-id="7cadb-173">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="7cadb-174">Configurações de notificação</span><span class="sxs-lookup"><span data-stu-id="7cadb-174">Notification settings</span></span>
----------------------------

<span data-ttu-id="7cadb-175">No momento, não estão disponibilizadas opções para administradores de TI definirem as configurações de notificação do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="7cadb-175">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="7cadb-176">Todas as opções de notificação são definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7cadb-176">All notification options are set by the user.</span></span> <span data-ttu-id="7cadb-177">A figura abaixo descreve as configurações padrão do cliente.</span><span class="sxs-lookup"><span data-stu-id="7cadb-177">The figure below outlines the default client settings.</span></span>

![Captura de tela das configurações de notificação.](media/Get_clients_for_Microsoft_Teams_image6.png)
