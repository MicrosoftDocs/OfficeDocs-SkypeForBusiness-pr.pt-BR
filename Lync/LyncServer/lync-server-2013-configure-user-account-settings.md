---
title: 'Lync Server 2013: definir configurações de conta de usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b3c8ea077b6dee724d131ea117aa7bf304e114
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="b5ac9-102">Definir configurações de conta de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5ac9-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5ac9-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b5ac9-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b5ac9-104">Os usuários de discagem digitam o número de telefone ou a extensão e um PIN para ingressar nas conferências como usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="b5ac9-105">O **URI de linha** de telefonia especificado nas contas de usuário do Lync Server é necessário para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="b5ac9-106">O procedimento neste tópico descreve como atribuir um **URI de Linha** para uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="b5ac9-107">Se você precisar atribuir um **URI da Linha** para várias contas de usuário, poderá criar um script que usa o cmdlet **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="b5ac9-108">Para obter detalhes sobre como usar um exemplo de script para atribuir **URI de linha** a várias contas de usuário, consulte "atribuir URIs de [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945)linha a vários usuários" em.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="b5ac9-109">Para configurar as definições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b5ac9-109">To configure user account settings</span></span>

1.  <span data-ttu-id="b5ac9-110">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-UserAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="b5ac9-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5ac9-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5ac9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5ac9-113">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b5ac9-114">No campo de pesquisa, digite o nome do usuário que você deseja configurar para conferência discada ou clique em **Adicionar filtro** para especificar os campos de pesquisa e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="b5ac9-115">Clique duas vezes no nome do usuário para abrir a caixa de diálogo **Editar usuário do Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="b5ac9-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="b5ac9-116">Em **Telefonia**, no campo **URI da Linha**, digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="b5ac9-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5ac9-117">Você pode especificar o <STRONG>URI da linha</STRONG> somente se a <STRONG>telefonia</STRONG> estiver definida <STRONG>como somente PC-PC</STRONG>, <STRONG>Enterprise Voice</STRONG>, controle de <STRONG>chamada remota</STRONG> ou <STRONG>controle de chamada remota</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="b5ac9-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b5ac9-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

