---
title: 'Lync Server 2013: desabilitar um usuário para Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dabe378f07cbca263ba3b32257c310b01bd922c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d90af-102">Desabilitar um usuário para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d90af-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d90af-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d90af-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d90af-104">Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário habilitada para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d90af-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="d90af-105">Para desabilitar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="d90af-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="d90af-106">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d90af-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d90af-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d90af-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d90af-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d90af-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d90af-109">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d90af-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d90af-110">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="d90af-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="d90af-111">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d90af-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="d90af-112">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d90af-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="d90af-113">Na página **Editar usuário do Lync Server** , em **telefonia**, clique em qualquer opção exceto **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="d90af-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d90af-114">Para impedir que um usuário faça chamadas de áudio ou vídeo usando o Lync, em <STRONG>telefonia</STRONG>, clique em <STRONG>áudio/vídeo desabilitado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d90af-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="d90af-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d90af-115">Click **Commit**.</span></span>

<span data-ttu-id="d90af-116">O usuário agora não pode usar o recurso Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d90af-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d90af-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="d90af-117">See Also</span></span>


[<span data-ttu-id="d90af-118">Habilitar usuários para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d90af-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="d90af-119">Gerenciando o Enterprise Voice para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d90af-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="d90af-120">Shell de Gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d90af-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

