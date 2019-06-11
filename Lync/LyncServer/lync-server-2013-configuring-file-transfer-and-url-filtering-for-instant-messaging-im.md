---
title: Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="7d041-102">Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d041-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d041-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7d041-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7d041-104">A ferramenta inteligente de filtro de IM ajuda a proteger a implantação do Lync Server 2013 contra a disseminação das formas mais comuns de vírus com uma redução mínima para a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="7d041-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="7d041-105">Use o filtro de IM inteligente para configurar filtros para bloquear mensagens instantâneas não solicitadas ou perigosas de pontos de extremidade desconhecidos fora do firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="7d041-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="7d041-106">Você pode configurar filtros especificando os critérios a serem usados para determinar o que deve ser bloqueado, como mensagens instantâneas contendo hiperlinks com prefixos e arquivos específicos com extensões específicas.</span><span class="sxs-lookup"><span data-stu-id="7d041-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="7d041-107">O filtro de IM inteligente fornece o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d041-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="7d041-108">Filtragem de URL aprimorada.</span><span class="sxs-lookup"><span data-stu-id="7d041-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="7d041-109">Filtragem de transferência de arquivos aprimorada.</span><span class="sxs-lookup"><span data-stu-id="7d041-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="7d041-110">A configuração do filtro de IM inteligente inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d041-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="7d041-111">Configurar a filtragem de URL.</span><span class="sxs-lookup"><span data-stu-id="7d041-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="7d041-112">Configurar a filtragem de transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7d041-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="7d041-113">Como as opções de filtragem são aplicadas às mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="7d041-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="7d041-114">Antes de implantar a ferramenta de filtro de mensagem de chat inteligente, você precisa entender como as opções de filtragem são aplicadas à medida que as mensagens são roteadas de um servidor do Lync Server 2013 para outro.</span><span class="sxs-lookup"><span data-stu-id="7d041-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="7d041-115">A maneira como essas opções de filtragem são consistentes é consistente, independentemente de os servidores estarem localizados em uma única organização ou entre fronteiras organizacionais.</span><span class="sxs-lookup"><span data-stu-id="7d041-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="7d041-116">Essa consistência se aplica à maneira como o aviso e o texto de aviso personalizados são inseridos em mensagens e enviados entre servidores.</span><span class="sxs-lookup"><span data-stu-id="7d041-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7d041-117">O filtro de mensagem instantânea aumenta a quantidade de recursos de CPU necessários para processar URLs em uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="7d041-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="7d041-118">Esse aumento na demanda de CPU também afeta o desempenho do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d041-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="7d041-119">Usando a página **filtro de URL** no grupo **mensagens instantâneas e presença** no painel de controle do Lync Server, você pode bloquear alguns ou todos os hiperlinks ou configurar um aviso.</span><span class="sxs-lookup"><span data-stu-id="7d041-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="7d041-120">O aviso é inserido no início de uma mensagem instantânea que contém um hiperlink quando você escolhe a opção de **prefixo de hiperlink** **Enviar mensagem de aviso**.</span><span class="sxs-lookup"><span data-stu-id="7d041-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="7d041-121">Quando uma mensagem instantânea transita de um servidor para outro, as seguintes diretrizes gerais se aplicam:</span><span class="sxs-lookup"><span data-stu-id="7d041-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="7d041-122">Se um servidor bloquear uma mensagem instantânea (porque você marcou a caixa de seleção **Bloquear URLs com extensão de arquivo** na página **filtro de URL** ou porque você escolheu a opção de prefixo de **hiperlink** **Bloquear**hiperlinks), uma mensagem de erro será retornada para o cliente.</span><span class="sxs-lookup"><span data-stu-id="7d041-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="7d041-123">Os servidores subsequentes não recebem esta mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="7d041-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="7d041-124">Se um servidor (Server1) adicionar um aviso a uma mensagem de chat que contém um hiperlink ativo, um servidor subsequente (Server2) que receber essa mensagem instantânea ainda poderá executar uma ação diferente com base nesse hiperlink ativo presente na mensagem instantânea e bloquear o Envie uma mensagem instantânea ou adicione um aviso.</span><span class="sxs-lookup"><span data-stu-id="7d041-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="7d041-125">Se Server2 estiver configurado somente para adicionar um aviso para esta URL, o aviso anterior adicionado pelo Server1 será removido, e o aviso configurado no Server2 será adicionado ao início da mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="7d041-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7d041-126">Se você estiver executando o Lync Server 2013 em um ambiente misto, o Live Communications Server 2005 com SP1 é a versão mínima necessária para usar o aplicativo filtro inteligente de IM.</span><span class="sxs-lookup"><span data-stu-id="7d041-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="7d041-127">Não há suporte para o filtro de IM inteligente no Live Communications Server 2005 sem SP1.</span><span class="sxs-lookup"><span data-stu-id="7d041-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="7d041-128">Filtragem de URL</span><span class="sxs-lookup"><span data-stu-id="7d041-128">URL Filtering</span></span>

