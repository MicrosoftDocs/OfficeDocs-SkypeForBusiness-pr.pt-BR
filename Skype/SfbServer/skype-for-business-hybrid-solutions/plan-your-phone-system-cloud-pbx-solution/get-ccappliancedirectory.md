---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: O Get-CcApplianceDirectory cmdlet recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800841"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
O Get-CcApplianceDirectory cmdlet recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório. 
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual onde os arquivos de configuração e máquina virtual dos componentes do Cloud Connector são armazenados:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Get-CcApplianceDirectory cmdlet mostra onde todos os arquivos de configuração e de máquina virtual, logs e certificados externos são armazenados para o dispositivo do Cloud Connector.
  
Cada dispositivo do Cloud Connector tem quatro componentes: Servidor de Mediação, Armazenamento de Gerenciamento Central, Servidor de Borda e um Controlador de Domínio. A pasta padrão é C:\Users \% userprofile%\CloudConnector\ApplianceRoot. Você pode alterar essa pasta usando o Set-CCApplianceDirectory cmdlet.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Get-CCApplianceDirectory cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

