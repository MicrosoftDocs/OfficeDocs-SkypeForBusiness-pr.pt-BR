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
ms.localizationpriority: medium
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporta a configuração Skype for Business Cloud Connector Edition para um arquivo local no servidor Skype for Business Cloud Connector Edition host.
ms.openlocfilehash: b2b3ea0171b68701b47b8ae2ed239f2e0495855b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625003"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exporta a configuração Skype for Business Cloud Connector Edition para um arquivo local no servidor Skype for Business Cloud Connector Edition host.
  
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

O Export-CcConfiguration cmdlet permite salvar a configuração do Cloud Connector em um arquivo em um caminho selecionado. Este comando foi introduzido no Cloud Connector Edition versão 2.0.
  
## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Caminho  <br/> |Obrigatório  <br/> |System.String  <br/> |Caminho completo do arquivo onde as configurações do Cloud Connector serão armazenadas.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="Examples"> </a>

Nenhum. O Export-CcConfiguration cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="Examples"> </a>

Import-CcConfiguration
  

