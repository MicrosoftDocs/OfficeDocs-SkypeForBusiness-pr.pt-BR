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
description: Exporta a configuração Skype for Business Cloud Connector Edition para um arquivo local no servidor Skype for Business Cloud Connector Edition host.
ms.openlocfilehash: f34f8454dfc3129be50b26114f71fdeee4a4b633f66ca9f80dc621c51c5af6ad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288830"
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
|Path  <br/> |Obrigatório  <br/> |System.String  <br/> |Caminho completo do arquivo onde as configurações do Cloud Connector serão armazenadas.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="Examples"> </a>

Nenhum. O Export-CcConfiguration cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="Examples"> </a>

Import-CcConfiguration
  

