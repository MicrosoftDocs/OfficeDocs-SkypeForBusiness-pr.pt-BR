---
title: Excluir uma configuração de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumo: saiba como excluir uma configuração de arquivamento no Skype for Business Server.'
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817621"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Excluir uma configuração de arquivamento no Skype for Business Server

**Resumo:** Saiba como excluir uma configuração de arquivamento no Skype for Business Server.
  
Você pode excluir uma configuração de site ou configuração de pool, mas não pode excluir a configuração global. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Excluir uma configuração de arquivamento usando o Painel de Controle

Para excluir uma configuração de arquivamento usando o Painel de Controle:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Na lista de configuração de arquivamento, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.
    
    > [!NOTE]
    > Você também pode clicar na configuração Global, mas escolha essa opção somente se quiser redefinir a configuração Global para os valores padrão. 
  
5. Clique em **Confirmar**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Excluir uma configuração de arquivamento usando o Windows PowerShell

Você também pode excluir uma configuração de arquivamento usando o cmdlet **Remove-CsArchivingConfiguration.**
  
Por exemplo, o comando a seguir remove as definições de configuração de arquivamento aplicadas ao site Redmond. Quando uma política configurada no escopo do site é excluída, os usuários gerenciados anteriormente pela política de site serão governados automaticamente pela política de arquivamento global:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

O comando a seguir remove todas as definições de configuração de arquivamento aplicadas ao escopo de serviço:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

O próximo comando remove todas as definições de configuração de arquivamento onde o arquivamento do Exchange foi desabilitado:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Você também pode usar o cmdlet **Remove-CsArchivingConfiguration** para redefinir as configurações globais para valores padrão. Por exemplo, suponha que você tenha habilitado o arquivamento de sessões de IM no nível global; o comando a seguir redefini o valor para o padrão Nenhum, o que desabilitará o arquivamento no nível global:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)
