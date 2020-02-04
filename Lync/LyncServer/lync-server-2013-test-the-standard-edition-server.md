---
title: 'Lync Server 2013: Testar o servidor de Edição Padrão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00918643fcc59efc33d12dc3f8f77c7d3ac69815
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="63be0-102">Testar o servidor de Edição Padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63be0-102">Test the Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63be0-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="63be0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="63be0-104">O procedimento a seguir descreve como testar a implantação de um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="63be0-104">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="63be0-105">Para testar a implantação de um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="63be0-105">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="63be0-106">Use computadores e usuários do Active Directory para adicionar o objeto de usuário do Active Directory da função Administrador para a implantação do Lync Server 2013 (em que o painel de controle do Lync Server está instalado) ao grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="63be0-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="63be0-107">Se o objeto do usuário está conectado atualmente, desconecte e conecte-se novamente para registrar a nova atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="63be0-107">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63be0-108">A conta de usuário não pode ser o administrador local do servidor que executa o Lync Server 2013, Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="63be0-108">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="63be0-109">Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Lync Server 2013, que afirma que "não autorizado: o acesso é negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)."</span><span class="sxs-lookup"><span data-stu-id="63be0-109">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="63be0-110">Use a conta administrativa para fazer logon no computador em que o painel de controle do Lync Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="63be0-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="63be0-111">Inicie o painel de controle do Lync Server e forneça as credenciais, se for solicitado.</span><span class="sxs-lookup"><span data-stu-id="63be0-111">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="63be0-112">O painel de controle do Lync Server 2013 exibe informações de implantação.</span><span class="sxs-lookup"><span data-stu-id="63be0-112">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="63be0-113">Na barra de navegação à esquerda, clique em **topologia**e, em seguida, confirme se o status do serviço é um ícone de computador com uma seta verde e se há uma marca de seleção verde ao lado de cada função de servidor do Lync que foi implantada e colocada online.</span><span class="sxs-lookup"><span data-stu-id="63be0-113">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="63be0-114">Na barra de navegação à esquerda, clique em **usuários**e, em seguida, habilite os dois usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63be0-114">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="63be0-115">Registrar um usuário em um computador que ingressou no domínio e o outro usuário em outro computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="63be0-115">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="63be0-116">Instale o Lync Server 2013 em cada um dos dois computadores cliente e verifique se os dois usuários podem entrar no Lync Server 2013 e enviar mensagens de chat para os outros.</span><span class="sxs-lookup"><span data-stu-id="63be0-116">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63be0-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="63be0-117">See Also</span></span>


[<span data-ttu-id="63be0-118">Implantando clientes e dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63be0-118">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

