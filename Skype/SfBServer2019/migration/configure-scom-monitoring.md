---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de migrar para o Microsoft Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284498"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="6c188-103">Configurar monitoramento SCOM</span><span class="sxs-lookup"><span data-stu-id="6c188-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="6c188-104">Depois de migrar para o Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6c188-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="6c188-105">Aplicar atualizações a um servidor escolhido para gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="6c188-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="6c188-106">Atualize a chave do registro do servidor candidato à descoberta central.</span><span class="sxs-lookup"><span data-stu-id="6c188-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="6c188-107">Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó de descoberta central de candidatos.</span><span class="sxs-lookup"><span data-stu-id="6c188-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="6c188-108">As instruções para executar cada uma dessas tarefas são fornecidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="6c188-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="6c188-109">Aplicar atualizações a um servidor escolhido para gerenciar a lógica de descoberta central.</span><span class="sxs-lookup"><span data-stu-id="6c188-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="6c188-110">Escolha um servidor que tenha os arquivos de agente do System Center Operations Manager instalados e esteja configurado como um nó de descoberta de candidatos.</span><span class="sxs-lookup"><span data-stu-id="6c188-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="6c188-111">Aplicar atualizações a este servidor.</span><span class="sxs-lookup"><span data-stu-id="6c188-111">Apply updates to this server.</span></span> <span data-ttu-id="6c188-112">Consulte o tópico [aplicar atualizações](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="6c188-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="6c188-113">Atualize a chave do registro do servidor candidato à descoberta central.</span><span class="sxs-lookup"><span data-stu-id="6c188-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="6c188-114">No servidor escolhido para gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c188-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="6c188-115">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6c188-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="6c188-116">Sempre que você edita o registro, pode ocorrer um erro inque o comando falhou se a chave do registro já existe.</span><span class="sxs-lookup"><span data-stu-id="6c188-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="6c188-117">Se isso acontecer, você pode ignorar o erro com segurança.</span><span class="sxs-lookup"><span data-stu-id="6c188-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="6c188-118">Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó do inspetor da descoberta do candidato.</span><span class="sxs-lookup"><span data-stu-id="6c188-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="6c188-119">Em um computador em que o console System Center Operations Manager foi instalado, expanda os **objetos do pacote de gerenciamento** e selecione descobertas de **objetos**.</span><span class="sxs-lookup"><span data-stu-id="6c188-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="6c188-120">Clique em **alterar escopo**</span><span class="sxs-lookup"><span data-stu-id="6c188-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="6c188-121">Na página **objetos do pacote de gerenciamento de escopo** , selecione **candidato para descoberta ls**.</span><span class="sxs-lookup"><span data-stu-id="6c188-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="6c188-122">Substitua o **valor efetivo de candidato à descoberta ls** pelo nome do servidor de candidatos escolhido no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="6c188-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="6c188-123">Para finalizar suas alterações, reinicie o serviço de integridade no servidor de gerenciamento raiz do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6c188-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

