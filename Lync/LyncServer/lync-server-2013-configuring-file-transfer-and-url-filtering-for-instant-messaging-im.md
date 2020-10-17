---
title: Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM)
description: Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548347"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="05347-103">Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05347-103">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05347-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="05347-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="05347-105">A ferramenta inteligente de filtro de IM ajuda a proteger sua implantação do Lync Server 2013 contra a disseminação das formas mais comuns de vírus com menor degradação para a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="05347-105">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="05347-106">Use o Filtro de IM Inteligente para configurar filtros para bloquear mensagens instantâneas não solicitadas ou potencialmente prejudiciais de pontos de extremidade desconhecidos fora do firewall da empresa.</span><span class="sxs-lookup"><span data-stu-id="05347-106">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="05347-107">Configure os filtros especificando os critérios que devem ser usados para determinar o que vai ser bloqueado, como mensagens instantâneas que tenham hiperlinks com prefixos específicos e arquivos com determinadas extensões.</span><span class="sxs-lookup"><span data-stu-id="05347-107">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="05347-108">O filtro de IM Inteligente fornece o seguinte:</span><span class="sxs-lookup"><span data-stu-id="05347-108">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="05347-109">Filtro avançado de URL.</span><span class="sxs-lookup"><span data-stu-id="05347-109">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="05347-110">Filtro avançado de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="05347-110">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="05347-111">A configuração do filtro de IM inteligente inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="05347-111">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="05347-112">Configuração do filtro de URL.</span><span class="sxs-lookup"><span data-stu-id="05347-112">Configuring URL filtering.</span></span>

  - <span data-ttu-id="05347-113">Configuração do filtro de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="05347-113">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="05347-114">Como as opções de filtro são aplicadas a mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="05347-114">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="05347-115">Antes de implantar a ferramenta de filtro de mensagens INSTANTÂNEAs inteligentes, você precisa entender como as opções de filtragem são aplicadas à medida que as mensagens são roteadas de um servidor do Lync Server 2013 para outro.</span><span class="sxs-lookup"><span data-stu-id="05347-115">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="05347-116">A forma como essas opções de filtragem são aplicadas é consistente, quer os servidores estejam em uma única organização ou ultrapasse os limites organizacionais.</span><span class="sxs-lookup"><span data-stu-id="05347-116">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="05347-117">Essa consistência se aplica à forma com que os textos personalizados de observação e aviso são inseridos em mensagens e enviados pelos servidores.</span><span class="sxs-lookup"><span data-stu-id="05347-117">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="05347-118">O filtro de mensagem instantânea aumenta a quantidade de recursos da CPU necessários para processar URLs em uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="05347-118">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="05347-119">Esse aumento na demanda da CPU também afeta o desempenho do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05347-119">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="05347-120">Usando a página de **filtro de URL** no grupo de **mensagens instantâneas e presença** no painel de controle do Lync Server, você pode bloquear alguns ou todos os hiperlinks ou configurar um aviso.</span><span class="sxs-lookup"><span data-stu-id="05347-120">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="05347-121">Esse aviso é inserido no início de uma mensagem instantânea que contém um hiperlink quando você escolhe a opção **Enviar mensagem de aviso** em **Prefixo de hiperlink**.</span><span class="sxs-lookup"><span data-stu-id="05347-121">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="05347-122">Quando uma mensagem instantânea passa de um servidor para outro, as seguintes diretrizes gerais se aplicam:</span><span class="sxs-lookup"><span data-stu-id="05347-122">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="05347-p105">Se um servidor bloqueia uma mensagem instantânea (por você ter marcado a caixa de seleção **Bloquear URLs com extensão de arquivo** na página **Filtro de URL** ou por você ter escolhido a opção **Bloquear hiperlinks** em **Prefixo de hiperlink**), uma mensagem de erro é devolvida ao cliente. Os servidores subsequentes não recebem essa mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="05347-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="05347-p106">Se um servidor (Servidor1) adiciona um aviso a uma mensagem instantânea que contém um hiperlink ativo, um servidor subsequente (Servidor2) que recebe essa mensagem ainda pode tomar uma ação diferente com base nesse hiperlink ativo, bloqueando a mensagem instantânea ou adicionando um aviso. Se o Servidor2 estiver configurado apenas para adicionar um aviso a esse URL, o aviso anterior adicionado pelo Servidor1 é removido, e o aviso configurado no Servidor2 é adicionado ao início da mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="05347-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="05347-127">Se você estiver executando o Lync Server 2013 em um ambiente misto, o Live Communications Server 2005 com SP1 é a versão mínima necessária para usar o aplicativo de filtro de IM inteligente.</span><span class="sxs-lookup"><span data-stu-id="05347-127">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="05347-128">O Filtro de IM Inteligente não é suportado no Live Communications Server 2005 sem o SP1.</span><span class="sxs-lookup"><span data-stu-id="05347-128">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="05347-129">Filtro de URL</span><span class="sxs-lookup"><span data-stu-id="05347-129">URL Filtering</span></span>

