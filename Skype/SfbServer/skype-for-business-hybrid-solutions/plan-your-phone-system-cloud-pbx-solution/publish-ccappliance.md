---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'O cmdlet Publish-CcAppliance obtém informações sobre alta disponibilidade da configuração do locatário online e depois as publica para o dispositivo do Skype for Business Cloud Connector Edition no servidor host. '
ms.openlocfilehash: da9135f669cb5b8cbe127295b20d82fd1632a3d3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003081"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
O cmdlet Publish-CcAppliance obtém informações sobre alta disponibilidade da configuração do locatário online e depois as publica para o dispositivo do Skype for Business Cloud Connector Edition no servidor host.  
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir obtém informações de alta disponibilidade da configuração do locatário online e a publica no dispositivo do conector de nuvem no servidor host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

As informações sobre alta disponibilidade contêm os FQDNs do Servidor de Mediação e endereços IP do site PSTN. Os novos registros do DNS A são adicionados ao Servidor AD para os endereços de IP do Servidor de Mediação. Os novos itens de topologia são atualizados para o Repositório de Gerenciamento Central para os FQDNs do Servidor de Mediação e endereços IP.  
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Publish-CcAppliance não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

