---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: O cmdlet Export-CcConfigurationSampleFile exporta um arquivo (.ini) de configuração de amostra do Skype for Business Cloud Connector Edition para o diretório de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo para usar na implantação.
ms.openlocfilehash: 3154ff3492899de244c3033e4e35345132d04f20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233985"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
O cmdlet Export-CcConfigurationSampleFile exporta um arquivo (.ini) de configuração de amostra do Skype for Business Cloud Connector Edition para o diretório de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo para usar na implantação.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2.
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir baixa um arquivo de configuração de amostra do site da Microsoft e grava-os para o diretório appliance do aparelho de conector de nuvem:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A versão atual do conector de nuvem exige que você forneça vários parâmetros no arquivo. ini; Por exemplo, parâmetros como os endereços IP de máquinas virtuais para os componentes do conector de nuvem, nomes de componente, os parâmetros de gateway e assim por diante.
  
Esse cmdlet, quando executado na máquina host do conector de nuvem, baixa um arquivo. ini de exemplo com exemplos de configuração do site da Microsoft. O cmdlet grava o arquivo para o diretório appliance do aparelho de conector de nuvem. Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Export-CcConfigurationSampleFile não aceita a entrada por pipeline. 
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

