---
title: 'Lync Server 2013: Testar a implantação de pool'
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
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="b3f16-102">Testar a implantação de pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3f16-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3f16-103">_**Tópico da última modificação:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="b3f16-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="b3f16-104">O procedimento a seguir descreve como testar a implantação do pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="b3f16-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="b3f16-105">Para testar a implantação do pool</span><span class="sxs-lookup"><span data-stu-id="b3f16-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="b3f16-106">Use computadores e usuários do Active Directory para adicionar o objeto de usuário do Active Directory da função Administrador para a implantação do Lync Server 2013 (em que o painel de controle do Lync Server 2013 está instalado) no grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="b3f16-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3f16-107">Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Lync Server, que afirma que "não autorizado: o acesso é negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)."</span><span class="sxs-lookup"><span data-stu-id="b3f16-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="b3f16-108">Se o objeto do usuário está conectado atualmente, desconecte e conecte-se novamente para registrar a nova atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="b3f16-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3f16-109">A conta de usuário não pode ser o administrador local de qualquer servidor que esteja executando o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3f16-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="b3f16-110">Use a conta administrativa para fazer logon no computador em que o painel de controle do Lync Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="b3f16-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="b3f16-111">Inicie o painel de controle do Lync Server e forneça as credenciais, se for solicitado.</span><span class="sxs-lookup"><span data-stu-id="b3f16-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="b3f16-112">O painel de controle do Lync Server exibe informações de implantação.</span><span class="sxs-lookup"><span data-stu-id="b3f16-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="b3f16-113">Na barra de navegação à esquerda, clique em **topologia**e, em seguida, confirme se o status do serviço mostra um computador com uma seta verde e se uma marca de seleção verde para o status de replicação está ao lado de cada função de servidor do Lync que foi implantada e colocada online.</span><span class="sxs-lookup"><span data-stu-id="b3f16-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="b3f16-114">Na barra de navegação esquerda, clique em **Usuários** e em **Habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="b3f16-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="b3f16-115">Na página **novo usuário do Lync Server** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b3f16-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="b3f16-116">Para definir os parâmetros de pesquisa para os objetos que deseja localizar, na página **Selecionar do Active Directory**, você pode selecionar **Pesquisa** e, opcionalmente, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="b3f16-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="b3f16-117">Também é possível selecionar **Pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados.</span><span class="sxs-lookup"><span data-stu-id="b3f16-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="b3f16-118">Depois de decidir nas opções de pesquisa, **Localize**o o.</span><span class="sxs-lookup"><span data-stu-id="b3f16-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="b3f16-119">No painel resultados da pesquisa, selecione todos os objetos para esta sessão de pesquisa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3f16-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="b3f16-120">Na página **novo usuário do Lync Server** , o objeto ou os objetos selecionados estão na exibição **usuários** .</span><span class="sxs-lookup"><span data-stu-id="b3f16-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="b3f16-121">Na lista **atribuir usuários a um pool** , selecione o servidor em que os objetos devem ser hospedados.</span><span class="sxs-lookup"><span data-stu-id="b3f16-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="b3f16-122">Veja a seguir várias opções para configurar os objetos.</span><span class="sxs-lookup"><span data-stu-id="b3f16-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="b3f16-123">**Gerar o URI SIP do usuário**</span><span class="sxs-lookup"><span data-stu-id="b3f16-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="b3f16-124">**Telefonia**</span><span class="sxs-lookup"><span data-stu-id="b3f16-124">**Telephony**</span></span>
    
      - <span data-ttu-id="b3f16-125">**URI de linha**</span><span class="sxs-lookup"><span data-stu-id="b3f16-125">**Line URI**</span></span>
    
      - <span data-ttu-id="b3f16-126">**Política de conferência**</span><span class="sxs-lookup"><span data-stu-id="b3f16-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="b3f16-127">**Política de versão do cliente**</span><span class="sxs-lookup"><span data-stu-id="b3f16-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="b3f16-128">**Política de PIN**</span><span class="sxs-lookup"><span data-stu-id="b3f16-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="b3f16-129">**Política de acesso externo**</span><span class="sxs-lookup"><span data-stu-id="b3f16-129">**External access policy**</span></span>
    
      - <span data-ttu-id="b3f16-130">**Política de arquivamento**</span><span class="sxs-lookup"><span data-stu-id="b3f16-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="b3f16-131">**Política local**</span><span class="sxs-lookup"><span data-stu-id="b3f16-131">**Location policy**</span></span>
    
      - <span data-ttu-id="b3f16-132">**Política de cliente**</span><span class="sxs-lookup"><span data-stu-id="b3f16-132">**Client policy**</span></span>
    
    <span data-ttu-id="b3f16-133">Para fins de teste da funcionalidade básica, selecione a opção que você prefere para a configuração **gerar URI SIP do usuário** (as outras opções na configuração usarão as configurações padrão) e clique em **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="b3f16-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="b3f16-134">Será exibida uma página de resumo que mostra uma marca de seleção na coluna **habilitado** para indicar que os objetos estão agora prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="b3f16-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="b3f16-135">A coluna **Endereço SIP** exibe o endereço necessário para a configuração de login do usuário.</span><span class="sxs-lookup"><span data-stu-id="b3f16-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="b3f16-136">Registrar um usuário em um computador que ingressou no domínio e outro usuário em outro computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="b3f16-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="b3f16-137">Instale o Lync 2013 em cada um dos dois computadores cliente e verifique se os dois usuários podem entrar no Lync Server 2013 e enviar mensagens de chat para os outros.</span><span class="sxs-lookup"><span data-stu-id="b3f16-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3f16-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="b3f16-138">See Also</span></span>


[<span data-ttu-id="b3f16-139">Implantando clientes e dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3f16-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

