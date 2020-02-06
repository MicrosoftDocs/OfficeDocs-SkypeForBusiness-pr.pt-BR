---
title: Verificar a topologia no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumo: saiba como verificar se a topologia do Skype for Business Server e os servidores do Active Directory estão funcionando conforme esperado. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: aa631e5b08ff8cbe9cb6db17009f286dcc975679
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791709"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="7d6fa-104">Verificar a topologia no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7d6fa-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="7d6fa-105">**Resumo:** Saiba como verificar se a topologia do Skype for Business Server e os servidores do Active Directory estão funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="7d6fa-106">Baixe um teste grátis do Skype for Business Server no [centro de avaliação da Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="7d6fa-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="7d6fa-107">Após a publicação da topologia e dos componentes do sistema do Skype for Business Server instalados em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="7d6fa-108">Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory para que todo o domínio saiba que o Skype for Business está disponível no domínio.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="7d6fa-109">Você pode executar os passos 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="7d6fa-110">No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="7d6fa-111">A verificação da topologia é a etapa 8 de 8.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-111">Verifying the topology is step 8 of 8.</span></span>
  
![Diagrama de visão geral.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="7d6fa-113">Teste a implantação do pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="7d6fa-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="7d6fa-114">A etapa final é testar o pool de front-ends e confirmar se os clientes do Skype for Business podem se comunicar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="7d6fa-115">Adicione usuários e verifique a conectividade do cliente</span><span class="sxs-lookup"><span data-stu-id="7d6fa-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="7d6fa-116">Use computadores e usuários do Active Directory para adicionar o objeto de usuário do Active Directory da função Administrador para a implantação do Skype for Business Server (no qual o painel de controle do Skype for Business Server está instalado) no grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="7d6fa-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7d6fa-117">Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Skype for Business Server, que lê "não autorizado: o acesso é negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC) ."</span><span class="sxs-lookup"><span data-stu-id="7d6fa-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="7d6fa-118">Se o objeto do usuário está conectado atualmente, desconecte e conecte-se novamente para registrar a nova atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7d6fa-119">A conta de usuário não pode ser o administrador local de qualquer servidor que esteja executando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="7d6fa-120">Use a conta administrativa para fazer logon no computador em que o painel de controle do Skype for Business Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="7d6fa-121">Inicie o painel de controle do Skype for Business Server e forneça as credenciais, se for solicitado.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="7d6fa-122">O painel de controle do Skype for Business Server exibe informações de implantação.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="7d6fa-123">Na barra de navegação à esquerda, clique em **topologia**e, em seguida, confirme se o status do serviço mostra um computador com uma seta verde e se uma marca de seleção verde para o status de replicação está ao lado de cada função do servidor do Skype for Business que foi implantada e colocada online.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="7d6fa-124">Na barra de navegação esquerda, clique em **Usuários** e em **Habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="7d6fa-125">Na página **novo usuário do Skype for Business Server** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="7d6fa-p105">Para definir os parâmetros de pesquisa para os objetos que deseja localizar, na página **Selecionar do Active Directory**, você pode selecionar **Pesquisa** e, opcionalmente, clique em **Adicionar filtro**. Também é possível selecionar **Pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Após decidir suas opções de pesquisa, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="7d6fa-129">No painel de resultados da pesquisa, selecione os usuários que você quer adicionar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="7d6fa-130">Na página **novo usuário do Skype for Business Server** , os usuários selecionados estão na exibição **usuários** .</span><span class="sxs-lookup"><span data-stu-id="7d6fa-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="7d6fa-131">In the **Assign users to a pool** list, select the server where the users should reside.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="7d6fa-132">A seguinte lista inclui as opções que você pode usar para configurar os objetos.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="7d6fa-133">**Gerar URI SIP do usuário**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="7d6fa-134">**Telefonia**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-134">**Telephony**</span></span>
    
    - <span data-ttu-id="7d6fa-135">**URI de linha**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-135">**Line URI**</span></span>
    
    - <span data-ttu-id="7d6fa-136">**Política de conferência**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="7d6fa-137">**Política de versão do cliente**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="7d6fa-138">**Política de PIN**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="7d6fa-139">**Política de acesso externo**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-139">**External access policy**</span></span>
    
    - <span data-ttu-id="7d6fa-140">**Política de arquivamento**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="7d6fa-141">**Política local**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-141">**Location policy**</span></span>
    
    - <span data-ttu-id="7d6fa-142">**Política de cliente**</span><span class="sxs-lookup"><span data-stu-id="7d6fa-142">**Client policy**</span></span>
    
    <span data-ttu-id="7d6fa-143">Para testar a funcionalidade básica, selecione a opção que você prefere para a configuração **gerar URI SIP do usuário** (as outras opções na configuração usar configurações padrão) e, em seguida, clique em **habilitar**, conforme mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Habilitar usuários no painel de controle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="7d6fa-p107">Será exibida uma página de resumo mostrando uma marca de verificação na coluna **Habilitado** para indicar que os objetos agora estão configurados. A coluna **Endereço SIP** exibe o endereço necessário para a configuração de login do usuário.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Usuários adicionados ao painel de controle do Skype for Business Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="7d6fa-148">Faça o logon de um usuário em um computador que tenha ingressado no domínio e outro usuário em outro computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="7d6fa-149">Instale o Skype for Business cliente em cada um dos dois computadores cliente e verifique se os dois usuários podem entrar no Skype for Business Server e enviar mensagens de chat para os outros.</span><span class="sxs-lookup"><span data-stu-id="7d6fa-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