<span data-ttu-id="05347-p108">Os URLs são filtrados de acordo com seu prefixo do hiperlink. Os exemplos a seguir são prefixos válidos:</span><span class="sxs-lookup"><span data-stu-id="05347-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="05347-132">www \* .</span><span class="sxs-lookup"><span data-stu-id="05347-132">www\*.</span></span>

  - <span data-ttu-id="05347-133">FTP.</span><span class="sxs-lookup"><span data-stu-id="05347-133">ftp.</span></span>

  - <span data-ttu-id="05347-134">http</span><span class="sxs-lookup"><span data-stu-id="05347-134">http:</span></span>

<span data-ttu-id="05347-p109">Se você não configurar o filtro de mensagem instantânea para realizar o filtro de URL, todos os URLs presentes em mensagens instantâneas passam pelo servidor sem serem modificados. Porém, se você configurá-lo para realizar o filtro de URL, os URLs presentes em mensagens instantâneas são filtrados de acordo com as opções que você selecionou nas caixas de diálogo **Editar Filtro de URL** ou **Novo Filtro de URL**.</span><span class="sxs-lookup"><span data-stu-id="05347-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="05347-137">**Habilitar filtro**     de URL Essa opção habilita a filtragem de URL para a implantação global ou para o site que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="05347-137">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="05347-138">**Bloquear URLs com extensão**     de arquivo O filtro de mensagem instantânea bloqueia qualquer URL ativa de intranet ou Internet que contenha um arquivo com uma extensão listada em **extensões de tipo de arquivo a serem bloqueadas** na caixa de diálogo **Editar Filtro de arquivo** .</span><span class="sxs-lookup"><span data-stu-id="05347-138">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="05347-139">Quando um URL é bloqueado, uma mensagem de erro é exibida para o remetente.</span><span class="sxs-lookup"><span data-stu-id="05347-139">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="05347-140">Quando selecionada, essa opção busca precedência em todas as outras opções de filtro para quaisquer extensões de arquivos definidas em **Extensões de tipos de arquivos a serem bloqueadas**.</span><span class="sxs-lookup"><span data-stu-id="05347-140">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="05347-p111">A filtragem de extensões de arquivo está limitada aos nomes padrão. A filtragem pode não funcionar com extensões de arquivo incorporadas em outros nomes.</span><span class="sxs-lookup"><span data-stu-id="05347-p111">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="05347-143">Para configurar como hiperlinks são manuseados em conversas de mensagem instantânea, selecione uma das opções a seguir em **Prefixo de hiperlink**:</span><span class="sxs-lookup"><span data-stu-id="05347-143">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="05347-144">Não **Filtrar**     As URLs nas mensagens são enviadas pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="05347-144">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="05347-145">Quando você escolhe essa opção, a caixa **Permitir mensagem** aparece.</span><span class="sxs-lookup"><span data-stu-id="05347-145">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="05347-146">Na caixa **Permitir mensagem**, especifique o aviso que você quer inserir no começo de cada mensagem instantânea que contenha hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="05347-146">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="05347-147">Esse aviso não pode ter mais que 65535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="05347-147">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="05347-148">**Bloquear hiperlinks**     A entrega de mensagens instantâneas contendo hiperlinks ativos é bloqueada pelo Lync Server e uma mensagem de erro é exibida para o remetente.</span><span class="sxs-lookup"><span data-stu-id="05347-148">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="05347-149">**Enviar mensagem**     de aviso O Lync Server permite hiperlinks ativos em mensagens instantâneas, mas inclui um aviso.</span><span class="sxs-lookup"><span data-stu-id="05347-149">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="05347-150">Quando você escolhe essa opção, a caixa de **mensagem de aviso** é exibida.</span><span class="sxs-lookup"><span data-stu-id="05347-150">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="05347-151">Na caixa de **mensagem de aviso** , você deve digitar o aviso que deseja incluir com mensagens instantâneas contendo hiperlinks válidos.</span><span class="sxs-lookup"><span data-stu-id="05347-151">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="05347-152">Por exemplo, este aviso pode declarar os possíveis perigos de clicar em um link desconhecido ou pode consultar as políticas e os requisitos relevantes da sua organização.</span><span class="sxs-lookup"><span data-stu-id="05347-152">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="05347-153">O aviso não pode ter mais de 65535 caracteres.</span><span class="sxs-lookup"><span data-stu-id="05347-153">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="05347-154">Se você selecionar **Bloquear hiperlinks** ou **Enviar mensagem de aviso**, as seguintes opções estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="05347-154">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="05347-155">**Excluir hiperlinks**     da intranet local O filtro de mensagens instantâneas bloqueia apenas URLs da Internet.</span><span class="sxs-lookup"><span data-stu-id="05347-155">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="05347-156">Os URLs para locais dentro da sua intranet passam pelo servidor sem serem modificados.</span><span class="sxs-lookup"><span data-stu-id="05347-156">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="05347-157">No entanto, as URLs de intranet que os servidores individuais que executam o Lync Server passam dependem de quais tipos de sites locais são considerados parte da zona da intranet.</span><span class="sxs-lookup"><span data-stu-id="05347-157">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="05347-158">Para verificar as configurações da zona da intranet de um servidor, consulte o procedimento "para definir suas configurações de intranet no Internet Explorer" em [Modificar o filtro de URL padrão no Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="05347-158">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="05347-159">**Filtrar esses prefixos**     de hiperlink Para escolher quais prefixos você deseja bloquear, clique em **selecionar**e, em **selecionar prefixo de hiperlink**, adicione os prefixos à lista de **prefixos de hiperlink** .</span><span class="sxs-lookup"><span data-stu-id="05347-159">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="05347-160">Todos os prefixos, exceto **href** devem terminar com ponto ou dois pontos, ou com um asterisco seguido por um ponto.</span><span class="sxs-lookup"><span data-stu-id="05347-160">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="05347-161">Os prefixos válidos podem conter quaisquer caracteres no conjunto de caracteres de URL válidos, exceto o asterisco ( \* ).</span><span class="sxs-lookup"><span data-stu-id="05347-161">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="05347-162">O conjunto de caracteres válidos da URL é: \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="05347-162">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="05347-163">Filtro de Transferência de Arquivo</span><span class="sxs-lookup"><span data-stu-id="05347-163">File Transfer Filtering</span></span>

