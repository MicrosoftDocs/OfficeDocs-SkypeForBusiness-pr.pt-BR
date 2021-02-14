---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: O Set-CcCredential cmdlet define a credencial da implantação atual do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221565"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
O Set-CcCredential cmdlet define a credencial da implantação atual do Skype for Business Cloud Connector Edition. 
  
Com a versão 2.0 e posterior do Cloud Connector, esse cmdlet também pode definir as informações da conta para o administrador da máquina virtual e para o administrador do domínio.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir especifica o nome da conta e a senha do administrador do locatário:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Set-CcCredential cmdlet define o nome e a senha da conta para o administrador de locatários. Para versões anteriores à 2.0, esse administrador deve ser um Administrador Global. O Cloud Connector usa essa conta para obter informações de configuração, definir parâmetros de configuração e atualizar o status do dispositivo para a configuração da organização do Microsoft 365 ou Office 365. Com a versão 2.0 e posterior, você também pode usar esse cmdlet para atualizar as senhas das contas VmAdmin e DomainAdmin.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obrigatório <br/> |System.String  <br/> | O valor do parâmetro deve ser "TenantAdmin", "VmAdmin" ou "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Set-CcCredential cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

