---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="28bee-102">Configurar monitoramento SCOM</span><span class="sxs-lookup"><span data-stu-id="28bee-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28bee-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="28bee-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="28bee-104">Após a migração para o Microsoft Lync Server 2013, você deve concluir algumas tarefas para configurar o Lync Server 2013 para trabalhar com o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="28bee-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="28bee-105">Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="28bee-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="28bee-106">Atualize a chave de registro do servidor candidato a descoberta central.</span><span class="sxs-lookup"><span data-stu-id="28bee-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="28bee-107">Configure seu servidor de gerenciamento do System Center Operations Manager principal para substituir o nó de descoberta central de candidatos.</span><span class="sxs-lookup"><span data-stu-id="28bee-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="28bee-108">Instruções para executar cada uma dessas tarefas são fornecidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="28bee-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="28bee-109">**Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.**</span><span class="sxs-lookup"><span data-stu-id="28bee-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="28bee-110">Eleja um servidor que possua os arquivos do agente do Gerenciador de Operações do Sistema Central instalados e esteja configurado como nó de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="28bee-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="28bee-111">Aplicar atualizações do Lync Server 2010 a este servidor.</span><span class="sxs-lookup"><span data-stu-id="28bee-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="28bee-112">Consulte o tópico [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="28bee-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="28bee-113">**Atualize a chave de registro do servidor candidato a descoberta central.**</span><span class="sxs-lookup"><span data-stu-id="28bee-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="28bee-114">No servidor escolhido para gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28bee-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="28bee-115">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="28bee-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="28bee-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span><span class="sxs-lookup"><span data-stu-id="28bee-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="28bee-117">If you experience this, you can safely ignore the error.</span><span class="sxs-lookup"><span data-stu-id="28bee-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="28bee-118">**Configure seu servidor de gerenciamento do System Center Operations Manager principal para substituir o nó do Inspetor de descoberta central de candidatos.**</span><span class="sxs-lookup"><span data-stu-id="28bee-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="28bee-119">Em um computador onde o console do Gerenciador de Operações do  System Center foi instalado, expanda **Objetos do Pacote de Gerenciamento** e selecione **Descobertas de Objeto**.</span><span class="sxs-lookup"><span data-stu-id="28bee-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="28bee-120">Clique em **Alterar escopo...**</span><span class="sxs-lookup"><span data-stu-id="28bee-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="28bee-121">Da página **Escopo de Objetos do Pacote de Gerenciamento**, selecione **Candidato a Descoberta LS**.</span><span class="sxs-lookup"><span data-stu-id="28bee-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="28bee-122">Substitua o **Valor Efetivo de Candidato a Descoberta LS** para o nome do servidor de candidato eleito para o procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="28bee-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="28bee-123">Por fim, finalize as alterações, reinicie o serviço de integridade no Servidor de Gerenciamento de Raiz de Gerenciamento de Operações do System Center.</span><span class="sxs-lookup"><span data-stu-id="28bee-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