<span data-ttu-id="05347-p116">O filtro de transferência de arquivo afeta as mensagens instantâneas e as conferências. Para as conferências, essas configurações afetam o recurso de folheto no cliente Office Live Meeting 2007 e os recursos de reprodução de multimídia.</span><span class="sxs-lookup"><span data-stu-id="05347-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="05347-166">O Lync Server também oferece opções de configuração de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="05347-166">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="05347-167">Essa opção do lado do servidor é oferecida além dos controles do lado do cliente disponíveis no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05347-167">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="05347-p118">Você pode filtrar transferências de arquivos durante as conversas com mensagens instantâneas, quando você estiver usando um recurso de folheto no cliente do Office Live Meeting 2007 e para recursos de reprodução de multimídia para todos os tipos de arquivo. Você pode definir as seguintes opções para controlar arquivos de transferência:</span><span class="sxs-lookup"><span data-stu-id="05347-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="05347-170">**Habilitar filtro**     de arquivo Essa opção habilita a filtragem de arquivos para a implantação global ou para o site que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="05347-170">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="05347-171">Quando você habilita o filtro de arquivo, você pode escolher uma das opções a seguir na **Transferência de arquivo**:</span><span class="sxs-lookup"><span data-stu-id="05347-171">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="05347-172">**Bloquear tipos**     de arquivo específicos Especifique quais solicitações de transferência de arquivo serão filtradas pelo servidor, especificando uma lista de extensões de arquivo a serem bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="05347-172">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="05347-173">As entradas na lista podem conter todos os caracteres padrão, mas não o caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="05347-173">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="05347-174">No cliente do Office Live Meeting 2007 o recurso de folheto está habilitado, mas nenhum arquivo com essa extensão pode ser carregado ou baixado.</span><span class="sxs-lookup"><span data-stu-id="05347-174">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="05347-175">Se você marcar a caixa de seleção **Bloquear URLs com extensão de arquivo** nas configurações listadas na guia **Filtro de URL**, o filtro de URL usa essa mesma lista para bloquear hiperlinks ativos que contenham qualquer uma dessas extensões de arquivos.</span><span class="sxs-lookup"><span data-stu-id="05347-175">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="05347-176">Para escolher quais tipos de arquivos você quer bloquear, clique em **Selecionar**, depois clique em **Selecionar Tipo de Arquivo**, e adicione as extensões de tipos de arquivos à lista **Extensões de tipos de arquivos selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="05347-176">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="05347-177">**Bloquear tudo**     O servidor descarta todas as mensagens instantâneas que contêm solicitações de transferência de arquivo e retorna uma mensagem de erro ao remetente da solicitação.</span><span class="sxs-lookup"><span data-stu-id="05347-177">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="05347-178">O recurso de folheto do cliente do Office Live Meeting 2007 será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="05347-178">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="05347-p121">A filtragem de extensões de arquivo está limitada aos nomes padrão. A filtragem pode não funcionar com extensões de arquivo incorporadas em outros nomes.</span><span class="sxs-lookup"><span data-stu-id="05347-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05347-181">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="05347-181">In This Section</span></span>

  - [<span data-ttu-id="05347-182">Modificar o filtro de transferência de arquivo padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05347-182">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="05347-183">Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico</span><span class="sxs-lookup"><span data-stu-id="05347-183">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="05347-184">Modificar o filtro de URL padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05347-184">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="05347-185">Criar um novo filtro de URL no Lync Server 2013 para lidar com hiperlinks em conversas de IM</span><span class="sxs-lookup"><span data-stu-id="05347-185">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05347-186">Confira também</span><span class="sxs-lookup"><span data-stu-id="05347-186">See Also</span></span>


[<span data-ttu-id="05347-187">Gerenciando configurações de IM e de presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05347-187">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

