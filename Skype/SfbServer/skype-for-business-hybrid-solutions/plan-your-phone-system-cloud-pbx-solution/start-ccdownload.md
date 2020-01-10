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
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: O cmdlet Start-CcDownload baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma sincronizada.
ms.openlocfilehash: 5c493862151a308208bf83e142421f3257e476e0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003181"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
O cmdlet Start-CcDownload baixa os bits e o arquivo msi do Skype for Business Cloud Connector Edition de forma sincronizada.
  
Com o Cloud Connector versão 2.0 e posteriores, você também pode especificar o parâmetro DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir baixa os bits do conector de nuvem e o arquivo MSI sincronicamente do site de download público do conector de nuvem:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo baixa os bits do conector de nuvem e o arquivo MSI de forma síncrona a partir de um site de download particular:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Exemplo 3

O terceiro exemplo baixa os bits e o arquivo msi do Cloud Connector de forma sincronizada de um site de download privado.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se houver uma nova versão disponível no site de download, o Start-CcDownload baixará e instalará o arquivo MSI do site de download e, em seguida, baixará o bits do conector de nuvem sincronicamente. Se não houver nenhuma nova versão do arquivo msi, o Start-CcDownload baixará apenas os bits do Cloud Connector. Se os bits do Cloud Connector já tiverem sido baixados, o Start-CcDownload não será executado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot   <br/> | Opcional  <br/> |System.String  <br/> | A URL completa de uma versão específica do conector de nuvem no site de download particular. Use esse parâmetro com cuidado: Certifique-se de que a versão do conector de nuvem que você está baixando. <br/> |
|DownloadBitsOnly   <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignore a etapa de baixar e instalar o MSI do site de download, baixe apenas os bits do Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Start-CcDownload não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

Nenhum
  

