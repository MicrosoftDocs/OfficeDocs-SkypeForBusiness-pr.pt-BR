---
title: Get-CcSiteLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'O cmdlet Get-CcSiteLogDirectory mostra o diretório atual onde estão armazenados os logs no nível do site do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 68d89200ac8bf2aec32db45752d62d7ae205b830
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
O cmdlet Get-CcSiteLogDirectory mostra o diretório atual onde estão armazenados os logs no nível do site do Skype for Business Cloud Connector Edition.  
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual, onde os arquivos de log para o site do conector de nuvem são armazenados:
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A pasta padrão é C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs. Você pode alterar a pasta executando o cmdlet Set-CcSiteDirectory. Não há cmdlet separado que altere somente o local da pasta de log sem alterar o diretório do site.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Get-CsClientVersionPolicy não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

