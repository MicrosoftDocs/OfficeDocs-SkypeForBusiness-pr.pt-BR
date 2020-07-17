---
title: Baixar a topologia da implantação existente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19cf24e1ef287b50ffece7407913a7d2c45e7062
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="a7dfa-102">Baixar a topologia da implantação existente</span><span class="sxs-lookup"><span data-stu-id="a7dfa-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7dfa-103">_**Última modificação do tópico:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="a7dfa-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="a7dfa-104">Ao criar um pool do Lync Server 2013, você usará o repositório de gerenciamento central associado ao Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="a7dfa-105">Quando você iniciar o construtor de topologia no primeiro uso e nas sessões de edição subsequentes, será solicitado o local em que deseja que o construtor de topologia carregue o documento de configuração atual.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="a7dfa-106">Como você já tem uma topologia do Lync Server 2010 definida e estabeleceu o repositório de gerenciamento central, você deve optar por baixar uma topologia de uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="a7dfa-107">O construtor de topologias lerá o banco de dados e recuperará a definição atual.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="a7dfa-108">**Para baixar uma topologia de uma implantação existente**</span><span class="sxs-lookup"><span data-stu-id="a7dfa-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="a7dfa-109">Abra o **Assistente de implantação do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="a7dfa-110">No **Lync Server 2013 – página Assistente de implantação** , clique em **instalar ferramentas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="a7dfa-111">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013** e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="a7dfa-112">Selecione **Download da topologia de uma implantação existente**.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="a7dfa-113">![Configurações do construtor de topologia do assistente de implantação](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Configurações do construtor de topologia do assistente de implantação")</span><span class="sxs-lookup"><span data-stu-id="a7dfa-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="a7dfa-114">Escolha um nome de arquivo e salve a topologia com um tipo de arquivo padrão .tbxml.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="a7dfa-115">Expanda o nó do Lync Server, conforme mostrado, para revelar as várias funções de servidor na implantação.</span><span class="sxs-lookup"><span data-stu-id="a7dfa-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="a7dfa-116">![Propriedades gerais da função de servidor do construtor de topologia](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propriedades gerais da função de servidor do construtor de topologia")</span><span class="sxs-lookup"><span data-stu-id="a7dfa-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

