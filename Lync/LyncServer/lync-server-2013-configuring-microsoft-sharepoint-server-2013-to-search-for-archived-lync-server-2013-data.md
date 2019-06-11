---
title: 'Lync Server 2013: Configurando o Microsoft SharePoint Server 2013 para pesquisar dados arquivados do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381db352aae635358dfd62cc1965ea238960bf8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="05d55-102">Configurando o Microsoft SharePoint Server 2013 para pesquisar dados do Microsoft Lync Server 2013 arquivados</span><span class="sxs-lookup"><span data-stu-id="05d55-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05d55-103">_**Tópico da última modificação:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="05d55-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="05d55-104">Uma das principais vantagens de armazenar mensagens instantâneas e transcrições de webconferências no Microsoft Exchange Server 2013 em vez do Microsoft Lync Server 2013 é o fato de que armazenar dados no mesmo local permite que os administradores usem uma única ferramenta para Pesquisar para dados arquivados do Exchange e/ou dados do Lync Server arquivados.</span><span class="sxs-lookup"><span data-stu-id="05d55-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="05d55-105">Como todos os dados são armazenados no mesmo lugar (Exchange), qualquer ferramenta que possa pesquisar dados do Exchange arquivado também pode procurar por dados arquivados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05d55-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="05d55-106">Uma ferramenta que torna mais fácil pesquisar dados arquivados é o Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05d55-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="05d55-107">Se quiser usar o SharePoint para pesquisar dados do Lync Server, primeiro você deve concluir todas as etapas envolvidas na configuração do arquivamento do Exchange no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05d55-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="05d55-108">Após o Exchange 2013 e o Lync Server 2013 terem sido integrados com sucesso, você deve instalar a versão 2,0 da API gerenciada dos serviços Web do Exchange no seu servidor do SharePoint; o programa de instalação dessa API pode ser baixado a partir do centro de download[http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)da Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="05d55-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="05d55-109">O arquivo baixado (EWSManagedAPI.msi) pode ser salvo em qualquer pasta do SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="05d55-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="05d55-110">Depois que o arquivo for baixado, conclua o procedimento a seguir no servidor do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="05d55-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="05d55-111">Abra uma janela de comando clicando em **Iniciar**, **Todos os Programas**, **Acessórios**, clicando com o botão direito em **Prompt de comando**, e então clicando em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="05d55-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="05d55-112">Na janela de comando, use o comando **cd** para mudar o diretório atual para a pasta onde o arquivo EWSManagedAPI.msi foi salvo.</span><span class="sxs-lookup"><span data-stu-id="05d55-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="05d55-113">Por exemplo, se você salvou o arquivo em C:\\downloads, digite o seguinte comando na janela de comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="05d55-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="05d55-114">Para instalar a API, digite o comando a seguir e então pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="05d55-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="05d55-115">Depois que a API for instalada, reinicie o IIS digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="05d55-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="05d55-116">Após a instalação do Exchange Web Services, você deve configurar a autenticação de servidor para servidor entre o SharePoint Server 2013 e o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="05d55-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="05d55-117">Para fazer isso, primeiro abra o Shell de gerenciamento do SharePoint 2013 e execute o seguinte conjunto de comandos:</span><span class="sxs-lookup"><span data-stu-id="05d55-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="05d55-118">Certifique-se de usar o URI para seu serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="05d55-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="05d55-119">Não use o URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1de exemplo.</span><span class="sxs-lookup"><span data-stu-id="05d55-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="05d55-120">Depois de criar o emissor do token e configurar o serviço de token, execute esses comandos, substituindo a URL do seu site do SharePoint pela URL de exemplohttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="05d55-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="05d55-121">Para configurar a autenticação de servidor para servidor para o Exchange 2013, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a isso (pressupondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):</span><span class="sxs-lookup"><span data-stu-id="05d55-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="05d55-122">Depois de configurar o aplicativo de parceiro, é recomendável parar e reiniciar os serviços de informações da Internet (IIS) em todos os servidores de caixa de correio do Exchange e de acesso para cliente.</span><span class="sxs-lookup"><span data-stu-id="05d55-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="05d55-123">Você pode reiniciar o IIS usando um comando similar a esse, que reinicia o serviço no atl-exchange-001 do computador:</span><span class="sxs-lookup"><span data-stu-id="05d55-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="05d55-124">Esse comando pode ser executado de dentro do Shell de gerenciamento do Exchange ou de qualquer outra janela de comando.</span><span class="sxs-lookup"><span data-stu-id="05d55-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="05d55-125">Em seguida, execute um comando semelhante ao seguinte, que fornece ao usuário especificado (neste exemplo, kenmyer) o direito de fazer a descoberta no Exchange:</span><span class="sxs-lookup"><span data-stu-id="05d55-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="05d55-126">Após o estabelecimento da autenticação de servidor para servidor entre o Exchange e o SharePoint, a próxima etapa é criar um site de descoberta eletrônica no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="05d55-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="05d55-127">Isso pode ser feito executando-se comandos semelhantes aos do Shell de gerenciamento do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="05d55-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="05d55-128">"eDiscovery" é uma abreviação de "electronic discovery (descoberta eletrônica)", e normalmente se refere ao processo de pesquisa por itens em arquivos eletrônicos, que possa ser "razoavelmente calculada para levar a provas admissíveis" em tribunal judicial.</span><span class="sxs-lookup"><span data-stu-id="05d55-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="05d55-129">Quando o novo site estiver pronto, a próxima etapa é configurar o Exchange 2013 para atuar como uma fonte de resultados para o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="05d55-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="05d55-130">Você pode fazer isso completando o seguinte procedimento na página Administração Central do SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="05d55-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="05d55-131">Na página de Administração Central, clique em **Gerenciar Aplicativos de Serviço** e então clique em **Aplicativo de Serviço de Pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="05d55-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="05d55-132">Na página Aplicativo de Serviço de Pesquisa: Administração de Pesquisa, clique em **Fontes de Resultado** e então clique em **Nova Fonte de Resultado**.</span><span class="sxs-lookup"><span data-stu-id="05d55-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="05d55-133">No painel **Nova Fonte de Resultado** insira um nome para a nova fonte de resultado (por exemplo, **Microsoft Exchange**) na caixa **Nome**.</span><span class="sxs-lookup"><span data-stu-id="05d55-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="05d55-134">Selecione **Exchange** como o **protocolo**de origem do resultado e, em seguida, insira a URL da fonte de serviços Web para o seu servidor Exchange na caixa **URL de origem do Exchange** .</span><span class="sxs-lookup"><span data-stu-id="05d55-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="05d55-135">A URL da fonte deve parecer com esta:</span><span class="sxs-lookup"><span data-stu-id="05d55-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="05d55-136">Certifique-se de que **Usar Descoberta Automática** não está selecionado e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="05d55-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="05d55-137">Por fim, crie um novo caso de descoberta eletrônica e um novo conjunto de descobertas eletrônicas completando o procedimento a seguir no site de descoberta do SharePoint (por exemplo,https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="05d55-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="05d55-138">Na página de Conteúdos do Site clique em **Criar um novo caso**.</span><span class="sxs-lookup"><span data-stu-id="05d55-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="05d55-p110">Na página Conteúdos do Site: Novo Site do SharePoint, insira o alias do email do usuário (por exemplo, **kenmyer**) na caixa **Título**, então adicione esta mesma URL à caixa **Endereço do Site**. Isso resultará em uma URL similar a esta:</span><span class="sxs-lookup"><span data-stu-id="05d55-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="05d55-141">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="05d55-141">Click **Create**.</span></span>

