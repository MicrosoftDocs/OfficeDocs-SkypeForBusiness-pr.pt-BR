---
title: Configurar perfil de usuário
description: Configure o perfil do usuário.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573087"
---
# <a name="configure-user-profile"></a><span data-ttu-id="c78f5-103">Configurar perfil de usuário</span><span class="sxs-lookup"><span data-stu-id="c78f5-103">Configure User Profile</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c78f5-104">_**Última modificação do tópico:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="c78f5-104">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="c78f5-105">As ferramentas incluídas no pacote de ferramentas de desempenho e stress do Lync Server 2013 permitem que você crie e configure as contas de usuário de teste que você pode usar para executar simulações de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-105">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="c78f5-106">Use a ferramenta de criação de usuário do Lync Server 2013 para criar os usuários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-106">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="c78f5-107">(Para obter detalhes, consulte [Create Users and contacts](create-users-and-contacts.md).) Depois que os usuários são criados, configure os perfis de usuário usando a ferramenta de configuração de carregamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c78f5-107">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="c78f5-108">Executando a ferramenta de configuração de carregamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c78f5-108">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="c78f5-109">Para configurar perfis de usuário, execute a ferramenta de configuração de carregamento do Lync Server 2013 (UserProfileGenerator.exe) e preencha cada uma das guias.</span><span class="sxs-lookup"><span data-stu-id="c78f5-109">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="c78f5-110">UserProfileGenerator.exe gera um diretório para cada computador cliente que você precisa para executar a simulação.</span><span class="sxs-lookup"><span data-stu-id="c78f5-110">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="c78f5-111">Cada diretório de cliente também vem com um script para iniciar todas as instâncias da ferramenta de desempenho e stress do Lync Server 2013 (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="c78f5-111">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c78f5-112">Os valores específicos do usuário especificados em UserProfileGenerator devem corresponder aos valores especificados na ferramenta de criação de usuário (UserProvisioningTool) do Lync Server 2013 para o pool.</span><span class="sxs-lookup"><span data-stu-id="c78f5-112">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="c78f5-113">Preencha os campos em cada guia da ferramenta de configuração de carga do Lync Server 2013, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c78f5-113">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="c78f5-114">Configuração comum</span><span class="sxs-lookup"><span data-stu-id="c78f5-114">Common Configuration</span></span>

