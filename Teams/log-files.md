---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre logs de depuração, mídia e área de trabalho produzidos pelo Microsoft Teams, onde eles podem ser encontrados e como eles podem ajudar no monitoramento e solução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689689"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="6bf88-103">Usar arquivos de log para monitorar e solucionar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6bf88-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="6bf88-104">Há três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para ajudar no monitoramento e solução de problemas Teams:</span><span class="sxs-lookup"><span data-stu-id="6bf88-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="6bf88-105">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="6bf88-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="6bf88-106">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="6bf88-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="6bf88-107">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="6bf88-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="6bf88-108">Este artigo descreve esses logs e como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="6bf88-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="6bf88-109">Para obter informações sobre como solucionar problemas específicos, consulte: [Teams Solução de Problemas](/MicrosoftTeams/troubleshoot/teams).</span><span class="sxs-lookup"><span data-stu-id="6bf88-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="6bf88-110">Para obter informações sobre como contatar o suporte, consulte [Obter suporte](/microsoft-365/business-video/get-help-support).</span><span class="sxs-lookup"><span data-stu-id="6bf88-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="6bf88-111">Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="6bf88-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="6bf88-112">Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="6bf88-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="6bf88-113">**Os** logs **de** mídia ou área de trabalho só serão necessários se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bf88-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="6bf88-114">Neste artigo, o termo **Logs de depuração** se refere aos logs usados para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="6bf88-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="6bf88-115">No entanto, os arquivos gerados para esses logs conterão o termo **logs de diagnóstico** em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="6bf88-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="6bf88-116">Coletar e habilitar o log</span><span class="sxs-lookup"><span data-stu-id="6bf88-116">Collect and enable logging</span></span>

<span data-ttu-id="6bf88-117">É importante coletar logs assim que ocorrer um problema.</span><span class="sxs-lookup"><span data-stu-id="6bf88-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="6bf88-118">Os logs podem ser coletados com apenas alguns cliques.</span><span class="sxs-lookup"><span data-stu-id="6bf88-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="6bf88-119">Windows: clique com o botão direito do mouse no ícone Teams na bandeja do sistema e escolha **Coletar arquivos de suporte**.</span><span class="sxs-lookup"><span data-stu-id="6bf88-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="6bf88-120">Mac: selecione o menu Ajuda e escolha **Coletar arquivos de suporte**.</span><span class="sxs-lookup"><span data-stu-id="6bf88-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="6bf88-121">Os logs de depuração, área de trabalho e mídia serão coletados em uma pasta com o nome MSTeams Diagnostics Log <local data and time> .</span><span class="sxs-lookup"><span data-stu-id="6bf88-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="6bf88-122">Essa pasta pode ser compactada e compartilhada quando você abre uma solicitação de suporte com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bf88-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="6bf88-123">A pasta conterá pastas para Área de Trabalho, Reunião (Mídia) e Depuração (Web).</span><span class="sxs-lookup"><span data-stu-id="6bf88-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="6bf88-124">Você pode coletar os arquivos usando os seguintes atalhos de teclado:</span><span class="sxs-lookup"><span data-stu-id="6bf88-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="6bf88-125">Windows: Crtl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="6bf88-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="6bf88-126">Mac: Opção + Comando + Turno + 1</span><span class="sxs-lookup"><span data-stu-id="6bf88-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="6bf88-127">O registro de mídia está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6bf88-127">Media logging is turned off by default.</span></span> <span data-ttu-id="6bf88-128">Para habilitar o log de mídia, os usuários devem ativar a opção no Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="6bf88-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="6bf88-129">Vá para **Configurações** Geral e selecione Habilitar log para diagnóstico de reunião (requer a  >   **reinicialização Teams)**.</span><span class="sxs-lookup"><span data-stu-id="6bf88-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="6bf88-130">O Teams cliente deve ser reiniciado para iniciar o registro em log.</span><span class="sxs-lookup"><span data-stu-id="6bf88-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="6bf88-131">Se o log de mídia estiver habilitado, haverá arquivos adicionais incluídos na pasta Reunião que são necessários para investigar problemas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="6bf88-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="6bf88-132">Se o log de mídia não estiver habilitado, haverá um número limitado de logs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6bf88-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="6bf88-133">A tabela a seguir descreve os vários clientes e seus logs associados.</span><span class="sxs-lookup"><span data-stu-id="6bf88-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="6bf88-134">Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="6bf88-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="6bf88-135">Cliente</span><span class="sxs-lookup"><span data-stu-id="6bf88-135">Client</span></span> |<span data-ttu-id="6bf88-136">Depuração</span><span class="sxs-lookup"><span data-stu-id="6bf88-136">Debug</span></span>|<span data-ttu-id="6bf88-137">Desktop</span><span class="sxs-lookup"><span data-stu-id="6bf88-137">Desktop</span></span>|<span data-ttu-id="6bf88-138">Mídia</span><span class="sxs-lookup"><span data-stu-id="6bf88-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="6bf88-139">Web</span><span class="sxs-lookup"><span data-stu-id="6bf88-139">Web</span></span>    |<span data-ttu-id="6bf88-140">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-140">X</span></span>         |-         |-         |
|<span data-ttu-id="6bf88-141">Windows</span><span class="sxs-lookup"><span data-stu-id="6bf88-141">Windows</span></span>     |<span data-ttu-id="6bf88-142">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-142">X</span></span>         |<span data-ttu-id="6bf88-143">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-143">X</span></span>         |<span data-ttu-id="6bf88-144">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-144">X</span></span>         |
|<span data-ttu-id="6bf88-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="6bf88-145">Mac OSX</span></span>     |<span data-ttu-id="6bf88-146">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-146">X</span></span>         |<span data-ttu-id="6bf88-147">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-147">X</span></span>         |<span data-ttu-id="6bf88-148">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-148">X</span></span>         |
|<span data-ttu-id="6bf88-149">Linux</span><span class="sxs-lookup"><span data-stu-id="6bf88-149">Linux</span></span>     |<span data-ttu-id="6bf88-150">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-150">X</span></span>         |<span data-ttu-id="6bf88-151">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-151">X</span></span>         |<span data-ttu-id="6bf88-152">X</span><span class="sxs-lookup"><span data-stu-id="6bf88-152">X</span></span>         |
|<span data-ttu-id="6bf88-153">iOS</span><span class="sxs-lookup"><span data-stu-id="6bf88-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="6bf88-154">Android</span><span class="sxs-lookup"><span data-stu-id="6bf88-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="6bf88-155">Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6bf88-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="6bf88-156">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="6bf88-156">Debug logs</span></span>

