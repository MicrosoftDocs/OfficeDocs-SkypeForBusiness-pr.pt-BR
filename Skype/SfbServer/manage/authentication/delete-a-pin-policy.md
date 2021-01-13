---
title: Excluir uma política de PIN no Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumo: exclua o PIN de conferência discada de um usuário para o Skype for Business Server.'
ms.openlocfilehash: 6cf93d2ade053ba6e4bdbe7aabf0138206fdff88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828391"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Excluir uma política de PIN no Skype for Business Server
 
**Resumo:** Exclua o PIN de conferência discada de um usuário para o Skype for Business Server.
  
Siga estas etapas para excluir uma política de PIN (número de identificação pessoal).
  
> [!NOTE]
> Não é possível excluir a política PIN global. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para excluir uma política de PIN no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN** e no campo de pesquisa, digite o nome todo ou parcial da política que deseja excluir.
    
5. Na lista de políticas, clique na política que você deseja, em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de PIN usando cmdlets do Windows PowerShell

Você pode excluir políticas de PIN usando o Windows PowerShell e o Remove-CsPinPolicy cmdlet. Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Para remover uma política de PIN específica

- Este comando remove a política de PIN com a Identidade RedmondPinPolicy:
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Para remover todas as políticas de PIN aplicadas ao escopo do site

- Este comando remove todas as políticas de PIN configuradas no escopo do site:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Para remover todas as políticas de PIN que permitem o uso de padrões comuns

- Isso remove todas as políticas de PIN que permitem o uso dos padrões comuns:G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
  

