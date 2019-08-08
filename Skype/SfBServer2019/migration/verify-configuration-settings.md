---
title: Verificar as definições da configuração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode validar a replicação de informações de configuração para o servidor de borda executando o cmdlet Get-CsManagementStoreReplicationStatus do Skype for Business Server 2019 no computador interno no qual o repositório de gerenciamento central está localizado ou em qualquer computador associado a domínio no qual o Skype for Business Server 2019 Core Components (OcsCore. msi) está instalado.
ms.openlocfilehash: 5beb3c80bbc4c2f9a73fe68b9d99d7752598c680
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240935"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="5261a-103">Verificar as definições da configuração</span><span class="sxs-lookup"><span data-stu-id="5261a-103">Verify configuration settings</span></span>

<span data-ttu-id="5261a-104">Você pode validar a replicação de informações de configuração para o servidor de borda executando o cmdlet **Get-CsManagementStoreReplicationStatus** do Skype for Business Server 2019 no computador interno no qual o repositório de gerenciamento central está localizado, ou em qualquer computador associado a um domínio no qual o Skype for Business Server 2019 Core Components (OcsCore. msi) está instalado.</span><span class="sxs-lookup"><span data-stu-id="5261a-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="5261a-105">Os resultados iniciais podem indicar o status como "falso" em vez de "verdadeiro" para replicação.</span><span class="sxs-lookup"><span data-stu-id="5261a-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="5261a-106">Em caso afirmativo, execute o cmdlet **Invoke-CsManagementStoreReplication** e aguarde o tempo de conclusão da replicação antes de executar o **Get-CsManagementStoreReplicationStatus** novamente.</span><span class="sxs-lookup"><span data-stu-id="5261a-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

