---
title: Set-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: O cmdlet Set-CcSiteDirectory define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
O cmdlet Set-CcSiteDirectory define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o diretório raiz do site como \\SiteShare\CloudConnector:
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Para fornecer alta disponibilidade e a afinidade de gateway, aparelhos de conector de nuvem podem ser combinados em sites. Os usuários são atribuídos a sites, em vez de aparelhos de conector de nuvem. Cada site tem uma pasta compartilhada onde o VHD de base e os arquivos de instalação do Cloud Connector são armazenados. Appliances usam essa pasta durante a implantação. Essa pasta deve ser compartilhada com todos os outros dispositivos em um site do conector de nuvem.
  
A pasta padrão é C:\Users\%userprofile%\CloudConnector\SiteRoot. O caminho pode ser exibido por meio do cmdlet Get-CcSiteDirectory.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obrigatório <br/> | System. String <br/> |Fornece o caminho para a pasta onde serão armazenados os arquivos do site de conector de nuvem.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Set-CcSiteDirectory não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

