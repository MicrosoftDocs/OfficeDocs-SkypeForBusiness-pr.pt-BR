---
title: 'Lync Server 2013: Criar ou modificar um número de acesso de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ecfebba25d45f53633fdd425e5901929fc32d0c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="8bed9-102">Criar ou modificar um número de acesso de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bed9-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bed9-103">_**Tópico da última modificação:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="8bed9-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="8bed9-104">Siga estas etapas se quiser criar ou modificar um número de acesso à conferência discada.</span><span class="sxs-lookup"><span data-stu-id="8bed9-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8bed9-105">Antes de criar um novo número de acesso à discagem, você deve definir uma região de conferência discada no plano de discagem associada ao novo número de acesso discado.</span><span class="sxs-lookup"><span data-stu-id="8bed9-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="8bed9-106">Vários planos de discagem podem usar a mesma região.</span><span class="sxs-lookup"><span data-stu-id="8bed9-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="8bed9-107">Para criar ou modificar um número de acesso à discagem</span><span class="sxs-lookup"><span data-stu-id="8bed9-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="8bed9-108">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8bed9-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8bed9-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bed9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8bed9-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8bed9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8bed9-111">Na barra de navegação à esquerda, clique em **Conferência** e, então, em  **Número de acesso de discagem**.</span><span class="sxs-lookup"><span data-stu-id="8bed9-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="8bed9-112">Na página **Número de Acesso de Discagem**, realize uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="8bed9-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8bed9-113">Clique em **Novo** para abrir **Novo Número de Acesso de Discagem**.</span><span class="sxs-lookup"><span data-stu-id="8bed9-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="8bed9-114">Clique em um dos números de acesso de discagem na lista, clique em **Editar**, e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8bed9-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8bed9-p103">Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado.</span><span class="sxs-lookup"><span data-stu-id="8bed9-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="8bed9-117">Em **Número para exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="8bed9-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8bed9-118">Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="8bed9-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="8bed9-119">Em **Nome para exibição**, digite uma descrição para o número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="8bed9-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="8bed9-120">Este é o nome que está associado ao número de acesso discada nos resultados da pesquisa do Lync.</span><span class="sxs-lookup"><span data-stu-id="8bed9-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8bed9-121">Esse nome é exibido no cliente quando um usuário disca o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="8bed9-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="8bed9-p105">Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="8bed9-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8bed9-124">O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="8bed9-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="8bed9-125">Em **URI do SIP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bed9-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="8bed9-126">Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="8bed9-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="8bed9-127">Esse URI SIP é exibido em vários locais, incluindo, entre outros, mensagens de notificação de chamada e versões anteriores de clientes do Communicator.</span><span class="sxs-lookup"><span data-stu-id="8bed9-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8bed9-p107">O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="8bed9-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="8bed9-131">Na caixa de listagem suspensa, clique no domínio do aplicativo de assistente de conferência que dá suporte a esse número de acesso à discagem.</span><span class="sxs-lookup"><span data-stu-id="8bed9-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="8bed9-132">Em  **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="8bed9-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8bed9-133">Se for preciso alterar o pool depois de criar o número de acesso, deve-se usar o cmdlet do <STRONG>Move-CsApplicationEndpoint</STRONG> ou excluir e recriar o número de acesso.</span><span class="sxs-lookup"><span data-stu-id="8bed9-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="8bed9-134">Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas para esse número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="8bed9-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8bed9-p108">O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="8bed9-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="8bed9-137">(Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8bed9-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8bed9-p109">É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.</span><span class="sxs-lookup"><span data-stu-id="8bed9-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="8bed9-140">Para adicionar uma região para o número de acesso de discagem, em **regiões associadas**, clique em **Adicionar**, clique em uma ou mais regiões associadas aos planos de discagem para este número de acesso à discagem e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8bed9-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="8bed9-141">Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="8bed9-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="8bed9-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8bed9-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

