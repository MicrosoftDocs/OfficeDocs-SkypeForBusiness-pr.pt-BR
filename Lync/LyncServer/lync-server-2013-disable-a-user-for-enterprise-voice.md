---
title: 'Lync Server 2013: desabilitar um usuário para o Enterprise Voice'
description: 'Lync Server 2013: desabilitar um usuário para o Enterprise Voice.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d99916444e2b1c984e251f6e6289d88e31a538a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568207"
---
# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4d626-103">Desabilitar um usuário para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d626-103">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d626-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4d626-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4d626-105">Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário habilitada para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d626-105">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="4d626-106">Para desabilitar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="4d626-106">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="4d626-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="4d626-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d626-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d626-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d626-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d626-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d626-110">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="4d626-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="4d626-111">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="4d626-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="4d626-112">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4d626-112">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="4d626-113">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="4d626-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="4d626-114">Na página **Editar usuário do servidor Lync**, sob **Telefonia**, clique em qualquer opção exceto **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="4d626-114">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d626-115">Para impedir que um usuário faça chamadas de áudio ou vídeo usando o Lync, em <STRONG>telefonia</STRONG>, clique em <STRONG>áudio/vídeo desabilitado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4d626-115">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="4d626-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4d626-116">Click **Commit**.</span></span>

<span data-ttu-id="4d626-117">O usuário agora não pode usar o recurso Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4d626-117">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d626-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d626-118">See Also</span></span>


[<span data-ttu-id="4d626-119">Habilitar usuários para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d626-119">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="4d626-120">Gerenciando o Enterprise Voice para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d626-120">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="4d626-121">Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d626-121">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

