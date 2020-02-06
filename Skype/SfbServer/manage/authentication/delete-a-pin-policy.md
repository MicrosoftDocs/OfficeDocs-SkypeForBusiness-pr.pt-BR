---
title: Excluir uma política de PIN no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumo: excluir o PIN de conferência discada de um usuário do Skype for Business Server.'
ms.openlocfilehash: c496c8b1966ad16ba63b3320b373d3c9ca27dd20
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818793"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Excluir uma política de PIN no Skype for Business Server
 
**Resumo:** Excluir o PIN de conferência discada de um usuário do Skype for Business Server.
  
Siga estas etapas para excluir uma política de PIN (número de identificação pessoal).
  
> [!NOTE]
> Não é possível excluir a política de PIN global. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para excluir uma política de PIN no painel de controle do Skype for Business Server

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN** e no campo de pesquisa, digite o nome todo ou parcial da política que deseja excluir.
    
5. Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de PIN usando cmdlets do Windows PowerShell

Você pode excluir políticas de PIN usando o Windows PowerShell e o cmdlet Remove-CsPinPolicy. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
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

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .
  

