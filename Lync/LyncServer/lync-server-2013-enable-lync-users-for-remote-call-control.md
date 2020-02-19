---
title: 'Lync Server 2013: habilitar usuários do Lync para controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e165efe4e9b679c5464a35aac1c4130840b801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="5a3b1-102">Habilitar usuários do Lync para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a3b1-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a3b1-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5a3b1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5a3b1-104">Você pode configurar os usuários do Lync para controle de chamada remota usando as políticas de provisionamento em banda que são baseadas em servidor.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="5a3b1-105">Você pode gerenciar as configurações de provisionamento em banda usando o painel de controle do Lync Server ou a interface de linha de comando do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="5a3b1-106">Essas ferramentas substituem o snap-in WMI (Instrumentação de gerenciamento do Windows) usado para gerenciar as configurações de política de grupo em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="5a3b1-107">Se preferir permitir que os usuários definam suas próprias configurações de controle de chamada remota no Lync, você pode definir as configurações de controle de chamada remota para usuários no servidor sem especificar o **URI do servidor de linha** e os valores de **URI da linha** .</span><span class="sxs-lookup"><span data-stu-id="5a3b1-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="5a3b1-108">Certifique-se de comunicar o **URI do servidor de linha** apropriado e os valores de URI da **linha** para seus usuários e forneça as instruções para definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="5a3b1-109">Para o procedimento para configurar manualmente o controle de chamada remota no Lync Server, consulte "configurar opções e números de <https://go.microsoft.com/fwlink/p/?linkid=210132> telefones" na documentação do cliente do Lync no site do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <https://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="5a3b1-110">Se você tiver uma implantação existente do Communications Server 2007 R2 ou Communications Server 2007, os clientes do Communicator 2007 R2 e do Communicator 2007 continuarão a usar a política de grupo durante a migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="5a3b1-111">No entanto, se você quiser que as configurações de política sejam transportadas para os clientes Lync, será necessário configurar as definições equivalentes de provisionamento em banda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a3b1-112">Para habilitar um usuário para controle de chamada remota, você precisa fornecer ao usuário um URI de linha e um URI de servidor de linha.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="5a3b1-113">Conforme descrito nas <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tarefas de implantação do controle de chamada remota no Lync Server 2013</A>, você precisará se certificar de usar a sintaxe exigida pelo gateway para essas configurações.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="5a3b1-114">Certifique-se de que o domínio no URI do servidor de linha é o mesmo que o domínio de destino especificado no parâmetro MatchUri quando você configurou a rota estática para o gateway.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="5a3b1-115">O URI da linha especifica o número de telefone atribuído ao usuário no formato E. 164, com o prefixo "TEL:" (por exemplo, Tel: + 14255550150).</span><span class="sxs-lookup"><span data-stu-id="5a3b1-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="5a3b1-116">Se você deseja configurar um número de extensão, o formato é tel:+14255550150;ext=111.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="5a3b1-117">Se você configurou anteriormente o URI de linha do usuário e o valor não foi alterado, não é necessário especificar o URI de linha ao habilitar o usuário para controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="5a3b1-118">Para habilitar o controle de chamada remota para usuários habilitados em Lync utilizando o Shell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="5a3b1-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="5a3b1-119">Faça logon em um computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou como uma função de controle de acesso baseado em função à qual você atribuiu o cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="5a3b1-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="5a3b1-120">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a3b1-121">Para usar o cmdlet **Set-CsUser** para configurar o controle de chamada remota para um usuário habilitado em Lync existente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5a3b1-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="5a3b1-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5a3b1-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="5a3b1-123">Para configurar os usuários para o controle de chamada remota usando o Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="5a3b1-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5a3b1-124">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5a3b1-125">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5a3b1-126">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5a3b1-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5a3b1-127">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="5a3b1-128">Na caixa **Pesquisar usuários** , digite todos (ou a primeira parte) do nome de exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI de linha da conta de usuário que você deseja e clique em localizar (em inglês), e em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="5a3b1-129">Na tabela, clique na conta de usuário que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="5a3b1-130">No menu **Editar**, clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="5a3b1-131">Em **Telefonia**, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="5a3b1-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="5a3b1-132">Para habilitar o controle de chamada remota para permitir que o usuário controle seu telefone de PBX (Private Branch Exchange) do Lync 2013 para fazer chamadas de áudio de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="5a3b1-133">Em **URI de linha**, especifique o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="5a3b1-134">Em **URI do servidor de linha**, especifique o URI SIP do gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="5a3b1-135">Para habilitar o controle de chamada remota, mas desabilitar as chamadas de áudio do PC para PC e permitir que apenas o usuário controle seu telefone PBX do Lync 2013 para fazer chamadas de PC para telefone, clique em **controle de chamada remota somente**.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="5a3b1-136">Em **URI de linha**, especifique o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="5a3b1-137">Em **URI do servidor de linha**, especifique o URI SIP do gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="5a3b1-138">Ao concluir, clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

