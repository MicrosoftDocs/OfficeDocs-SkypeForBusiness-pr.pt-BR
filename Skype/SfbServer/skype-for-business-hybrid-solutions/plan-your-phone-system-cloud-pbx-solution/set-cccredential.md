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
description: 'O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824205"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
O cmdlet Set-CcCredential define a credencial da implantação atual do Skype for Business Cloud Connector Edition.  
  
Com o Cloud Connector versão 2,0 e posterior, esse cmdlet também pode definir as informações da conta para o administrador da máquina virtual e para o administrador do domínio.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir especifica o nome e a senha da conta do administrador do locatário:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Set-CcCredential define o nome da conta e a senha para o administrador do locatário. Para versões anteriores à 2.0, o administrador deve ser um Administrador Global do Office 365. O Cloud Connector usa essa conta para obter informações de configuração, definir parâmetros de configuração e atualizar o status do aparelho para a configuração do locatário do Office 365. Com a versão 2,0 e posterior, você também pode usar esse cmdlet para atualizar as senhas das contas VmAdmin e DomainAdmin.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obrigatório <br/> |System.String  <br/> |  O valor do parâmetro deve ser "TenantAdmin", "VmAdmin" ou "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Set-CcCredential não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

