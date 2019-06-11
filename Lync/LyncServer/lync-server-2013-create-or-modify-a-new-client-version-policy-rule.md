---
title: 'Lync Server 2013: criar ou modificar uma nova regra de política de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="f007a-102">Criar ou modificar uma nova regra de política de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f007a-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f007a-103">_**Tópico da última modificação:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="f007a-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="f007a-104">As regras de política de versão do cliente definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes e versões específicas do cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="f007a-105">Você pode criar ou modificar regras individuais para uma política de versão do cliente no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f007a-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f007a-106">As regras são listadas em ordem de prioridade.</span><span class="sxs-lookup"><span data-stu-id="f007a-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="f007a-107">Por exemplo, se você tiver uma regra que permita que os clientes que executam a versão 1,5 se conectem, seguido por uma regra que bloqueia clientes que executam uma versão anterior a 2,0, a primeira regra tem prioridade e os clientes que executam a versão 1,5 têm permissão para se conectar.</span><span class="sxs-lookup"><span data-stu-id="f007a-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="f007a-108">Para criar ou modificar regras de política de versão do cliente com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="f007a-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f007a-109">[Crie ou modifique uma nova política de versão do cliente no Lync server 2013 com o](lync-server-2013-create-or-modify-a-new-client-version-policy.md) painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f007a-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="f007a-110">Na página **Editar política de versão do cliente** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f007a-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f007a-111">Clique em **novo** para criar uma nova regra de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="f007a-112">Clique em um dos tipos de cliente definidos na lista e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f007a-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f007a-113">Você pode usar caracteres curinga para indicar o tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="f007a-114">Em **agente do usuário**, selecione um tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="f007a-115">Em **número de versão**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f007a-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="f007a-116">Na **versão principal**, digite o número que corresponde à versão principal do cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="f007a-117">Em **versão secundária**, digite o número que corresponde à versão secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="f007a-118">Em **Compilar**, digite o número que corresponde à versão principal e secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="f007a-119">Em **Atualizar**, digite o número que corresponde à versão atualizada do cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f007a-120">Você pode usar caracteres curinga para indicar o número da versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="f007a-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="f007a-121">Para especificar a operação correspondente à versão do cliente que você especificou nas etapas anteriores, em **operação de comparação**, clique em uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f007a-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="f007a-122">**Igual a**</span><span class="sxs-lookup"><span data-stu-id="f007a-122">**Same as**</span></span>
    
      - <span data-ttu-id="f007a-123">**Não é**</span><span class="sxs-lookup"><span data-stu-id="f007a-123">**Is not**</span></span>
    
      - <span data-ttu-id="f007a-124">**Mais novo que**</span><span class="sxs-lookup"><span data-stu-id="f007a-124">**Newer than**</span></span>
    
      - <span data-ttu-id="f007a-125">**Mais novo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="f007a-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="f007a-126">**Mais antigo que**</span><span class="sxs-lookup"><span data-stu-id="f007a-126">**Older than**</span></span>
    
      - <span data-ttu-id="f007a-127">**Mais antigo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="f007a-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="f007a-128">Para especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos, clique em um dos seguintes itens em **ação**:</span><span class="sxs-lookup"><span data-stu-id="f007a-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="f007a-129">Para permitir que o cliente faça logon, clique em **permitir**.</span><span class="sxs-lookup"><span data-stu-id="f007a-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="f007a-130">Para permitir que o cliente faça logon e Receba atualizações do Windows Server Update Service ou do Microsoft Update, clique em **permitir e atualizar**.</span><span class="sxs-lookup"><span data-stu-id="f007a-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="f007a-131">Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="f007a-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f007a-132">Selecionar essa ação faz com que uma notificação seja exibida na próxima vez que os usuários entrarem no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f007a-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="f007a-133">A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="f007a-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="f007a-134">Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f007a-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="f007a-135">Para permitir que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão do cliente, clique em **permitir com URL**.</span><span class="sxs-lookup"><span data-stu-id="f007a-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="f007a-136">Você especifica a URL mais adiante neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="f007a-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="f007a-137">Para impedir que o cliente faça logon, clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="f007a-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="f007a-138">Para impedir que o cliente faça logon e permita que o cliente Receba atualizações do Windows Server Update Service ou do Microsoft Update, clique em **bloquear e atualizar**.</span><span class="sxs-lookup"><span data-stu-id="f007a-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="f007a-139">Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="f007a-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="f007a-140">Para impedir que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão do cliente, clique em **Bloquear com URL**.</span><span class="sxs-lookup"><span data-stu-id="f007a-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="f007a-141">Você especifica a URL mais adiante neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="f007a-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="f007a-142">Adicionais Se você clicou em **permitir com URL** ou **bloco com URL** na etapa anterior, digite a URL de download do cliente a ser incluída na mensagem em **URL**.</span><span class="sxs-lookup"><span data-stu-id="f007a-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="f007a-143">Clique em **OK**e, em seguida, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f007a-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

