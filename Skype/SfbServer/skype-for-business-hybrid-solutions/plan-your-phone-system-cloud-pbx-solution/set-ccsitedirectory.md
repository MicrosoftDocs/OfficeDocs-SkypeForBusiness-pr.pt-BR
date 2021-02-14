---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: O Set-CcSiteDirectory cmdlet define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD base e os arquivos de configuração do Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824185"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
O Set-CcSiteDirectory cmdlet define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD base e os arquivos de configuração do Cloud Connector.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o diretório raiz do \\ site como SiteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Para fornecer afinidade de gateway e alta disponibilidade, os dispositivos do Cloud Connector podem ser combinados em sites. Os usuários são atribuídos a sites em vez de dispositivos do Cloud Connector. Cada site tem uma pasta compartilhada onde os arquivos de instalação base do VHD e do Cloud Connector são armazenados. Os dispositivos usam essa pasta durante a implantação. Essa pasta deve ser compartilhada com todos os outros dispositivos em um site do Cloud Connector.
  
A pasta padrão é C:\Users \% userprofile%\CloudConnector\SiteRoot. O caminho pode ser exibido usando o Get-CcSiteDirectory cmdlet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obrigatório <br/> | System.String <br/> |Fornece o caminho para a pasta onde os arquivos de site do Cloud Connector serão armazenados.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Set-CcSiteDirectory cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

