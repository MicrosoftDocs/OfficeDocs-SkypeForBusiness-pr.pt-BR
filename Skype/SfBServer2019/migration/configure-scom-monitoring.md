---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a migração para o Microsoft Skype for Business Server 2019, você deve concluir algumas tarefas para configurar Skype para negócios 2019 de servidor funcionar com o System Center Operations Manager.
ms.openlocfilehash: 80ef737c57006550111331db7f46fd607f7cf1ed
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238720"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="1d8f5-103">Configurar monitoramento SCOM</span><span class="sxs-lookup"><span data-stu-id="1d8f5-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="1d8f5-104">Após migrar para o Skype para Business Server 2019, você deve concluir algumas tarefas para configurar Skype para negócios 2019 de servidor funcionar com o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="1d8f5-105">Aplica atualizações a um servidor eleito a gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="1d8f5-106">Atualize a chave de registro do servidor de candidato a descoberta central.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="1d8f5-107">Configure o servidor de gerenciamento do System Center Operations Manager primário para substituir o nó do candidato a descoberta central.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="1d8f5-108">Instruções para executar cada uma dessas tarefas são fornecidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="1d8f5-109">Aplica atualizações a um servidor eleito a gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="1d8f5-110">Eleja um servidor que tem o System Center Operations Manager arquivos do agente instalados e esteja configurado como um nó do candidato a descoberta.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="1d8f5-111">Aplique atualizações a esse servidor.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-111">Apply updates to this server.</span></span> <span data-ttu-id="1d8f5-112">Consulte o tópico [Aplicar atualizações](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="1d8f5-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="1d8f5-113">Atualize a chave de registro do servidor de candidato a descoberta central.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="1d8f5-114">No servidor eleito a gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="1d8f5-115">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d8f5-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="1d8f5-116">Sempre que você edite o registro, você pode enfrentar um erro dizendo que o comando falha se a chave do registro já existir.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="1d8f5-117">Se você enfrentar isso, você pode ignorar com segurança o erro.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="1d8f5-118">Configure seu servidor de gerenciamento do System Center Operations Manager primário para substituir o nó de Inspetor do candidato a descoberta central.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="1d8f5-119">Em um computador onde o console do System Center Operations Manager foi instalado, expanda **Objetos do pacote de gerenciamento** e selecione **Descobertas de objeto**.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="1d8f5-120">Clique em **Alterar escopo**</span><span class="sxs-lookup"><span data-stu-id="1d8f5-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="1d8f5-121">Na página de **Objetos do pacote de gerenciamento de escopo** , selecione **Candidato a descoberta LS**.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="1d8f5-122">Substitua o **Valor efetivo de candidato de descoberta LS** para o nome do servidor candidato eleito no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="1d8f5-123">Finalize as alterações, reinicie o serviço de integridade no servidor de gerenciamento do System Center Operations Manager raiz.</span><span class="sxs-lookup"><span data-stu-id="1d8f5-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

