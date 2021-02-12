---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Depois de migrar para o Microsoft Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754041"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="946af-103">Configurar monitoramento SCOM</span><span class="sxs-lookup"><span data-stu-id="946af-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="946af-104">Depois de migrar para o Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="946af-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="946af-105">Aplicar atualizações a um servidor selecionado para gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="946af-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="946af-106">Atualize a chave de registro do servidor candidato a descoberta central.</span><span class="sxs-lookup"><span data-stu-id="946af-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="946af-107">Configure seu servidor de gerenciamento principal do System Center Operations Manager para substituir o nó candidato de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="946af-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="946af-108">Instruções para executar cada uma dessas tarefas são fornecidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="946af-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="946af-109">Aplicar atualizações a um servidor selecionado para gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="946af-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="946af-110">Eleja um servidor que possua os arquivos do agente do Gerenciador de Operações do Sistema Central instalados e esteja configurado como nó de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="946af-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="946af-111">Aplique atualizações a este servidor.</span><span class="sxs-lookup"><span data-stu-id="946af-111">Apply updates to this server.</span></span> <span data-ttu-id="946af-112">Consulte o tópico [Aplicar atualizações.](apply-updates.md)</span><span class="sxs-lookup"><span data-stu-id="946af-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="946af-113">Atualize a chave de registro do servidor candidato a descoberta central.</span><span class="sxs-lookup"><span data-stu-id="946af-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="946af-114">No servidor escolhido para gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="946af-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="946af-115">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="946af-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="946af-p102">Sempre que você editar o registro, você poderá receber um erro em que o comando falha caso a chave de registro já exista. Caso isso aconteça, você pode ignorar com segurança o erro.</span><span class="sxs-lookup"><span data-stu-id="946af-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="946af-118">Configure seu servidor de gerenciamento principal do System Center Operations Manager para substituir o nó candidato do watcher de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="946af-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="946af-119">Em um computador onde o console do Gerenciador de Operações do  System Center foi instalado, expanda **Objetos do Pacote de Gerenciamento** e selecione **Descobertas de Objeto**.</span><span class="sxs-lookup"><span data-stu-id="946af-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="946af-120">Clique **em Alterar Escopo**</span><span class="sxs-lookup"><span data-stu-id="946af-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="946af-121">Da página **Escopo de Objetos do Pacote de Gerenciamento**, selecione **Candidato a Descoberta LS**.</span><span class="sxs-lookup"><span data-stu-id="946af-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="946af-122">Substitua o **Valor Efetivo de Candidato a Descoberta LS** para o nome do servidor de candidato eleito para o procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="946af-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="946af-123">Para finalizar suas alterações, reinicie o serviço de saúde no System Center Operations Manager Root Management Server.</span><span class="sxs-lookup"><span data-stu-id="946af-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

