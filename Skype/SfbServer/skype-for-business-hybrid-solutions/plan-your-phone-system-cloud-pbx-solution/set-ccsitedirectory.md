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
description: O Set-CcSiteDirectory cmdlet define o diretório onde os arquivos de configuração de nível de site Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá os arquivos de configuração base VHD e Cloud Connector.
ms.openlocfilehash: 9642c91e811e62b08f2b0e219b5eaa7b9ac7359fcdb6114c028735851280da59
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286240"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
O Set-CcSiteDirectory cmdlet define o diretório onde os arquivos de configuração de nível de site Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá os arquivos de configuração base VHD e Cloud Connector.
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o diretório raiz do site \\ como SiteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Para fornecer afinidade de gateway e alta disponibilidade, os dispositivos do Cloud Connector podem ser combinados em sites. Os usuários são atribuídos a sites em vez de dispositivos do Cloud Connector. Cada site tem uma pasta compartilhada onde os arquivos de instalação base VHD e Cloud Connector são armazenados. Os dispositivos usam essa pasta durante a implantação. Essa pasta deve ser compartilhada com todos os outros dispositivos em um site do Cloud Connector.
  
A pasta padrão é C:\Users \% userprofile%\CloudConnector\SiteRoot. O caminho pode ser exibido usando o cmdlet Get-CcSiteDirectory.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obrigatório <br/> | System.String <br/> |Fornece o caminho para a pasta onde os arquivos de site do Cloud Connector serão armazenados.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Set-CcSiteDirectory cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

