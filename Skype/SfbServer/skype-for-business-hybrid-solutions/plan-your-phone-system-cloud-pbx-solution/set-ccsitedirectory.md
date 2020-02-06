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
description: O cmdlet Set-CcSiteDirectory define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824185"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
O cmdlet Set-CcSiteDirectory define o diretório onde os arquivos de configuração no nível do site do Skype for Business Cloud Connector Edition serão armazenados. A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o diretório raiz do \\site para SiteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Para oferecer afinidade de gateway e alta disponibilidade, os aparelhos do Cloud Connector podem ser combinados em sites. Os usuários são atribuídos a sites em vez de aparelhos de conector de nuvem. Cada site tem uma pasta compartilhada na qual os arquivos de instalação do VHD e do conector de nuvem base estão armazenados. Os dispositivos usam essa pasta durante a implantação. Essa pasta deve ser compartilhada com todos os outros dispositivos em um site do conector de nuvem.
  
A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\SiteRoot. O caminho pode ser exibido por meio do cmdlet Get-CcSiteDirectory.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obrigatório <br/> | System.String <br/> |Fornece o caminho para a pasta em que os arquivos do site do conector de nuvem serão armazenados.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Set-CcSiteDirectory não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

