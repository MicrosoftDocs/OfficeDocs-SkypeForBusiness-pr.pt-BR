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
description: Você pode validar a replicação de informações de configuração para o servidor de borda executando o cmdlet Get-CsManagementStoreReplicationStatus do Skype for Business Server 2019 no computador interno no qual o repositório de gerenciamento central está localizado, ou em qualquer computador ingressado no domínio no qual o Skype for Business Server 2019 Core Components (OcsCore.msi) está instalado.
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752143"
---
# <a name="verify-configuration-settings"></a>Verifique as configurações

Você pode validar a replicação de informações de configuração no servidor de borda executando o cmdlet **Get-CsManagementStoreReplicationStatus** do Skype for Business Server 2019 no computador interno no qual o repositório de gerenciamento central está localizado, ou em qualquer computador associado a um domínio em que o Skype for Business Server 2019 Core Components (OcsCore.msi) está instalado. 
  
Os resultados iniciais podem indicar o status como "Falso" e não "Verdadeiro" para replicação. Se isso acontecer, execute o cmdlet **Invoke-CsManagementStoreReplication** e dê tempo para a replicação ser concluída antes de executar o **Get-CsManagementStoreReplicationStatus** novamente. 
  

