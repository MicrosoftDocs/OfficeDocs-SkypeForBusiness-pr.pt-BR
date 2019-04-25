---
title: Exibir informações de política PIN no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumo: Exiba informações de política PIN do usuário de Skype para Business Server.'
ms.openlocfilehash: 5fdd042f01c325bfffedbfa32fa14d9e667ef7be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222853"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Exibir informações de política PIN no Skype para Business Server
 
**Resumo:** Exiba informações de política PIN do usuário de Skype para Business Server.
  
Você pode usar a guia **Política de PIN** para exibir identificação pessoal número (PIN) a autenticação de usuários que estiverem se conectando ao Skype for Business com telefones IP. Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.
  
Siga estas etapas para modificar uma política de PIN no nível de usuário ou local. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para exibir informações sobre uma política PIN no Skype para painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN**, clique em uma política, clique em **Editar** e clique em **Mostrar detalhes**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Exibir políticas de PIN usando Cmdlets do Windows PowerShell

Você também pode exibir políticas de PIN usando o Windows PowerShell e o cmdlet Get-CsPinPolicy. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-view-pin-policies"></a>Para exibir políticas de PIN

Para exibir informações sobre todas as suas políticas PIN, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
  ```
  Get-CsPinPolicy
  ```

Isso retornará informações parecidas com:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>Confira também

[Criar uma nova política PIN no Skype para Business Server](create-a-new-pin-policy.md)
