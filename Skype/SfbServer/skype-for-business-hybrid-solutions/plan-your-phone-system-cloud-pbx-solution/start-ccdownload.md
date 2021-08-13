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
description: O Start-CcDownload cmdlet baixa os bits Skype for Business Cloud Connector Edition e o arquivo msi de forma síncrona.
ms.openlocfilehash: 0447c75ac3e6df79a20d2c87b664bfb92cf7124fc7253c839a88fad1b335eaec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351910"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
O Start-CcDownload cmdlet baixa os bits Skype for Business Cloud Connector Edition e o arquivo msi de forma síncrona.
  
Com o Cloud Connector versão 2.0 e posterior, você também pode especificar o parâmetro DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir baixa os bits do Cloud Connector e o arquivo msi de forma síncrona do site de download público do Cloud Connector:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo baixa os bits do Cloud Connector e o arquivo msi de forma síncrona de um site de download privado:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Exemplo 3

O terceiro exemplo baixa os bits do Cloud Connector e o arquivo msi de forma síncrona de um site de download privado.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se houver uma nova versão disponível no site de download, o Start-CcDownload baixará e instalará o arquivo msi no site de download e baixará os bits do Cloud Connector de forma síncrona. Se não houver nenhuma nova versão do arquivo msi, Start-CcDownload baixará apenas os bits do Cloud Connector. Se os bits do Cloud Connector já foram baixados, Start-CcDownload não será executado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Opcional <br/> |System.String  <br/> | A URL completa de uma versão específica do Cloud Connector no site de download privado. Use esse parâmetro com cuidado— certifique-se de que você está ciente de qual versão do Cloud Connector você está baixando. <br/> |
|DownloadBitsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignore a etapa para baixar e instalar o MSI do site de download, baixe apenas os bits do Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Start-CcDownload cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

None
  