<span data-ttu-id="c78f5-115">A guia **configuração comum** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c78f5-115">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="c78f5-116">Preencha os campos da guia **configuração comum** , conforme descrito nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c78f5-116">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="c78f5-117">![Guia configuração comum.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Guia configuração comum.")</span><span class="sxs-lookup"><span data-stu-id="c78f5-117">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="c78f5-118">Em **número de máquinas disponíveis**, digite ou clique no número de computadores que você deseja usar para executar o LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="c78f5-118">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="c78f5-119">Recomendamos que você tenha um computador para todos os usuários do 4.500 que você vai simular.</span><span class="sxs-lookup"><span data-stu-id="c78f5-119">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="c78f5-120">Esse número pode variar se você reduzir o nível de carga ou se usar apenas um subconjunto dos recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c78f5-120">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="c78f5-121">(Os níveis de carga são definidos na guia **cenários gerais** .)</span><span class="sxs-lookup"><span data-stu-id="c78f5-121">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="c78f5-122">Em **prefixo para nomes de usuário**, digite o prefixo para o nome de usuário dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-122">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="c78f5-123">Para fazer logon, o URI (Uniform Resource Identifier) será: userprefix \[ User Start index... (Número de usuários-1) \] @User domínio.</span><span class="sxs-lookup"><span data-stu-id="c78f5-123">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="c78f5-124">Em **senha para todos os usuários**, insira a senha usada para a criação dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-124">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="c78f5-125">Se você deixar este campo vazio, o nome de usuário será usado como a senha.</span><span class="sxs-lookup"><span data-stu-id="c78f5-125">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="c78f5-126">Em **Iniciar índice de usuário**, clique ou digite o índice do primeiro usuário a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="c78f5-126">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="c78f5-127">Você pode configurar intervalos diferentes para diferentes tipos ou níveis de carga, mas você deve executar UserProfileGenerator.exe uma vez pelo intervalo que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="c78f5-127">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="c78f5-128">Em **número de usuários**, clique ou digite o número total de usuários que você vai configurar.</span><span class="sxs-lookup"><span data-stu-id="c78f5-128">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="c78f5-129">Em **domínio do usuário**, digite o domínio usado para o URI do SIP.</span><span class="sxs-lookup"><span data-stu-id="c78f5-129">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="c78f5-130">Isso é usado para construir o URI SIP de cada usuário para fazer logon no servidor front-end do Lync Server 2013 ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c78f5-130">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="c78f5-131">Pode ser diferente do domínio da conta.</span><span class="sxs-lookup"><span data-stu-id="c78f5-131">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="c78f5-132">Em **domínio da conta**, digite o logon do domínio dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c78f5-132">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="c78f5-133">Insira o número máximo de pontos de extremidade simultâneos em **entrar por segundo (por instância)** para o qual você deseja que a ferramenta faça logon em todos os pontos de extremidade/usuários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-133">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="c78f5-134">A taxa recomendada é \< = 2 por segundo/SKU padrão Fe.</span><span class="sxs-lookup"><span data-stu-id="c78f5-134">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="c78f5-135">Em **proxy de acesso ou FQDN de pool**, digite o nome de domínio totalmente qualificado (FQDN) do servidor ao qual você deseja que os clientes se conectem.</span><span class="sxs-lookup"><span data-stu-id="c78f5-135">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="c78f5-136">Se os usuários estiverem fazendo logon externamente, especifique o proxy de acesso.</span><span class="sxs-lookup"><span data-stu-id="c78f5-136">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="c78f5-137">Se os usuários forem internos, especifique o FQDN do seu pool ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c78f5-137">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="c78f5-138">Em **porta**, clique ou digite a porta que você deseja que os usuários usem para SIP (o padrão é 5061).</span><span class="sxs-lookup"><span data-stu-id="c78f5-138">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="c78f5-139">Para configurações de servidor de rede externo, especifique o **proxy de acesso ou o FQDN do pool** e a **porta**.</span><span class="sxs-lookup"><span data-stu-id="c78f5-139">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="c78f5-140">Essas configurações são usadas apenas para simulação de carga de pontos de extremidade externos.</span><span class="sxs-lookup"><span data-stu-id="c78f5-140">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="c78f5-141">Cenários gerais</span><span class="sxs-lookup"><span data-stu-id="c78f5-141">General Scenarios</span></span>

<span data-ttu-id="c78f5-142">A guia **cenários gerais** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c78f5-142">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c78f5-143">Configure os níveis de carga e os parâmetros para cada um dos cenários gerais que você deseja executar ou deixe desabilitado.</span><span class="sxs-lookup"><span data-stu-id="c78f5-143">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="c78f5-144">![Guia cenários gerais.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Guia cenários gerais.")</span><span class="sxs-lookup"><span data-stu-id="c78f5-144">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="c78f5-145">Em **mensagens instantâneas**, que incluem ponto-a-ponto e conferência, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-145">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c78f5-146">Os valores de nível de carga para todos os campos (exceto serviços de informações de local) são <STRONG>desabilitados</STRONG>, <STRONG>baixo</STRONG>, <STRONG>médio</STRONG>, <STRONG>alto</STRONG>e <STRONG>personalizado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c78f5-146">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="c78f5-147">Quando baixo, médio, alto ou personalizado for selecionado, as configurações serão geradas para cada cliente e modalidade.</span><span class="sxs-lookup"><span data-stu-id="c78f5-147">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="c78f5-148">Alto fará com que a carga de máximo com suporte seja gerada para o servidor, média corresponde a 60% da carga e baixa corresponde a 30% da carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-148">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="c78f5-149">Na **audioconferência**, que é apenas a audioconferência, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-149">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c78f5-150">As chamadas ponto a ponto são abordadas na seção cenários de voz mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c78f5-150">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="c78f5-151">Para habilitar o MultiView, abra a guia **avançado** para essa modalidade.</span><span class="sxs-lookup"><span data-stu-id="c78f5-151">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="c78f5-152">Em **compartilhamento de aplicativos**, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-152">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="c78f5-153">Em **colaboração de dados**, que inclui a conferência de dados, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-153">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="c78f5-154">Em **expansão de lista de distribuição**, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-154">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c78f5-155">Você também deve clicar no botão **avançado** e preencher os campos com os mesmos valores que você configurou na guia lista de **distribuição** da ferramenta de criação de usuários do Lync Server (UserProvisioningTool.exe).</span><span class="sxs-lookup"><span data-stu-id="c78f5-155">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="c78f5-156">Para obter detalhes sobre esses campos, consulte [Create Users and contacts](create-users-and-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="c78f5-156">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="c78f5-157">Na **consulta à Web do catálogo de endereços**, que é o serviço de pesquisa de catálogo de endereços (não o download do arquivo do catálogo de endereços), especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-157">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c78f5-158">Para habilitar downloads do catálogo de endereços, clique no botão **avançado** correspondente e, em seguida, defina **EnableABSDownload** como true.</span><span class="sxs-lookup"><span data-stu-id="c78f5-158">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="c78f5-159">Em **serviço de grupo de resposta**, especifique o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-159">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="c78f5-160">Você também deve clicar no botão **avançado** correspondente e especificar os URIs dos grupos de resposta que você já criou ao provisionar os agentes de serviço do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="c78f5-160">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="c78f5-161">É necessário especificar pelo menos um grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="c78f5-161">You must specify at least one response group.</span></span> <span data-ttu-id="c78f5-162">Use pontos-e-vírgulas para separar vários grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="c78f5-162">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="c78f5-163">Atualize o RGSUriSuffixStartIndex e o RGSUriSuffixEndIndex para os valores reais.</span><span class="sxs-lookup"><span data-stu-id="c78f5-163">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="c78f5-164">Em **serviços de informações de local**, selecione o valor apropriado para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-164">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="c78f5-165">O nível de carga para o local Information Services deve ser **habilitado** ou **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="c78f5-165">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c78f5-166">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele e um conjunto de caixas de seleção que permitem variações dos cenários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-166">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="c78f5-167">O <STRONG>ad-hoc</STRONG> significa gerar simulação de conferências que serão criadas durante a hora.</span><span class="sxs-lookup"><span data-stu-id="c78f5-167"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="c78f5-168"><STRONG>Grande conf</STRONG> significa que o cenário de conferência grande será simulado.</span><span class="sxs-lookup"><span data-stu-id="c78f5-168"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="c78f5-169"><STRONG>External</STRONG> significa também simular usuários externos.</span><span class="sxs-lookup"><span data-stu-id="c78f5-169"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="c78f5-170">Esses botões e caixas de seleção permitem acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e tornará a personalização possível.</span><span class="sxs-lookup"><span data-stu-id="c78f5-170">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="c78f5-171">Para cada cenário na guia <STRONG>cenários gerais</STRONG> (exceto para serviços de informações de local), se o valor de nível de carga for <STRONG>personalizado</STRONG>, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo <STRONG>avançado</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c78f5-171">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="c78f5-172">O nome do campo difere, dependendo do cenário, mas a descrição do campo entrará em estado, "Observação: este número só será usado se personalizado for selecionado no menu suspenso."</span><span class="sxs-lookup"><span data-stu-id="c78f5-172">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="c78f5-173">Em geral, os valores <STRONG>alto</STRONG>, <STRONG>médio</STRONG>e <STRONG>baixo</STRONG> mudarão as taxas de conversa por modalidade em linha com o modelo de usuário que é um saldo de todos os cenários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-173">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="c78f5-174">Se houver necessidade de alterar o nível de carga por modalidade devido à diferença de uso esperado, recomendamos usar uma taxa de conversa <STRONG>personalizada</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c78f5-174">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="c78f5-175">Cenários de voz</span><span class="sxs-lookup"><span data-stu-id="c78f5-175">Voice Scenarios</span></span>

<span data-ttu-id="c78f5-176">A guia **cenários de voz** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c78f5-176">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c78f5-177">Use a guia **cenários de voz** para configurar todos os cenários relacionados à voz.</span><span class="sxs-lookup"><span data-stu-id="c78f5-177">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="c78f5-178">![Guia cenários de voz.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Guia cenários de voz.")</span><span class="sxs-lookup"><span data-stu-id="c78f5-178">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="c78f5-179">Em **VoIP**, clique no botão **avançado** e forneça valores para os campos **PhoneAreaCode** e **LocationProfile** (plano de discagem).</span><span class="sxs-lookup"><span data-stu-id="c78f5-179">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="c78f5-180">Você também deve especificar um valor para o **nível de carga**.</span><span class="sxs-lookup"><span data-stu-id="c78f5-180">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="c78f5-181">Se o nível de carga para **VoIP** e o **Gateway de UC/PSTN** estiver habilitado, será sempre gerado um arquivo de configuração de rede telefônica pública comutada (PSTN) para comunicação unificada (UC) que irá simular chamadas externas.</span><span class="sxs-lookup"><span data-stu-id="c78f5-181">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="c78f5-182">No **Gateway UC/PSTN**, especifique um valor para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-182">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="c78f5-183">Se você selecionar um nível de carga diferente de **desabilitado**, deverá fornecer um valor para o **código de área PSTN** clicando no botão **Adicionar** em servidor de mediação e PSTN.</span><span class="sxs-lookup"><span data-stu-id="c78f5-183">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="c78f5-184">Verifique se você tem uma rota configurada para esse código de área.</span><span class="sxs-lookup"><span data-stu-id="c78f5-184">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c78f5-185">Você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para verificar a configuração da rota de voz.</span><span class="sxs-lookup"><span data-stu-id="c78f5-185">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="c78f5-186">Em **atendedor de conferência**, especifique um valor para o nível de carga.</span><span class="sxs-lookup"><span data-stu-id="c78f5-186">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="c78f5-187">Selecionar um nível de carga (diferente de **desabilitado**) habilitará o campo **número de telefone** .</span><span class="sxs-lookup"><span data-stu-id="c78f5-187">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="c78f5-188">Insira o número de telefone do atendedor automático que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="c78f5-188">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="c78f5-189">Além disso, clique no botão **avançado** e, em seguida, especifique um valor para o campo **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="c78f5-189">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="c78f5-190">Em **serviço de estacionamento de chamada**, especifique o valor apropriado para o **nível de carga**.</span><span class="sxs-lookup"><span data-stu-id="c78f5-190">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="c78f5-191">No **servidor de mediação e PSTN**, para cada servidor de mediação que você deseja usar, você deve ter um simulador PSTN separado.</span><span class="sxs-lookup"><span data-stu-id="c78f5-191">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="c78f5-192">Depois de determinar qual cliente será usado como o simulador, você precisará configurar seu servidor de mediação para rotear chamadas para esse computador na porta de simulador PSTN que você configurou.</span><span class="sxs-lookup"><span data-stu-id="c78f5-192">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="c78f5-193">Clique em **Adicionar** para configurar o valor do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c78f5-193">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c78f5-194">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="c78f5-194">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="c78f5-195">Esses botões permitem o acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e habilitará a personalização.</span><span class="sxs-lookup"><span data-stu-id="c78f5-195">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="c78f5-196">Para cada cenário na guia <STRONG>cenários de voz</STRONG> , se o valor de <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo <STRONG>avançado</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c78f5-196">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="c78f5-197">O nome do campo difere, dependendo do cenário, mas a descrição do campo entrará em estado, "Observação: este número só será usado se personalizado for selecionado no menu suspenso."</span><span class="sxs-lookup"><span data-stu-id="c78f5-197">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="c78f5-198">Contactar</span><span class="sxs-lookup"><span data-stu-id="c78f5-198">Reach</span></span>

<span data-ttu-id="c78f5-199">Reach é uma nova experiência no Lync Server 2013 que oferece suporte a cenários de conferência por meio do servidor UCWA (Unified Communications Web API) instalado no servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="c78f5-199">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="c78f5-200">A guia **REACH** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c78f5-200">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c78f5-201">Use a guia **alcance** para configurar todos os cenários relacionados ao alcance.</span><span class="sxs-lookup"><span data-stu-id="c78f5-201">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="c78f5-202">![Guia alcance.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Guia alcance.")</span><span class="sxs-lookup"><span data-stu-id="c78f5-202">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="c78f5-203">Clique no botão **avançado** ao lado de **configurações de REACH gerais**.</span><span class="sxs-lookup"><span data-stu-id="c78f5-203">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="c78f5-204">Defina o campo **UcwaTargetServerUrl** como o VIP (IP virtual) do pool diretor ou o VIP do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c78f5-204">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="c78f5-205">Em **compartilhamento de aplicativos**, **colaboração de dados**e **im**, selecione o valor apropriado para o **nível de carga**.</span><span class="sxs-lookup"><span data-stu-id="c78f5-205">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c78f5-206">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="c78f5-206">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="c78f5-207">Esses botões permitem o acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e habilitará a personalização.</span><span class="sxs-lookup"><span data-stu-id="c78f5-207">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="c78f5-208">Para cada um dos cenários de alcance, se o <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, o valor especificado no campo <STRONG>ConversationsPerHour</STRONG> será usado em vez do padrão</span><span class="sxs-lookup"><span data-stu-id="c78f5-208">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="c78f5-209">Use a guia **mobilidade** para configurar todos os cenários relacionados à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="c78f5-209">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="c78f5-210">![Guia Mobility.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Guia Mobility.")</span><span class="sxs-lookup"><span data-stu-id="c78f5-210">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="c78f5-211">Clique no botão **avançado** ao lado de **mobilidade (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="c78f5-211">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="c78f5-212">Defina o campo **UcwaTargetServerUrl** como o VIP (IP virtual) do pool diretor ou o VIP do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c78f5-212">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="c78f5-213">Em **presença e \\ áudio de mensagens instantâneas P2P**, selecione o valor apropriado para o **nível de carga** para habilitar a simulação de cenário de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="c78f5-213">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c78f5-214">Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="c78f5-214">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="c78f5-215">Esses botões permitem o acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e habilitará a personalização.</span><span class="sxs-lookup"><span data-stu-id="c78f5-215">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="c78f5-216">Para cada um dos cenários de alcance, se o <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, o valor especificado no campo <STRONG>ConversationsPerHour</STRONG> será usado em vez do padrão.</span><span class="sxs-lookup"><span data-stu-id="c78f5-216">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="c78f5-217">Resumo</span><span class="sxs-lookup"><span data-stu-id="c78f5-217">Summary</span></span>

<span data-ttu-id="c78f5-218">A guia **Resumo** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c78f5-218">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="c78f5-219">![Guia Resumo.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Guia Resumo.")</span><span class="sxs-lookup"><span data-stu-id="c78f5-219">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="c78f5-220">A guia **Resumo** indica quais usuários usar para cada um dos cenários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-220">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="c78f5-221">É possível configurar manualmente intervalos de números de usuário, marcando a caixa de seleção **habilitar geração de intervalo de usuários personalizados** e clicando duas vezes no cenário na tabela que tem o **intervalo de usuários** que você deseja personalizar.</span><span class="sxs-lookup"><span data-stu-id="c78f5-221">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="c78f5-222">Verificar (RunClient.bat) adicionar atraso de entrada ao iniciar, para incluir atrasos nos arquivos de lote gerados para corresponder à taxa de entrada.</span><span class="sxs-lookup"><span data-stu-id="c78f5-222">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="c78f5-223">Isso é útil para evitar a sobrecarga do servidor ao entrar em um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="c78f5-223">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="c78f5-224">Clique em **gerar arquivos**e selecione a pasta onde você deseja gerar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c78f5-224">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="c78f5-225">Uma caixa de diálogo semelhante à figura a seguir será exibida quando os arquivos forem criados com êxito.</span><span class="sxs-lookup"><span data-stu-id="c78f5-225">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="c78f5-226">![Reconhecimento de que os arquivos foram criados.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Reconhecimento de que os arquivos foram criados.")</span><span class="sxs-lookup"><span data-stu-id="c78f5-226">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c78f5-227">Confira também</span><span class="sxs-lookup"><span data-stu-id="c78f5-227">See Also</span></span>


[<span data-ttu-id="c78f5-228">Criar usuários e contatos</span><span class="sxs-lookup"><span data-stu-id="c78f5-228">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
