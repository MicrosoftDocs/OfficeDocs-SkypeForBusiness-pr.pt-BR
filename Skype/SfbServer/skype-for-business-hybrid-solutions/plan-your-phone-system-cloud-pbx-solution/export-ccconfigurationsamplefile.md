---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: O cmdlet Export-CcConfigurationSampleFile exporta um arquivo (.ini) de configuração de amostra do Skype for Business Cloud Connector Edition para o diretório de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo para usar na implantação.
ms.openlocfilehash: b62d5d7ffa9e8f10aeae509201c5aa0a1e7fa0a4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003421"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
O cmdlet Export-CcConfigurationSampleFile exporta um arquivo (.ini) de configuração de amostra do Skype for Business Cloud Connector Edition para o diretório de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo para usar na implantação.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir baixa um arquivo de configuração de exemplo do site da Microsoft e grava-o no diretório de aplicativos do dispositivo do conector de nuvem:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A versão atual do conector de nuvem exige que você forneça vários parâmetros no arquivo. ini; por exemplo, parâmetros como os endereços IP de máquinas virtuais para componentes do conector de nuvem, nomes de componentes, parâmetros de gateway e assim por diante.
  
Esse cmdlet, quando executado na máquina host do conector de nuvem, baixa um arquivo. ini de exemplo com exemplos de configuração do site da Microsoft. O cmdlet grava o arquivo no diretório de aplicativos do aparelho do conector de nuvem. Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Export-CcConfigurationSampleFile não aceita a entrada por pipeline. 
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