<span data-ttu-id="7d041-129">As URLs são filtradas de acordo com o prefixo do hiperlink.</span><span class="sxs-lookup"><span data-stu-id="7d041-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="7d041-130">Os exemplos a seguir são prefixos válidos:</span><span class="sxs-lookup"><span data-stu-id="7d041-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="7d041-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="7d041-131">www\*.</span></span>

  - <span data-ttu-id="7d041-132">FTP.</span><span class="sxs-lookup"><span data-stu-id="7d041-132">ftp.</span></span>

  - <span data-ttu-id="7d041-133">http</span><span class="sxs-lookup"><span data-stu-id="7d041-133">http:</span></span>

<span data-ttu-id="7d041-134">Se você não configurar o filtro de mensagem instantânea para executar qualquer filtragem de URL, todas as URLs contidas em mensagens instantâneas serão passadas de forma não modificada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="7d041-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="7d041-135">Se você configurar o filtro de mensagem instantânea para executar a filtragem de URL, as URLs nas mensagens instantâneas serão filtradas de acordo com as opções que você selecionar na caixa de diálogo **Editar Filtro de URL** ou **novo filtro de URL** .</span><span class="sxs-lookup"><span data-stu-id="7d041-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="7d041-136">**Habilitar filtro**   de URL essa opção habilita a filtragem de URL para a implantação global ou para o site que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="7d041-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="7d041-137">**Bloquear URLs com a extensão**   de arquivo o filtro de mensagem instantânea bloqueia qualquer URL ativa da intranet ou da Internet que contém um arquivo com uma extensão listada em **extensões de tipo de arquivo a serem bloqueadas** na caixa de diálogo **Editar Filtro de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="7d041-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="7d041-138">Quando uma URL é bloqueada, uma mensagem de erro é exibida para o remetente.</span><span class="sxs-lookup"><span data-stu-id="7d041-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="7d041-139">Quando selecionada, essa opção tem precedência sobre todas as outras opções de filtragem para qualquer extensão de arquivo definida em **extensões de tipo de arquivo a serem bloqueadas**.</span><span class="sxs-lookup"><span data-stu-id="7d041-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7d041-140">A filtragem de extensões de arquivo limita-se a nomes de arquivo padrão.</span><span class="sxs-lookup"><span data-stu-id="7d041-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="7d041-141">A filtragem pode não funcionar com extensões de arquivo inseridas em outros nomes.</span><span class="sxs-lookup"><span data-stu-id="7d041-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="7d041-142">Para configurar como os hiperlinks são manipulados nas conversas de mensagens instantâneas, selecione uma das seguintes opções em **prefixo do hiperlink**:</span><span class="sxs-lookup"><span data-stu-id="7d041-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="7d041-143">**Não filtre**   URLs nas mensagens são enviadas pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="7d041-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="7d041-144">Quando você escolhe essa opção, a caixa de **mensagem permitir** é exibida.</span><span class="sxs-lookup"><span data-stu-id="7d041-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="7d041-145">Na caixa de **mensagem permitir** , especifique o aviso que você deseja inserir no início de cada mensagem instantânea contendo hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="7d041-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="7d041-146">Este aviso pode consistir em no máximo 65535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7d041-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="7d041-147">**Bloquear**   hiperlinks a entrega de mensagens instantâneas com hiperlinks ativos é bloqueada pelo Lync Server, e uma mensagem de erro é exibida para o remetente.</span><span class="sxs-lookup"><span data-stu-id="7d041-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="7d041-148">**Enviar mensagem**   de aviso o Lync Server permite hiperlinks ativos em mensagens instantâneas, mas inclui um aviso.</span><span class="sxs-lookup"><span data-stu-id="7d041-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="7d041-149">Quando você escolhe essa opção, a caixa de **mensagem de aviso** é exibida.</span><span class="sxs-lookup"><span data-stu-id="7d041-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="7d041-150">Na caixa de **mensagem de aviso** , você deve digitar o aviso que deseja incluir com mensagens instantâneas que contenham hiperlinks válidos.</span><span class="sxs-lookup"><span data-stu-id="7d041-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="7d041-151">Por exemplo, este aviso pode declarar os possíveis perigos de clicar em um link desconhecido, ou pode se referir às políticas e requisitos relevantes da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7d041-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="7d041-152">O aviso não pode ter mais de 65535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7d041-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="7d041-153">Se você selecionar **Bloquear** hiperlinks ou **Enviar uma mensagem de aviso**, as seguintes opções estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7d041-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="7d041-154">**Excluir hiperlinks da intranet local**   o filtro de mensagem instantânea bloqueia somente URLs da Internet.</span><span class="sxs-lookup"><span data-stu-id="7d041-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="7d041-155">As URLs para locais na sua intranet são passadas de forma não modificada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="7d041-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="7d041-156">No entanto, as URLs de intranet que os servidores individuais que executam o Lync Server passam dependem de quais tipos de sites locais são considerados parte da zona da intranet deles.</span><span class="sxs-lookup"><span data-stu-id="7d041-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="7d041-157">Para verificar as configurações de zona da intranet de um servidor, consulte o procedimento "para configurar suas configurações de intranet no Internet Explorer" em [Modificar o filtro de URL padrão no Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="7d041-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="7d041-158">**Filtre esses**   prefixos de hiperlink para escolher quais prefixos deseja bloquear, clique em **selecionar**e, em seguida, no **prefixo selecionar Hiperlink**, adicione os prefixos à lista prefixos de **hiperlink** .</span><span class="sxs-lookup"><span data-stu-id="7d041-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="7d041-159">Todos os prefixos exceto **href** devem terminar com um ponto ou dois-pontos, ou um asterisco seguido por um ponto.</span><span class="sxs-lookup"><span data-stu-id="7d041-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="7d041-160">Prefixos válidos podem conter qualquer caractere no conjunto de caracteres de URL válidos, exceto o\*asterisco ().</span><span class="sxs-lookup"><span data-stu-id="7d041-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="7d041-161">O conjunto de caracteres válidos para URL é \# \*: +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ\_ \` ^ abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="7d041-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="7d041-162">Filtragem de transferência de arquivo</span><span class="sxs-lookup"><span data-stu-id="7d041-162">File Transfer Filtering</span></span>

<span data-ttu-id="7d041-163">A filtragem de transferência de filtro afeta mensagens instantâneas e conferências.</span><span class="sxs-lookup"><span data-stu-id="7d041-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="7d041-164">Em conferências, essas configurações afetam o recurso folheto no cliente do Office Live Meeting 2007 e os recursos de reprodução de multimídia.</span><span class="sxs-lookup"><span data-stu-id="7d041-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7d041-165">O Lync Server também oferece opções de configuração de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7d041-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="7d041-166">Essa opção do lado do servidor é oferecida além dos controles do lado do cliente disponíveis no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d041-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="7d041-167">Você pode filtrar transferências de arquivos durante conversas de mensagem instantânea, quando estiver usando o recurso folheto no cliente do Office Live Meeting 2007 e para recursos de reprodução de multimídia para todos os tipos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7d041-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="7d041-168">Você pode definir as seguintes opções para controlar as transferências de arquivos:</span><span class="sxs-lookup"><span data-stu-id="7d041-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="7d041-169">**Habilitar filtro**   de arquivo esta opção habilita a filtragem de arquivo para a implantação global ou para o site que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="7d041-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="7d041-170">Ao habilitar o filtro de arquivo, você pode escolher uma das seguintes opções na **transferência de arquivos**:</span><span class="sxs-lookup"><span data-stu-id="7d041-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="7d041-171">**Bloquear tipos**   de arquivo específicos você especifica quais solicitações de transferência de arquivo são filtradas pelo servidor especificando uma lista de extensões de arquivo a serem bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="7d041-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="7d041-172">As entradas na lista podem conter todos os caracteres padrão, mas não o caractere curinga\*().</span><span class="sxs-lookup"><span data-stu-id="7d041-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="7d041-173">No cliente do Office Live Meeting 2007, o recurso folheto está habilitado, mas qualquer arquivo com essa extensão não pode ser carregado ou baixado.</span><span class="sxs-lookup"><span data-stu-id="7d041-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="7d041-174">Se você marcar a caixa de seleção **Bloquear URLs com extensão de arquivo** nas configurações de um filtro de URL listado na guia **filtro de URL** , o filtro de URL usará essa mesma lista para bloquear hiperlinks ativos que contenham qualquer uma dessas extensões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7d041-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="7d041-175">Para escolher quais tipos de arquivo você deseja bloquear, clique em **selecionar**e, em seguida, em **Selecionar tipo de arquivo**, adicione as extensões de tipo de arquivo à lista de extensões de tipo de **arquivo selecionadas** .</span><span class="sxs-lookup"><span data-stu-id="7d041-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="7d041-176">**Bloquear todos**   os servidores descarta todas as mensagens instantâneas que contêm solicitações de transferência de arquivo e retorna uma mensagem de erro para o remetente da solicitação.</span><span class="sxs-lookup"><span data-stu-id="7d041-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="7d041-177">O recurso folheto no cliente do Office Live Meeting 2007 está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="7d041-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="7d041-178">A filtragem de extensões de arquivo limita-se a nomes de arquivo padrão.</span><span class="sxs-lookup"><span data-stu-id="7d041-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="7d041-179">A filtragem pode não funcionar com extensões de arquivo inseridas em outros nomes.</span><span class="sxs-lookup"><span data-stu-id="7d041-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7d041-180">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7d041-180">In This Section</span></span>

  - [<span data-ttu-id="7d041-181">Modificar o filtro de transferência de arquivo padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d041-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="7d041-182">Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico</span><span class="sxs-lookup"><span data-stu-id="7d041-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="7d041-183">Modificar o filtro de URL padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d041-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="7d041-184">Criar um novo filtro de URL no Lync Server 2013 para manipular hiperlinks em conversas de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="7d041-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d041-185">Confira também</span><span class="sxs-lookup"><span data-stu-id="7d041-185">See Also</span></span>


[<span data-ttu-id="7d041-186">Gerenciando configurações de IM e de presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d041-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

