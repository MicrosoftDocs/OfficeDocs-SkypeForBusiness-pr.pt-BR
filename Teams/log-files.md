---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre registros de depuração, mídia e desktop produzidos pelo Microsoft Teams, onde podem ser encontrados e como eles podem ajudar na resolução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5e670ffb90c91735578668bc42d1622386a0613
ms.sourcegitcommit: 5895afd0d5752a6ea1ace68d613f86c68eae8bdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857394"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="f73cc-103">Usar arquivos de registro para solucionar problemas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f73cc-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="f73cc-104">Existem três tipos de arquivos de registro produzidos automaticamente pelo cliente que podem ser aproveitados para ajudar na solução de problemas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f73cc-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="f73cc-105">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="f73cc-105">Debug logs</span></span>

-   <span data-ttu-id="f73cc-106">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="f73cc-106">Media logs</span></span>

-   <span data-ttu-id="f73cc-107">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="f73cc-107">Desktop logs</span></span>

<span data-ttu-id="f73cc-108">Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="f73cc-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="f73cc-109">Ter esses registros em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f73cc-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="f73cc-110">Os registros de mídia ou de desktop só são necessários se forem solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f73cc-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="f73cc-111">A tabela a seguir descreve os diversos clientes e seus registros associados.</span><span class="sxs-lookup"><span data-stu-id="f73cc-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="f73cc-112">Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f73cc-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="f73cc-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="f73cc-113">Client</span></span> |<span data-ttu-id="f73cc-114">Depuração</span><span class="sxs-lookup"><span data-stu-id="f73cc-114">Debug</span></span>|<span data-ttu-id="f73cc-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="f73cc-115">Desktop</span></span>|<span data-ttu-id="f73cc-116">Mídia</span><span class="sxs-lookup"><span data-stu-id="f73cc-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="f73cc-117">Web</span><span class="sxs-lookup"><span data-stu-id="f73cc-117">Web</span></span>    |<span data-ttu-id="f73cc-118">X</span><span class="sxs-lookup"><span data-stu-id="f73cc-118">X</span></span>         |-         |-         |
|<span data-ttu-id="f73cc-119">Windows</span><span class="sxs-lookup"><span data-stu-id="f73cc-119">Windows</span></span>     |<span data-ttu-id="f73cc-120">X</span><span class="sxs-lookup"><span data-stu-id="f73cc-120">X</span></span>         |<span data-ttu-id="f73cc-121">X</span><span class="sxs-lookup"><span data-stu-id="f73cc-121">X</span></span>         |<span data-ttu-id="f73cc-122">X</span><span class="sxs-lookup"><span data-stu-id="f73cc-122">X</span></span>         |
|<span data-ttu-id="f73cc-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f73cc-123">Mac OSX</span></span>     |<span data-ttu-id="f73cc-124">X</span><span class="sxs-lookup"><span data-stu-id="f73cc-124">X</span></span>         |<span data-ttu-id="f73cc-125">X</span><span class="sxs-lookup"><span data-stu-id="f73cc-125">X</span></span>         |<span data-ttu-id="f73cc-126">X</span><span class="sxs-lookup"><span data-stu-id="f73cc-126">X</span></span>         |
|<span data-ttu-id="f73cc-127">iOS</span><span class="sxs-lookup"><span data-stu-id="f73cc-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="f73cc-128">Android</span><span class="sxs-lookup"><span data-stu-id="f73cc-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="f73cc-129">Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f73cc-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="f73cc-130">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="f73cc-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="f73cc-131">Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f73cc-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="f73cc-132">Os logs de depuração são produzidos pelos clientes de área de trabalho do Windows e do Mac, bem como clientes baseados em navegador.</span><span class="sxs-lookup"><span data-stu-id="f73cc-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="f73cc-133">Os registros são baseados em texto e são lidos de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="f73cc-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="f73cc-134">Eles podem ser lidos usando qualquer editor baseado em texto, e novos registros são criados ao acessar o cliente.</span><span class="sxs-lookup"><span data-stu-id="f73cc-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="f73cc-135">Os registros de depuração mostram os seguintes fluxos de dados:</span><span class="sxs-lookup"><span data-stu-id="f73cc-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="f73cc-136">Login</span><span class="sxs-lookup"><span data-stu-id="f73cc-136">Login</span></span>

-   <span data-ttu-id="f73cc-137">Solicitações de conexão para serviços de camada intermediária</span><span class="sxs-lookup"><span data-stu-id="f73cc-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="f73cc-138">Chamada/conversa</span><span class="sxs-lookup"><span data-stu-id="f73cc-138">Call/conversation</span></span>

