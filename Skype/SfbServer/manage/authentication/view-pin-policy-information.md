---
title: Exibir informações de política de PIN no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumo: exibir as informações de política do PIN do usuário para o Skype for Business Server.'
ms.openlocfilehash: 5f6269b766748d5027c0a8182dd027754cd5cc00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297586"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Exibir informações de política de PIN no Skype for Business Server
 
**Resumo:** Exibir as informações de política do PIN do usuário para o Skype for Business Server.
  
Você pode usar a guia **política de PIN** para exibir a autenticação de PIN (número de identificação pessoal) de usuários que estão se conectando ao Skype for Business com telefones IP. Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.
  
Siga estas etapas para modificar uma política de PIN no nível de usuário ou local. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para ver informações sobre uma política de PIN no painel de controle do Skype for Business Server

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.
    
4. Na página **Política de PIN**, clique em uma política, clique em **Editar** e clique em **Mostrar detalhes**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Exibindo políticas de PIN usando cmdlets do Windows PowerShell

Você também pode exibir as políticas de PIN usando o Windows PowerShell e o cmdlet Get-CsPinPolicy. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-pin-policies"></a>Para exibir políticas de PIN

Para ver as informações sobre todas as suas políticas de PIN, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
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

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>Confira também

[Criar uma nova política de PIN no Skype for Business Server](create-a-new-pin-policy.md)
