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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889673"
---
# <a name="verify-configuration-settings"></a>Verificar as definições da configuração

Você pode validar a replicação das informações de configuração para o servidor de borda executando o Skype para Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet no computador no qual o repositório de gerenciamento Central está localizado, interno ou em qualquer computador do domínio no qual o Skype para componentes de principais (ocscore. msi) do Business Server 2019 é instalado. 
  
Resultados iniciais podem indicar o status como "False", em vez de "True" para replicação. Em caso afirmativo, execute o cmdlet **Invoke-CsManagementStoreReplication** e reserve um tempo para a replicação ser concluída antes de executar o **Get-CsManagementStoreReplicationStatus** novamente. 
  

