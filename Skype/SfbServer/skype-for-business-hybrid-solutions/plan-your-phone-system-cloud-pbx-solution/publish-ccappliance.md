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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: O Publish-CcAppliance cmdlet obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo do Skype for Business Cloud Connector Edition no servidor host.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824307"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
O Publish-CcAppliance cmdlet obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo do Skype for Business Cloud Connector Edition no servidor host. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo do Cloud Connector no servidor host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

As informações de alta disponibilidade contêm os FQDNs e endereços IP do Servidor de Mediação do site PSTN. Novos registros DNS A são adicionados ao Servidor AD para endereços IP do Servidor de Mediação. Novos itens de topologia são atualizados para o Armazenamento de Gerenciamento Central para os FQDNs e endereços IP do Servidor de Mediação. 
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Publish-CcAppliance cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

