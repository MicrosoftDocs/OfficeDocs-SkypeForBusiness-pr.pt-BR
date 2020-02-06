---
title: Gerenciar aplicativos confiáveis
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Um aplicativo confiável é um aplicativo baseado em SDK do Microsoft Unified Communications Managed (UCMA) 3,0 Core API que é confiável para o Skype for Business Server.
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817072"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="f95a3-103">Gerenciar aplicativos confiáveis no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f95a3-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="f95a3-104">Um *aplicativo confiável* é um aplicativo baseado em SDK do Microsoft Unified Communications Managed (UCMA) 3,0 Core API que é confiável para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f95a3-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="f95a3-105">Para obter detalhes sobre aplicativos do UCMA, consulte "documentação do SDK do 3,0 Core Communications http://go.microsoft.com/fwlink/p/?linkId=210320Managed API" em.</span><span class="sxs-lookup"><span data-stu-id="f95a3-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="f95a3-106">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio.</span><span class="sxs-lookup"><span data-stu-id="f95a3-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="f95a3-107">Use este artigo para saber como configurar um novo servidor de aplicativos confiável, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f95a3-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="f95a3-108">Configurar um novo servidor de aplicativos confiável</span><span class="sxs-lookup"><span data-stu-id="f95a3-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="f95a3-109">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f95a3-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f95a3-110">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server**e em **Construtor de topologias do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="f95a3-111">Selecione **baixar topologia da implantação existente**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="f95a3-112">Na caixa de diálogo **salvar topologia como** , clique no arquivo do construtor de topologias que você deseja usar e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="f95a3-113">No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis**e, em seguida, clique em **novo pool de aplicativos confiável**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="f95a3-114">Digite o **FQDN do pool** do pool de aplicativos confiáveis, selecione se ele será um único servidor ou vários servidores e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="f95a3-115">Na lista **selecionar o próximo salto** , selecione o pool de front-end do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f95a3-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="f95a3-116">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="f95a3-117">Selecione o nó superior **Skype for Business Server**e, em seguida, no menu **ações** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="f95a3-118">O **pool de aplicativos confiável** deve ter sido criado com êxito e associado ao pool de front-end correto.</span><span class="sxs-lookup"><span data-stu-id="f95a3-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="f95a3-119">Exibir uma lista de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="f95a3-119">View a list of trusted applications</span></span>

<span data-ttu-id="f95a3-120">Você pode usar o painel de controle do Skype for Business Server para exibir uma lista dos aplicativos confiáveis que você implantou em seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f95a3-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="f95a3-121">Um aplicativo confiável é um aplicativo baseado em SDK do Microsoft Unified Communications Managed (UCMA) 3,0 Core API que é confiável para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f95a3-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="f95a3-122">Essa relação de confiança é resumida na seguinte lista:</span><span class="sxs-lookup"><span data-stu-id="f95a3-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="f95a3-123">Aplicativos confiáveis não são desafiados para autenticação pelo Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f95a3-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="f95a3-124">Os aplicativos confiáveis não são restringidos pelo Skype for Business Server para transações de SIP, conexões ou chamadas de protocolo de voz por Internet (VoIP) de saída.</span><span class="sxs-lookup"><span data-stu-id="f95a3-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="f95a3-125">Aplicativos confiáveis podem representar qualquer usuário e podem participar de conferências sem que apareçam em escalas.</span><span class="sxs-lookup"><span data-stu-id="f95a3-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="f95a3-126">Aplicativos confiáveis são altamente disponíveis e resilientes.</span><span class="sxs-lookup"><span data-stu-id="f95a3-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="f95a3-127">No painel de controle do Skype for Business Server, você pode ver o nome dos aplicativos, o pool onde eles são executados e a porta que eles usam.</span><span class="sxs-lookup"><span data-stu-id="f95a3-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="f95a3-128">Para exibir uma lista de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="f95a3-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="f95a3-129">Usando uma conta de usuário atribuída à função do CsServerAdministrator, CsAdministrator, CsHelpDesk, ou CsViewOnlyAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f95a3-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="f95a3-130">Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype for Business Server, consulte [controle de acesso baseado em função (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="f95a3-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="f95a3-131">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f95a3-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="f95a3-132">Na barra de navegação à esquerda, clique em **topologia**e, em seguida, clique em **aplicativo confiável**.</span><span class="sxs-lookup"><span data-stu-id="f95a3-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="f95a3-133">Na página **aplicativo confiável** , clique em um título de coluna para classificar os aplicativos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="f95a3-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="f95a3-134">Exibir informações de aplicativo confiável</span><span class="sxs-lookup"><span data-stu-id="f95a3-134">View trusted application information</span></span>

<span data-ttu-id="f95a3-135">Você pode exibir informações sobre seus aplicativos confiáveis usando o Windows PowerShell e o cmdlet **Get-CsTrustedApplication** .</span><span class="sxs-lookup"><span data-stu-id="f95a3-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="f95a3-136">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f95a3-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="f95a3-137">Para exibir aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="f95a3-137">To view trusted applications</span></span>

<span data-ttu-id="f95a3-138">Para ver todos os seus aplicativos confiáveis, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="f95a3-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="f95a3-139">Esse comando retorna informações semelhantes às seguintes para cada aplicativo confiável:</span><span class="sxs-lookup"><span data-stu-id="f95a3-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="f95a3-140">Para obter detalhes, consulte [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="f95a3-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
