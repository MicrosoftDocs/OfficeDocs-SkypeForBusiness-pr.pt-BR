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
description: O cmdlet Export-CcConfigurationSampleFile exporta um Skype for Business Cloud Connector Edition de configuração de exemplo (.ini) para o diretório de dispositivos de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.
ms.openlocfilehash: f59e93cf241ca762dcb41cf23d617017a62581b453cb84cebc915b1703f5a019
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326257"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
O cmdlet Export-CcConfigurationSampleFile exporta um Skype for Business Cloud Connector Edition de configuração de exemplo (.ini) para o diretório de dispositivos de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir baixa um arquivo de configuração de exemplo do site da Microsoft e o grava no diretório do dispositivo do dispositivo Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

A versão atual do Cloud Connector exige que você forneça vários parâmetros no arquivo .ini. por exemplo, parâmetros como os endereços IP de máquinas virtuais para os componentes do Cloud Connector, nomes de componentes, parâmetros de gateway e assim por diante.
  
Este cmdlet, quando executado no computador host do Cloud Connector, baixa um arquivo de .ini de exemplo com exemplos de configuração do site da Microsoft. O cmdlet grava o arquivo no diretório do dispositivo do dispositivo Cloud Connector. O diretório do dispositivo é especificado usando o cmdlet Set-CcApplianceDirectory de usuário.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Export-CcConfigurationSampleFile cmdlet não aceita entrada canalada. 
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

