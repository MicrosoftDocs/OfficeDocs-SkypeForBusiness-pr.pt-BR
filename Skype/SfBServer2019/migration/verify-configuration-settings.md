---
title: Verifique as configurações
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
description: Você pode validar a replicação das informações de configuração para o servidor de Borda executando o cmdlet Get-CsManagementStoreReplicationStatus do Skype for Business Server 2019 no computador interno no qual o armazenamento de Gerenciamento Central está localizado ou em qualquer computador ingressado no domínio no qual o Skype for Business Server 2019 Core Components (OcsCore.msi) está instalado.
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752143"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="208ce-103">Verifique as configurações</span><span class="sxs-lookup"><span data-stu-id="208ce-103">Verify configuration settings</span></span>

<span data-ttu-id="208ce-104">Você pode validar a replicação das informações de configuração para o servidor de Borda executando o cmdlet **Get-CsManagementStoreReplicationStatus** do Skype for Business Server 2019 no computador interno no qual o repositório de Gerenciamento Central está localizado ou em qualquer computador ingressado no domínio no qual o Skype for Business Server 2019 Core Components (OcsCore.msi) está instalado.</span><span class="sxs-lookup"><span data-stu-id="208ce-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="208ce-105">Os resultados iniciais podem indicar o status como "Falso" e não "Verdadeiro" para replicação.</span><span class="sxs-lookup"><span data-stu-id="208ce-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="208ce-106">Se isso acontecer, execute o cmdlet **Invoke-CsManagementStoreReplication** e dê tempo para a replicação ser concluída antes de executar o **Get-CsManagementStoreReplicationStatus** novamente.</span><span class="sxs-lookup"><span data-stu-id="208ce-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

