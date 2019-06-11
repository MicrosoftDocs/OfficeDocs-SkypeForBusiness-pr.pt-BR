---
title: Configurar perfil de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e982156928cf36b4e20eaf86175d7acbdf048b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="c53e1-102">Configurar perfil de usuário</span><span class="sxs-lookup"><span data-stu-id="c53e1-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c53e1-103">_**Tópico da última modificação:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="c53e1-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="c53e1-104">As ferramentas incluídas no pacote de ferramentas de desempenho e stress do Lync Server 2013 permitem criar e configurar as contas de usuário de teste que você pode usar para executar simulações de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="c53e1-105">Use a ferramenta de criação de usuários do Lync Server 2013 para criar os usuários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="c53e1-106">(Para obter detalhes, consulte [criar usuários e contatos](create-users-and-contacts.md).) Após a criação dos usuários, configure os perfis de usuário usando a ferramenta de configuração de carregamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c53e1-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="c53e1-107">Executando a ferramenta de configuração de carga do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c53e1-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="c53e1-108">Para configurar perfis de usuário, execute a ferramenta de configuração de carregamento do Lync Server 2013 (UserProfileGenerator. exe) e preencha cada uma das guias.</span><span class="sxs-lookup"><span data-stu-id="c53e1-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="c53e1-109">O UserProfileGenerator. exe gera um diretório para cada um dos computadores cliente que você precisa para executar a simulação.</span><span class="sxs-lookup"><span data-stu-id="c53e1-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="c53e1-110">Cada diretório de cliente também vem com um script para iniciar todas as instâncias da ferramenta de stress e desempenho do Lync Server 2013 (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="c53e1-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c53e1-111">Os valores específicos de usuário especificados em UserProfileGenerator devem coincidir com os valores especificados na UserProvisioningTool (ferramenta de criação de usuário) do Lync Server 2013 para o pool.</span><span class="sxs-lookup"><span data-stu-id="c53e1-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="c53e1-112">Preencha os campos em cada guia da ferramenta de configuração de carregamento do Lync Server 2013, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c53e1-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="c53e1-113">Configuração comum</span><span class="sxs-lookup"><span data-stu-id="c53e1-113">Common Configuration</span></span>

