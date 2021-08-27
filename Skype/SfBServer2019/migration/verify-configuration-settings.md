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
ms.localizationpriority: medium
description: Você pode validar a replicação das informações de configuração para o servidor de Borda executando o cmdlet Get-CsManagementStoreReplicationStatus 2019 Get-CsManagementStoreReplicationStatus no computador interno no qual o armazenamento de Gerenciamento Central está localizado ou em qualquer computador ingressado em domínio no qual o Skype for Business Server Componentes Principais (OcsCore.msi) do Skype for Business Server 2019 está instalado. Skype for Business Server
ms.openlocfilehash: ff46dbad696ac4bf200bb669de768a28d0815e1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594259"
---
# <a name="verify-configuration-settings"></a>Verifique as configurações

Você pode validar a replicação das informações de configuração para o servidor de Borda executando o cmdlet **Get-CsManagementStoreReplicationStatus** do Skype for Business Server 2019 no computador interno no qual o repositório de Gerenciamento Central está localizado ou em qualquer computador ingressado no domínio no qual o Skype for Business Server Componentes Principais (OcsCore.msi) do OcsCore.msi está instalado. 
  
Os resultados iniciais podem indicar o status como "Falso" em vez de "Verdadeiro" para a replicação. Se isso acontecer, execute o cmdlet **Invoke-CsManagementStoreReplication** e dê tempo para a replicação ser concluída antes de executar o **Get-CsManagementStoreReplicationStatus** novamente. 
  

