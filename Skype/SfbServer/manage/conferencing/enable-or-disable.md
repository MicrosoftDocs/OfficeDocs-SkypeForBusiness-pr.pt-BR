---
title: Habilitar ou desabilitar a conferência discagem no Skype for Business Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumo: saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discagem em Skype for Business Server.'
ms.openlocfilehash: 335252904ea015046e9caf5689fe31e4b0a9b8c3569b6c7d233fb8c4e74857ec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297287"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Habilitar ou desabilitar a conferência discagem no Skype for Business Server
 
**Resumo:** Saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discagem em Skype for Business Server.
  
Você pode habilitar a conferência discada usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Habilitar ou desabilitar a conferência discada usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**. 
    
5. Para permitir que os usuários participen por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a 	Rede Telefônica Pública Comutada (PSTN).
    
6. Clique em **Confirmar**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Habilitar ou desabilitar a conferência discada usando Skype for Business Server Shell de Gerenciamento

Para habilitar ou desabilitar a conferência discada, use o cmdlet **Set-CsConferencingPolicy** com o parâmetro EnableDialInConferencing da seguinte forma:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Para obter mais informações, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
