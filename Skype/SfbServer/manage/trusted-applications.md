---
title: Gerenciar aplicativos confiáveis
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que confia Skype para Business Server.
ms.openlocfilehash: b4bad58d93ca231a9405734dd148cee675c5d1ea
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222888"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="30084-103">Gerenciar aplicativos confiáveis no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="30084-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="30084-104">Um *aplicativo confiável* é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que confia Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="30084-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="30084-105">Para obter detalhes sobre aplicativos UCMA, consulte "Unified Communications Managed API 3.0 Core documentação do SDK" em http://go.microsoft.com/fwlink/p/?linkId=210320.</span><span class="sxs-lookup"><span data-stu-id="30084-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="30084-106">Para publicar com êxito, habilitar ou desabilitar uma topologia quando a adição ou remoção de uma função de servidor, você deve estar conectado como um usuário que seja membro dos grupos RTCUniversalServerAdmins e administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="30084-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="30084-107">Use este artigo para saber como configurar um novo servidor de aplicativos confiáveis, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="30084-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="30084-108">Configurar um novo servidor de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="30084-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="30084-109">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="30084-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="30084-110">Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique **Skype para o construtor de topologia de servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="30084-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="30084-111">Selecione **Baixar topologia da implantação existente**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="30084-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="30084-112">Na caixa de diálogo **Salvar topologia como** , clique no arquivo do construtor de topologia que você deseja usar e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30084-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="30084-113">No painel esquerdo, clique com o botão **servidores de aplicativos confiáveis**e, em seguida, clique em **Novo Pool de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="30084-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="30084-114">Insira o **FQDN do Pool** do pool de aplicativos confiáveis, selecione se ele será um servidor único ou vários servidores e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="30084-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="30084-115">Na página **Selecionar o próximo salto** , na lista, selecione o Skype para pool de Front End do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="30084-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="30084-116">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="30084-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="30084-117">Selecione o nó superior **Skype para Business Server**e, em seguida, no menu **ações** , clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="30084-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="30084-118">O **Pool de aplicativos confiáveis** deve ter foi criado com êxito e associado ao pool de Front-End correto.</span><span class="sxs-lookup"><span data-stu-id="30084-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="30084-119">Exibir uma lista de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="30084-119">View a list of trusted applications</span></span>

<span data-ttu-id="30084-120">Você pode usar o Skype para painel de controle do Business Server para exibir uma lista dos aplicativos confiáveis que você tiver implantado na sua Skype para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="30084-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="30084-121">Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que confia Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="30084-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="30084-122">Essa relação de confiança está resumida na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="30084-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="30084-123">Aplicativos confiáveis não são desafiados para autenticação pelo Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="30084-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="30084-124">Aplicativos confiáveis não são acelerados pelo Skype para Business Server para transações SIP, conexões ou voz de saída chamadas de protocolo da Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="30084-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="30084-125">Aplicativos confiáveis podem representar qualquer usuário e participem de conferências sem aparecer em escalações.</span><span class="sxs-lookup"><span data-stu-id="30084-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="30084-126">Aplicativos confiáveis são altamente disponíveis e flexíveis.</span><span class="sxs-lookup"><span data-stu-id="30084-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="30084-127">No Skype para painel de controle do Business Server, você pode ver o nome dos aplicativos, o pool onde são executados e a porta que usam.</span><span class="sxs-lookup"><span data-stu-id="30084-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="30084-128">Para exibir uma lista de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="30084-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="30084-129">Usando uma conta de usuário atribuída à função do CsServerAdministrator, CsAdministrator, CsHelpDesk, ou CsViewOnlyAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="30084-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="30084-130">Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype para Business Server, consulte [o controle de acesso baseado em função (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="30084-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="30084-131">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="30084-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="30084-132">Na barra de navegação à esquerda, clique em **topologia**e, em seguida, clique em **Aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="30084-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="30084-133">Na página **Aplicativos confiáveis** , clique em um título de coluna para classificar os aplicativos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="30084-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="30084-134">Exibir informações de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="30084-134">View trusted application information</span></span>

<span data-ttu-id="30084-135">Você pode exibir informações sobre seus aplicativos confiáveis usando o Windows PowerShell e o cmdlet **Get-CsTrustedApplication** .</span><span class="sxs-lookup"><span data-stu-id="30084-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="30084-136">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30084-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="30084-137">Para ver aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="30084-137">To view trusted applications</span></span>

<span data-ttu-id="30084-138">Para exibir todos os aplicativos confiáveis, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="30084-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="30084-139">Esse comando retorna informações semelhantes às seguintes para cada aplicativo confiável:</span><span class="sxs-lookup"><span data-stu-id="30084-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="30084-140">Para obter detalhes, consulte [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="30084-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>