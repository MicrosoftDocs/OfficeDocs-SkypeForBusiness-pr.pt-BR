---
title: Verificar as definições da configuração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode validar a replicação das informações de configuração para o servidor de borda executando o Skype para Business Server 2019 Get-CsManagementStoreReplicationStatus cmdlet no computador interno no qual está localizado o repositório de gerenciamento Central ou em qualquer um computador que ingressou domínio no qual o Skype para componentes de principais (ocscore. msi) do Business Server 2019 está instalado.
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231354"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="76f2f-103">Verificar as definições da configuração</span><span class="sxs-lookup"><span data-stu-id="76f2f-103">Verify configuration settings</span></span>

<span data-ttu-id="76f2f-104">Você pode validar a replicação das informações de configuração para o servidor de borda executando o Skype para Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet no computador no qual o repositório de gerenciamento Central está localizado, interno ou em qualquer computador do domínio no qual o Skype para componentes de principais (ocscore. msi) do Business Server 2019 é instalado.</span><span class="sxs-lookup"><span data-stu-id="76f2f-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="76f2f-105">Resultados iniciais podem indicar o status como "False", em vez de "True" para replicação.</span><span class="sxs-lookup"><span data-stu-id="76f2f-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="76f2f-106">Em caso afirmativo, execute o cmdlet **Invoke-CsManagementStoreReplication** e reserve um tempo para a replicação ser concluída antes de executar o **Get-CsManagementStoreReplicationStatus** novamente.</span><span class="sxs-lookup"><span data-stu-id="76f2f-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

