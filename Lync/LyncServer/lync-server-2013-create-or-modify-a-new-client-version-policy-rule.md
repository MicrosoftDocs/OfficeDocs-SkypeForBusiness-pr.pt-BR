---
title: 'Lync Server 2013: criar ou modificar uma nova regra de política de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9207ff9d615990d0e944ac8c435561f0c937f089
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="6c164-102">Criar ou modificar uma nova regra de política de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c164-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c164-103">_**Última modificação do tópico:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="6c164-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="6c164-104">As regras de política de versão do cliente definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes e versões de cliente específicos.</span><span class="sxs-lookup"><span data-stu-id="6c164-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="6c164-105">Você pode criar ou modificar regras individuais para uma política de versão de cliente no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c164-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c164-106">As regras são listadas em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="6c164-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="6c164-107">Por exemplo, se você tiver uma regra que permita que os clientes executando a versão 1,5 se conectem, seguido por uma regra que bloqueia clientes que executam uma versão anterior a 2,0, a primeira regra tem precedência e os clientes executando a versão 1,5 têm permissão para se conectar.</span><span class="sxs-lookup"><span data-stu-id="6c164-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="6c164-108">Para criar ou modificar as regras de política de versão do cliente com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6c164-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6c164-109">[Criar ou modificar uma nova política de versão do cliente no Lync server 2013 com o](lync-server-2013-create-or-modify-a-new-client-version-policy.md) painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c164-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="6c164-110">Na página **Editar política de versão do cliente** , execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6c164-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6c164-111">Clique em **Nova** para criar uma nova regra de versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="6c164-112">Clique em um dos tipos de cliente definidos na lista e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6c164-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c164-113">É possível usar caracteres curinga para indicar o tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="6c164-114">Em **Agente do usuário**, selecione um tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="6c164-115">Em **Número de versão**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6c164-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="6c164-116">Em **Versão principal**, digite o número que corresponde à versão principal do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="6c164-117">Em **Versão secundária**, digite o número que corresponde à versão secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="6c164-118">Em **Compilação**, digite o número que corresponde à versão principal e secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="6c164-119">Em **Atualização**, digite o número que corresponde à versão atualizada do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c164-120">Você pode usar caracteres curinga para indicar o número da versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c164-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="6c164-121">Para especificar a operação correspondente para a versão do cliente especificada nas etapas anteriores, em **Operação de comparação**, clique em um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6c164-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="6c164-122">**Igual a**</span><span class="sxs-lookup"><span data-stu-id="6c164-122">**Same as**</span></span>
    
      - <span data-ttu-id="6c164-123">**Não é**</span><span class="sxs-lookup"><span data-stu-id="6c164-123">**Is not**</span></span>
    
      - <span data-ttu-id="6c164-124">**Mais novo que**</span><span class="sxs-lookup"><span data-stu-id="6c164-124">**Newer than**</span></span>
    
      - <span data-ttu-id="6c164-125">**Mais novo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="6c164-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="6c164-126">**Mais antigo que**</span><span class="sxs-lookup"><span data-stu-id="6c164-126">**Older than**</span></span>
    
      - <span data-ttu-id="6c164-127">**Mais antigo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="6c164-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="6c164-128">Para especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos, clique em uma das seguintes opções em **Ação**:</span><span class="sxs-lookup"><span data-stu-id="6c164-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="6c164-129">Para permitir o logon do cliente, clique em **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="6c164-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="6c164-p103">Para permitir que o cliente faça o login e receba atualizações do Windows Server Update Service ou Microsoft Update, clique em **Permitir e atualizar**. Esta seção está disponível apenas quando o agente de usuário **OC** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="6c164-p103">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6c164-132">Selecionar esta ação faz com que uma notificação seja exibida na próxima vez que os usuários entrarem no Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6c164-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="6c164-133">A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="6c164-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6c164-134">Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6c164-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="6c164-p105">Para permitir que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão de cliente, clique em **Permitir com URL**. Você especifica a URL posteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="6c164-p105">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**. You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="6c164-137">Para impedir que o cliente faça logon, clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="6c164-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="6c164-p106">Para evitar que o cliente faça o login e permitir que ele receba atualizações do Windows Server Update Service ou Microsoft Update, clique em **Bloquear e atualizar**. Esta ação está disponível apenas quando o agente do usuário **OC** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="6c164-p106">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="6c164-p107">Para impedir o cliente de fazer logon e exibir uma mensagem sobre onde baixar outra versão de cliente, clique em **Bloquear com URL**. Você especifica a URL posteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="6c164-p107">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**. You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="6c164-142">(Opcional) se você clicou em **Permitir com URL** ou **Bloquear com URL** na etapa anterior, digite a URL de download do cliente para incluir na mensagem em **URL**.</span><span class="sxs-lookup"><span data-stu-id="6c164-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="6c164-143">Clique em **OK** e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6c164-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

