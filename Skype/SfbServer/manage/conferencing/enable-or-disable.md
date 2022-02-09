---
title: Habilitar ou desabilitar a conferência discagem no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumo: saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discagem em Skype for Business Server.'
ms.openlocfilehash: 24ea07c0a5a1995a35f01cddd41435f6ea00445d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403913"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Habilitar ou desabilitar a conferência discagem no Skype for Business Server
 
**Resumo:** Saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discagem em Skype for Business Server.
  
Você pode habilitar a conferência discada usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Habilitar ou desabilitar a conferência discada usando Skype for Business Server Painel de Controle

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique **em Conferência e** em **Política de Conferência**.
    
4. Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**. 
    
5. Para permitir que os usuários participen por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a 	Rede Telefônica Pública Comutada (PSTN).
    
6. Clique em **Confirmar**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Habilitar ou desabilitar a conferência discada usando Skype for Business Server Shell de Gerenciamento

Para habilitar ou desabilitar a conferência discada, use o cmdlet **Set-CsConferencingPolicy** com o parâmetro EnableDialInConferencing da seguinte forma:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Para obter mais informações, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