<span data-ttu-id="6bf88-157">Consulte a _seção Coletar e habilitar o registro em log_ para obter Windows e instruções do Mac.</span><span class="sxs-lookup"><span data-stu-id="6bf88-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="6bf88-158">Os logs de depuração são produzidos pelos clientes de desktop Windows e Mac, bem como por clientes baseados em navegador.</span><span class="sxs-lookup"><span data-stu-id="6bf88-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="6bf88-159">Os logs são baseados em texto e são lidos de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="6bf88-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="6bf88-160">Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao efetuar o registro em log no cliente.</span><span class="sxs-lookup"><span data-stu-id="6bf88-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="6bf88-161">Os registros de depuração mostram os seguintes fluxos de dados:</span><span class="sxs-lookup"><span data-stu-id="6bf88-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="6bf88-162">Login</span><span class="sxs-lookup"><span data-stu-id="6bf88-162">Login</span></span>

-   <span data-ttu-id="6bf88-163">Solicitações de conexão para serviços de nível intermediário</span><span class="sxs-lookup"><span data-stu-id="6bf88-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="6bf88-164">Chamada/conversa</span><span class="sxs-lookup"><span data-stu-id="6bf88-164">Call/conversation</span></span>

<span data-ttu-id="6bf88-165">Para coletar logs para Linux: atalho do teclado: Ctrl + Alt + Shift + 1 Os arquivos estarão disponíveis em ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="6bf88-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="6bf88-166">Para coletar logs para Navegador: Atalho do teclado: Crtl + Alt + Shift + 1 Os arquivos estarão disponíveis em %userprofile%\Downloads</span><span class="sxs-lookup"><span data-stu-id="6bf88-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="6bf88-167">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="6bf88-167">Media logs</span></span>

