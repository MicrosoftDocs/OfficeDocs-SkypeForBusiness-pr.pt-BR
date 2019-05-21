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
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: O cmdlet Get-CcSiteDirectory mostra o diretório atual em que os arquivos de configuração no nível do site estão armazenados. A pasta contém o VHD de base e os arquivos de instalação do Skype for Business Cloud Connector Edition. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.
ms.openlocfilehash: e0b8a793f0210535a726b0bed19f240bf8b30dd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287297"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
O cmdlet Get-CcSiteDirectory mostra o diretório atual em que os arquivos de configuração no nível do site estão armazenados. A pasta contém o VHD de base e os arquivos de instalação do Skype for Business Cloud Connector Edition. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.
  
Este cmdlet se aplica ao Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual em que os arquivos de configuração e máquinas virtuais dos componentes do conector de nuvem são armazenados:
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Para oferecer afinidade de gateway e alta disponibilidade, os aparelhos do Cloud Connector podem ser combinados em sites. Os usuários são atribuídos a sites em vez de aparelhos de conector de nuvem. Cada site tem uma pasta compartilhada na qual os arquivos de instalação do VHD e do conector de nuvem base estão armazenados. Os dispositivos usam essa pasta durante a implantação. A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\SiteRoot. Você pode alterar o caminho usando o cmdlet Set-CcSiteDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Get-CcSiteDirectory não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Este comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

