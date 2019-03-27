---
title: Excluir uma configuração de arquivamento no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumo: Saiba como excluir uma configuração de arquivamento no Skype para Business Server.'
ms.openlocfilehash: 5e567a08606bb9d0475033515b4b9148deb2f446
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895580"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Excluir uma configuração de arquivamento no Skype para Business Server

**Resumo:** Saiba como excluir uma configuração de arquivamento no Skype para Business Server.
  
Você pode excluir uma configuração de site ou de pool, mas não a configuração global. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Excluir uma configuração de arquivamento usando o Painel de Controle

Para excluir uma configuração de arquivamento usando o Painel de Controle:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Na lista de configuração de arquivamento, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.
    
    > [!NOTE]
    > Você também pode clicar na configuração global, mas selecione essa opção somente se quiser redefinir a configuração global com os valores padrão. 
  
5. Clique em **Confirmar**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Excluir uma configuração de arquivamento usando o Windows PowerShell

Você também pode excluir uma configuração de arquivamento usando o cmdlet **Remove-CsArchivingConfiguration** .
  
Por exemplo, o seguinte comando remove as configurações de arquivamento aplicadas ao site Redmond. Quando uma política configurada no escopo do site é excluída, os usuários previamente gerenciados pela política de site passarão a ser governados pela política global de arquivamento:
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

O seguinte comando remove todas as definições de configuração de arquivamento aplicadas ao escopo do site:
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

O próximo comando remove todas as definições de configuração de arquivamento onde o arquivamento do Exchange foi desativado:
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Você também pode usar o cmdlet **Remove-CsArchivingConfiguration** para redefinir as configurações globais com o valor padrão. Por exemplo, suponhamos que você tenha habilitado o arquivamento de sessões de IM no nível global; o seguinte comando redefinirá o valor para o padrão Nenhum, que desabilitará o arquivamento no nível global:
  
```
Remove-CsArchivingConfiguration -Identity global
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .
