---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'O cmdlet Get-CcApplianceDirectory recupera o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados neste diretório. '
ms.openlocfilehash: bcd80018b2286865945638f66c13e4c5198346dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233971"
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

O exemplo a seguir mostra a pasta atual, onde estão armazenados os arquivos de máquina virtual e configuração dos componentes do conector de nuvem:
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A cmdlet Get-CcApplianceDirectory mostra onde todos os certificados externos, logs e arquivos de configuração e a máquina virtual são armazenados para o aparelho de conector de nuvem.
  
Cada dispositivo de conector de nuvem tem quatro componentes: o servidor de mediação, repositório de gerenciamento Central, servidor de borda e um controlador de domínio. A pasta padrão é C:\Users\%userprofile%\CloudConnector\ApplianceRoot. Você pode alterar esta pasta quando o cmdlet Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Get-CcApplianceLogDirectory não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

