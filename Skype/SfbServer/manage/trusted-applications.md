---
title: Gerenciar aplicativos confiáveis
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server.
ms.openlocfilehash: b99b1c989437e6f474a97463fc53d4179858346e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103157"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="90c6d-103">Gerenciar aplicativos confiáveis no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="90c6d-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="90c6d-104">Um *aplicativo confiável* é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c6d-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="90c6d-105">Para obter detalhes sobre aplicativos UCMA, consulte "Unified Communications Managed API 3.0 Core SDK Documentation" em https://go.microsoft.com/fwlink/p/?linkId=210320 .</span><span class="sxs-lookup"><span data-stu-id="90c6d-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="90c6d-106">Para publicar, habilitar ou desabilitar com êxito uma topologia ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="90c6d-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="90c6d-107">Use este artigo para saber como configurar um novo servidor de aplicativos confiáveis, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="90c6d-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="90c6d-108">Configurar um novo servidor de aplicativo confiável</span><span class="sxs-lookup"><span data-stu-id="90c6d-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="90c6d-109">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="90c6d-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="90c6d-110">Iniciar Construtor de Topologias: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business Server** e em Construtor de Topologias do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="90c6d-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="90c6d-111">Selecione **Baixar topologia da implantação existente** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="90c6d-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="90c6d-112">Na caixa **de diálogo Salvar Topologia Como,** clique no arquivo Construtor de Topologias que você deseja usar e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="90c6d-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="90c6d-113">No painel esquerdo, clique com o botão direito do mouse em **Servidores de aplicativos confiáveis** e clique em **Novo Pool de Aplicativos Confiáveis.**</span><span class="sxs-lookup"><span data-stu-id="90c6d-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="90c6d-114">Insira o **FQDN do Pool** do pool de aplicativos confiável, selecione se será um servidor único ou vários servidores e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="90c6d-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="90c6d-115">Na página **Selecionar o próximo salto,** na lista, selecione o pool de Front-End do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c6d-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="90c6d-116">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="90c6d-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="90c6d-117">Selecione o nó superior **Skype for Business Server** e, no menu **Ações,** clique em **Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="90c6d-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="90c6d-118">O **Pool de Aplicativos Confiáveis** deve ter sido criado com êxito e associado ao pool de Front-End correto.</span><span class="sxs-lookup"><span data-stu-id="90c6d-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="90c6d-119">Exibir uma lista de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="90c6d-119">View a list of trusted applications</span></span>

<span data-ttu-id="90c6d-120">Você pode usar o Painel de Controle do Skype for Business Server para exibir uma lista dos aplicativos confiáveis que você implantou em seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c6d-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="90c6d-121">Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c6d-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="90c6d-122">Essa relação de confiança é resumida na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="90c6d-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="90c6d-123">Aplicativos confiáveis não são desafiados para autenticação pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c6d-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="90c6d-124">Os aplicativos confiáveis não são aceleradas pelo Skype for Business Server para transações SIP, conexões ou chamadas voIP (Voice over Internet Protocol) de saída.</span><span class="sxs-lookup"><span data-stu-id="90c6d-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="90c6d-125">Aplicativos confiáveis podem representar qualquer usuário e participar de conferências sem aparecer em lista.</span><span class="sxs-lookup"><span data-stu-id="90c6d-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="90c6d-126">Os aplicativos confiáveis são altamente disponíveis e resilientes.</span><span class="sxs-lookup"><span data-stu-id="90c6d-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="90c6d-127">No Painel de Controle do Skype for Business Server, você pode ver o nome dos aplicativos, o pool onde eles são executados e a porta que eles usam.</span><span class="sxs-lookup"><span data-stu-id="90c6d-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="90c6d-128">Para exibir uma lista de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="90c6d-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="90c6d-129">Em uma conta de usuário atribuída à função CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="90c6d-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="90c6d-130">Para obter detalhes sobre as funções administrativas predefinida disponíveis no Skype for Business Server, consulte Controle de acesso baseado em função [(RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="90c6d-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="90c6d-131">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c6d-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="90c6d-132">Na barra de navegação esquerda, clique em **Topologia** e clique em **Aplicativo Confiável.**</span><span class="sxs-lookup"><span data-stu-id="90c6d-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="90c6d-133">Na página **Aplicativo Confiável,** clique em um título de coluna para classificar os aplicativos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="90c6d-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="90c6d-134">Exibir informações de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="90c6d-134">View trusted application information</span></span>

<span data-ttu-id="90c6d-135">Você pode exibir informações sobre seus aplicativos confiáveis usando Windows PowerShell e o cmdlet **Get-CsTrustedApplication.**</span><span class="sxs-lookup"><span data-stu-id="90c6d-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="90c6d-136">Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90c6d-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="90c6d-137">Para ver aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="90c6d-137">To view trusted applications</span></span>

<span data-ttu-id="90c6d-138">Para exibir todos os seus aplicativos confiáveis, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="90c6d-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="90c6d-139">Esse comando retorna informações semelhantes às seguintes para cada aplicativo confiável:</span><span class="sxs-lookup"><span data-stu-id="90c6d-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="90c6d-140">Para detalhes, consulte [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="90c6d-140">For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span></span>