<span data-ttu-id="6bf88-168">Consulte a _seção Coletar e habilitar o registro em log_ para obter Windows e instruções do Mac.</span><span class="sxs-lookup"><span data-stu-id="6bf88-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="6bf88-169">Os registros de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela nas reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="6bf88-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="6bf88-170">Eles são necessários para casos de suporte vinculados a problemas relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="6bf88-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="6bf88-171">O registro de mídia está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6bf88-171">Media logging is turned off by default.</span></span> <span data-ttu-id="6bf88-172">Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="6bf88-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="6bf88-173">Vá para **Configurações** > **Gerais**, marque a caixa de seleção **Habilitar registro para diagnóstico de reunião (requer a reinicialização do Teams**), reinicie o Teams e reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="6bf88-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="6bf88-174">Ao enviar os arquivos de log para o suporte da Microsoft, verifique a data e hora dos arquivos de log para garantir que os logs abrangem o período de tempo em que você reproduziu o problema.</span><span class="sxs-lookup"><span data-stu-id="6bf88-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="6bf88-175">Para coletar logs para Linux: os arquivos estarão disponíveis em ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog e *~/.config/Microsoft/Microsoft Teams/skylib/ .blog.*</span><span class="sxs-lookup"><span data-stu-id="6bf88-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="6bf88-176">Aqui está uma lista dos arquivos de log gerados e as informações que eles contêm.</span><span class="sxs-lookup"><span data-stu-id="6bf88-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="6bf88-177">Nome do arquivo de log</span><span class="sxs-lookup"><span data-stu-id="6bf88-177">Log file name</span></span>  |<span data-ttu-id="6bf88-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="6bf88-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6bf88-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="6bf88-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="6bf88-180">Contém informações relacionadas à pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="6bf88-180">Contains information related to the media stack.</span></span> <span data-ttu-id="6bf88-181">Isso inclui o status do canal, como resolução, decodificadores e codificadores usados e o número de quadros enviados e recebidos, além do status da sessão de compartilhamento de tela com base em vídeo e câmera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="6bf88-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="6bf88-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="6bf88-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="6bf88-183">Registra informações relacionadas a ações de controle remoto, como o carimbo de hora quando o controle é fornecido e informações do ponteiro do mouse.</span><span class="sxs-lookup"><span data-stu-id="6bf88-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="6bf88-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="6bf88-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="6bf88-185">Registra eventos de rastreamento de pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="6bf88-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="6bf88-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="6bf88-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="6bf88-187">Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.</span><span class="sxs-lookup"><span data-stu-id="6bf88-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="6bf88-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="6bf88-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="6bf88-189">Registra eventos na API de chamada de ts.</span><span class="sxs-lookup"><span data-stu-id="6bf88-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="6bf88-190">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="6bf88-190">Desktop logs</span></span>

<span data-ttu-id="6bf88-191">Consulte a _seção Coletar e habilitar o registro em log_ para obter Windows e instruções do Mac.</span><span class="sxs-lookup"><span data-stu-id="6bf88-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="6bf88-192">Os logs da área de trabalho, também conhecidos como logs de bootstrapper, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador.</span><span class="sxs-lookup"><span data-stu-id="6bf88-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="6bf88-193">Como os logs de mídia, esses logs só são necessários se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bf88-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="6bf88-194">Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="6bf88-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="6bf88-195">Para coletar logs para Linux: clique no ícone Microsoft Teams na bandeja do sistema e selecione **Obter Logs.**</span><span class="sxs-lookup"><span data-stu-id="6bf88-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="6bf88-196">Os arquivos estarão disponíveis em ~/.config/Microsoft/Microsoft Teams/logs.txt.</span><span class="sxs-lookup"><span data-stu-id="6bf88-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="6bf88-197">Rastreamento do navegador</span><span class="sxs-lookup"><span data-stu-id="6bf88-197">Browser trace</span></span>

<span data-ttu-id="6bf88-198">Para algumas categorias de erros, o Suporte da Microsoft pode exigir que você colete um rastreamento do navegador.</span><span class="sxs-lookup"><span data-stu-id="6bf88-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="6bf88-199">Essas informações podem fornecer detalhes importantes sobre o estado do cliente Teams quando o erro ocorrer.</span><span class="sxs-lookup"><span data-stu-id="6bf88-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="6bf88-200">Antes de iniciar o rastreamento do navegador, certifique-se de estar Teams.</span><span class="sxs-lookup"><span data-stu-id="6bf88-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="6bf88-201">É importante fazer isso antes de iniciar o rastreamento para que o rastreamento não contenha informações confidenciais de login.</span><span class="sxs-lookup"><span data-stu-id="6bf88-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="6bf88-202">Depois de entrar, selecione um dos links a seguir, conforme apropriado para seu navegador, e siga as etapas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="6bf88-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="6bf88-203">Borda & Chrome (Chromium)</span><span class="sxs-lookup"><span data-stu-id="6bf88-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="6bf88-204">Borda</span><span class="sxs-lookup"><span data-stu-id="6bf88-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="6bf88-205">Safari</span><span class="sxs-lookup"><span data-stu-id="6bf88-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="6bf88-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="6bf88-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="6bf88-207">Nas etapas, substitua todas as referências ao portal do Azure pelo Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="6bf88-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="6bf88-208">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6bf88-208">Related topics</span></span>

[<span data-ttu-id="6bf88-209">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="6bf88-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
