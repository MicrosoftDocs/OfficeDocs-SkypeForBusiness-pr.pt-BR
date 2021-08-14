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
description: O Publish-CcAppliance cmdlet obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo Skype for Business Cloud Connector Edition no servidor host.
ms.openlocfilehash: 83b0a7e3806a271a358085bb0cca2a2ef6a518e67e124f0be97c1ff4616e3dcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326177"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
O Publish-CcAppliance cmdlet obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo Skype for Business Cloud Connector Edition no servidor host. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo Cloud Connector no servidor host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

As informações de alta disponibilidade contêm os FQDNs do Servidor de Mediação e endereços IP do site PSTN. Novos registros DNS A são adicionados ao Servidor AD para endereços IP do Servidor de Mediação. Novos itens de topologia são atualizados para o Armazenamento de Gerenciamento Central para os FQDNs do Servidor de Mediação e endereços IP. 
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Publish-CcAppliance cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

