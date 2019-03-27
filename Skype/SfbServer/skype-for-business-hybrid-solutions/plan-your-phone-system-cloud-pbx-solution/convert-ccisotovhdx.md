---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: O cmdlet Convert-CcIsoToVhdx cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 181d1af762d1f8c9c8f3e65a4411b317ab36ce4a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898484"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
O cmdlet Convert-CcIsoToVhdx cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parâmetros

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obrigatório <br/> |System.String  <br/> | O caminho do arquivo ISO do Windows Server 2012 R2.  <br/> |
|GeneralizeOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se o processo de conversão falhar durante a atualização do Windows, você pode tentar configurar uma rede/proxy e atualizar o Windows manualmente. Após a conclusão do trabalho manual, você pode executar este cmdlet com o parâmetro -GeneralizeOnly e ele concluirá as tarefas  restantes.   <br/> |
|PauseBeforeUpdate  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Para atualizar o Windows, alguma configuração manual de rede/proxy na VM base pode ser necessária. O processo de conversão pausará antes da atualização do Windows, se esse parâmetro for fornecido. Depois que a configuração manual for concluída, será possível retomar o processo.   <br/> |
   
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte prepara o arquivo VHDX base usando um arquivo ISO do Windows Server 2012 R2 localizado em "C:\Windows_Server_2012_R2-EN-US-x64.ISO":  
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Exemplo 2

Se o cmdlet Convert-CcIsoToVhdx falhar durante a atualização do Windows, provavelmente é devido à configuração incorreta/proxy da rede. Você pode seguir as instruções na mensagem de erro e fazer logon na máquina virtual base para corrigir o problema e atualizar o Windows manualmente. Após a conclusão do trabalho manual, execute novamente o cmdlet com o parâmetro -GeneralizeOnly e ele concluirá as tarefas  restantes. 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Exemplo 3

Se a configuração manual for necessária para atualizar o Windows, você pode usar o parâmetro -PauseBeforeUpdate. Com esse parâmetro, o conector de nuvem fará uma pausa antes que o processo de atualização do Windows. Então, você poderá concluir a configuração manual e retomar o processo de conversão como a seguir:
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Convert-CcIsoToVhdx cria uma base que VM instala em primeiro lugar, alguns componentes básicas que o conector de nuvem depende e, em seguida, instala atualizações do Windows. Finalmente, ele generaliza a máquina virtual (sysprep) para obter um arquivo VHDX base que será utilizado pelas máquinas virtuais do aparelho de um conector de nuvem. 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Convert-CcIsoToVhdx não aceita a entrada por pipeline. 
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

Nenhum
  

