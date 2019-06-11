---
title: 'Lync Server 2013: Habilitar usuários do Lync para controle de chamada remotas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="62522-102">Habilitar usuários do Lync para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62522-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62522-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="62522-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="62522-104">Você pode configurar os usuários do Lync para controle de chamada remota usando políticas de provisionamento em banda com base em servidor.</span><span class="sxs-lookup"><span data-stu-id="62522-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="62522-105">Você pode gerenciar as configurações de provisionamento em banda usando o painel de controle do Lync Server ou a interface de linha de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62522-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="62522-106">Essas ferramentas substituem o snap-in de instrumentação de gerenciamento do Windows (WMI) que foi usado para gerenciar as configurações de política de grupo nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="62522-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="62522-107">Se preferir permitir que os usuários configurem suas próprias configurações de controle de chamada remota no Lync, você pode definir as configurações de controle de chamada remota para os usuários no servidor sem especificar o **URI do servidor de linhas** e os valores de **URI da linha** .</span><span class="sxs-lookup"><span data-stu-id="62522-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="62522-108">Certifique-se de que você comunique os valores apropriados de **URI** e de URI do **servidor de linha** para seus usuários e forneça aos usuários as instruções para definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="62522-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="62522-109">Para obter o procedimento para configurar manualmente o controle de chamada remota no Lync Server, consulte "definir opções e números <http://go.microsoft.com/fwlink/p/?linkid=210132> de telefones" na documentação do cliente do Lync no site do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="62522-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="62522-110">Se você tiver uma implantação existente do Communications Server 2007 R2 ou Communications Server 2007 implantação, os clientes do Communicator 2007 R2 e do Communicator 2007 continuarão a usar a política de grupo durante a migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="62522-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="62522-111">No entanto, se desejar que as configurações de política sejam transferidas para clientes do Lync, você precisará configurar as configurações equivalentes de provisionamento em banda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62522-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62522-112">Para habilitar um usuário para controle de chamada remota, você precisa fornecer ao usuário um URI de linha e um URI de servidor de linha.</span><span class="sxs-lookup"><span data-stu-id="62522-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="62522-113">Conforme descrito nas <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tarefas de implantação do controle de chamada remota no Lync Server 2013</A>, você precisa se certificar de usar a sintaxe exigida pelo gateway para essas configurações.</span><span class="sxs-lookup"><span data-stu-id="62522-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="62522-114">Certifique-se de que o domínio no URI do servidor de linha seja o mesmo que o domínio de destino que você especificou no parâmetro MatchUri quando configurou a rota estática para o gateway.</span><span class="sxs-lookup"><span data-stu-id="62522-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="62522-115">O URI da linha especifica o número de telefone atribuído ao usuário no formato E. 164, com o prefixo "TEL:" (por exemplo, Tel: + 14255550150).</span><span class="sxs-lookup"><span data-stu-id="62522-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="62522-116">Se você quiser configurar um número de ramal, o formato será Tel: + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="62522-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="62522-117">Se você configurou anteriormente o URI da linha do usuário e o valor não foi alterado, você não precisa especificar o URI da linha quando habilitar o usuário para o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="62522-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="62522-118">Para habilitar o controle de chamada remota para usuários habilitados para Lync usando o Shell de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="62522-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="62522-119">Faça logon em um computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou como uma função de controle de acesso baseado em função à qual você atribuiu o cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="62522-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="62522-120">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="62522-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="62522-121">Para usar o cmdlet **set-CsUser** para configurar o controle de chamada remota para um usuário existente compatível com o Lync, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="62522-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="62522-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="62522-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="62522-123">Para configurar usuários para o controle de chamada remota usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="62522-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="62522-124">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="62522-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62522-125">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62522-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="62522-126">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="62522-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="62522-127">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="62522-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="62522-128">Na caixa **Pesquisar usuários** , digite todos (ou a primeira parte) do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e, em seguida, clique em \*\* Localizar\*\*.</span><span class="sxs-lookup"><span data-stu-id="62522-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="62522-129">Na tabela, clique na conta de usuário que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="62522-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="62522-130">No menu **Editar** , clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="62522-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="62522-131">Em **telefonia**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="62522-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="62522-132">Para habilitar o controle de chamada remota para permitir que o usuário controle o telefone do seu PBX (Private Branch Exchange) do Lync 2013 para fazer chamadas de áudio PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**.</span><span class="sxs-lookup"><span data-stu-id="62522-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="62522-133">Em **URI de linha**, especifique o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="62522-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="62522-134">Em **URI do servidor de linha**, ESPECIFIQUE o URI SIP do gateway de SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="62522-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="62522-135">Para habilitar o controle de chamada remota, mas desabilitar as chamadas de áudio do PC para PC e permitir que somente o usuário controle o telefone PBX do Lync 2013 para fazer chamadas de PC para telefone, clique em **controle de chamada remota somente**.</span><span class="sxs-lookup"><span data-stu-id="62522-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="62522-136">Em **URI de linha**, especifique o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="62522-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="62522-137">Em **URI do servidor de linha**, ESPECIFIQUE o URI SIP do gateway de SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="62522-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="62522-138">Quando terminar, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="62522-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

