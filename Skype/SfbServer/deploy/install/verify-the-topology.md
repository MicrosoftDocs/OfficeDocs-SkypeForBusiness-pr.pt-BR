---
title: Verificar a topologia no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumo: Saiba como verificar o Skype para a topologia de servidor de negócios e os servidores do Active Directory estão funcionando conforme o esperado. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: fc0e3a4b76ab25a8b99a3c7d48d0527fc2a1f5ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891779"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="45137-104">Verificar a topologia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="45137-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="45137-105">**Resumo:** Saiba como verificar o Skype para a topologia de servidor de negócios e os servidores do Active Directory estão funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="45137-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="45137-106">Baixe uma versão de avaliação gratuita do Skype para Business Server a partir do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="45137-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="45137-107">Depois que a topologia publicada e o Skype para componentes do sistema Business Server instalado em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="45137-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="45137-108">Isso inclui a opção confirmar que a configuração tenha propagadas check-out para todos os servidores do Active Directory para que o domínio inteiro reconheça que Skype para a empresa está disponível no domínio.</span><span class="sxs-lookup"><span data-stu-id="45137-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="45137-109">Você pode executar os passos 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="45137-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="45137-110">No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="45137-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="45137-111">A verificação da topologia é a etapa 8 de 8.</span><span class="sxs-lookup"><span data-stu-id="45137-111">Verifying the topology is step 8 of 8.</span></span>
  
![Diagrama de visão geral.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="45137-113">Teste a implantação do pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="45137-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="45137-114">A etapa final é testar o pool de Front-End e confirme que o Skype para clientes corporativos pode se comunicar entre si.</span><span class="sxs-lookup"><span data-stu-id="45137-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="45137-115">Adicione usuários e verifique a conectividade do cliente</span><span class="sxs-lookup"><span data-stu-id="45137-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="45137-116">Use usuários e computadores do Active Directory para adicionar o objeto de usuário do Active Directory da função de administrador para o Skype para implantação de servidor de negócios (no qual Skype para painel de controle do Business Server está instalado) para o grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="45137-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="45137-117">Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, você receberá um erro quando você abre o Skype para painel de controle do servidor de negócios que lê, "não autorizado: acesso negado devido a uma falha de autorização do acesso baseado em função RBAC (controle) ."</span><span class="sxs-lookup"><span data-stu-id="45137-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="45137-118">Se o objeto do usuário está conectado atualmente, desconecte e conecte-se novamente para registrar a nova atribuição de grupo.</span><span class="sxs-lookup"><span data-stu-id="45137-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45137-119">A conta de usuário não pode ser o administrador local de qualquer servidor executando o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="45137-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="45137-120">Use a conta administrativa para fazer logon no computador onde o Skype para painel de controle do Business Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="45137-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="45137-121">Inicie o Skype para painel de controle do servidor de negócios e forneça as credenciais, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="45137-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="45137-122">Skype para painel de controle do Business Server exibe informações sobre a implantação.</span><span class="sxs-lookup"><span data-stu-id="45137-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="45137-123">Na barra de navegação à esquerda, clique em **topologia**e, em seguida, confirme se o status do serviço mostra um computador com uma seta verde e que uma marca de seleção verde para obter o status de replicação está localizado ao lado de cada Skype para a função de servidor de negócios que tenha sido implantada e colocada on-line.</span><span class="sxs-lookup"><span data-stu-id="45137-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="45137-124">Na barra de navegação esquerda, clique em **Usuários** e em **Habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="45137-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="45137-125">Na página **Novo Skype para usuário de servidor de negócios** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="45137-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="45137-p105">Para definir os parâmetros de pesquisa para os objetos que deseja localizar, na página **Selecionar do Active Directory**, você pode selecionar **Pesquisa** e, opcionalmente, clique em **Adicionar filtro**. Também é possível selecionar **Pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Após decidir suas opções de pesquisa, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="45137-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="45137-129">No painel de resultados da pesquisa, selecione os usuários que você quer adicionar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="45137-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="45137-130">Na página **Novo Skype para usuário de servidor de negócios** , os usuários que você selecionou estão na exibição de **usuários** .</span><span class="sxs-lookup"><span data-stu-id="45137-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="45137-131">In the **Assign users to a pool** list, select the server where the users should reside.</span><span class="sxs-lookup"><span data-stu-id="45137-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="45137-132">A seguinte lista inclui as opções que você pode usar para configurar os objetos.</span><span class="sxs-lookup"><span data-stu-id="45137-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="45137-133">**Gerar o URI do SIP do usuário**</span><span class="sxs-lookup"><span data-stu-id="45137-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="45137-134">**Telefonia**</span><span class="sxs-lookup"><span data-stu-id="45137-134">**Telephony**</span></span>
    
    - <span data-ttu-id="45137-135">**URI de linha**</span><span class="sxs-lookup"><span data-stu-id="45137-135">**Line URI**</span></span>
    
    - <span data-ttu-id="45137-136">**Política de conferência**</span><span class="sxs-lookup"><span data-stu-id="45137-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="45137-137">**Política de versão do cliente**</span><span class="sxs-lookup"><span data-stu-id="45137-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="45137-138">**Política de PIN**</span><span class="sxs-lookup"><span data-stu-id="45137-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="45137-139">**Política de acesso externo**</span><span class="sxs-lookup"><span data-stu-id="45137-139">**External access policy**</span></span>
    
    - <span data-ttu-id="45137-140">**Política de arquivamento**</span><span class="sxs-lookup"><span data-stu-id="45137-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="45137-141">**Política local**</span><span class="sxs-lookup"><span data-stu-id="45137-141">**Location policy**</span></span>
    
    - <span data-ttu-id="45137-142">**Política de cliente**</span><span class="sxs-lookup"><span data-stu-id="45137-142">**Client policy**</span></span>
    
    <span data-ttu-id="45137-143">Para testar a funcionalidade básica, selecione a opção que você prefere para que a configuração **URI SIP do usuário Generate** (as outras opções nas configurações padrão de uso de configuração) e clique em **Habilitar**, conforme mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="45137-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Permitir que os usuários no painel de controle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="45137-p107">Será exibida uma página de resumo mostrando uma marca de verificação na coluna **Habilitado** para indicar que os objetos agora estão configurados. A coluna **Endereço SIP** exibe o endereço necessário para a configuração de login do usuário.</span><span class="sxs-lookup"><span data-stu-id="45137-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Usuários adicionados à Skype para painel de controle do servidor de negócios.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="45137-148">Faça o logon de um usuário em um computador que tenha ingressado no domínio e outro usuário em outro computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="45137-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="45137-149">Instale o Skype para o cliente de negócios em cada um dos dois computadores cliente e, em seguida, verifique se ambos os usuários podem se conectar ao Skype para Business Server e podem enviar mensagens instantâneas entre si.</span><span class="sxs-lookup"><span data-stu-id="45137-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