4.  <span data-ttu-id="05d55-142">Quando a página de conjunto de descoberta eletrônica aparecer, clique em **novo item** sob **Identidade e Preservação: Conjuntos de Descoberta**.</span><span class="sxs-lookup"><span data-stu-id="05d55-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="05d55-143">Na página Novo: Conjunto de Descoberta, insira o alias do email do usuário na caixa **Nome do Conjunto de Descoberta**.</span><span class="sxs-lookup"><span data-stu-id="05d55-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="05d55-144">Digite **Lync\* do descoberta eletrônica** na caixa **filtro** e clique em **Adicionar & gerenciar fontes**.</span><span class="sxs-lookup"><span data-stu-id="05d55-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="05d55-p112">Na página Adicionar e Gerenciar Fontes, insira o alias do email do usuário na primeira caixa de texto sob **Caixas de correio**. Clique no ícone de verificação da caixa de correio ao lado da caixa de texto para verificar se o SharePoint consegue se conectar à caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="05d55-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="05d55-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="05d55-147">Click **OK**.</span></span>

8.  <span data-ttu-id="05d55-148">Na página do conjunto de descoberta eletrônica, clique em **Salvar** para salvar o novo conjunto de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="05d55-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="05d55-149">Nesse ponto, você pode pesquisar a caixa de correio especificada (kenmyer) e/ou habilitar no local suspensões da mesma maneira que faria para qualquer outro conteúdo do SharePoint ou fonte de resultados.</span><span class="sxs-lookup"><span data-stu-id="05d55-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

