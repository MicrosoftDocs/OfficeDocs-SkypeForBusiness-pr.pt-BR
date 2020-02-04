---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7904edf9723dacdd28f69a75bec17cb5db3c2061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="ad000-102">Configurar monitoramento SCOM</span><span class="sxs-lookup"><span data-stu-id="ad000-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad000-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ad000-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ad000-104">Depois de migrar para o Microsoft Lync Server 2013, você deve concluir algumas tarefas para configurar o Lync Server 2013 para trabalhar com o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ad000-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="ad000-105">Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="ad000-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="ad000-106">Atualize a chave do registro do servidor candidato à descoberta central.</span><span class="sxs-lookup"><span data-stu-id="ad000-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="ad000-107">Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó de descoberta central de candidatos.</span><span class="sxs-lookup"><span data-stu-id="ad000-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="ad000-108">As instruções para executar cada uma dessas tarefas são fornecidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="ad000-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="ad000-109">**Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.**</span><span class="sxs-lookup"><span data-stu-id="ad000-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="ad000-110">Escolha um servidor que tenha os arquivos de agente do System Center Operations Manager instalados e esteja configurado como um nó de descoberta de candidatos.</span><span class="sxs-lookup"><span data-stu-id="ad000-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="ad000-111">Aplicar atualizações do Lync Server 2010 a este servidor.</span><span class="sxs-lookup"><span data-stu-id="ad000-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="ad000-112">Consulte o tópico [aplicar atualizações do Lync Server 2010](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="ad000-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="ad000-113">**Atualize a chave do registro do servidor candidato à descoberta central.**</span><span class="sxs-lookup"><span data-stu-id="ad000-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="ad000-114">No servidor escolhido para gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad000-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="ad000-115">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ad000-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="ad000-116">Sempre que você edita o registro, pode ocorrer um erro inque o comando falhou se a chave do registro já existe.</span><span class="sxs-lookup"><span data-stu-id="ad000-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="ad000-117">Se isso acontecer, você pode ignorar o erro com segurança.</span><span class="sxs-lookup"><span data-stu-id="ad000-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="ad000-118">**Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó do inspetor da descoberta do candidato.**</span><span class="sxs-lookup"><span data-stu-id="ad000-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="ad000-119">Em um computador em que o console System Center Operations Manager foi instalado, expanda os **objetos do pacote de gerenciamento** e selecione descobertas de **objetos**.</span><span class="sxs-lookup"><span data-stu-id="ad000-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="ad000-120">Clique em **alterar escopo..** .</span><span class="sxs-lookup"><span data-stu-id="ad000-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="ad000-121">Na página **objetos do pacote de gerenciamento de escopo** , selecione **candidato para descoberta ls**.</span><span class="sxs-lookup"><span data-stu-id="ad000-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="ad000-122">Substitua o **valor efetivo de candidato à descoberta ls** pelo nome do servidor de candidatos escolhido no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="ad000-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="ad000-123">Por fim, para finalizar suas alterações, reinicie o serviço de integridade no servidor de gerenciamento raiz do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ad000-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

