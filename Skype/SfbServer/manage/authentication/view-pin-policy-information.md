---
title: Exibir informações de política de PIN em Skype for Business Server
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
description: 'Resumo: Exibir informações de política de PIN de um usuário para Skype for Business Server.'
ms.openlocfilehash: 385602c4395ec0a189bc25d8a1ab052a8bf1475b440fc34795d54110b4bcffc2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286830"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Exibir informações de política de PIN em Skype for Business Server
 
**Resumo:** Exibir informações de política pin de um usuário para Skype for Business Server.
  
Você pode usar a guia **Política de PIN** para exibir a autenticação de número de identificação pessoal (PIN) de usuários que estão se conectando Skype for Business com telefones IP. Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.
  
Siga estas etapas para modificar uma política de PIN de nível do usuário ou nível local. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para exibir informações sobre uma política de PIN no Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN**, clique em uma política, em **Editar** e em **Exibir detalhes**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Exibindo políticas de PIN usando Windows PowerShell cmdlets

Você também pode exibir políticas de PIN usando o Windows PowerShell e o cmdlet Get-CsPinPolicy. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 Usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-pin-policies"></a>Para exibir políticas de PIN

Para exibir informações sobre todas as políticas de PIN, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
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

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Confira também

[Criar uma nova política de PIN no Skype for Business Server](create-a-new-pin-policy.md)