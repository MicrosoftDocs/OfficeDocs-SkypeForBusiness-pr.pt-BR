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
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'O cmdlet Get-CcApplianceDirectory recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados neste diretório. '
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287388"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
O cmdlet Get-CcApplianceDirectory recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados neste diretório.  
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual na qual os arquivos de configuração e de máquina virtual dos componentes do conector de nuvem são armazenados:
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Get-CcApplianceDirectory mostra onde todos os arquivos de configuração e de máquina virtual, logs e certificados externos são armazenados para o aparelho do conector de nuvem.
  
Cada dispositivo de conector de nuvem tem quatro componentes: servidor de mediação, repositório de gerenciamento central, servidor de borda e um controlador de domínio. A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot. Você pode alterar esta pasta quando o cmdlet Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Get-CcApplianceLogDirectory não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