<span data-ttu-id="c53e1-114">A guia **configuração comum** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c53e1-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="c53e1-115">Preencha os campos da guia **configuração comum** , conforme descrito nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c53e1-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="c53e1-116">![Guia configuração comum.] (images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Guia configuração comum.")</span><span class="sxs-lookup"><span data-stu-id="c53e1-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="c53e1-117">Em **número de máquinas disponíveis**, digite ou clique no número de computadores que você deseja usar para executar o LyncPerfTool. exe.</span><span class="sxs-lookup"><span data-stu-id="c53e1-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="c53e1-118">Recomendamos que você tenha um computador para cada usuário do 4.500 que você vai simulando.</span><span class="sxs-lookup"><span data-stu-id="c53e1-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="c53e1-119">Esse número pode variar se você reduzir o nível de carga ou se usar apenas um subconjunto de recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c53e1-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="c53e1-120">(Os níveis de carga são definidos na guia **cenários gerais** .)</span><span class="sxs-lookup"><span data-stu-id="c53e1-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="c53e1-121">Em **prefixo para nomes de usuário**, digite o prefixo para o nome de usuário dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="c53e1-122">Para entrar, o URI (Uniform Resource Identifier) será: userprefix\[User Start index... (Número de usuários-1) \]@User domínio.</span><span class="sxs-lookup"><span data-stu-id="c53e1-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="c53e1-123">Em **senha para todos os usuários**, insira a senha que foi usada para criar os usuários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="c53e1-124">Se você deixar este campo vazio, o nome de usuário será usado como senha.</span><span class="sxs-lookup"><span data-stu-id="c53e1-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="c53e1-125">Em **índice de início do usuário**, clique ou digite o índice do primeiro usuário a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="c53e1-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="c53e1-126">Você pode configurar intervalos diferentes para tipos ou níveis diferentes de carga, mas é necessário executar o UserProfileGenerator. exe uma vez pelo intervalo que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="c53e1-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="c53e1-127">Em **número de usuários**, clique ou digite o número total de usuários que você vai configurar.</span><span class="sxs-lookup"><span data-stu-id="c53e1-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="c53e1-128">Em **domínio do usuário**, digite o domínio usado para o URI do SIP.</span><span class="sxs-lookup"><span data-stu-id="c53e1-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="c53e1-129">Isso é usado para construir o URI SIP de cada usuário para fazer logon no servidor front-end do Lync Server 2013 ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c53e1-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="c53e1-130">Ele pode ser diferente do domínio da conta.</span><span class="sxs-lookup"><span data-stu-id="c53e1-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="c53e1-131">Em **domínio da conta**, digite o logon de domínio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c53e1-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="c53e1-132">Digite o número máximo de pontos de extremidade simultâneos em **entrar por segundo (por instância)** para o qual você deseja que a ferramenta faça logon em todos os pontos de extremidade/usuários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="c53e1-133">A taxa recomendada é \<= 2 por segundo/SKU padrão Fe.</span><span class="sxs-lookup"><span data-stu-id="c53e1-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="c53e1-134">Em **proxy do Access ou FQDN do pool**, digite o nome de domínio totalmente qualificado (FQDN) do servidor ao qual você deseja que os clientes se conectem.</span><span class="sxs-lookup"><span data-stu-id="c53e1-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="c53e1-135">Se os usuários estiverem fazendo logon externo, especifique o proxy de acesso.</span><span class="sxs-lookup"><span data-stu-id="c53e1-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="c53e1-136">Se os usuários forem internos, especifique o FQDN do pool ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c53e1-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="c53e1-137">Em **porta**, clique ou digite a porta que você deseja que os usuários usem para o SIP (o padrão é 5061).</span><span class="sxs-lookup"><span data-stu-id="c53e1-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="c53e1-138">Para configurações de servidor de rede externo, especifique o **proxy de acesso ou o FQDN do pool** e a **porta**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="c53e1-139">Essas configurações são usadas apenas para simulação de carga de pontos de extremidade externos.</span><span class="sxs-lookup"><span data-stu-id="c53e1-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="c53e1-140">Cenários gerais</span><span class="sxs-lookup"><span data-stu-id="c53e1-140">General Scenarios</span></span>

<span data-ttu-id="c53e1-141">A guia **cenários gerais** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c53e1-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c53e1-142">Configure os níveis de carga e os parâmetros para cada um dos cenários gerais que você deseja executar ou deixe desabilitado.</span><span class="sxs-lookup"><span data-stu-id="c53e1-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="c53e1-143">![Guia cenários gerais.] (images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Guia cenários gerais.")</span><span class="sxs-lookup"><span data-stu-id="c53e1-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="c53e1-144">Em **mensagens instantâneas**, que incluem ponto a ponto e conferência, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c53e1-145">Os valores de nível de carga para todos os campos (exceto serviços <STRONG></STRONG>de informações de localização) são desabilitados, <STRONG>baixados</STRONG>, <STRONG>médios</STRONG>, <STRONG>altos</STRONG>e <STRONG>personalizados</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c53e1-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="c53e1-146">Quando baixo, médio, alto ou personalizado estiver selecionado, as configurações serão geradas para cada cliente e modalidade.</span><span class="sxs-lookup"><span data-stu-id="c53e1-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="c53e1-147">Alto fará com que a carga máxima compatível seja gerada para o servidor, média corresponderá a 60% da carga, e que seja menor corresponda a 30% da carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="c53e1-148">Na **videoconferência**, que é somente videoconferência, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c53e1-149">As chamadas ponto a ponto são abordadas na seção cenários de voz mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c53e1-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="c53e1-150">Para habilitar o MultiView, abra a guia **avançado** para essa modalidade.</span><span class="sxs-lookup"><span data-stu-id="c53e1-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="c53e1-151">Em **compartilhamento de aplicativos**, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="c53e1-152">Na **colaboração de dados**, que inclui a conferência de dados, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="c53e1-153">Na **expansão da lista de distribuição**, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c53e1-154">Você também deve clicar no botão **avançado** e preencher os campos com os mesmos valores que você configurou na guia lista de **distribuição** da ferramenta de criação de usuários do Lync Server (UserProvisioningTool. exe).</span><span class="sxs-lookup"><span data-stu-id="c53e1-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="c53e1-155">Para obter detalhes sobre esses campos, consulte [criar usuários e contatos](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="c53e1-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="c53e1-156">Na **consulta à Web do catálogo de endereços**, que é o serviço de pesquisa de catálogo de endereços (não o download do arquivo do catálogo de endereços), especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c53e1-157">Para habilitar downloads do catálogo de endereços, clique no botão **avançado** correspondente e defina **EnableABSDownload** como verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="c53e1-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="c53e1-158">Em **serviço de grupo de resposta**, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c53e1-159">Você também deve clicar no botão **avançado** correspondente e, em seguida, especificar os URIs dos grupos de resposta que você já criou ao provisionar agentes de serviço de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="c53e1-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="c53e1-160">Você deve especificar pelo menos um grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="c53e1-160">You must specify at least one response group.</span></span> <span data-ttu-id="c53e1-161">Use ponto-e-vírgula para separar vários grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="c53e1-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="c53e1-162">Atualize RGSUriSuffixStartIndex e RGSUriSuffixEndIndex para os valores reais.</span><span class="sxs-lookup"><span data-stu-id="c53e1-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="c53e1-163">Em **serviços de informações de localização**, selecione o valor apropriado para nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="c53e1-164">O nível de carga dos serviços de informações de localização deve ser **habilitado** ou **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53e1-165">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele e um conjunto de caixas de seleção que permitem variações dos cenários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="c53e1-166"><STRONG>Ad-hoc</STRONG> significa gerar simulação de conferências que serão criadas em toda hora.</span><span class="sxs-lookup"><span data-stu-id="c53e1-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="c53e1-167"><STRONG>Grande conf</STRONG> significa que o cenário de conferência grande será simulado.</span><span class="sxs-lookup"><span data-stu-id="c53e1-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="c53e1-168">Os meios <STRONG>externos</STRONG> também simulam usuários externos.</span><span class="sxs-lookup"><span data-stu-id="c53e1-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="c53e1-169">Esses botões e caixas de seleção permitem o acesso a valores específicos para cada cenário que alterarão o comportamento da ferramenta de stress e desempenho do Lync Server 2013 e tornará a personalização possível.</span><span class="sxs-lookup"><span data-stu-id="c53e1-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="c53e1-170">Para cada cenário na guia <STRONG>cenários gerais</STRONG> (exceto para serviços de informações de localização), se o valor do nível de carga for <STRONG>personalizado</STRONG>, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo <STRONG>avançado</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c53e1-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="c53e1-171">O nome do campo é diferente, dependendo do cenário, mas a descrição do campo entrará em "Observação: este número só será usado se personalizado estiver selecionado no menu suspenso".</span><span class="sxs-lookup"><span data-stu-id="c53e1-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="c53e1-172">Em geral, os valores <STRONG>alto</STRONG>, <STRONG>médio</STRONG>e <STRONG>baixo</STRONG> mudarão as tarifas de conversa por modalidade em linha com o modelo de usuário que é o saldo de todos os cenários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="c53e1-173">Se houver necessidade de alterar o nível de carga por modalidade devido a uma diferença no uso esperado, recomendamos usar uma taxa de conversa <STRONG>personalizada</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c53e1-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="c53e1-174">Cenários de voz</span><span class="sxs-lookup"><span data-stu-id="c53e1-174">Voice Scenarios</span></span>

<span data-ttu-id="c53e1-175">A guia **cenários de voz** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c53e1-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c53e1-176">Use a guia **cenários de voz** para configurar todos os cenários relacionados a voz.</span><span class="sxs-lookup"><span data-stu-id="c53e1-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="c53e1-177">![Guia cenários de voz.] (images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Guia cenários de voz.")</span><span class="sxs-lookup"><span data-stu-id="c53e1-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="c53e1-178">Em **VoIP**, clique no botão **avançado** e, em seguida, forneça valores para os campos **PhoneAreaCode** e **LocationProfile** (plano de discagem).</span><span class="sxs-lookup"><span data-stu-id="c53e1-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="c53e1-179">Você também deve especificar um valor para o **nível de carga**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="c53e1-180">Se o nível de carga do gateway de **VoIP** e de **UC/PSTN** estiver habilitado, uma rede telefônica pública comutada (PSTN) para o arquivo de configuração de comunicação unificada (UC) será sempre gerada e simulará chamadas externas.</span><span class="sxs-lookup"><span data-stu-id="c53e1-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="c53e1-181">Em **Gateway UC/PSTN**, especifique um valor para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="c53e1-182">Se você selecionar um nível de carga diferente de **Disabled**, deverá fornecer um valor para o **código de área PSTN** clicando no botão **Adicionar** em servidor de mediação e PSTN.</span><span class="sxs-lookup"><span data-stu-id="c53e1-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="c53e1-183">Verifique se você tem uma rota configurada para esse código de área.</span><span class="sxs-lookup"><span data-stu-id="c53e1-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c53e1-184">Você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para verificar a configuração da rota de voz.</span><span class="sxs-lookup"><span data-stu-id="c53e1-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="c53e1-185">Em **atendedor de conferência**, especifique um valor para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c53e1-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="c53e1-186">Selecionar um nível de carga (diferente \*\*\*\* de desabilitado) habilitará o campo de **número de telefone** .</span><span class="sxs-lookup"><span data-stu-id="c53e1-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="c53e1-187">Digite o número de telefone do atendedor automático que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="c53e1-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="c53e1-188">Além disso, clique no botão **avançado** e, em seguida, especifique um valor para o campo **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="c53e1-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="c53e1-189">Em **serviço de estacionamento de chamadas**, especifique o valor apropriado para o **nível de carga**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="c53e1-190">No **servidor de mediação e PSTN**, para cada servidor de mediação que você deseja usar, você deve ter um simulador PSTN separado.</span><span class="sxs-lookup"><span data-stu-id="c53e1-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="c53e1-191">Depois de determinar qual cliente será usado como o simulador, você precisará configurar o servidor de mediação para direcionar chamadas para esse computador na porta do simulador PSTN que você configurou.</span><span class="sxs-lookup"><span data-stu-id="c53e1-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="c53e1-192">Clique em **Adicionar** para configurar o valor do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c53e1-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53e1-193">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="c53e1-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="c53e1-194">Esses botões permitem o acesso a valores específicos a cada cenário que alterarão o comportamento da ferramenta de desempenho e stress (LyncPerfTool) do Lync Server 2013 e habilitarão a personalização.</span><span class="sxs-lookup"><span data-stu-id="c53e1-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="c53e1-195">Para cada cenário na guia <STRONG>cenários de voz</STRONG> , se o valor do <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo <STRONG>avançado</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c53e1-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="c53e1-196">O nome do campo é diferente, dependendo do cenário, mas a descrição do campo entrará em "Observação: este número só será usado se personalizado estiver selecionado no menu suspenso".</span><span class="sxs-lookup"><span data-stu-id="c53e1-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="c53e1-197">Atender</span><span class="sxs-lookup"><span data-stu-id="c53e1-197">Reach</span></span>

<span data-ttu-id="c53e1-198">Reach é uma nova experiência no Lync Server 2013 que dá suporte a cenários de conferência por meio do servidor da API da Web de comunicação unificada (UCWA) instalada no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="c53e1-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="c53e1-199">A guia **REACH** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c53e1-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c53e1-200">Use a guia **alcançar** para configurar todos os cenários relacionados ao alcance.</span><span class="sxs-lookup"><span data-stu-id="c53e1-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="c53e1-201">![Guia de acesso.] (images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Guia de acesso.")</span><span class="sxs-lookup"><span data-stu-id="c53e1-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="c53e1-202">Clique no botão **avançado** ao lado de **configurações de alcance geral**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="c53e1-203">Defina o campo **UcwaTargetServerUrl** para o VIP (IP virtual) do pool diretor ou o VIP do pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="c53e1-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="c53e1-204">Em **compartilhamento de aplicativos**, **colaboração de dados**e **mensagens instantâneas**, selecione o valor apropriado para nível de **carga**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53e1-205">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="c53e1-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="c53e1-206">Esses botões permitem o acesso a valores específicos a cada cenário que alterarão o comportamento da ferramenta de desempenho e stress (LyncPerfTool) do Lync Server 2013 e habilitarão a personalização.</span><span class="sxs-lookup"><span data-stu-id="c53e1-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="c53e1-207">Para cada um dos cenários de alcance, se o <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, o valor especificado no campo <STRONG>ConversationsPerHour</STRONG> será usado em vez do padrão</span><span class="sxs-lookup"><span data-stu-id="c53e1-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="c53e1-208">Use a guia **Mobility** para configurar todos os cenários relacionados à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="c53e1-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="c53e1-209">![Guia mobilidade.] (images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Guia mobilidade.")</span><span class="sxs-lookup"><span data-stu-id="c53e1-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="c53e1-210">Clique no botão **avançado** ao lado de **Mobility (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="c53e1-211">Defina o campo **UcwaTargetServerUrl** para o VIP (IP virtual) do pool diretor ou o VIP do pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="c53e1-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="c53e1-212">Em **presença e áudio de mensagem\\instantânea P2P**, selecione o valor apropriado para o **nível de carga** para habilitar a simulação do cenário de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="c53e1-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53e1-213">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="c53e1-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="c53e1-214">Esses botões permitem o acesso a valores específicos a cada cenário que alterarão o comportamento da ferramenta de desempenho e stress (LyncPerfTool) do Lync Server 2013 e habilitarão a personalização.</span><span class="sxs-lookup"><span data-stu-id="c53e1-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="c53e1-215">Para cada um dos cenários de alcance, se o <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, o valor especificado no campo <STRONG>ConversationsPerHour</STRONG> será usado em vez do padrão.</span><span class="sxs-lookup"><span data-stu-id="c53e1-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="c53e1-216">Resumo</span><span class="sxs-lookup"><span data-stu-id="c53e1-216">Summary</span></span>

<span data-ttu-id="c53e1-217">A guia **Resumo** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c53e1-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c53e1-218">![Guia Resumo.] (images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Guia Resumo.")</span><span class="sxs-lookup"><span data-stu-id="c53e1-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="c53e1-219">A guia **Resumo** indica quais usuários usar para cada um dos cenários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="c53e1-220">É possível configurar manualmente intervalos de números de usuário, marcando a caixa de seleção **habilitar geração de intervalo de usuários personalizados** e clicando duas vezes no cenário na tabela que tem o **intervalo de usuários** que você deseja personalizar.</span><span class="sxs-lookup"><span data-stu-id="c53e1-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="c53e1-221">Verifique (RunClient. bat) adicionar atraso de entrada ao iniciar, para incluir atrasos nos arquivos em lote gerados para que correspondam à taxa de conexão.</span><span class="sxs-lookup"><span data-stu-id="c53e1-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="c53e1-222">Isso é útil para evitar a sobrecarga do servidor ao entrar em um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="c53e1-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="c53e1-223">Clique em **gerar arquivos**e selecione a pasta onde deseja gerar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c53e1-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="c53e1-224">Será exibida uma caixa de diálogo semelhante à seguinte figura quando seus arquivos forem criados com êxito.</span><span class="sxs-lookup"><span data-stu-id="c53e1-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="c53e1-225">![Confirmação de que os arquivos foram criados.] (images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Confirmação de que os arquivos foram criados.")</span><span class="sxs-lookup"><span data-stu-id="c53e1-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c53e1-226">Confira também</span><span class="sxs-lookup"><span data-stu-id="c53e1-226">See Also</span></span>


[<span data-ttu-id="c53e1-227">Criar usuários e contatos</span><span class="sxs-lookup"><span data-stu-id="c53e1-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
