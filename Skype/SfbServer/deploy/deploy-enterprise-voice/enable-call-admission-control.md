---
title: Habilitar o controle de admissão de chamada Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilitar o controle de admissão de chamada Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 9532208e9734f0a404e95e5c8035e0d4d0aff463
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842403"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Habilitar o controle de admissão de chamada Skype for Business Server
 
Habilitar o controle de admissão de chamada Skype for Business Server Enterprise Voice. 
  
Após definir as configurações de rede para a implantação do serviço de controle de admissão de chamadas, habilite o CAC para que as políticas de largura de banda entrem em vigor.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Para habilitar o controle de admissão de chamada usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
2. Execute o cmdlet Set-CsNetworkConfiguration para ativar o CAC na rede. Por exemplo, execute:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Se você deseja desativar o CAC na rede, execute o seguinte:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Para habilitar o controle de admissão de chamada usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.
    
2. Na barra de navegação esquerda, clique em **Configuração de Rede**.
    
3. Clique no botão de navegação **Global**.
    
4. Clique em **Global** na lista e selecione **Exibir detalhes**    no menu **Editar**.
    
5. Na página **Editar Configurações Globais**, marque a caixa de seleção **Ativar controle de admissão de chamada**.
    
    > [!NOTE]
    > Se você deseja desativar o controle de admissão de chamada durante a implantação, desmarque esta caixa de seleção. 
  
6. Clique em **Confirmar**. 
    
## <a name="see-also"></a>Confira também

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)