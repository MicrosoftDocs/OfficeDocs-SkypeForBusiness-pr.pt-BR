---
title: Excluir uma política de PIN no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumo: Exclua discada um usuário PIN para Skype para Business Server 2015.'
ms.openlocfilehash: b64a4509105214358549f320cf8885d6386986f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="delete-a-pin-policy-in-skype-for-business-server-2015"></a>Excluir uma política de PIN no Skype for Business Server 2015
 
**Resumo:** Exclua discada um usuário PIN para Skype para Business Server 2015.
  
Siga estas etapas para excluir uma política de PIN (número de identificação pessoal).
  
> [!NOTE]
> Não é possível excluir a política de PIN global. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para excluir uma política de PIN no Skype para painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN** e no campo de pesquisa, digite o nome todo ou parcial da política que deseja excluir.
    
5. Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Remover políticas de PIN usando Cmdlets do Windows PowerShell

Você pode excluir diretivas de PIN usando o Windows PowerShell e o cmdlet Remove-CsPinPolicy. Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Para remover uma política de PIN específica

- Este comando remove a política de PIN com a Identidade RedmondPinPolicy:
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Para remover todas as políticas de PIN aplicadas ao escopo do site

- Este comando remove todas as políticas de PIN configuradas no escopo do site:
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Para remover todas as políticas de PIN que permitem o uso de padrões comuns

- Isso remove todas as políticas de PIN que permitem o uso dos padrões comuns:G
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .
  

