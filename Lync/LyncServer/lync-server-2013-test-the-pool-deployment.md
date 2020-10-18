---
title: 'Lync Server 2013: testar a implantação do pool'
description: 'Lync Server 2013: testar a implantação do pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576037"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="6d1d2-103">Testar a implantação do pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d1d2-103">Test the pool deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d1d2-104">_**Última modificação do tópico:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="6d1d2-104">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="6d1d2-105">O procedimento a seguir descreve como testar a implantação do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-105">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="6d1d2-106">Para testar a implantação do pool</span><span class="sxs-lookup"><span data-stu-id="6d1d2-106">To test the pool deployment</span></span>

1.  <span data-ttu-id="6d1d2-107">Use usuários e computadores do Active Directory para adicionar o objeto de usuário do Active Directory da função de administrador para a implantação do Lync Server 2013 (em que o painel de controle do Lync Server 2013 está instalado) no grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="6d1d2-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6d1d2-108">Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Lync Server, que afirma que "não autorizado: acesso negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)."</span><span class="sxs-lookup"><span data-stu-id="6d1d2-108">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="6d1d2-109">Se o objeto de usuário estiver conectado no momento, saia e faça logon novamente para registrar a nova atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-109">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d1d2-110">A conta de usuário não pode ser o administrador local de qualquer servidor executando o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-110">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="6d1d2-111">Use a conta administrativa para fazer logon no computador onde o painel de controle do Lync Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="6d1d2-112">Inicie o painel de controle do Lync Server e forneça as credenciais, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-112">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="6d1d2-113">O painel de controle do Lync Server exibe informações de implantação.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-113">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="6d1d2-114">Na barra de navegação esquerda, clique em **topologia**e confirme que o status do serviço mostra um computador com uma seta verde e que uma marca de seleção verde para status de replicação é próxima a cada função de servidor do Lync Server que foi implantada e colocada online.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-114">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="6d1d2-115">Na barra de navegação esquerda, clique em **usuários**e em **habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-115">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="6d1d2-116">Na página **novo usuário do Lync Server** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-116">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="6d1d2-117">Para definir parâmetros de pesquisa para os objetos que você deseja localizar, na página **selecionar a partir do Active Directory** , você pode selecionar **pesquisa**e, opcionalmente, clicar em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-117">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="6d1d2-118">Você também pode selecionar a **pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-118">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="6d1d2-119">Depois de decidir sobre suas opções de pesquisa, **encontre Find**.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-119">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="6d1d2-120">No painel de resultados da pesquisa, selecione todos os objetos para esta sessão de pesquisa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-120">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="6d1d2-121">Na página **novo usuário do Lync Server** , o objeto ou objetos que você selecionou estão na exibição **dos usuários** .</span><span class="sxs-lookup"><span data-stu-id="6d1d2-121">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="6d1d2-122">Na lista **atribuir usuários a um pool** , selecione o servidor no qual os objetos devem estar hospedados.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-122">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="6d1d2-123">A seguir, há várias opções para configurar os objetos.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-123">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="6d1d2-124">**Gerar URI SIP do usuário**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-124">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="6d1d2-125">**Telefonia**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-125">**Telephony**</span></span>
    
      - <span data-ttu-id="6d1d2-126">**URI da linha**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-126">**Line URI**</span></span>
    
      - <span data-ttu-id="6d1d2-127">**Política de conferência**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-127">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="6d1d2-128">**Política de versão do cliente**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-128">**Client version policy**</span></span>
    
      - <span data-ttu-id="6d1d2-129">**Política de PIN**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-129">**PIN policy**</span></span>
    
      - <span data-ttu-id="6d1d2-130">**Política de acesso externo**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-130">**External access policy**</span></span>
    
      - <span data-ttu-id="6d1d2-131">**Política de arquivamento**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-131">**Archiving policy**</span></span>
    
      - <span data-ttu-id="6d1d2-132">**Política de local**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-132">**Location policy**</span></span>
    
      - <span data-ttu-id="6d1d2-133">**Política de cliente**</span><span class="sxs-lookup"><span data-stu-id="6d1d2-133">**Client policy**</span></span>
    
    <span data-ttu-id="6d1d2-134">Para fins de teste da funcionalidade básica, selecione a opção que você preferir para a configuração **gerar URI do SIP do usuário** (as outras opções na configuração usarão as configurações padrão) e clique em **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-134">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="6d1d2-135">É exibida uma página de resumo que mostra uma marca de seleção na coluna **habilitado** para indicar que os objetos agora estão prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-135">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="6d1d2-136">A coluna **endereço SIP** exibe o endereço que você precisa para a configuração de entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-136">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="6d1d2-137">Faça o logon de um usuário em um computador que tenha ingressado no domínio e outro usuário em outro computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-137">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="6d1d2-138">Instale o Lync 2013 em cada um dos dois computadores cliente e verifique se ambos os usuários podem entrar no Lync Server 2013 e enviar mensagens instantâneas entre si.</span><span class="sxs-lookup"><span data-stu-id="6d1d2-138">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d1d2-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d1d2-139">See Also</span></span>


[<span data-ttu-id="6d1d2-140">Implantando clientes e dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d1d2-140">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

