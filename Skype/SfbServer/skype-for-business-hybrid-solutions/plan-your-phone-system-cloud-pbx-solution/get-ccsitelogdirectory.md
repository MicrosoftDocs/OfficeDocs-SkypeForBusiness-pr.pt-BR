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
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'O cmdlet Get-CcSiteLogDirectory mostra o diretório atual onde estão armazenados os logs no nível do site do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: a03c4c0cc3e993fb5e1426f3f27f76a68d081c26
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003351"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
O cmdlet Get-CcSiteLogDirectory mostra o diretório atual onde estão armazenados os logs no nível do site do Skype for Business Cloud Connector Edition.  
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual na qual os arquivos de log para o site do conector de nuvem são armazenados:
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\SiteRoot\Logs. Você pode alterar a pasta executando o cmdlet Set-CcSiteDirectory. Não há cmdlet separado que altere somente o local da pasta de log sem alterar o diretório do site.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Get-CsClientVersionPolicy não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

