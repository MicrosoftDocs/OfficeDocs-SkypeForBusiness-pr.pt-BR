---
title: Habilitar ou desabilitar a conferência discada no Skype for Business Server
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
description: 'Resumo: Saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discada no Skype for Business Server.'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119460"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Habilitar ou desabilitar a conferência discada no Skype for Business Server
 
**Resumo:** Saiba como usar o Painel de Controle ou o Shell de Gerenciamento para habilitar ou desabilitar a conferência discada no Skype for Business Server.
  
Você pode habilitar a conferência discada usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Habilitar ou desabilitar a conferência discada usando o Painel de Controle do Skype for Business Server

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**
    
4. Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**. 
    
5. Para permitir que os usuários participen por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a 	Rede Telefônica Pública Comutada (PSTN).
    
6. Clique em **Confirmar**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Habilitar ou desabilitar a conferência discada usando o Shell de Gerenciamento do Skype for Business Server

Para habilitar ou desabilitar a conferência discada, use o cmdlet **Set-CsConferencingPolicy** com o parâmetro EnableDialInConferencing da seguinte forma:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Para obter mais informações, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
