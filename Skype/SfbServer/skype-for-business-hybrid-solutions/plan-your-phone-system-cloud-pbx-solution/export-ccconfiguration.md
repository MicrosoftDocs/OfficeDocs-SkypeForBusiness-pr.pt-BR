---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801461"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporta a configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host do Skype for Business Cloud Connector Edition.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o parâmetro Path como um caminho de arquivo completo e exporta configurações para esse arquivo.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="Examples"> </a>

O Export-CcConfiguration cmdlet permite que você salve a configuração do Cloud Connector em um arquivo em um caminho selecionado. Este comando foi introduzido na versão 2.0 do Cloud Connector Edition.
  
## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Obrigatório  <br/> |System.String  <br/> |Caminho completo do arquivo onde as configurações do Cloud Connector serão armazenadas.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="Examples"> </a>

Nenhum. O Export-CcConfiguration cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="Examples"> </a>

Import-CcConfiguration
  

