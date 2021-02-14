---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: O Convert-CcIsoToVhdx cmdlet cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802421"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
O Convert-CcIsoToVhdx cmdlet cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parâmetros

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obrigatório <br/> |System.String  <br/> | O caminho para o arquivo ISO do Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se o processo de conversão falhar durante a atualização do Windows, você pode tentar configurar uma rede/proxy e atualizar o Windows manualmente. Depois que o trabalho manual for concluído, você poderá executar esse cmdlet com o parâmetro -GeneralizeOnly e ele concluirá os trabalhos restantes.  <br/> |
|PauseBeforeUpdate  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Para atualizar o Windows, algumas configurações manuais de rede/proxy na VM base podem ser necessárias. O processo de conversão será pausado antes da atualização do Windows se esse parâmetro for fornecido. Depois que a configuração manual for feita, você poderá retomar o processo.  <br/> |
   
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir prepara o arquivo VHDX base usando um arquivo ISO do Windows Server 2012 R2 localizado em "C:\Windows_Server_2012_R2-EN-US-x64.ISO": 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Exemplo 2

Se o Convert-CcIsoToVhdx cmdlet falhar durante a atualização do Windows, provavelmente é devido à configuração incorreta de rede/proxy. Você pode seguir as instruções na mensagem de erro e fazer logon na máquina virtual base para corrigir o problema e atualizar o Windows manualmente. Depois que o trabalho manual for concluído, execute o cmdlet novamente com o parâmetro -GeneralizeOnly para concluir os trabalhos restantes: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Exemplo 3

Se a configuração manual for necessária para atualizar o Windows, você poderá usar o parâmetro -PauseBeforeUpdate. Com esse parâmetro, o Cloud Connector pausa antes do processo de atualização do Windows. Em seguida, você pode concluir a configuração manual e retomar o processo de conversão da seguinte forma:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Convert-CcIsoToVhdx cmdlet cria uma VM base primeiro, instala alguns componentes básicos dos que o Cloud Connector depende e, em seguida, instala as atualizações do Windows. Por fim, ele generaliza a máquina virtual (sysprep) para obter um arquivo VHDX base que será usado pelas máquinas virtuais de um dispositivo do Cloud Connector. 
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Convert-CcIsoToVhdx cmdlet não aceita entrada em pipeline. 
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

Nenhum
  

