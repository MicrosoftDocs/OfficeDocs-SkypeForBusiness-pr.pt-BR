---
title: Set-CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a>Set-CcCredential
 
O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition.  
  
Com o conector de nuvem versão 2.0 e posteriores, este cmdlet também pode definir as informações de conta para o administrador de máquina virtual e para o administrador de domínio.
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir especifica o nome e a senha da conta do administrador do locatário:
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Set-CcCredential define o nome e a senha da conta do administrador do locatário. Para versões anteriores à versão 2.0, este administrador deve ser um Administrador Global do Office 365. Conector de nuvem usa essa conta para obter informações de configuração, defina os parâmetros de configuração e status de aparelho de atualização na configuração de Inquilino do Office 365. Com a versão 2.0 e posterior, você também pode usar esse cmdlet para atualizar as senhas das contas VmAdmin e DomainAdmin.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obrigatório <br/> |System. String  <br/> |  O valor do parâmetro deve ser "TenantAdmin", "VmAdmin" ou "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Set-CcCredential não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

