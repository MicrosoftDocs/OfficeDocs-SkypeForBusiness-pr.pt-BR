---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: O Get-CcSiteLogDirectory cmdlet mostra o diretório atual onde os logs de nível do site para Skype for Business Cloud Connector Edition estão armazenados.
ms.openlocfilehash: 7c15d0b715384fd18522122571da69f58a83ed337d46420e83f7ac35cfd0c018
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349513"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
O Get-CcSiteLogDirectory cmdlet mostra o diretório atual onde os logs de nível do site para Skype for Business Cloud Connector Edition estão armazenados. 
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual onde os arquivos de log do site do Cloud Connector são armazenados:
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A pasta padrão é C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs. Você pode alterar a pasta executando o Set-CcSiteDirectory cmdlet. Não há cmdlet separado que altera apenas o local da pasta de log sem alterar o diretório do site.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Get-CcSiteLogDirectory cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

