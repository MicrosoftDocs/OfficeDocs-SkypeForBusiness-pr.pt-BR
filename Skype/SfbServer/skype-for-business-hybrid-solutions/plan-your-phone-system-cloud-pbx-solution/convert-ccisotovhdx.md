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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: O cmdlet Convert-CcIsoToVhdx cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 780002c54a77746c51f418cae077ffcc9b1fb608
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001341"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
O cmdlet Convert-CcIsoToVhdx cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Skype for Business Cloud Connector Edition.
  
```powershell
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
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Exemplo 2

Se o cmdlet Convert-CcIsoToVhdx falhar durante a atualização do Windows, provavelmente será devido à configuração incorreta de rede/proxy. Você pode seguir as instruções na mensagem de erro e fazer logon na máquina virtual base para corrigir o problema e atualizar o Windows manualmente. Após a conclusão do trabalho manual, execute novamente o cmdlet com o parâmetro -GeneralizeOnly e ele concluirá as tarefas  restantes. 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Exemplo 3

Se a configuração manual for necessária para atualizar o Windows, você pode usar o parâmetro -PauseBeforeUpdate. Com esse parâmetro, o conector de nuvem será pausado antes do processo do Windows Update. Então, você poderá concluir a configuração manual e retomar o processo de conversão como a seguir:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Convert-CcIsoToVhdx cria uma VM base primeiro, instala alguns componentes básicos dos quais o conector de nuvem depende e, em seguida, instala as atualizações do Windows. Por fim, ele generaliza a máquina virtual (Sysprep) para obter um arquivo VHDX básico que será usado pelas máquinas virtuais de um aparelho de conexão de nuvem. 
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Convert-CcIsoToVhdx não aceita a entrada por pipeline. 
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

Nenhum
  

