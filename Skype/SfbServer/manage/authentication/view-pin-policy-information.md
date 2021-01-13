---
title: Exibir informações de política de PIN no Skype for Business Server
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumo: Exibir as informações de política de PIN de um usuário para o Skype for Business Server.'
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806521"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Exibir informações de política de PIN no Skype for Business Server
 
**Resumo:** Exibir as informações de política de PIN de um usuário para o Skype for Business Server.
  
Você pode usar a **guia Política de PIN** para exibir a autenticação de PIN (número de identificação pessoal) de usuários que estão se conectando ao Skype for Business com telefones IP. Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.
  
Siga estas etapas para modificar uma política de PIN de nível do usuário ou nível local. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para exibir informações sobre uma política de PIN no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN**, clique em uma política, em **Editar** e em **Exibir detalhes**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Exibindo políticas de PIN usando cmdlets do Windows PowerShell

Você também pode exibir políticas de PIN usando o Windows PowerShell e o Get-CsPinPolicy cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-pin-policies"></a>Para exibir políticas de PIN

Para exibir informações sobre todas as suas políticas de PIN, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
  ```PowerShell
  Get-CsPinPolicy
  ```

Isto retorna informações semelhantes à seguinte:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Confira também

[Criar uma nova política de PIN no Skype for Business Server](create-a-new-pin-policy.md)