<span data-ttu-id="f73cc-139">Os registros de depuração são produzidos usando os seguintes métodos para o sistema operacional específico:</span><span class="sxs-lookup"><span data-stu-id="f73cc-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="f73cc-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="f73cc-140">Windows:</span></span>

      <span data-ttu-id="f73cc-141">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="f73cc-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="f73cc-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="f73cc-142">Mac OSX:</span></span>

      <span data-ttu-id="f73cc-143">Atalho do teclado: Opção + Comando + Shift+1</span><span class="sxs-lookup"><span data-stu-id="f73cc-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="f73cc-144">Os registros de depuração serão baixados automaticamente nas seguintes pastas.</span><span class="sxs-lookup"><span data-stu-id="f73cc-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="f73cc-145">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="f73cc-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="f73cc-146">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="f73cc-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="f73cc-147">Navegador: Você será instruído para salvar o registro de depuração no local padrão de salvamento</span><span class="sxs-lookup"><span data-stu-id="f73cc-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="f73cc-148">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="f73cc-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="f73cc-149">Os registros de mídia contêm dados de diagnóstico de áudio, vídeo e compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="f73cc-149">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="f73cc-150">Eles são necessários para casos de suporte apenas mediante solicitação e só podem ser inspecionados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f73cc-150">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="f73cc-151">A tabela a seguir descreve a localização dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="f73cc-151">The following table outlines the log location.</span></span>


|<span data-ttu-id="f73cc-152">Cliente</span><span class="sxs-lookup"><span data-stu-id="f73cc-152">Client</span></span> |<span data-ttu-id="f73cc-153">Localização</span><span class="sxs-lookup"><span data-stu-id="f73cc-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f73cc-154">Windows</span><span class="sxs-lookup"><span data-stu-id="f73cc-154">Windows</span></span>     |<span data-ttu-id="f73cc-155">blog\*do%AppData%\Microsoft\Teams\media-Stack.</span><span class="sxs-lookup"><span data-stu-id="f73cc-155">%appdata%\Microsoft\Teams\media-stack\*.blog</span></span>         |
|            |<span data-ttu-id="f73cc-156">blog\*do%AppData%\Microsoft\Teams\skylib.</span><span class="sxs-lookup"><span data-stu-id="f73cc-156">%appdata%\Microsoft\Teams\skylib\*.blog</span></span>
|            |<span data-ttu-id="f73cc-157">%appdata%\Microsoft\Teams\media-stack\*. etl</span><span class="sxs-lookup"><span data-stu-id="f73cc-157">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="f73cc-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f73cc-158">Mac OSX</span></span>     |<span data-ttu-id="f73cc-159">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="f73cc-159">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |
|            |<span data-ttu-id="f73cc-160">~/Library/Application Support Support/Microsoft/Teams/\*skylib. blog</span><span class="sxs-lookup"><span data-stu-id="f73cc-160">~/Library/Application Support/Microsoft/Teams/skylib\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="f73cc-161">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="f73cc-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="f73cc-162">Os registros de desktop, também conhecidos como registros de bootstrapper, contém dados de registro que ocorrem entre o clientes desktop e o navegador.</span><span class="sxs-lookup"><span data-stu-id="f73cc-162">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="f73cc-163">Assim como os registros de mídia, esses registros só são necessários se forem solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f73cc-163">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="f73cc-164">Os registros são baseados em texto e podem ser lidos usando qualquer editor baseado em texto no formato de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="f73cc-164">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="f73cc-165">Windows:</span><span class="sxs-lookup"><span data-stu-id="f73cc-165">Windows:</span></span>

1.  <span data-ttu-id="f73cc-166">Clique com o botão direito do mouse no **ícone do Microsoft Teams** na bandeja do aplicativo e selecione **Obter registros**</span><span class="sxs-lookup"><span data-stu-id="f73cc-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="f73cc-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="f73cc-167">Mac OsX:</span></span>

1.  <span data-ttu-id="f73cc-168">Escolher **Obter registros** no menu suspenso de **Ajuda**</span><span class="sxs-lookup"><span data-stu-id="f73cc-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="f73cc-169">Cliente</span><span class="sxs-lookup"><span data-stu-id="f73cc-169">Client</span></span> |<span data-ttu-id="f73cc-170">Localização</span><span class="sxs-lookup"><span data-stu-id="f73cc-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f73cc-171">Windows</span><span class="sxs-lookup"><span data-stu-id="f73cc-171">Windows</span></span>     |<span data-ttu-id="f73cc-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="f73cc-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="f73cc-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f73cc-173">Mac OSX</span></span>     |<span data-ttu-id="f73cc-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="f73cc-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
