---
title: Verificar as definições da configuração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode validar a replicação de informações de configuração para o servidor de borda executando o cmdlet Get-CsManagementStoreReplicationStatus do Skype for Business Server 2019 no computador interno no qual o repositório de gerenciamento central está localizado ou em qualquer computador associado a domínio no qual o Skype for Business Server 2019 Core Components (OcsCore. msi) está instalado.
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812749"
---
# <a name="verify-configuration-settings"></a>Verificar as definições da configuração

Você pode validar a replicação de informações de configuração para o servidor de borda executando o cmdlet **Get-CsManagementStoreReplicationStatus** do Skype for Business Server 2019 no computador interno no qual o repositório de gerenciamento central está localizado ou em qualquer computador associado a um domínio no qual o Skype for Business Server 2019 componentes principais (OcsCore. msi) estiver instalado. 
  
Os resultados iniciais podem indicar o status como "falso" em vez de "verdadeiro" para replicação. Em caso afirmativo, execute o cmdlet **Invoke-CsManagementStoreReplication** e aguarde o tempo de conclusão da replicação antes de executar o **Get-CsManagementStoreReplicationStatus** novamente. 
  

