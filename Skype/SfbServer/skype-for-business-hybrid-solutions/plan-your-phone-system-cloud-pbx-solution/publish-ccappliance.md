---
title: Publicar-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'O cmdlet Publish-CcAppliance obtém informações sobre alta disponibilidade da configuração do locatário online e depois as publica para o dispositivo do Skype for Business Cloud Connector Edition no servidor host. '
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a>Publicar-CcAppliance
 
O cmdlet Publish-CcAppliance obtém informações sobre alta disponibilidade da configuração do locatário online e depois as publica para o dispositivo do Skype for Business Cloud Connector Edition no servidor host.  
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir obtém informações de alta disponibilidade da configuração do inquilino online e publicá-lo para o aparelho de conector de nuvem no servidor host:
  
```
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
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Desinstalar-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Cancelar o registro de CcAppliance](unregister-ccappliance.md)
  

