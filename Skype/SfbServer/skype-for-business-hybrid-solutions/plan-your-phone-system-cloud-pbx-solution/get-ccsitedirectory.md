---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: O Get-CcSiteDirectory cmdlet mostra o diretório atual onde os arquivos de configuração no nível do site são armazenados. A pasta contém o VHD base e os arquivos de instalação do Skype for Business Cloud Connector Edition. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799861"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
O Get-CcSiteDirectory cmdlet mostra o diretório atual onde os arquivos de configuração no nível do site são armazenados. A pasta contém o VHD base e os arquivos de instalação do Skype for Business Cloud Connector Edition. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do Cloud Connector.
  
Este cmdlet se aplica ao Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual onde os arquivos de configuração e máquinas virtuais dos componentes do Cloud Connector são armazenados:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Para fornecer afinidade de gateway e alta disponibilidade, os dispositivos do Cloud Connector podem ser combinados em sites. Os usuários são atribuídos a sites em vez de dispositivos do Cloud Connector. Cada site tem uma pasta compartilhada onde os arquivos de instalação base do VHD e do Cloud Connector são armazenados. Os dispositivos usam essa pasta durante a implantação. A pasta padrão é C:\Users \% userprofile%\CloudConnector\SiteRoot. Você pode alterar o caminho usando o Set-CcSiteDirectory cmdlet.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Get-CcSiteDirectory cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Este comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

