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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: O cmdlet Export-CcConfigurationSampleFile exporta um arquivo de configuração de exemplo (.ini) do Skype for Business Cloud Connector Edition para o diretório de dispositivos de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801001"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
O cmdlet Export-CcConfigurationSampleFile exporta um arquivo de configuração de exemplo (.ini) do Skype for Business Cloud Connector Edition para o diretório de dispositivos de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir baixa um arquivo de configuração de exemplo do site da Microsoft e o grava no diretório de dispositivos do dispositivo do Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A versão atual do Cloud Connector exige que você forneça vários parâmetros no arquivo .ini; por exemplo, parâmetros como os endereços IP de máquinas virtuais para os componentes do Cloud Connector, nomes de componentes, parâmetros de gateway e assim por diante.
  
Este cmdlet, quando executado no computador host do Cloud Connector, baixa um arquivo .ini de exemplo com exemplos de configuração do site da Microsoft. O cmdlet grava o arquivo no diretório de dispositivos do dispositivo do Cloud Connector. O diretório do dispositivo é especificado usando o Set-CcApplianceDirectory cmdlet.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Export-CcConfigurationSampleFile cmdlet não aceita entrada em pipeline. 
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

