---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: O Start-CcDownload cmdlet baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma síncrona.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824175"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
O Start-CcDownload cmdlet baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma síncrona.
  
Com o Cloud Connector versão 2.0 e posterior, você também pode especificar o parâmetro DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir baixa os bits e o arquivo msi do Cloud Connector de forma síncrona do site de download público do Cloud Connector:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo baixa os bits e o arquivo msi do Cloud Connector de forma síncrona de um site de download privado:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Exemplo 3

O terceiro exemplo baixa os bits e o arquivo msi do Cloud Connector de forma síncrona de um site de download privado.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se houver uma nova versão disponível no site de download, o Start-CcDownload baixará e instalará o arquivo msi do site de download e baixará os bits do Cloud Connector de forma síncrona. Se não houver nenhuma nova versão do arquivo msi, o Start-CcDownload baixará apenas os bits do Cloud Connector. Se os bits do Cloud Connector já foram baixados, Start-CcDownload não será executado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Opcional <br/> |System.String  <br/> | A URL completa de uma versão específica do Cloud Connector no site de download privado. Use esse parâmetro com cuidado. Certifique-se de que está ciente de qual versão do Cloud Connector você está baixando. <br/> |
|DownloadBitsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignore a etapa para baixar e instalar o MSI do site de download, baixe apenas os bits do Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Start-CcDownload cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

Nenhum
  

