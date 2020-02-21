---
title: 'Lync Server 2013: criar o design de topologia inicial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ccdec2c39839674c6304000680ec611a48c016
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="fefe1-102">Criar o design de topologia inicial para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fefe1-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fefe1-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fefe1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fefe1-104">Após concluir a instalação da ferramenta de planejamento do Lync Server 2013, você está pronto para iniciar a ferramenta de planejamento e começar a criar a infraestrutura proposta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fefe1-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fefe1-105">A ferramenta de planejamento é uma ferramenta orientada por assistente com guias detalhadas para informar o processo de tomada de decisão na criação de sites e topologia.</span><span class="sxs-lookup"><span data-stu-id="fefe1-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="fefe1-106">Este tópico não se destina a um guia abrangente, mas simplesmente para ajudá-lo a começar a usar a ferramenta de planejamento nas sessões de design.</span><span class="sxs-lookup"><span data-stu-id="fefe1-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="fefe1-107">Para iniciar usando a Ferramenta de Planejamento e criar o design inicial</span><span class="sxs-lookup"><span data-stu-id="fefe1-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="fefe1-108">Inicie a ferramenta de planejamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **ferramenta de planejamento**.</span><span class="sxs-lookup"><span data-stu-id="fefe1-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="fefe1-109">Após o início da ferramenta de planejamento, a página **Bem-vindo à ferramenta de planejamento para o Microsoft Lync Server 2013** é exibida.</span><span class="sxs-lookup"><span data-stu-id="fefe1-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="fefe1-110">Escolha uma das seguintes opções para começar seu design:</span><span class="sxs-lookup"><span data-stu-id="fefe1-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="fefe1-111">**Opção 1:**   introdução **ao clique em introdução fornece** uma série específica de perguntas de entrevista com seleções relevantes para definir os critérios.</span><span class="sxs-lookup"><span data-stu-id="fefe1-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="fefe1-112">Após ter finalizado a seção de entrevista **Iniciando** inicial, você continua com **Design de sites** para definir sua arquitetura de site.</span><span class="sxs-lookup"><span data-stu-id="fefe1-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="fefe1-113">Para concluir esta opção, continue na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="fefe1-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="fefe1-114">**Opção 2: design sites**   clicando em **sites de design** na página de boas-vindas ignora as perguntas de entrevista apresentadas na seção **introdução** .</span><span class="sxs-lookup"><span data-stu-id="fefe1-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="fefe1-115">As informações que seriam coletadas respondendo às perguntas de entrevista na seção **introdução** é definida como valores padrão com essa opção.</span><span class="sxs-lookup"><span data-stu-id="fefe1-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="fefe1-116">Ao clicar em **sites de design**, o designer experiente pode ignorar a entrevista inicial e alterar os valores padrão, conforme necessário, na página inicial dos **sites centrais** .</span><span class="sxs-lookup"><span data-stu-id="fefe1-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="fefe1-117">Para concluir esta opção, pule as etapas 3 a 5 e inicie na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="fefe1-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="fefe1-118">**Opção 3: exibir sua topologia**   salva se você já tiver concluído e salvo uma topologia por meio do uso anterior da ferramenta de planejamento, poderá ignorar a maioria dessas etapas e começar abrindo e exibindo a topologia.</span><span class="sxs-lookup"><span data-stu-id="fefe1-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="fefe1-119">Você também pode fazer alterações e atualizações na topologia, salvá-la novamente e, em seguida, exportá-la para o Microsoft Excel ou Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="fefe1-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="fefe1-120">Para concluir esta opção, pule as etapas 3 a 12 e inicie na etapa 13.</span><span class="sxs-lookup"><span data-stu-id="fefe1-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="fefe1-121">Clique **em introdução para** começar a criar sua topologia do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fefe1-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="fefe1-122">Responda cada seção selecionando o critério adequado para seu design e clique em **Avançar** para continuar com a próxima página do Assistente.</span><span class="sxs-lookup"><span data-stu-id="fefe1-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="fefe1-123">Clique em **voltar** para fazer alterações nas páginas anteriores.</span><span class="sxs-lookup"><span data-stu-id="fefe1-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="fefe1-124">Cada página possui uma descrição do critério de seleção e recomendações com base nas práticas preferidas e no planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="fefe1-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="fefe1-125">Se você precisar de mais detalhes, clique em <STRONG>saiba mais</STRONG> para ler informações detalhadas da documentação de planejamento do Lync Server 2013 no site da Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="fefe1-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="fefe1-126">Você deve ter uma conectividade com a Internet para acessar o site da Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="fefe1-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="fefe1-127">Selecione as opções adequadas para seu design.</span><span class="sxs-lookup"><span data-stu-id="fefe1-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="fefe1-128">Após o critério inicial ser definido, uma página confirmará que sua Visão Geral dos Recursos está concluída.</span><span class="sxs-lookup"><span data-stu-id="fefe1-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="fefe1-129">Clique em **design de sites** para definir seu site central.</span><span class="sxs-lookup"><span data-stu-id="fefe1-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fefe1-130">Cada topologia do Lync Server 2013 terá pelo menos um site central.</span><span class="sxs-lookup"><span data-stu-id="fefe1-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="fefe1-131">O design pode ter um único site central, um site central com vários sites de filiais, vários sites centrais ou vários sites centrais com sites de filial associados a cada site central.</span><span class="sxs-lookup"><span data-stu-id="fefe1-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="fefe1-132">Em **nome do site**, digite o nome que identificará esse site central.</span><span class="sxs-lookup"><span data-stu-id="fefe1-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="fefe1-133">Em **usuários hospedados no site**, digite o número esperado de usuários simultâneos locais que serão hospedados neste site central.</span><span class="sxs-lookup"><span data-stu-id="fefe1-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="fefe1-134">Em **usuários hospedados na nuvem**, digite o número esperado de usuários simultâneos online que serão hospedados neste site central.</span><span class="sxs-lookup"><span data-stu-id="fefe1-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="fefe1-135">Modifique as seleções para colaboração online, usuários, voz, opções de implantação adicionais ou aplicativos de servidor, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fefe1-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fefe1-136">Neste ponto no design, você só pode selecionar ou desmarcar opções para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="fefe1-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="fefe1-137">No entanto, você pode configurar mais opções em uma fase posterior da ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fefe1-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="fefe1-138">Existem também outras opções que não estão disponíveis e não podem ser desmarcadas.</span><span class="sxs-lookup"><span data-stu-id="fefe1-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="fefe1-139">Além disso, você pode precisar desmarcar uma opção para desmarcar outra.</span><span class="sxs-lookup"><span data-stu-id="fefe1-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="fefe1-140">Por exemplo, se você desmarcar a opção <STRONG>Enterprise Voice</STRONG> em voz, as opções <STRONG>grupo de resposta</STRONG>, <STRONG>anúncio</STRONG>e <STRONG>estacionamento de chamada</STRONG> em aplicativos de servidor (todos os recursos do Enterprise Voice) também serão desmarcadas.</span><span class="sxs-lookup"><span data-stu-id="fefe1-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="fefe1-141">Após definir um nome de site e número de usuários, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fefe1-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="fefe1-142">As páginas a seguir solicitam informações sobre domínios SIP, configurações de conferência, configurações de voz e infraestrutura, a UM do Exchange, acesso de usuário externo, configurações de chat persistente, configurações de cliente, opções de colocação e sites de filial.</span><span class="sxs-lookup"><span data-stu-id="fefe1-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="fefe1-143">Respondas estas perguntas conforme adequado.</span><span class="sxs-lookup"><span data-stu-id="fefe1-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="fefe1-144">A pergunta final pergunta se você deseja criar outro site central.</span><span class="sxs-lookup"><span data-stu-id="fefe1-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="fefe1-145">Se você selecionar **Sim**, a ferramenta de planejamento voltará para a página sites centrais.</span><span class="sxs-lookup"><span data-stu-id="fefe1-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="fefe1-146">Se você selecionar **não**, clique em **Avançar**e, em seguida, clique em **desenhar** para exibir o modo de exibição de topologia global de alto nível.</span><span class="sxs-lookup"><span data-stu-id="fefe1-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="fefe1-147">Para exibir uma topologia existente, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="fefe1-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="fefe1-148">Clique no arquivo .xml que representa a topologia salva anteriormente e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fefe1-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="fefe1-149">A ferramenta de planejamento exibe a página de topologia global.</span><span class="sxs-lookup"><span data-stu-id="fefe1-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="fefe1-150">Agora você pode começar a editar, atualizar ou alterar a topologia usando as ferramentas disponíveis na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fefe1-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fefe1-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="fefe1-151">See Also</span></span>


[<span data-ttu-id="fefe1-152">Editando o design no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fefe1-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

